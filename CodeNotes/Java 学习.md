# Java 学习

# Java基础

## 一：Java程序的基础语法

### 1：字面量

字面量就是程序中能直接书写的数据，学这个知识的重点是：搞清楚Java程序中数据的书写格式。

分类：

### 2：变量

按数据类型分为两类，一类为基础数据类型，可视为存储数据的“盒子”，直接存储数据本身。另一类为引用数据类型，“盒子”中存放对象在堆内存中的引用（地址），而非对象本身，变量名（引用）存在栈中，对象本体存在堆中，其余暂不表。



- **基础数据类型分类：**



### 3：关键字与标识符

关键字为Java中具有特殊含义的一些词，我们不能把其当作变量名；例如new case for 等

标识符就是变量名，由数字，字母，下划线，美元符等组成，且不能数字开头，不能用关键字，不能用特殊符号。



### 4：方法

方法是一种用于执行特定任务或操作的代码块，代表一个功能，它可以接收数据进行处理，并返回一个处理后的结果。大体与c中的函数一致。



**方法的定义格式：**修饰符  返回值类型  方法名\( 形参列表 \)\{
                                    方法体代码\(需要执行的功能代码\)
                                    return 返回值;
                         \}

![Image](https://internal-api-drive-stream.feishu.cn/space/api/box/stream/download/authcode/?code=YjJjMTFhNTE0MDI1MGFmNGE0YmUyMDQ3ZDcwMTgzMGNfMWYzZjUxZDc0MDdhMmI5NmRhYzEwY2ZkM2Y3ZDk4OGNfSUQ6NzYxNDQ4NDM4ODM4MTkzNjU4OF8xNzgwOTc2Nzc1OjE3ODEwNjMxNzVfVjM)

**注意事项：**

- **方法重载：**一个类中，出现多个方法的名称相同，但是它们的形参列表是不同的，那么这些方法就称为方法重载了

```Java
public static void printVariable(int a) {    
     System.out.println(a);
}
public static void printVariable(String str) {   
     System.out.println(str);
}
public static void printVariable(int a, String str) {   
     System.out.println(a);    
     System.out.println(str);
}

```





- **无返回值的方法中可以直接通过单独的return;立即结束当前方法的执行**



### 5：类型转换

#### **自动类型转换：****类型范围小（所占字节大小）****的变量，可以****直接赋值****给****类型范围大****的变量**

常见数据类型所占内存大小：

![Image](https://internal-api-drive-stream.feishu.cn/space/api/box/stream/download/authcode/?code=OGNmYWFiZjk2YjMzYjQ4MzZmNGRiYjZlZTc1NDMxODNfNzljZDJiNWZmYWE4MWViZjM5NWE5YWZjY2Y1NGRkZDZfSUQ6NzYxNDQ5NTc1MTAzMjM3NjI4MF8xNzgwOTc2Nzc1OjE3ODEwNjMxNzVfVjM)



自动类型转换在计算机中的执行原理：

![Image](https://internal-api-drive-stream.feishu.cn/space/api/box/stream/download/authcode/?code=ODZkMTAzMTU4MDQyYTNlMWM0YmQzNzgxZTA1YTI5NmFfNTE3YmNkYWVjNzcwZjZmZDAzODMzNmE1NmRiOTg3ZjRfSUQ6NzYxNDQ5NjE0NjM1NDA0Nzk2NF8xNzgwOTc2Nzc1OjE3ODEwNjMxNzVfVjM)

#### **强制类型转换：****类型范围大****的变量， 不可以****直接赋值****给****类型范围小****的变量，会报错，需要强制类型转换过去**

强转格式：  数据类型 变量2 = \(数据类型\)变量1、数据

```Java
int a = 20;
byte b =  (byte)a;
System.*out*.println(b); *// 20*

int i = 1500;
byte j =  (byte)i;
System.*out*.println(j); *// -36*
```



**注意事项：**

强制类型转换可能造成数据\(丢失\)溢出；浮点型强转成整型，直接丢掉小数部分，保留整数部分返回

![Image](https://internal-api-drive-stream.feishu.cn/space/api/box/stream/download/authcode/?code=YzY1MWY2NmZkMmQ1OWVkYzdhYjU3MTc2ODYzNzVmYjNfMGE2MGQ5YTQ2ZGY1NWNkMTQ0ZDY4MjJmZTAyYzU2ZmVfSUQ6NzYxNDUwMjUyMjQzODM3MjU0M18xNzgwOTc2Nzc1OjE3ODEwNjMxNzVfVjM)



#### **表达式的自动类型转换：**在表达式中，小范围类型的变量，会自动转换成表达式中较大范围的类型，再参与运算。

****

**注意事项：**

- 表达式的最终结果类型由表达式中的最高类型决定。

- 在表达式中，byte、short、char 是直接转换成int类型参与运算的。 

### 6：输入输出

#### 输出：把程序中的数据展示出来

```Java
System.out.println("Hello world!");//输出并换行
System.out.print("Hello world!");//输出不换行
```

#### 输入：程序读取用户键盘输入的数据。通过Java提供的 Scanner程序来实现

```Java
package com.itheima.scanner;
//导包：告诉程序去JDK的哪个包中找扫描器技术
import java.util.Scanner;
public class Test {
    public static void main(String[] args) {
        //抄代码：代表得到键盘扫描器对象(东西)。
        Scanner sc = new Scanner(System.*in*);

        System.*out*.println(“请输入您的年龄：”);
        //抄代码：等待接收用户输入数据
        int age = sc.nextInt();
        System.*out*.println(“年龄是：” + age);

        System.*out*.println(“请输入您的名称：”);
        //抄代码：等待接收用户输入数据
        String name = sc.next();
        System.*out*.println("欢迎：" + name);
    }
```

**Scanner是Java提供好的API，程序员可以直接调用**

**API （Application Programming Interface：应用程序编程接口）**

Java写好的程序，咱们程序员可以直接拿来调用。

Java为自己写好的程序提供了相应的 程序使用说明书\(API文档\)。

![Image](https://internal-api-drive-stream.feishu.cn/space/api/box/stream/download/authcode/?code=YjZkMDFjNjZkZjhiMzY3MTY1MjJmMGZlY2E0MDU4MmRfOTRjMTJmNDM0ZDRmODdlNGYyMGJhNDlmYzc3OWMzNjlfSUQ6NzYxNDUwODgwMjAxMTk3NDU5OF8xNzgwOTc2Nzc1OjE3ODEwNjMxNzVfVjM)



### 7：运算符

#### 基本算术运算符

**“\+”符号在Java中的特殊用途：**

- “\+”符号与字符串运算的时候是用作连接符的，其结果依然是一个字符串。    

```Java
int a = 5;
System.*out*.println("abc" + a);//输出abc5
System.*out*.println(a + 5);//输出10
System.*out*.println("me"+ a + 'a');//me5a 
System.*out*.println(a + 'a' + "me");//102me 
```

- **如何识别\+符号是做运算，还是做连接：****能算则算，不能算就连接在一起。**



#### 自增自减运算符

**注意：**

- \+\+ 、\-\- 只能操作变量，不能操作字面量的。

- \+\+、\-\- 如果在变量前后单独使用是没有区别的。

```Java
int a = 10;
++a;
a++;
```

- \+\+、\-\- 如果不是单独使用（如在表达式中、或同时有其它操作），放在变量前后会存在明显区别

在变量的前面，先对变量\+1、\-1，再拿变量的值运算。

```Java
int a = 10;
int rs = ++a; //先加再用*   *
```

在变量的后面，先拿变量的值运算，再对变量的值\+1、\-1 。

```Java
int b = 10;
int rs = b++;//先用再加
```



#### 赋值运算符

就是“**=**”，从右边往左看。

```Java
int a = 5;
```

扩展赋值运算符：

注意：**扩展的赋值运算符隐含了强制类型转换。**

```Java
int num1 = 5;  
// 执行逻辑：num1 = (int)(num1 + 3.8) → 先计算5+3.8=8.8，再强制转int为8 
num1 += 3.8;    
System.out.println("num1 = " + num1); 
// 输出：num1 = 8// 示例2：byte类型变量使用 +=，右侧是int（超出byte范围）
byte num2 = 10;
// 执行逻辑：num2 = (byte)(num2 + 130) → 先计算10+130=140，再强制转byte（byte范围-128~127）        
num2 += 130;          
System.out.println("num2 = " + num2);// 输出：num2 = -116（140超出范围，按二进制补码转换）
// 对比：普通赋值运算符（=）不会自动转换，直接报错byte 
num3 = 10;
//  num3 = num3 + 130; // 编译报错：不兼容的类型，int无法转byte
```

#### 关系运算符、三元运算符

关系运算符：

三元运算符：

格式：条件表达式 ？ 值1** ****:**** **值2;

执行流程：首先计算关系表达式的值，如果值为true，返回值1，如果为false，返回值2。



#### 逻辑运算符

注意：

- 在java中， “\&” 、 “\|”:   无论左边是 false还是 true，右边都要执行。

- \& ： 有一个为false、结果是false

- \&\&： 一个为false、结果是false，但前一个为false,后一个条件不执行了

- \| ： 有一个为true、结果是true

- \|\| ：一个为true、结果是true，但前一个为true，后一个条件不执行了

- \! ：\!false=true、 \!true=false

- ^  ：相同是false、不同是true。

## 二：Java程序的流程控制

### **分支结构**

#### if分支

根据条件的真或假，来决定执行某段代码。

![Image](https://internal-api-drive-stream.feishu.cn/space/api/box/stream/download/authcode/?code=YjA1NDIzZjg4MzQ1MWVlYTM4YmNiODJhN2Q4NzgyOGRfNjljODU0MTU3NjliMmUyMmE4MjI0MWQ0ZDUzZWE0MGRfSUQ6NzYxNDg2OTUwMDI1MjU4OTI3OF8xNzgwOTc2Nzc1OjE3ODEwNjMxNzVfVjM)

#### switch

![Image](https://internal-api-drive-stream.feishu.cn/space/api/box/stream/download/authcode/?code=NGQzYjgzMzBlODhiNmRlN2IwZTVlNzM1NTkzZDBlOGFfOTYwYjk4NzZiNjE3ZGJmMDA5MTJkMDM4MDU3MDg3ZjZfSUQ6NzYxNDg3MDEwNDY2MDEwMjA5N18xNzgwOTc2Nzc1OjE3ODEwNjMxNzVfVjM)

**注意事项：**

- 表达式类型只能是byte、short、int、char，JDK5开始支持枚举，JDK7开始支持String、不支持double、float、long。

- case给出的值不允许重复，且只能是字面量，不能是变量（可以是已经初始化的变量）。

- 正常使用switch的时候，不要忘记写break，否则会出现穿透现象（在某些情况下，也可使用穿透现象简化代码）。

### **循环结构**

#### for循环：

for循环格式

```Java
*// 输出3次HelloWorld*
for (int i = 0; i < 3; i++) {
    System.*out*.println("Hello World");
}
```

#### while循环：

定义示例：

```Java
int i = 0;
while (i < 3) {
    System.*out*.println("Hello World");
    i++;
 }
```



#### dowhile循环：



```Java
int i = 0;
do {
       System.*out*.println(“Hello World！");
       i++;
 } while( i < 3);
```

先执行一次，在判断条件是否成立，如果成立就再次执行语句，反之停止循环。



#### 三种循环小结：

- for循环 和 while循环（先判断后执行）; do\.\.\.while （先执行后判断）

- for循环和while循环的执行流程是一模一样的，功能上无区别，for能做的while也能做，反之亦然。

- 使用规范：如果已知循环次数建议使用for循环，如果不清楚要循环多少次建议使用while循环。

- 其他区别：for循环中，控制循环的变量只在循环中使用。while循环中，控制循环的变量在循环后还可以继续使用。

### **break、continue**

- break   :  跳出并结束当前所在循环的执行。

- continue:  用于跳出当前循环的当次执行，直接进入循环的下一次执行。



## 三：数组，二维数组

### 一维数组定义方式：

#### 静态初始化数组：

```Java
*// 静态初始化数组，定义时已经确定了数据*
//数据类型[] 数组名 = { 元素1，元素2 ，元素3，… };* *
int[] arr = {12, 24, 36};
*//完整格式*
//数据类型[]  数组名 = new 数据类型[]{元素1，元素2 ，元素3… };
int[] arr = new int[]{12, 24, 36};
```



#### 动态初始化数组：

```Java
//动态：定义数组时先不存入具体的元素值，只确定数组存储的数据类型和数组的长度
//数据类型[]  数组名 = new 数据类型[长度];
int[] arr = new int[3];
```

**动态初始化数组元素默认值规则：**

### 二维数组：

数组中的每个元素都是一个一维数组，这个数组就是二维数组。

#### 静态初始化：

```Java
//数据类型[][]  数组名 = new 数据类型[][]{元素1, 元素2, 元素3, ...};
int[][] arr = new int[][]{ {12, 24, 36} , {666, 888} , {10, 20, 30} , {999} };
```

#### 动态初始化：

```Java
//数据类型[][]  数组名 = new 数据类型[长度1][长度2];
int[][] arr = new int[3][5];
```

#### 二维数组的遍历：

```Java
for (int i = 0; i < arr.length; i++) {
    for (int j = 0; j < arr[i].length; j++) {
        int data = arr[i][j];
        System.*out*.print(data + "\t");
    }
    System.*out*.println();
 }
```





## 四：面向对象编程：

### 对象是什么：

对象是一种特殊的数据结构，可以用来记住一个事物的数据，从而代表该事物。对象本质上是一种特殊的数据结构（可以理解成一张表）。**class也就是****类****，也****称为对象的设计图****（或者****对象的模板****）。**

![Image](https://internal-api-drive-stream.feishu.cn/space/api/box/stream/download/authcode/?code=NjA5MDc1YTkzY2QwMTgyNGIwZGFmOTY1OGMyY2QyOTVfMTM0NmVlNmZmNGFhZjNjZjFhYzAzMDJiYzQ1ZGNkNzdfSUQ6NzYxNTY0Mzg4NDU1ODc4MTM5MV8xNzgwOTc2Nzc1OjE3ODEwNjMxNzVfVjM)



### 类的基本语法：

#### 构造器：

构造器是在创建对象时，同时完成对对象成员变量（属性）的初始化赋值的方法。创建对象时，对象会去调用构造器。

![Image](https://internal-api-drive-stream.feishu.cn/space/api/box/stream/download/authcode/?code=ZGViNmU1NjRjZjhlYjQwNDViYTNjYzM1MjhhNWY3N2FfMjJiOTIwYjk3MDQwMmY5ODA2YjA4ZGExMzVjYWQ0ZDVfSUQ6NzYxNTY0NDIwNTcwODUxMjQ2M18xNzgwOTc2Nzc1OjE3ODEwNjMxNzVfVjM)

```Java
// 定义一个父类 Person
class Person {
    // 成员变量
    private String name;
    private int age;

    // 1. 无参构造器
    public Person() {
        System.out.println("Person 无参构造器被调用");
        // 可以在无参构造器中给成员变量设置默认值
        this.name = "未知姓名";
        this.age = 0;
    }

    // 2. 有参构造器（单参数）
    public Person(String name) {
        System.out.println("Person 单参数构造器被调用");
        this.name = name;
        this.age = 0; // 年龄默认值
    }

    // 3. 有参构造器（多参数）
    public Person(String name, int age) {
        System.out.println("Person 多参数构造器被调用");
        this.name = name;
        this.age = age;
    }

    // 获取信息的方法，用于验证构造器赋值结果
    public String getInfo() {
        return "姓名：" + name + "，年龄：" + age;
    }
}
// 测试类，演示构造器调用
public class ConstructorDemo {
    public static void main(String[] args) {
        System.out.println("=== 测试父类构造器调用 ===");
        // 调用父类无参构造器
        Person person1 = new Person();
        System.out.println(person1.getInfo() + "\n");//输出姓名：未知姓名，年龄：0
        // 调用父类单参数构造器
        Person person2 = new Person("张三");
        System.out.println(person2.getInfo() + "\n");//输出姓名：张三，年龄：0
        // 调用父类多参数构造器
        Person person3 = new Person("李四", 20);
        System.out.println(person3.getInfo() + "\n"); //输出姓名：李四，年龄：20     
    }
}
```

注意事项：

- 类默认就自带了一个无参构造器。

- 如果为类定义了有参数构造器，类默认的无参数构造器就没有了，此时如果还想用无参数构造器，就必须自己手写一个无参数构造器出来。

#### this关键字：

this就是一个变量，可以用在方法中，来拿到当前对象，this就是一个变量， 可以用在方法中 ，用来拿到当前对象；哪个对象调用方法，this就指向哪个对象，也就是拿到哪个对象**。**

应用场景：this主要用来解决：变量名称冲突问题的。

```Java
public class Student {
    String name;
    double score;

    public void checkPass(double score){
        //使用this.score 来表示变量的score 与所传参数的 score区分开来
        if(this.score >= score){
            System.*out*.println("恭喜您，考上哈佛，走向巅峰~~~");
        }else {
            System.*out*.println("不好意思，您没有考上~~~");
        }
    }
 }
```



#### 封装：

封装就是用类设计对象处理某一个事物的数据时，应该把要处理的数据，以及处理这些数据的方法，设计到一个对象中去。封装的设计规范是 **合理隐藏，合理暴露。**隐藏与暴露的设计方法与权限修饰符有关，将在后文学到。



#### javabean：

javabean是一种特殊类\(也叫实体类\)，类中要满足如下需求：

- 类中的成员变量全部私有，并提供public修饰的getter/setter方法  

- 类中需要提供一个无参数构造器，有参数构造器可选

```TypeScript
public class Person {
    private String name;
    private int age;
    public Person() {}

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }
    public String getName() {
        return name;
    }
    public void setName(String name) {
        this.name = name;
    }
    public int getAge() {
        return age;
    }
    public void setAge(int age) {
        this.age = age;
    }
 }
```

**应用场景**：实体类的对象只负责数据存取（仅仅只是一个用来保存数据的java类，可以用它创建对象，保存某个事物的数据。），而对数据的处理交给其他类的对象来完成，以实现数据和数据业务处理相分离。



#### static：

##### static修饰成员变量：

成员变量按照有无static修饰分为两种：

- 静态变量（类变量）：属于类，与类一起加载一次，在内存中只有一份，可以被类和类的所有对象共享。

- 实例变量（对象的变量）：属于对象，每个对象中都有一份，只能用对象访问。

```Java
public class Student{
    //静态变量
    static String name;
    //实例变量
    int age;
}

public class Test{
    public void main(String[] args){
        *// 1、类变量的用法*
*        // 类名.静态变量(推荐)；在自己的类中访问自己的静态变量类名可以省略不写，*
        // *在其它类中访问其他类的静态变量必须带类名访问*
        Student.name = "ha";
        System.out.println(Student.name);//输出ha
        //对象也可直接调用静态变量，但不推荐
        Student stu = new Student();
        System.out.println(stu.name);//输出ha
        *// 2、实例变量的用法*
*        // 对象.实例变量*
        stu.age = 18;
        System.out.println(stu.age);
}
}
```

静态变量的应用场景：

- 如果某个数据只需要一份，且希望能够被共享\(访问、修改），则该数据可以定义成静态变量来记住。

##### static修饰方法：

静态方法 ：有static修饰的成员方法，属于类。

实例方法：无static修饰的成员方法，属于对象。

其调用方法与变量一致。

##### 静态方法的应用：

常见应用场景：做工具类

工具类：工具类中的方法都是一些静态方法，每个方法用来完成一个功能，以便供给开发人员直接使用。

实例方法需要创建对象调用，而静态方法不需要，直接用类名调用，节省内存。

注意：工具类不需要创建对象，建议将工具类的构造器私有。

##### static的注意事项：

- 静态方法中可以直接访问静态成员，不可以直接访问实例成员。

- 实例方法中既可以直接访问静态成员，也可以直接访问实例成员。

- 实例方法中可以出现this关键字，静态方法中不可以出现this关键字的。



### 继承：

#### super的三种核心用法：

1. 调用父类的构造方法

- 子类的构造方法中，`super()`必须是**第一条语句**（如果显式写），且只能出现一次。

- 如果子类构造方法中没有显式写`super()`，编译器会自动添加`super()`（调用父类的无参构造方法）。

- 可以通过`super(参数)`调用父类的有参构造方法，实现父类属性的初始化。

2. 调用父类的普通方法

- 子类重写了父类的方法后，想在子类中调用**父类原有的方法实现**，就需要用`super.方法名()`。

3. 访问父类的成员变量

- 子类定义了和父类同名的成员变量（变量隐藏），想在子类中访问父类的变量，用`super.变量名`。

#### 认识继承：

Java中提供了一个关键字extends，用这个关键字，可以让一个类和另一个类建立起父子关系。继承能增加代码复用性，减少重复代码的编写。

```Java
public class A{
    
}

public class B extends A{

}
```



在上述代码中，类B为A的子类。子类能继承父类的非私有成员（包括变量与方法）。在继承后子类的对象是由子类、父类共同完成的。



#### 权限修饰符： 

权限修饰符是用来限制类中的成员的受访问的范围。



#### 继承的特点：

- 单继承：Java是单继承模式：一个类只能继承一个直接父类

- 多层继承：Java不支持多继承，但支持多层继承

- 祖宗类：Java中所有的类都是Object类的子类

- 就近原则：优先访问自己类中，自己类中的没有才会访问父类。可以通过super关键字，指定访问父类的成员：

super\.父类成员变量/父类成员方法



#### 方法重写：

当子类觉得父类中的某个方法不好用，或者无法满足自己的需求时，子类可以重写一个方法名称、参数列表一样的方法，去覆盖父类的这个方法，这就是方法重写。

重写小技巧：使用@Override注解，他可以指定java编译器，检查我们方法重写的格式是否正确，代码可读性也会更好。



注意事项：

- 子类重写父类方法时，访问权限必须大于或者等于父类该方法的权限（ public \> protected \> 缺省 ）。

- 重写的方法返回值类型，必须与被重写方法的返回值类型一样，或者范围更小。

- 私有方法、静态方法不能被重写，如果重写会报错的。

- 子类重写Object类的toString\(\)方法，以便返回对象的内容。

```TypeScript
public class Student {
    // 定义类的属性，private修饰数据更安全可靠
    private String name;
    private int age;
    private String studentId;

    // 构造方法
    public Student(String name, int age, String studentId) {
        this.name = name;
        this.age = age;
        this.studentId = studentId;
    }
    //写了有参构造器后，不再默认生成无参构造器，可以写一个无参构造器以备不时之需
    public Student(){};
    // 重写Object类的toString()方法
    @Override  // @Override注解用于检查是否正确重写了父类方法
    public String toString() {
        /*
        返回包含对象属性的有意义字符串
        格式建议：类名[属性1=值1, 属性2=值2, ...]
        下式中'\''表示单引号字符。在 Java 字符串中，单引号本身是特殊字符，若要在字符串中表示            单引号，需要使用反斜杠进行转义，'\''这种写法就是用于在字符串中插入单引号。
         */
        return "Student[" +
                "name='" + name + '\'' +
                ", age=" + age +
                ", studentId='" + studentId + '\'' +
                ']';
    }

    // 测试主方法
    public static void main(String[] args) {
        // 创建Student对象
        Student student = new Student("张三", 20, "2024001");
        
        // 直接打印对象，会自动调用toString()方法
        System.out.println(student);//输出Student[name='张三', age=20, studentId='2024001']
        
        // 显式调用toString()方法，效果和上面一致
        System.out.println(student.toString());
    }
}
```

#### 子类构造器的特点：

特点：子类的全部构造器，都会先调用父类的构造器，再执行自己



子类构造器是如何实现调用父类构造器的：

- 默认情况下，子类全部构造器的第一行代码都是 super\(\) （写不写都有） ，它会调用父类的无参数构造器。

- 如果父类没有无参数构造器，则我们必须在子类构造器的第一行手写super\(参数\)，指定去调用父类的有参数构造器

```C++
class People{
    private String name;
    private int age;
    public People() {
    }

    public People(String name, int age) {
        this.name = name;
        this.age = age;
    }

    //get + set方法尚未写出
 }
 class Teacher extends People{
    private String skill;
    public Teacher(){
    }

    public Teacher(String name, int age, String skill) {
        //super调用父类有参构造器
        super(name, age);
        this.skill = skill;
    }

   //get + set方法尚未写出
 }
```



注意：任意类的构造器中，是可以通过this\(…\) 去调用该类的其他构造器的。this\(…\) 、super\(…\) 都只能放在构造器的第一行，因此，有了this\(…\)就不能写super\(…\)了，反之亦然。



### 多态：

#### 认识多态:

多态是在继承/实现情况下的一种现象，表现为：对象多态、行为多态。

```Java
public class A{
    public void run(){
        System.out.println("A");
    }
}
public class B extends A{
    public void run(){
        System.out.println("B");
    }
}
public class C extends A{
    public void run(){
        System.out.println("C");
    }
}
A a = new B();
a.run();//输出B
A a = new C();
a.run();//输出C
```

多态的前提：有继承/实现关系；存在父类引用子类对象；存在方法重写。

注意事项：多态是对象、行为的多态，Java中的属性\(成员变量\)不谈多态。 



#### 多态的好处：

- 在多态形式下，右边对象是解耦合的，更便于扩展和维护。

![Image](https://internal-api-drive-stream.feishu.cn/space/api/box/stream/download/authcode/?code=ZTAyOGZiMTJiNTQyODcwZjFkNDMzMjVkMmEzMzRkOWNfNWE5NGM2M2QwZjNjNzZlNzZhOTkxMWQ0NTk5OTkzNGVfSUQ6NzYxNTk4ODQxNzQ2MTE0NDgwNF8xNzgwOTc2Nzc1OjE3ODEwNjMxNzVfVjM)

- 定义方法时，使用父类类型的形参，可以接收一切子类对象，扩展性更强、更便利。



问题：多态下不能使用子类的独有方法。



#### 多态下的类型转换：



自动类型转换：父类 变量名 = new 子类\(\)。 例如：People p = new Teacher\(\);（子类转换为父类类型）

强制类型转换：子类 变量名 = \(子类\) 父类变量。例如 Teacher t = \(Teacher\)p;

强制类型转换注意事项：

- 存在继承/实现关系就可以在编译阶段进行强制类型转换，编译阶段不会报错。

- 运行时，如果发现对象的真实类型与强转后的类型不同，就会报类型转换异常（ClassCastException）的错误出来；强转前，Java建议使用instanceof关键字，判断当前对象的真实类型，再进行强转：

boolean isStudent = p  **instanceof Student ;** 



### final关键字：

#### 认识final关键字：

final 关键字是最终的意思，可以修饰：类、方法、变量。

- 修饰类：该类被称为最终类，特点是不能被继承了。

- 修饰方法：该方法被称为最终方法，特点是不能被重写了。

- 修饰变量：该变量有且仅能被赋值一次。

final修饰变量的注意：

- final修饰基本类型的变量，变量存储的**数据**不能被改变。

- final修饰引用类型的变量，变量存储的**地址**不能被改变，但地址所指向对象的内容是可以被改变的。



#### 常量：

使用了 static final 修饰的成员变量就被称为常量\.

作用：常用于记录系统的配置信息。

常量的命名规范：建议使用大写英文单词，多个单词使用下划线连接起来。



使用常量记录系统配置信息的优势、执行原理：

- 代码可读性更好，可维护性也更好。

- 程序编译后，常量会被“宏替换”：出现常量的地方全部会被替换成其记住的字面量，这样可以保证使用常量和直接用字面量的性能是一样的。



### 单例类（设计模式）：



#### 设计模式：

一个问题通常有n种解法，其中肯定有一种解法是最优的，这个最优的解法被人总结出来了，称之为**设计模式。**



#### 单例设计模式：

作用：确保某一个类只能创建一个对象。



**实现步骤：**

```TypeScript
*// 单例类*

//饿汉式单例：拿对象时，对象已经创建好
public class A {
    *// 2、定义一个静态变量记住类的一个对象*
*    *private static A *a *= new A();

    *// 1、私有构造器*
*    *private A(){
    }

    *// 3、定义一个静态方法返回对象*
*    *public static A getObject(){
        return *a*;
    }
 }
 
 //懒汉式单例：拿对象时才创建对象
 public class B {
    *// 2、定义一个类变量量用于存储对象*
*    *private static B *b *; *// null*
*    // 1、单例必须私有构造器*
*    *private B(){
    }

    *// 3、提供一个类方法返回类的一个对象*
*    *public static B getObject(){
        if(*b *== null){
            *b *= new B();
        }
        return *b*;
    }
 }
```



### 枚举类：



#### 认识枚举类：

枚举类是一种特殊类；枚举类的写法：

![Image](https://internal-api-drive-stream.feishu.cn/space/api/box/stream/download/authcode/?code=OWRiYWI4NmRhOWM4Y2VmM2EyNzlmMTEzZTQ0ZmNhZTRfNWI4OTQ4YjZkMzg0OGQyYTRhZDlhZGQzZTY2YmYyYzRfSUQ6NzYxNjAxODMzNzE1OTcxMTk2MV8xNzgwOTc2Nzc1OjE3ODEwNjMxNzVfVjM)

**特点：**

- 枚举类中的第一行，只能写枚举类的对象名称，且要用逗号隔开。

- 这些名称，本质是常量，每个常量都记住了枚举类的一个对象。



![Image](https://internal-api-drive-stream.feishu.cn/space/api/box/stream/download/authcode/?code=Yzc4NTUxZDhkNzZlN2MwOWY2ODM5NDVkZTYxZjE4Y2VfY2EzMjA4MjE3MThmMGQzMDJhNjk2Y2FlZTliYTNmMzZfSUQ6NzYxNjM3NTQwNTc0NTg2NzcyOV8xNzgwOTc2Nzc1OjE3ODEwNjMxNzVfVjM)

![Image](https://internal-api-drive-stream.feishu.cn/space/api/box/stream/download/authcode/?code=NjI4MDQwOWRlN2YyYWE5OWQyZWQ2ZTZmYTFiMDAxMjhfYTlmODgzZDRhZDAwM2Y3MTFmNTNiNzA5YzgwMDI3NjBfSUQ6NzYxNjM3NTQzMjEzNjUxMDQwN18xNzgwOTc2Nzc1OjE3ODEwNjMxNzVfVjM)





注意：

- 枚举都是最终类，不可以被继承，枚举类都是继承java\.lang\.Enum类的。

- 枚举类的第一行只能罗列一些名称，这些名称都是常量，并且每个常量会记住枚举类的一个对象。

- 枚举类的构造器都是私有的（写不写都只能是私有的），因此，枚举类对外不能创建对象。

- 编译器为枚举类新增了几个方法。



应用场景：信息分类与标志



### 抽象类：



#### 认识抽象类：

Java中有一个关键字叫：abstract，它就是抽象的意思，可以用它修饰类、成员方法。abstract修饰类，这个类就是抽象类。abstract修饰方法，这个方法就是抽象方法。

![Image](https://internal-api-drive-stream.feishu.cn/space/api/box/stream/download/authcode/?code=OTc4NTRiYzZkZGE0Njk1MTdmNWZjZDUxMjQwMTdmYzZfMDNlODlmZjhiNDc1MTJkNzgyZDRkMjJiYjE0ZmUzMjlfSUQ6NzYxNjM3NjE5MzEwNDc0MzM3Nl8xNzgwOTc2Nzc1OjE3ODEwNjMxNzVfVjM)

```Java
public abstract class A {
    *// 抽象方法：必须abstract修饰，只有方法签名，不能有方法体*
*    *public abstract void test();
 }
```



注意事项：

- 抽象类中不一定要有抽象方法，有抽象方法的类必须是抽象类。

- 类有的成员：成员变量、方法、构造器，抽象类都可以有。

- **抽象类最主要的特点：**抽象类不能创建对象，仅作为一种特殊的父类，让子类继承并实现。

- 一个类继承抽象类，必须重写完抽象类的全部抽象方法，否则这个类也必须定义成抽象类。



#### 使用抽象类的好处：

父类知道每个子类都要做某个行为，但每个子类要做的情况不一样，父类就定义成抽象方法，交给子类去重写实现，我们设计这样的抽象类，就是为了更好的支持多态。



#### 模板方法设计模式：

提供一个方法作为完成某类功能的模板，模板方法封装了每个实现步骤，但允许子类提供特定步骤的实现。模板方法设计模式可以：提高代码的复用、并简化子类设计。

1. 定义一个抽象类。

2. 在里面定义2个方法

- 一个是模板方法：把共同的实现步骤放里面去。

- 一个是抽象方法：不确定的实现步骤，交给具体的子类来完成。



注意：建议使用final关键字修饰模板方法：  

- 模板方法是给子类直接使用的，不能被子类重写。

- 一旦子类重写了模板方法，模板方法就失效了。



### 接口：

#### 接口概述：

Java提供了一个关键字interface定义出接口。

```Java
public interface 接口名{
       //成员变量（常量）
       //成员方法（抽象方法）
       
       //**JDK 8开始，接口新增了三种形式的方法：**
           */***
*     * 1、默认方法（实例方法）：使用用default修饰，默认会被加上public修饰。*
*     * 注意：只能使用接口的实现类对象调用*
*     */*
*    *default void test1(){
        ...
    }

    */***
*     * 2、私有方法：必须用private修饰(JDK 9开始才支持)*
*     */*
*    *private void test2(){
        ...
    }

    */***
*     * 3、类方法（静态方法）：使用static修饰，默认会被加上public修饰。*
*     * 注意：只能用接口名来调用。*
*     */*
*    *static void test3(){
        ...
    }
}
//注意：接口不能创建对象
```

接口是用来被类实现（implements）的，实现接口的类称为实现类，一个类可以同时实现多个接口。

![Image](https://internal-api-drive-stream.feishu.cn/space/api/box/stream/download/authcode/?code=YmYxOTBiODBmYmIwMTExYjhkMjk0OGE5OGM2OTRkMDJfNDRjMWMzZmI4ZjI0M2E4MTRjZjUzN2M4ODgxN2ViYWRfSUQ6NzYxNjM4NDc2MDg2MDExNzk4MV8xNzgwOTc2Nzc1OjE3ODEwNjMxNzVfVjM)



#### 接口好处：

- 弥补了类单继承的不足，一个类同时可以实现多个接口，使类的角色更多，功能更强大。

- 让程序可以面向接口编程，这样程序员就可以灵活方便的切换各种业务实现（更利于程序的解耦合）。



注意事项：

- 接口与接口可以多继承：一个接口可以同时继承多个接口\[重点\]。

- 一个接口继承多个接口，如果多个接口中存在方法签名冲突，则此时不支持多继承，也不支持多实现。

- 一个类继承了父类，又同时实现了接口，如果父类中和接口中有同名的默认方法，实现类会优先用父类的。（此时若想调用接口中的类：接口名\.super\.同名方法（）;）

- 一个类实现了多个接口，如果多个接口中存在同名的默认方法，这个类必须重写该方法。



### 代码块

代码块是类的5大成分之一（成员变量、构造器、方法、代码块、内部类）。

**代码块分为两种：**

1. **静态代码块**: 

- **格式**：static \{ \}

- **特点**：类加载时自动执行，由于类只会加载一次，所以静态代码块也只会执行一次。

- **作用**：完成类的初始化，例如：对静态变量的初始化赋值。

2. **实例代码块: **

- **格式**：\{ \}

- **特点**：每次创建对象时，执行实例代码块，并在构造器前执行。

- **作用：**和构造器一样，都是用来完成对象的初始化的，例如：对实例变量进行初始化赋值。





### 内部类：

内部类是类的5大成分之一，就是定义在一个类内部的类。根据定义位置和修饰符的不同，内部类分为四种：成员内部类、静态内部类、局部内部类、匿名内部类。

#### 成员内部类：

就是类中的一个普通成员，类似普通的成员变量。属于外部类的对象持有。

特点：

- 成员内部类中可以直接访问外部类的成员（包括私有成员），因为内部类持有外部类对象的引用（外部类名.this）。

- 成员内部类中不能定义静态成员（static修饰的变量和方法），但可以定义静态常量（static final）。

- 成员内部类的实例一定依附于一个外部类的实例。

创建对象的格式：

```Java
// 外部类名.内部类名 对象名 = new 外部类(...).new 内部类(...);
Outer.Inner in = new Outer().new Inner();
```

代码示例：

```Java
public class Outer {
    private String name = "外部类";

    // 成员内部类
    public class Inner {
        private String name = "内部类";

        public void show() {
            // 访问内部类自己的name
            System.out.println(name);            // 输出：内部类
            // 通过 Outer.this 访问外部类的name
            System.out.println(Outer.this.name); // 输出：外部类
        }
    }
}

public class Test {
    public static void main(String[] args) {
        // 必须先有外部类对象，才能创建内部类对象
        Outer.Inner in = new Outer().new Inner();
        in.show();
    }
}
```

#### 静态内部类：

使用static修饰的成员内部类，属于外部类本身，不依赖于外部类的实例。

特点：

- 静态内部类中可以直接访问外部类的静态成员，但不能直接访问外部类的实例成员（需要通过外部类对象来访问）。

- 静态内部类中可以定义静态成员和实例成员。

- 静态内部类不持有外部类对象的引用，因此不会造成内存泄漏。

创建对象的格式：

```Java
// 外部类名.内部类名 对象名 = new 外部类名.内部类名(...);
Outer.Inner in = new Outer.Inner();
```

代码示例：

```Java
public class Outer {
    private static String staticName = "外部类静态变量";
    private String instanceName = "外部类实例变量";

    // 静态内部类
    public static class Inner {
        public void show() {
            // 可以直接访问外部类的静态成员
            System.out.println(staticName);       // OK
            // 不能直接访问外部类的实例成员
            // System.out.println(instanceName);   // 编译报错
        }
    }
}

public class Test {
    public static void main(String[] args) {
        // 不需要外部类对象，直接创建静态内部类对象
        Outer.Inner in = new Outer.Inner();
        in.show();
    }
}
```

成员内部类和静态内部类的区别：

- 成员内部类依附于外部类的对象，创建时必须先有外部类对象；静态内部类依附于外部类本身，创建时不需要外部类对象。

- 成员内部类可以直接访问外部类的所有成员；静态内部类只能直接访问外部类的静态成员。

- 成员内部类不能定义静态成员；静态内部类可以定义静态成员。

#### 局部内部类：

定义在方法内部的类，类似于局部变量，只在当前方法内有效。

特点：

- 局部内部类的作用域仅限于所在的方法内部，方法外部无法访问。

- 局部内部类可以直接访问外部类的所有成员。

- 局部内部类还可以访问所在方法的局部变量，但该局部变量必须是事实最终变量（即赋值后不再修改），JDK8以后可以省略final关键字。

- 局部内部类中不能定义静态成员。

代码示例：

```Java
public class Outer {
    private String name = "外部类";

    public void method() {
        // 局部变量
        int num = 10;  // 事实最终变量（赋值后未修改）

        // 局部内部类
        class Inner {
            public void show() {
                // 可以直接访问外部类成员
                System.out.println(name);  // 输出：外部类
                // 可以访问所在方法的局部变量
                System.out.println(num);   // 输出：10
            }
        }

        // 在方法内创建局部内部类对象并使用
        Inner in = new Inner();
        in.show();
    }
}

public class Test {
    public static void main(String[] args) {
        new Outer().method();
    }
}
```

为什么局部变量必须是事实最终变量？

因为局部变量存储在栈中，方法执行完毕后就会被销毁。而局部内部类对象可能在方法返回后仍然存在于堆中（如果被传递出去的话）。为了解决这个生命周期不一致的问题，Java会将局部变量的值拷贝一份到局部内部类中。如果允许修改局部变量，就会导致内部类中的拷贝值和原变量值不一致，所以Java规定被访问的局部变量必须是事实最终变量。

#### 匿名内部类：

匿名内部类是一种没有名字的内部类，本质上是局部内部类的简化写法。它在创建对象的同时定义类，通常用于只需要使用一次的类。

语法格式：

```Java
new 类名或接口名() {
    // 类体（重写方法或实现方法）
};
```

代码示例：

```Java
// 1. 匿名内部类实现接口
public interface Animal {
    void speak();
}

public class Test {
    public static void main(String[] args) {
        // 使用匿名内部类创建Animal的实现类对象
        Animal dog = new Animal() {
            @Override
            public void speak() {
                System.out.println("汪汪汪！");
            }
        };
        dog.speak();  // 输出：汪汪汪！

        // 也可以直接调用，一步到位
        new Animal() {
            @Override
            public void speak() {
                System.out.println("喵喵喵！");
            }
        }.speak();  // 输出：喵喵喵！
    }
}
```

```Java
// 2. 匿名内部类继承抽象类
public abstract class Shape {
    public abstract double area();
}

public class Test {
    public static void main(String[] args) {
        // 匿名内部类继承Shape，实现area方法
        Shape circle = new Shape() {
            @Override
            public double area() {
                return 3.14 * 5 * 5;
            }
        };
        System.out.println("圆的面积：" + circle.area()); // 输出：圆的面积：78.5
    }
}
```

```Java
// 3. 匿名内部类作为方法参数（最常见的应用场景）
public class Test {
    public static void main(String[] args) {
        // 直接将匿名内部类作为参数传递
        method(new Animal() {
            @Override
            public void speak() {
                System.out.println("嘎嘎嘎！");
            }
        });
    }

    public static void method(Animal animal) {
        animal.speak();
    }
}
```

匿名内部类的特点：

- 匿名内部类没有类名，因此不能定义构造器。

- 匿名内部类只能创建一个对象，创建之后就不能再复用这个类了。

- 匿名内部类本质上是继承了父类或实现了接口的子类/实现类对象。

- 在开发中，匿名内部类最常见的用途是作为方法的实参传递，简化代码。

注意事项：

- 匿名内部类中访问局部变量时，该变量同样必须是事实最终变量。

- 匿名内部类在编译后会产生独立的class文件，命名为：外部类名$数字.class（如 Outer$1.class）。

## 常见api接口

### String
#### 创建对象的方式
①String s = “hello ”;
②调用构造器




