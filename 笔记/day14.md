# Day 14

## StringBuffer 和 StringBuilder
`StringBuffer` 线程安全，效率低
```java
// 构造函数
StringBuffer()//初始化16个字符空间
StringBuffer(int a)//初始化时定义缓冲区长度为a
StringBuffer(String str)//初始化时定义缓冲区长度为16加str的字符长度

//其他方法
append()//在末尾追加字符,超过缓冲区长度时，缓冲区长度变为原来的两倍加2，以此类推
capacity()//返回缓冲区长度
toString()//将StringBuffer对象转成String对象
delete(int stratNum,int EndNum)//删除stratNum至endNum的字符，含前不含后
deleteCharAt(int Num)//删除第Num个字符
reverse()//字符串反转
insert(int num, String str)//从num位置开始插入字符串str

subString()//返回截取后的字符串，需要接收
```
`StringBuilder` 线程不安全，效率高,与`StringBuffer`用法相同。

## 集合类(集合框架)
从JDK1.5允许使用泛型，容量可变的容器
```java
List<String> list = new Arraylist<String>();
```
`List<String>`接口泛型
`Arraylist<String>`方法泛型
指定了泛型的集合对象，只能存储相应数据类型的元素；
制定泛型时，前后要一致；
泛型不能制定基本数据类型；
从定义了泛型的集合对象中取数据，不需要强制类型转换；
不指定泛型的集合对象，使用foreach时只能用Object来接收集合中的元素。

### Collection[接口]
在java.
```java
add(Object obj)//添加
size()//返回长度
addAll(Collection coll)//将Collection的元素逐个放入对象
addAll(int num, Collection)//从num位置开始，将Collection的元素逐个放入对象
toArray()//把集合转数组
```
#### List[接口]
有序集合，可以存储相同元素。
在java.util包下
```java
add(int num, Object obj)//从指定下标，插入元素
get(int num)//返回制定下标位置的元素，返回元素是Object类型的，如果要指定类型需要向下转型。
remove(int num)//删除指定下标位置的元素

coptains(object obj)//判断是否存在某个元素
containsAll(List list)//判断是否含有list中所有元素
removeAll(List list)//删除list中包含的元素
```
##### ArrayList
数组结构，在数据遍历效率更高
##### LinkedList
链表结构，在增加和删除数据效率更高
```java
addFirst()
addLast()

getFirst()
getLast()

removeFirst()
removeLast()
```
#### set[接口]
无序集合，不能用下标取值不能存储相同数据。
##### HashSet
Collection集合中的元素可以赋给迭代器itarator();
hasNext();//下一个是否有值
### Map[接口]
```java
//put()//用于存储元素，需要给出可以（键）和value(值)
key相同，value则覆盖
不指定泛型时，可以喝value均为Object类型
get()方法通过key获取value的值
map e 的key是无序的
map不能直接进入循环，需要转成 相应的collection类型，
通过调用map的keyset方法可以得到所有key的值。
```
##### HashMap
允许有null键和null值
##### HashTable
不允许有null键和null值
##### COLLCTIONs
操作集合的工具类