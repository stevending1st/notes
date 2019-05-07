# 第一天

## Java 与编程概述

> 计算机程序： 一系列有序指令的集合。

> Java 是 Sun Microsystems 于 1995 年推出的高级编程语言。

> Java Development Kit -- Java 开发平台。
> JDK 1.50  = JDK5.0
> JDK 1.60  = JDK6.0
> ...

> **Java 语言平台版本**
> J2SE标准版
> J2ME小型版
> J2EE企业版
> ...

> JMV == Java虚拟机
> JRE == Java运行环境
> JDK == Java开发工具包
> 简言之，使用JDK开发Java程序交给JRE运行。
> JDK包含JRE,JRE包含JVM。

## 利用 eclipse 创建 Java 项目
1. eclipse创建项目
2. src文件夹下创建包
3. 包里写.java文件

## Hello World 
```java
/*
	这是多行注释
*/
public class Hello{
	// 这是一条单行注释
	public static void main(String[] args) {
		System.out.print("Hello World!");
	}
}
```

`public static void main(String[] args) `：JRE程序入口

**标识符：** 所有自定义名名称内容，见名知意。
- 规范：
  - 数字、字母、下划线、美分符（$）、不能数字开头，不能是关键字（*强制*）。
  
  - 类名首字母大写，多个单词每个单词首字母大写。
  - 方法名、变量名

## 
- **声明变量：** `数据类型 变量名;`
  - eg:  `int a;`
- **给变量赋值：**`变量名 = 值;`
  - eg:  `a = 10;`
- **声明并赋值：** `数据类型 数据名 = 值;`
  - eg: `int b = 20;`
- **同时声明多个变量：** `数据类型 变量名1,变量名2...`
  - eg: `int x,y,z;`
- **同时声明多个变量并赋值：** `数据类型 变量名1=值1,变量名2=值2,变量名=值3;`
  - eg: `int a=1,b=2,c=3;//a=1,b=2,c=3 `
  - eg: `int a=1,b,c=3;//a=1,c=3,b未赋值`
  - eg: `int a,b,c=3;//a、b未赋值，c=3`

  