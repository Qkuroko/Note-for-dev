# 一、常用语法

### 		基础语法

​				1、输入: Scanner sc = new Scanner(System.in);

​								int/String 变量名 = sc.nextInt(); //a为接收字符的变量

## 基础思想知识				

* 链式编程:调用一个方法的时候,不需要变量接受它的结果,可以继续调用其他方法

  ​	eg sb.append("aaa").append("bbb");

  ​	eg:String result = new StringBuilder(str).append(str).reverse().toString(); 字符串反转





# 技巧

#### 	idea快捷操作

​		1、**psvm**  : public static void main(String[] args) {}

​		2、**sout**  : System .out.println();

* 快捷键
  * 快速生成构造方法:alt+insert
  * 格式化代码 ctrl + alt + L
  
* 好用方法
  * 按住鼠标滚轮或者按alt 可以垂直勾选
  * 快速生成标准Javabe类 ptg插件安装后 鼠标右键
  * 显示对象的参数 ctrl + p   Dog g1 = new Dog();  在括号里按快捷键 会显示带参构造的参数.
  * fori ; arr.fori 快速生成 数组的遍历for循环 str.length().fori 集合遍历list.fori
  * ctrl + shift + t : 用循环体等包裹代码

#### 常用方法

* 注意事项:
  * 遍历对象数组的使用get set方法 要进行非空判断否则为存满可能报错

* * 键盘录入：

    * 
  
      ```java
      Sanner sc = new Sanner(System.in);
      int a = sc.nextInt(); //用变量a接收输入的整数
      /*
      	nextDouble();接收小数
      	next(); 接收字符串
      	
      	遇到空格,制表符,回车就停止接收.这些符号后面的就不会接收了,后面的会传给下一个next**接收
      */
      
      /*
      	第二套
      	nextLine();接收字符串
      	可以接收空格制表符,遇到空格才停止接收数据
      */
      
      //混用 先用nextInt 再用nextLine 会导致下面nextLine接收不到数据  输入123 其实是123+回车 , 回车被下面的nextLine接收了 学完类型转换再用第二套
      ```
  
  * 跳出到外面循环(System.exit(0); //停止虚拟机运行)  
  
    ```java
    //给外面循坏起个名字 ,然后在里面跳到外面循环
    while (true) {
                System.out.println("-----------------欢迎来到mikotokoruk学生管理系统-------------------");
                System.out.println("1:添加学生");
                System.out.println("5:退出");
                System.out.println("请输入您的选择：");
                Scanner sc = new Scanner(System.in);
                String choose = sc.next();
                switch(choose){
                    case "1" -> System.out.println("添加学生");
                        System.out.println("退出");
                        break;  //这里break只跳出Switch
                    }
                    default -> System.out.println("无此选项");
                }
            }
    
    loop: while (true) { //给外面循坏起个名字 ,然后在里面跳到外面循环
                System.out.println("-----------------欢迎来到mikotokoruk学生管理系统-------------------");
                System.out.println("1:添加学生");
                System.out.println("5:退出");
                System.out.println("请输入您的选择：");
                Scanner sc = new Scanner(System.in);
                String choose = sc.next();
                switch(choose){
                    case "1" -> System.out.println("添加学生");
                        System.out.println("退出");
                        break loop;  //调出到loop外面
                    }
                    default -> System.out.println("无此选项");
                }
            }
    ```
  
    
  
  * 生成随机数:
  
    ```java
    Random r = new Random();
    int number1 = r.nextInt(100);   //生成[0,100)间的整数,不包括100
    int number2 = r.nextInt(100)+1; //生成1-100间的整数
    ```
  
  * ***int number = r.nextInt(arr.length);*** //生成0-索引最大值的随机索引
  
    ```java
    //小于零值为零 否则还是那个值
    remainBlood = remainBlood < 0 ? 0 : remainBlood;
    ```
  
  * 随机挑选数组中的元素
  
    ```java
    //eg
    String[] boyfaces= {"风流俊雅","气宇轩昂","相貌英俊","五官端正","相貌平平","一塌糊涂","面目狰狞"};
    
    Random r1 = new Random();
    int index = r1.nextInt(boyfaces.length);//生成其索引的随机数
    String face = boyfaces[index];
    
    ```
  
  * 判断数组中有多少元素的方法
  
    ```java
    public static int getCount(Student[] arr){
        int cnt=0;
        for(int i = 0; i<arr.length; i++){
            if(arr[i] != null);
            cnt ++;
        }
        return cnt;
    }
    ```
  
  * 将数组扩大一位(不实用 后面用ArrayList对象)
  
    ```java
        //创建一个新数组 长度为老数组加一
        //之前元素拷贝到新数组中
    public static Student[] createNewArr(Student[] arr){
        Student[] newArr = new Student[arr.length+1];
        for(int i = 0; i<arr.length; i++){
            newArr[i] = arr[i]; 
        }
        return newArr;
    }
    ```
  
  * 打印对象数组元素的信息
  
    ```java
    //注意非空才打印
    public static void printArr(Student[] arr){
        for (int i = 0; i < arr.length; i++) {
            if(arr[i]!=null){
                System.out.println(arr[i].getId()+","+arr[i].getName()+","+arr[i].getAge());
            }
        }
    }
    ```
  
  * 字符串反转
  
    ```java
    String result = new StringBuilder(str).append(str).reverse().toString();
    ```
  
    

#### 基础技巧

* 判断大小写字母

  * ```java
    if(c >= 'a' && c <= 'z')//小写
    if(c >= 'A' && c <= 'Z')//大写
    ```
  
* 字符型数字转换为整型

  * ```java
    char c = '2';
    //利用ASCII码表进行转换
    //'0' --->  48
    //'1' --->  49
    //'2' --->  50
    int num = c - 48;
    ```
  
    
  
* 获取整数中每一位数(取模得到最右边一位 然后除10)

  * ```java
    //得到money中每一位数字  eg 123 从右获取 3 2 1
    /*
    123 第一次 ge = 3 moeny =12
        第二次 ge = 2 moeny =1
        第三次 ge = 1 moeny =0 跳出循环
     */
    while(true){
        int ge = money % 10;//123%10 = 3     12%10 = 2
        System.out.println(ge);   //第一次输出3 第二次输出2 第三次
        money = money / 10;  //但是当其等于0的时候没有必要再除
        if(money == 0){
            break;
        }
    }
    ```

  

* 反拿反拼

  ```java
  //得到money中每一位数字  eg 123 从右获取 3 2 1  并转换为大写字符串
  /*
  123 第一次 ge = 3 moeny =12
      第二次 ge = 2 moeny =1
      第三次 ge = 1 moeny =0 跳出循环
   */
  String moenyStr = "";
  while(true){
      int ge = money % 10;//123%10 = 3     12%10 = 2
  	moenystr = moneystr + ge; //得到的是321
     	moenystr = ge + moneystr; //得到的是123
      money = money / 10;  //但是当其等于0的时候没有必要再除
      if(money == 0){
          break;
      }
  }
  
  ```

  

  

  

  

  



#### 易错

* 循环中定义的变量 只在循环内生效 解决办法 在循坏外定义不赋值 循环里面赋值



#### 面向对象

子类中用继承

```java
//可手动写子类的带参构造
public Student(String name,int age){
    super(name,age);
}
```

* 判断是否是那个对象类型

  * ```java
    //用instanceof关键字 判断是否是那个
    if(a istanceof Dog){
        Dog d = (Dog)a;//强制转换成Dog类
    }
    
    if(a istanceof Dog d){
      //如果是dog 用 d 命名 不是就是不是
    }
    ```



# 常用基础知识

### 常用的

* souf(System.out.printlf("");) 输出语句

  * ```java
    eg
    System.out.printlf("你好,%s","张三");
    System.out.printlf("你好,%s %s","张三","李四");
    //只有输出没有换行
    ```

    

​	字符与数字用加号连接 eg："个位是"+**ge**

​	字符+字符/字符加数字 先通过ASCII码表查询到对应数字再计算

​	1+‘a’ 结果98

​	1+“a” 结果“1a"

​	***只要有字符串出现进行相加就是拼接操作并产生新字符串***



​	'a'   -----    97

​	'A'   -----    65



​	&& 和 & 、||和|的运行结果都是一模一样的。

​	但是短路逻辑运算符可以提高程序的运行效率。



**关系表达式 ？ 表达式1 ：表达式2 ；**

* 计算关系表达式的值。
* 如果关系表达式的值为真，那么执行表达式1。
* 如果关系表达式的值为假，那么执行表达式2。

​	 int max =  a > b ? a : b ;

`        //格式：关系表达式 ？ 表达式1 ： 表达式2 ；
        //注意点：
        //三元运算符的最终结果一定要被使用。
        //要么赋值给一个变量，要么直接输出。
       int max =  a > b ? a : b ;
        System.out.println(max);


```java
        //格式：关系表达式 ？ 表达式1 ： 表达式2 ；
        //注意点：
        //三元运算符的最终结果一定要被使用。
        //要么赋值给一个变量，要么直接输出。
       int max =  a > b ? a : b ;
        System.out.println(max);
	    System.out.println(a > b ? a : b);
```

​                               

```java
switch (表达式) {
	case 1:
		语句体1;
		break;
	case 2:
		语句体2;
		break;
	...
	default:
		语句体n+1;
		break;
}

package a01switch选择语句;

import java.util.Scanner;

public class SwitchDemo2 {
    public static void main(String[] args) {
        //1.键盘录入一个整数表示星期
        Scanner sc = new Scanner(System.in);
        System.out.println("请输入一个整数表示星期");
        int week = sc.nextInt();

        //2.书写一个switch语句去跟week进行匹配
        switch (week){
            case 1:
                System.out.println("跑步");
                break;
            case 2:
                System.out.println("游泳");
                break;
            case 3:
                System.out.println("慢走");
                break;
            case 4:
                System.out.println("动感单车");
                break;
            case 5:
                System.out.println("拳击");
                break;
            case 6:
                System.out.println("爬山");
                break;
            case 7:
                System.out.println("好好吃一顿");
                break;
            default:
                System.out.println("输入错误，没有这个星期");
                break;
        }
    }
}

jdk12
int number = 10;
switch (number) {
    case 1 -> {
        System.out.println("一");
    }//只有一行代码大括号可省略
    case 2 -> System.out.println("二");
    case 3 -> System.out.println("三");
    default -> System.out.println("其他");
}

利用JDK12简化代码书写
switch (week) {
    case 1, 2, 3, 4, 5 -> System.out.println("工作日");
    case 6, 7 -> System.out.println("休息日");
    default -> System.out.println("没有这个星期");
}
```





case穿透

不写break会引发case穿透现象

不写break程序会继续执行下一个case语句体（**尽管不满足那个case条件**）；

应用：多个case语句体重复，可用case穿透简化代码



- **switch和if第三种格式各自的使用场景**

当我们需要对一个范围进行判断的时候，用if的第三种格式

当我们把有限个数据列举出来，选择其中一个执行的时候，用switch语句

比如：

​	小明的考试成绩，如果用switch，那么需要写100个case，太麻烦了，所以用if简单。

​	如果是星期，月份，客服电话中0~9的功能选择就可以用switch

###	数组

​	可以存储**同种数据类型**多个值的**容器** 

​	定义 1.int [] array  (常用)  2.int array []

​		1.	静态初始化:	数据类型[] 数组名 = new 数据类型[]{元素1，元素2，元素3，元素4...}; eg:int[] arr = new 							int[]		{11,22,33};

​		**常用简化: 数据类型[] 数组名 = {元素1，元素2，元素3，元素4...};** eg:**int[] array = {1,2,3,4,5}**

​	

```java
int[] arr = {1,2,3,4,6};
System.out.println(arr);//这里输出的是地址值
System.out.println(arr[1]);
```

​		想正常访问要加**索引**  (从0开始的)

2. 动态初始化  eg:int[] arr = new int[3];  手动指定数组长度 其他没有赋值都是默认值



#### 数组常用技巧

##### 获取数组长度(用length属性)

​		arr.length 就是数组长度

**数组常用操作**

* 求最值	求和	交换数据	打乱数据(用0,1,2...等索引与随机索引交换元素)

###### 练习6：***交换数据 (***两个指针一起双向奔赴)

需求：定义一个数组，存入1,2,3,4,5。按照要求交换索引对应的元素。交换前：1,2,3,4,5交换后：5,2,3,4,1

```java
//1.定义数组存储数据
int[] arr = {1,2,3,4,5};
//2.利用循环去交换数据
for(int i = 0,j = arr.length - 1; i < j; i++,j--){
    //交换变量i和变量j指向的元素
    int temp = arr[i];
    arr[i] = arr[j];
    arr[j] = temp;
}
//当循环结束之后，那么数组中的数据就实现了头尾交换
for (int i = 0; i < arr.length; i++) {
    System.out.print(arr[i] + " ");
}
```

###### ***打乱数据***

* ***int number = r.nextInt(arr.length);*** //生成0-索引最大值的随机索引
* 因此随机的生成为[0-所填数)







### 方法

程序中最小的执行单元         用:重复高,有独立功能             好处:复用性,可维护性

#### 定义与调用                                                                                                                                                                                      

定义写在main方法外面 调用写在里面

```java
//定义
public static void 方法名 (   ) {
	// 方法体;
}

//调用
方法名();

//带参数 参数格式  数据类型 变量名 eg int a
public static void 方法名 (参数1) {
	方法体;
}

public static void 方法名 (参数1, 参数2, 参数3...) {
	方法体;
}
```

* 注意 return关键字 无返回值可不写 有返回值必须写  return下面不执行 写在方法里面



#### 方法重载

**多个方法在同一个类中,有相同方法名,参数不同数据类型不同**

* ***同一个类中,方法名相同,参数不同的方法**.(与返回值无关)   ***一定注意参数是指形参 方法括号里面的***

```java
public class MethodDemo {
	public static void fn(int a) {
    	//方法体
    }
    public static int fn(double a) {
    	//方法体
    }
}

//不构成  不在同一个类
public class MethodDemo01 {
    public static void fn(int a) {
        //方法体
    }
} 
public class MethodDemo02 {
    public static int fn(double a) { /*错误原因：这是两个类的两个fn方法*/
        //方法体
    }
}
```



## 面向对象

#### 三种类

* Javabean类:用来描述一类事物的类.比如Student,Teacher

* 测试类:用来检查其他类是否书写正确,带有main方法,程序主入口

* 工具类:帮我们做一些事情的类

  * eg 

    ```java
    //私有化成员变量不让外界创建这个类 方法都定义为静态
    public class ArrUtil{
    	private ArrUtil(){
        }    
        
        public static void getMax(){}
    }
    ```

    

*想干什么都是找一个个东西来解决*  对象即一个又一个能帮我们解决问题的东西

有些东西并不是凭空出现 

* 类:类就是对现实事物的一种描述(**理解为设计图**)

* 类和对象的关系:**类是对事物的一种描述，对象则为具体存在的事物**

  

* 类的定义步骤：

  ①定义类 ②编写类的成员变量 ③编写类的成员方法  

  类的组成 ①属性:    ②行为:通常用方法体现

  **类是抽象的 只定义不给值**
  
  ---	***类里面的行为的方法不用static***
  
  ```java
  public class 类名 {
  	// 成员变量
  	变量1的数据类型 变量1；//类是抽象的 只定义不给值
  	变量2的数据类型 变量2;
  	…
  	// 成员方法
  	方法1;
  	方法2;	
  }
  
  //对象的使用/*
      创建对象
          格式：类名 对象名 = new 类名();
          范例：Phone p = new Phone();
  
      使用对象
          1：使用成员变量
              格式：对象名.变量名
              范例：p.brand
          2：使用成员方法
              格式：对象名.方法名()
              范例：p.call()
   */
  public class Phone {
      //成员变量
      String brand;
      int price;
  
      //成员方法
      public void call() {
          System.out.println("打电话");
      }
  
      public void sendMessage() {
          System.out.println("发短信");
      }
  }
  
  public class PhoneDemo {
      public static void main(String[] args) {
          //创建对象
          Phone p = new Phone();
  
          //使用成员变量
          System.out.println(p.brand);
          System.out.println(p.price);
  
          p.brand = "小米";
          p.price = 2999;
  
          System.out.println(p.brand);
          System.out.println(p.price);
  
          //使用成员方法
          p.call();
          p.sendMessage();
      }
  }
  
  //例如数组中 有arr.length属性
  ```
  
  
  
  * Javabean类:用来描述一类事物的类,不写main方法
  
    * public class 类名{
  
      ​	1.成员变量(代表属性)
  
      ​	2.成员方法(代表行为)
  
      }
  
  * 测试类:编写main方法的类 ,可以在测试类中创建Javabean类并进行赋值使用
  
    
  
    

* 注意

  * 一个文件定义一个class类

  * 成员变量 一般无需指定初始值(所有的学生都交张三?)

    

#### 面向对象三大特征

**封装 继承 多态**

* 封装: 

  eg:定义一个类描述人 只要一个类就行

  eg:人画圆 	里有两个对象人和圆  要定义一个类 人 一个类 圆  画这个动作 **放在圆里**

  > 圆是自己画出来的 人只是调用了 画圆的方法 画圆要知道圆的属性 所以放到圆里面
  >
  > 人关门 : 门是自己关的 人只是给门一个作用力而已 关门这个方法是门的方法不是人的

  

  * **对象代表什么，就得封装对应的数据，并提供数据对应的行为** 

    ```java
    public static Circle(){
        double r;
        public void draw(){
            System.out.println("画圆");
        }
    }
    ```

    

  * private修饰符:被private修饰的成员，只能在本类进行访问 为了保护数据安全性

    * 要想访问private修饰的成员 要用“get变量名()”“set变量名(参数)”(用public修饰)
    * **set方法:给变量赋值 , 无返回值**
    * **get方法:对外提供成员变量的值**

    ```java
    /*
        学生类
     */
    class Student {
        //成员变量
        String name;
        private int age;
    
        //提供get/set方法
        public void setAge(int a) {
            if(a<0 || a>120) {
                System.out.println("你给的年龄有误");
            } else {
                age = a;
            }
        }
    
        public int getAge() {
            return age;
        }
    
        //成员方法
        public void show() {
            System.out.println(name + "," + age);
        }
    }
    /*
        学生测试类
     */
    public class StudentDemo {
        public static void main(String[] args) {
            //创建对象
            Student s = new Student();
            //给成员变量赋值
            s.name = "林青霞";
            s.setAge(30);
            //调用show方法
            s.show();
        }
    }
    ```

    

  * this关键字:成员变量与局部变量(方法里面的变量)重名 , 就近原则局部优先 , 优先输出方法里面的局部变量, **加this可输出成员变量**

    * 成员变量:类中,方法外
    * 局部变量:方法内
    
    ```java
    //用例 这里this.name是setName外面的属性.
    public void setName (String name) {
            this.name = name;
    }
    ```

* 构造方法

  * 

    ```java
    /*创建对象   Student stu = **new Student();**
    
    是一种特殊的方法 主要是完成对象数据的初始化
    
    格式
      public class 类名{
             修饰符 类名( 参数 ) {
             }
      }*/
    //   
          
    public class Student {
        private String name;
        private int age;
    
        //构造方法 空参构造
        public Student() {
            System.out.println("无参构造方法");
        }
    	//构造方法 
        public Student(String name, int age){
            this.name = name;
            this.age = age;
        }
        
        //行为
        public void show() {
            System.out.println(name + "," + age);
        }
    }
    /*
        测试类
     */
    public class StudentDemo {
        public static void main(String[] args) {
            //创建对象
            Student s = new Student();//会执行上面的 输出"无参数构造方法"
            Student s = new Student("xiaowang",23);//会执行上面带参数构造
            s.show();
        }
    }
    ```

  * ***注意***

    * 作用:创造对象的时候，由虚拟机自动调用，给成员变量进行初始化的。

    * 无参数构造方法:初始化的对象时，成员变量的数据均采用默认值。

      有参数构造方法: 在初始化对象的时候，同时可以为对象进行赋值。

    * 注意

      * 任何类定义出来，默认就自带了无参数构造器，写不写都有
      * 一旦定义了有参数构造器，无参数构造器就没有了，此时就需要自己写无参数构造器了
      * 建议在任何时候都手动写上空参和带全部参数的构造方法

      

      

      

### 标准的Javabean类

① 类名需要见名知意

② 成员变量使用private修饰

③ 提供至少两个构造方法 

* 无参构造方法
* 带全部参数的构造方法

④ get和set方法  : 提供每一个成员变量对应的setXxx()/getXxx()

⑤ 如果还有其他行为，也需要写上		

* ```java
  public class User{
      //属性
      private String name;
      private String password;
      private String email;
      private String gender;
      private int age;
      
      //空参
      public User(){
          System.out.println("空参构造哦");
      }
      
      //带全部参的构造
      public User(String name, String password, String email, String gender, int age){
          this.name = name;
          this.password = password;
          this.email = email;
          this.gender = gender;
          this.age = age;
      }
      
      //get()和set()方法
      public void setName(String name){
          this.name = name;
      }
      public String getName(){
          return name;
      }
  }
  
  //
  ```


子类

* 
  * 要有构造函数 , 重写的抽象方法 和 接口里的方法

```java
public class Dog extends Animal implements Swim{
    public Dog() {
    }

    public Dog(String name, int age) {
        super(name, age);
    }

    @Override
    public void eat() {
        System.out.println("狗吃骨头");
    }

    @Override
    public void swim() {
        System.out.println("狗在狗刨");
    }
}
```



#### toString方法

JavaBean中的toString方法 toString的好处是在碰到“println”之类的输出方法时会自动调用，不用显式打出来。

#### 练习

***注意:改值用set()方法改 获取值用get()方法*** 

eg:用name1变量接受小明名字:name1 = getName();             

小明年龄设成18岁:xiaoming.setAge(18);

* 格斗游戏

  * ```java
    package com.mikotokoruk.test;
    
    import java.util.Random;
    
    public class Role {
        //格斗游戏 血量姓名 k o
        private String name;
        private int blood;
    
        public Role() {
        }
    
        public Role(String name, int blood) {
            this.name = name;
            this.blood = blood;
        }
    
        public String getName() {
            return name;
        }
    
        public void setName(String name) {
            this.name = name;
        }
    
        public int getBlood() {
            return blood;
        }
    
        public void setBlood(int blood) {
            this.blood = blood;
        }
    
    
        //定义一个方法用于攻击别人
        //Role r1 = new Role();
        //Role r2 = new Role();
        //r1.攻击(r2);  方法的调用着攻击参数
        public void attack(Role role){
            //计算造成伤害 //加一表示1-20
            Random r = new Random();
            int hurt = r.nextInt(20)+1;
    //        role.blood = role.blood-hurt;
            int remainBlood = role.getBlood()-hurt;
    
            remainBlood = remainBlood < 0 ? 0 :remainBlood;
    
            //修改挨揍人的血量 改要用set方法不能直接改
            role.setBlood(remainBlood);
    
    
            //this 表示方法的调用者
            //A打了B一下造成XX点伤害,B还剩XX血
            //这里用this.getName
            //System.out.println(this.name + "打了" + role+"一下,造成"+""+"点伤害"+role+"还剩"+""+"血");
            System.out.println(this.getName() + "打了" + role.getName()+"一下,造成"+hurt+"点伤害"+role+"还剩"+remainBlood+"血");
    
    
    
        }
    }
    
    ```

    

### 批量往对象类型的数组中存入对象

```java
       Car[] arr = new Car[3];

        Scanner sc = new Scanner(System.in);
        for(int i = 0; i<arr.length;i++){
            Car c = new Car();
            System.out.println("请输入第"+i+"辆车的品牌:");
            String brand = sc.next();
            c.setBrand(brand);
            // 课替换为 c.setBrand(sc.next());

            System.out.println("请输入第"+i+"辆车的价格:");
            c.setPrice(sc.nextInt());

            System.out.println("请输入第"+i+"辆车的颜色:");
            c.setColor(sc.next());

            arr[i] = c;
        }
```



### API

​	简单理解: API就是别人已经写好的东西,我们不需要自己编写,直接使用即可

​	java API : JDK中提供的





## 字符串

​	String StringBuilder StringJoiner 

**字符串内容不能被改变**(可通过转化为数组改变后再转化为字符串)

String 类代表字符串，Java 程序中的所有字符串文字（例如“abc”）都被实现为此类的实例。

* 创建String对象

* 2.3String类的构造方法

  * 常用的构造方法
    
    | 方法名                    | 说明                                           |
    | ------------------------- | ---------------------------------------------- |
    | public String()           | 创建一个空白字符串对象，不含有任何内容         |
    | public String(char[] chs) | 根据字符数组的内容，来创建字符串对象           |
    | public String(byte[] bys) | 根据字节数组的内容，来创建字符串对象           |
    | String s = “abc”;         | 直接赋值的方式创建字符串对象，内容就是abc 常用 |
    
  * 示例代码
    
    ```java
    public class StringDemo01 {
        public static void main(String[] args) {
            //public String()：创建一个空白字符串对象，不含有任何内容
            String s1 = new String();
            System.out.println("s1:" + s1);
    
            //public String(char[] chs)：根据字符数组的内容，来创建字符串对象
            char[] chs = {'a', 'b', 'c'};
            String s2 = new String(chs);
            System.out.println("s2:" + s2);
    
            //public String(byte[] bys)：根据字节数组的内容，来创建字符串对象
            byte[] bys = {97, 98, 99};
            String s3 = new String(bys);
            System.out.println("s3:" + s3);
    
            //String s = “abc”;    直接赋值的方式创建字符串对象，内容就是abc
            String s4 = "abc";
            System.out.println("s4:" + s4);
        }
    }
    ```

#### 字符串比较

​		通过 new 创建的字符串对象，每一次 new 都会申请一个内存空间，虽然内容相同，但是地址值不同

* 

  * ```java
    String s1 = "abc";
    String s2 = "abc";
    //s1 和 s2在内存里是同一个 结果相等
    
    String s1 = new String("abc");
    String s2 = new String("abc");
    // new 出来的 在内存中开辟新空间 比较的是地址值
    
    String s1 = "abc";
    String s2 = new String("abc");
    //s2 记录堆中的地址值 s1 串池中的地址值 两者不相同
    ```

  #### 常用方式

* 遍历数组(遍历后可进行许多常用操作)

  ```java
  Scanner sc = new Scanner(System.in);
  System.out.println("请输入一个字符:");
  String str = sc.next();
  for (int i = 0; i < str.length(); i++) {
      char c = str.charAt(i);
      System.out.println(c);
  }
  //
  ```

  

#### 字符串常用方法

* 

  ```java
  public char charAt(int index) //根据索引返回字符
  public int length()   //返回字符串长度
  
  public boolean equals(String s){}     //比较两个字符串内容是否相同、区分大小写
  public boolean equalsIgnoreCase(String s){}  //忽略大小写比较 如验证码    
  
  
  //截取  注意:包头不包尾 包左不包右 要用变量接收一下
  String substring(int beginIndex,int endIndex)
  //截取重载方法 
  String substring(int beginIndex)
      
      
  //替换
  String replace(旧值,新值)                                                                                                                      
  ```
  
* 字符串拼接 

* 字符串反转

  * StringBuilder :常用于字符串拼接字符串反转

    StringBuilder 可以看成是一个容器，创建之后里面的内容是可变的。

    当我们在拼接字符串和反转字符串的时候会使用到

    ```java
    public StringBuilder append(任意类型)  //添加数据并返回对象本身
    public StringBuilder reverse()   //反转容器中的内容
    public int length()  //返回长度 (字符出现个数)
    public String toString() //通过toString()就可以实现把StringBuilder转换为String
        
    
    ```

    ```java
    //创建示例
    StringBuilder sb = new StringBuilder("abc");
    //此时sb 只是一个容器 帮助我们操作字符串的工具
    String str = sb.toString();
    
    //字符串反转
    String result = new StringBuilder(str).append(str).reverse().toString();
    ```

  * StringJoiner

    * 注意 StringJoiner的 add() 方法只能添加字符串
    * StringBuilder 的append() 可以添加int 型

    ```java
    StringJoiner sj = new StringJoiner("间隔符号","开始符号","结束符号")
    //成员方法
    public StringJoiner add()  //添加数据并返回对象本身
    public int length()   //返回长度(字符出现个数)所有字符总个数
    public String toString()  //返回一个字符串(该字符串就是拼接之后的结果)
        
    //eg
    StringJoiner sj = new StringJoiner(",","[","]");
    String str = sj.add("aaa").add("bbb").toString();
    System.out.println(str);//[aaa,bbb]
    
    ```

    

## 集合

​	**长度可变的容器**  (添加元素自动扩容) :自动伸缩 可长可短

* 

  * **不能存基本数据类型,可以存引用数据类型** (数组都可存)

    * 要存基本数据类型,要先变成包装类再存

    ​	

* ArrayList

  * tip

    * 打印对象不是地址值是内容,展示时会拿[]把所有的数据进行包裹

  * 泛型 (加个尖括号里面放入引用数据类型(String是引用数据类型,int不是)) 

    ArrayList<String>  list = new ArrayList<> ();

* ArrayList 成员方法

  * 增删改查

    | 方法名                              | 说明                                         |
    | ----------------------------------- | -------------------------------------------- |
    | public boolean add(要添加的元素)    | 将指定的元素追加到此集合的末尾(返回永远true) |
    | public boolean remove(要删除的元素) | 删除指定元素,返回值表示是否删除成功          |
    | public E remove(int index)          | 删除指定索引处的元素，返回被删除的元素       |
    | public E set(int index,E element)   | 修改指定索引处的元素，返回被修改的元素       |
    | public E get(int index)             | 返回指定索引处的元素                         |
    | public int size()                   | 返回集合中的元素的个数                       |

* 包装类 

  * 常用

    * char  Character

    * int    Integer   

    * 其他第一个字母大写

      ```java
      //eg
      ArrayList<Integer> list = new ArrayList<>();
      list.add(1);
      ```

      

# 进阶

### static

* ​	static是静态的意思。 static可以修饰成员变量或者修饰方法。

##### ***注意***

* **静态方法中,只能访问静态(不能访问非静态成员变量,不能访问非静态成员方法)**

* **非静态方法可以访问所有**

* **静态方法中没有this关键字**

  * eg

    ```java
    public class Student {
        private String name;
        private int age;
        private String gender;
        
        public void show1(){
            System.out.println(name+","+age+","+gender);
            show2();
        }
        //上述等价于  不过我们this 通常省略 ,这里this特指这次赋值的这个对象
        public void show1(Student this){
            System.out.println(this.name+","+this.age+","+this.gender);
            this.show2();
            this.method();//非静态方法可以访问所有
        }
        
        public void show2(){
            System.out.println("show2");
        }
        
        public static void method(){
            //System.out.println("this:"+this);//会报错
           	System.out.println("静态方法");
          	//System.out.println(name);   //访问了 非静态报错                                      
        }
        
        //非静态的 是跟对象相关的 跟某个对象相关
        //静态的是共享的 跟某一个对象没有太大关系
        
    }    
    ```

    

##### 静态变量

* 特点
  * 被该类所有对象***共享***
    * 例如班级里老师的姓名
  * 不属于对象,属于类
  * 随着类的加载而加载,优先于对象存在
* 调用方法 
  * 类名调用(推荐(不属于类)) 
    * eg:Studetn.teacherName = "";                                                                                                                                                                   
  * 对象调用  

##### 静态方法

* 特点
  * ***多用在测试类工具类,JavaBean中很少用***
  
* 调用方法:
  * 类名调用(推荐)
  
  * 对象名调用
  
    

### 继承

* 基础

  * 什么是继承、继承的好处？

    * 面向对象三大特征(封装.继承.多态)之一,可以让类跟类之间产生子父的关系
    * 可以把多个子类中重复的代码抽取到父类中，子类可以直接使用，减少代码冗余，提高代码的复用性

  * 格式

    * ```java
      public class 子类 extends 父类{}
      ```

  * 继承后特点

    * 子类可以得到父类的属性和行为，子类可以使用。子类可以在父类的基础上新增其他功能，子类更强大。

    

  * 继承特点

    * 只能***单继承***,但支持多层继承 爷爷(间接父类)
    
    * Java中所有类都直接或者间接继承与Object类
      * eg: public class A{} = public class A extends Objcet{}
      
    * 子类只能访问父类中非私有成员

      
    
  * 继承中成员方法的访问特点:
  
    this调用:就近原则
  
    super调用:直接找父类
  
  * 重写
  
    * ***重写的方法尽量和父类保持一致***(名称,形参列表)要用@override备注
  
    * eg:
  
      ```java
      @Override
      public void eat() {
          super.eat();
          System.out.println("吃骨头");
      }
      //调用时如果加super.方法名() 父类和子类重写的都执行
      ```
  
  * ***继承中构造方法访问特点***
  
    * 子类不能继承父类构造方法,但是可以通过super调用
  
    * 子类构造方法第一行有个隐藏的super();
  
    * 默认先访问父类中的无参构造再访问自己. 可手动写子类的有参构造
  
      * ```java
        public class Person(){
           String name;
           int age;
           public Person(){}//父类无参
           public Person(String name,int age){
               this.name = name;
               this.age = age;
           }
        }
        public class Studetn extends Person(){
            public Studetn{
                super();//这行是默认的不写也有
            }
            
        	//可手动写子类的带参构造
        	public Student(String name,int age){
                super(name,age);
            }
        }
        
        ```
  
        
  
  * 子类中的构造方法
  
  * ```java
    public class Cooker extends Employee{
        public Cooker() {
        }
    
        public Cooker(String id, String name, double salary) {
            super(id, name, salary);
        }
    }
    ```
  
    

### 多态

* ***封装:对象代表什么,就得封装对应的数据,并提供对应的行为***

* ***封装:为解决JavaBean中代码重复问题,将同一类事物中共同部分抽取到父类中***

* ***多态: 使用父类作为参数,可以接收所有子类对象***
  * 表现形式:父类类型 对象名称 = 子类对象;(子类的对象赋值给父类的类型)
  * 前提
    * 有继承关系
    * 有父类引用子类对象 Fu f = new Zi();
    * 有方法重写





* 

  * 应用场景

    //注册方法 的参数用父类Persen 

    但接收时 Person p = new Student();

    ```java
    //有三个子类 Student Teacher Admin 三个共同继承Person 通用下面方法
    public void register(Person p){
    
    }
    ```

    eg:

    ​	

    ```java
    public class Test {
        public static void main(String[] args) {
            Student student1 = new Student();
            student1.setName("学生1");
            student1.setAge(18);
    
            Teacher teacher1 = new Teacher();
            teacher1.setName("老师1");
            teacher1.setAge(30);
    
            Admin admin1 = new Admin();
            admin1.setName("管理员1");
            admin1.setAge(25);
            
            show(teacher1);//传入不同的 形态
            show(student1);
            show(admin1);
        }
    
        public static void show(Person person){
            String name = person.getName();
            int age = person.getAge();
            System.out.println(name);
            System.out.println(age);
        }
    }
    
    ```

    

#### 多态中调用成员特点

* 调用成员方法:编译看左边,运行也看右边

* 调用成员变量:编译看左边,运行也看左边

  ```java
  public class Test {
      public static void main(String[] args) {
          Animal a = new Dog();
          //调用成员变量:编译看左边,运行也看左边
          System.out.println(a.name);//动物
  
          //调用成员方法:编译看左边,运行也看右边
          a.show();//dog show
  
      }
  }
  
  class Animal{
      String name = "动物";
      public void show(){
          System.out.println("animal show");
      }
  }
  
  class Dog extends Animal{
      String name = "狗";
      public void show(){
          System.out.println("dog show");
      }
  }
  ```

  * ***弊端***

    * **//不能调用子类的特有功能**

    * **解决方法 : 变回子类类型(类似强制转换)  小转大要加括号**

      * **强制转换最好用instanceof关键字判断一下**
      
      ```java
      public void show(Anmial a){
          Dog d = (Dog) a
      }
      
      //强制转换最好用instanceof关键字判断一下
      if(a instance of Dog){
          Dog d = (Dog) a;
      }
      ```
      
    * 多态方法的书写格式
    
    * ```java
      public void keepPet(Animal animal,String something){
          if (animal instanceof Dog){
              Dog dog = (Dog) animal;
              System.out.println("人在喂狗"+something);
          }else if(animal instanceof  Cat){
              Cat cat = (Cat) animal;
              System.out.println("人在喂猫"+something);
          }else{
              System.out.println("没有这种动物");
          }
      }
      ```

##### 



### 其他细节

#### 包

* 文件夹,管理各种不同的java类

* 公司域名反写+包的作用 eg:com.itheima.domain'

  *  

    * 同一个包中的类和使用java.lang包(eg:String)中类不用导包,其他都要

    * 同时使用两个包中同名类要用全类名

      ```java
      com.itheima.domain1.Teacher t = new com.itheima.domain1.Teacher;
      ```

      

#### final

final修饰的方法:最终方法,不能被重写。 eg:规则

final修饰的类:最终类,不能被继承

final修饰变量:叫做常量,只能被赋值一次.类似**(常用)**

* **常量:命名:全部大写多个单词用下划线隔开**  例如(PI表示圆周率)



#### 权限修饰符

|                  | public | protected | 默认 | private |
| ---------------- | ------ | --------- | ---- | ------- |
| 同一类中         | √      | √         | √    | √       |
| 同一包中的类     | √      | √         | √    |         |
| 不同包的子类     | √      | √         |      |         |
| 不同包中的无关类 | √      |           |      |         |

实际开发中 只用private 和 public

* **成员变量私有** 
* **方法公开**



#### 抽象类

* 作用

  * 抽取共性时,无法确定方法体,就把方法定义为抽象的 ,

    强制让子类按照某种格式重写

    抽象方法所在的类必须是抽象类

    * eg 猫吃鱼 狗吃肉

* 好处:**统一格式方便管理** 比如起名字

* 定义:abstract 加 方法分号

  ```java
  public abstract class Person{
      public abstract void work();
  }
  ```

  *  
    * 抽象类不能实例化,即不能创建对象
    * 抽象类中不一定有抽象方法,**有抽象方法的类一定是抽象类**,可以有构造方法
    * 抽象类的子类 : 要重写抽象类中所有抽象方法(常用)或者是抽象类

  * eg

    ```java
    package com.mikotokoruk.abstracttest;
    
    public abstract class Animal {
        private String name;
        private int age;
    
        public abstract void eat();
    }
    
    //每种动物吃的不一样 要他的子类都要重写这个方法 但是每个程序员分工时书写习惯不同
    //用抽象可以统一命名
    ```

    

#### **接口**

eg:动物类

兔子类 青蛙类 狗类 

只在青蛙和狗类中添加游泳功能  但其不同人命名格式不一样

弄一个拥有游泳功能的接口 接口里定义一个游泳的规则



* 接口就是一种规则 , 对行为的抽象



* 掌握

  * 定义和使用接口

    * ```java
      public interface 接口名{}
      ```

    * 接口不能实例化

    * 接口和类之间是实现关系,用implements关键字表示 , 可以实现多个接口

      ```java
      public class 类名 implements 接口名{}
      public class 类名 implements 接口名1,接口名2{}
      ```

  * 接口中成员特点

    * 成员变量 :  只能是常量 , 默认修饰符 public static final

    * 构造方法: 没有

    * 成员方法: 只能是抽象方法 默认修饰符: **public abstract (jdk7前)**(可以省略)

      ```java
      public interface SpeakEnglish {
          public abstract void speakEnglish();//
          void speakEnglish();//与上行代码等价
      }
      ```

```java
//不让外界创建人的对象 直接创建顶层父类人的对象 没有意义
public abstract class Person {}
```





##### default方法

接口中的默认方法

​	格式: public default 返回值类型 方法名(参数列表){}

* 
  * 不是抽象方法,不用强制重写,**重写时要去掉default关键字**
  * public 可以省略,default不可省

* 

  * 场景:大哥给小弟安排的接口中方法都是abstract修饰的,但是如果接口中新加方法,小弟的实现接口的类就会报错(因为用abstract修饰的方法,必须强制子类(父类中)或实现接口的类中重写;) , 大哥接口中的方法如果用default代替abstract修饰 , 添加新的方法就不会报错

  * ```java
    public interface SpeakEnglish {
        public abstract void speakEnglish();//
        void speakEnglish();//与上行代码等价
        
        
        public default void show(){
            System.out.println("接口中的默认方法 ---show");
        }
        default void show(){
            System.out.println("接口中的默认方法 ---show");
        }//与上面等价
    }
    ```

    

接口中静态方法

* 定义格式

  ```java
  public static 返回值类型 方法名(参数列表){}
  ```

  只能通过接口名调用,不能实现类名或者对象调用,不能被重写(重写格式也是在类里建个同名方法)
