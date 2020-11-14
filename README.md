#
一、实验目的
1.掌握Java中抽象类和抽象方法的定义；

2.掌握Java中接口的定义，熟练掌握接口的定义形式以及接口的实现方法

3.了解异常的使用方法，并在程序中根据输入情况做异常处理

#
二、实验内容
某学校为了给学生提供勤工俭学机会，也减轻授课教师的部分压力，准许博士研究生参与课程的助教工作。此时，该博士研究生有双重身份：学生和助教教师。

1.设计两个管理接口：学生管理接口和教师管理接口。学生接口必须包括缴纳学费、查学费的方法；教师接口包括发放薪水和查询薪水的方法。

2.设计博士研究生类，实现上述的两个接口，该博士研究生应具有姓名、性别、年龄、每学期学费、每月薪水等属性。（其他属性及方法，可自行发挥）

3.编写测试类，并实例化至少两名博士研究生，统计他们的年收入和学费。根据两者之差，算出每名博士研究生的年应纳税金额（国家最新工资纳税标准，请自行检索）。

#实验要求
1.在博士研究生类中实现各个接口定义的抽象方法;

2.对年学费和年收入进行统计，用收入减去学费，求得纳税额；

3.国家最新纳税标准（系数），属于某一时期的特定固定值，与实例化对象没有关系，考虑如何用static  final修饰定义。

4.实例化研究生类时，可采用运行时通过main方法的参数args一次性赋值，也可采用Scanner类实现运行时交互式输入。

5.根据输入情况，要在程序中做异常处理。


#实验过程
一、首先创建一个实验对象，对于实验对象的各项参数和信息进行定义。
//package shiyan;
////创建博士研究生对象
//public class DRStudent implements Student, Teacher {
//	private String name;                //姓名
//	private String gender;              //性别
//	private int age;                        //年龄
//	private String major;                //专业
//	private String banji;                 //班级
//	private float feeOfTerm;         //每学期学费
//	private float salaryOfMonth;  //每月薪水
//	private float money = 0;          //当前的余额
             ……
             
 二、设定年龄、班级、专业等基本信息，并获取。
 //获得姓名
	public String getName() {
		return name;
	}
//设置姓名
	public void setName(String name) {
		this.name = name;
	}
//获得性别
	public String getGender() {
		return gender;
	}
//设置性别
	public void setGender(String gender) {
		this.gender = gender;
	}
  …………
  
  
  
  三、设置学费以及薪水的计算方法
  
  //计算每年的学费  每年的学费=每学期的学费*2
	    public float feeOfYear() {
	        return feeOfTerm * 2;
	    }
	    public void getSalary() {
	        money = money + salaryOfMonth;
	    }
//计算每年的薪水 每年的薪水=每个月的薪水*12
	    public float salaryOfYear() {
	        return salaryOfMonth * 12;
	    }
      ………


四、最后获取学生信息
//获得学生信息
    public String toString() {
        return "学生信息 {" + "\n" +
                "姓名='" + name + '\'' + "\n" +
                "性别='" + gender + '\'' + "\n" +
                "年龄=" + age + " 岁\n" +
                "专业='" + major + '\'' + "\n" +
                "班级='" + banji + '\'' + "\n" +
                "学费=" + feeOfTerm + " 元/学期\n" +
                "工资=" + salaryOfMonth + " 元/月\n" +
                "余额=" + money + " 元\n" +
                '}';
    }
	
	public void statistics() {
		float tax = Tax.getTax(getMoney());
		System.out.println("信息统计：\n学生：" + getName() + "\n" + 
		"每学期学费：" + getFeeOfTerm() + "\n" + 
		"每学年学费："+ feeOfYear() +"\n"+
		"每月薪水：" + getSalaryOfMonth() + "\n" + 
		"每年薪水：" + salaryOfYear() + "\n"+ 
		"税前年收入：" + getMoney() + "\n" + 
		"需交税：" + tax + "\n" +
		"税后年收入：" + (money - tax));
	}


#实验感受与反思

通过本次实验，让我对于Java中抽象类有了更进一步的了解，对于其定义有了心得看法和认识；
实验中，学习了对于接口的定义和使用方法，我认为我对于接口的认识还比较浅薄，没有足够的认识，不能够熟悉的使用接口这一方法，在今后的学习中我会不断地学习，弥补这一不足；
通过查阅资料和阅读教材，我了解到了异常处理，并有了一定的了解，不过在于应用方面还是比较欠缺的，希望自己以后可以有新的看法和认识，争取掌握这一部分的知识内容。
