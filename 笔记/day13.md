# day13

## 异常处理
**异常：** 异常就是Java程序在运行过程中出现的错误。

- Throwable
  - Error（处理不了）
  - Exception （能手动处理）
    - 子类 (检查型异常，强制要求异常处理)
    - RuntimeException （运行时异常，不强制要求异常处理）
      - 子类

### 处理
```java
try{
    //可能出现异常的语句；
}catch(/*异常类型对象*/) {
    //如果出现异常的处理；
}

try{
    //可能出现异常的语句；
}catch(/*异常类型1*/) {
    //如果出现异常1的处理；
}catch(/*异常类型2*/) {
    //如果出现异常2的处理；
}
//...
catch(/*父类型异常*/) {
    //如果出现父类异常的处理；
}

try{
    //可能出现异常的语句；
}catch(/*异常类型1*/) {
    //如果出现异常1的处理；
}catch(/*异常类型2*/) {
    //如果出现异常2的处理；
}
//...
catch(/*父类型异常*/) {
    //如果出现父类异常的处理；
}finally{
    // 一定会被执行的部分，无论try中是否有return，如有则在return前执行
}

try{
    //可能出现异常的语句；
}finally{
    // 一定会被执行的部分，无论try中是否有return，如有则在return前执行
}

try{
    //可能出现异常的语句0；
    try{
        //可能出现异常的语句1；
    }catch(/*异常类型对象*/) {
        //如果语句1出现异常的处理；
    }
}catch(/*异常类型对象*/) {
    //如果语句0出现异常或语句1的异常未处理的处理；
}
```
例：
```java
try{
    a = nextInt();
}catch(Exception e){
    System.out.ptintln("输入有误。。。。")
}

try{
    a = nextInt();
}catch(InputMi) {
    //如果出现异常1的处理；
}catch(/*异常类型2*/) {
    //如果出现异常2的处理；
}
//...
catch(/*父类型异常*/) {
    //如果出现父类异常的处理；
}
```
```java
//手动抛出异常
throw new Exception(/*自定义异常信息*/);

throws 异常名1，异常...//用于方法头，在参数列表后
```

### 自定义异常
自定义异常必须继承Exception或其子类。
一般定义两个构造方法，一个不带参，一个带报错参数。0
```java
class myException extends Exception{
    public MyException() {

    }
    public MyException(String msg) {
        super(msg);
    }
}
```

## 常用类库

### 包装类
基本包装
- Byte 
- Short 
- Integer (int) [常用] 
  - `public static int pareInt(String s)`
- Long 
- Float 
- Double [常用]
- Character (char)
- Boolean

Jdk1.5开始，支持基本数据类型和包装类之间的自动转换
1.5以前：
```java
int a = 9;
Integer x= new Integer(a);

```
### Arrays类(数字类)
存放在java.util.Arrays包下，是操作数组的包装类，Arrays是普通类，继承Object,其构造方法是私有的，Arrays类中都是静态方法。

### Math类*(数学类)
存放在java.lang包下，是最终类(finall)，只提供一个私有构造方法。 
```java
Math.abs()//绝对值
Math.ceil()//向上取整（返回值是double型的）
Math.floor()//向下取整（返回值是double型的）
Math.round()//四舍五入（返回值是long型的）
Math.PI//3.14159265...
Math.max(a,b)//返回较大值
Math.sqrt()//算术平方根（返回值为double型的）
Math.pow(a,b)//a的b次方
```
### 大的数字处理类
Biginteger、BigDecimal类存放在java.Math报下。
```java
add()//加
divide()//除
multiply()//乘
subtract()//减
divideAndRemainder()//得到商和余数。
```

### Randoml类(随机数类）
存放在java.util.Random包下。
```java
//构造方法
Random()
Random(Lang l)//带种子数，生成的随机数相同

//方法
nextInt()//生成随机数
nextInt(int a)//生成0-a随机数（不包含0和a）

```

----

### Date类（日期类）
在java.util.Date包(优先选择)和java.sql.Date包下。
```java
//构造方法
new Date()//当前系统时间的对象
new Date(long date)//构建一个特定时间的构造对象，1970-1-1 0:0:0后date毫秒的时刻，以标准时间为准。
new Date(int year,int month,int day)//构建一个时间对象（已过时，可用），实际年year+1900,时间月month,实际日day,月份是0-12，如果超过月日限制，自动进位。

//方法
getTime()//1970-1-1 0:0:0到对象时刻的毫秒数
setTime(long time)//设置1970-1-1 0:0:0后time毫秒的时间
```
```java
System.currentTimeMillis();//当前系统时间的毫秒数。
```

### DateFormat类、SimpleDateFormat类（格式化时间对象）

```java
//构造方法
DateFormat  df = new SimpleDateFormat(String str);//按格式输出时刻,str为格式类型
//方法
format(Date date)//时间转字符串
parse(String str)//字符串转时间对象
```
### Calendar类（日历类）
在java.util.Calendar包下,抽象方法。
```java
//构造函数
Calendar c = Calendar.getInstance();
//方法
get(Calendar.XXX);
set(Calendar.XXX, int value);// 设置时间
add(Calendar.XXX, int value);//  过value XXX的时间
/*
XXX:YEAR
MONTH
DATE
DAY_OF_WEEK
*/
getTime();//日历对象转成日期对象。
setTime(Date date); // 日期对象转成日历对象。
```
