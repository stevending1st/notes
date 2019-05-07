b# Day11

## 设计模式
**设计模式**是一套被反复使用、多数人知晓得、经过分类编目的、代码设计经验的总结。
不是一种方法技术，而是一种思想。

### 设计原则
- 单一职责原则
  - “高内聚，低耦合”
- 开闭原则
  - 对拓展开放，对修改关闭。
- 里氏替换原则
  - 继承和多态
- 依赖注入原则
  - 依赖于抽象，不依赖于具体实现
  - 依赖于抽象类和接口
- 接口分离原则
- 迪米特原则
  - 一个对象应当对其他对象尽可能少的了解

### 单例模式（单例）
单例模式就是要确保类在内存中只有一个对象，该实例必须自动创建，并对外提供。

**饿汉式单例模式**
```java
public class Singleton {
    private static Singleton s = new Singleton();
    private Singleton(){}
    public static Singleton getInstance(){
        return s;
    }
}
```

**懒汉式单例模式**
```java
public class Singleton {
    private static Singleton s = null;
    private Singleton(){}
    public static Singleton getInstance(){
        if(s==null){
            s =  new Singleton();
        }
        return s;
    }
}
```

### 简单工厂模式（静态工厂模式）

## String

### 构造方法
```java
public String()
```

```java
public String(byte[] bytes)
```
把byte数组中所有数据连接成字符串对象

```java
public String(byte[] bytes, int offset,int length)
```
