# Day10

## 二维数组
装着一维数组的一组容器。
```java
// 动态初始化
元素类型[][] 数组名 = new int[值1][值2];
```
```java
// 静态初始化
元素类型[][] 数组名 = {{值[0,0],值[0,1],值[0,2],值[0,3]......},{值[1,0],值[1,1],值[1,2]......},{值[2,0],值[2,1]......}}
```
静态初始化生成的数组，每一层的长度可以不一样，每一层的长度等于它实际赋值的长度。
```java
int[][] arr = {{1,2,3},{2,9,6,2,6},{5,2}};
int[0].length // 3
int[1].length // 5
int[2].length // 2
```
## 值传递和地址传递（重点）
地址传递也被称为引用传递或址传递。
基本数据类型都是值传递(call by value)，引用数据类型*基本*是地址传递(call by reference)。
引用数据类型中**String型数据是值传递**。
引用数据无法改变引用地址，只能改变数据属性。

## 动态参数
可以当做数组处理,一个方法只能有一个动态参数，且放在参数列表的最后。
```java
public void fun(int... a){
    a[0]//调用第1个参数
    a[2]//调用第2个参数
    ...
}

fun([1,2...])//可以放入对应的数组类型
fun(1,2...)
```

## Object类
存放在 java.lang 包中，使用时不强制引入该包。
任何类在声明时都可以用Object接收，如：`Object 对象名 = new 类名()`。

public int hashCode()
用于返回对象的哈希码。

public String toString()
用于返回内存地址（对象的类型，哈希码的16进制形式。）
通过print()/println()输出对象，默认输出对象的toString()方法。

## String 类
String类是最终类，无法创建子类。
只产生一个对象:
```java
String str1 = "hello";
```
产生两个对象:
```java
String str2 = new String("hello");
```
```java
boolean equals(Object o)
```
equals方法和比较运算符用于对象是一样的效果。
基本数据类型不能调用方法。

## String类和对象比较
一般对象的equals方法用于比较地址。
字符串对象的equals方法用于比较值。

`==`用于比较`String str1 = "hello"`形式声明的string 类型变量时，比较的是变量的值。

在 String 类型中 toString() 方法和 String() 方法被重写，用于返回 String 类型变量的值。

## 私有构造方法（单例模式）
