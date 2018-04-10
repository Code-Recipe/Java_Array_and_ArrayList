<notice>教程读者请不要直接阅读本文件，因为诸多功能在此无法正常使用，请移步至[程谱 coderecipe.cn](https://coderecipe.cn/learn/1)学习完整教程。如果您喜欢我们的教程，请在右上角给我们一个“Star”，谢谢您的支持！</notice>
Java教程-
======

欢迎来到程谱社区！😁 我们是一群留学生，致力于搭建一个系统而又不枯燥的零基础入门编程学习平台。希望大家能多多支持我们，如果发现我们的不足之处也欢迎联系我们~

这是程谱Java教程数组与数组列表单元的的第2章，主要为大家讲解数组列表（ArrayList）。请大家进行学习！

数组列表的定义
----
数组列表（ArrayList）也是一种储存一组数据的方式，与Array不同，ArrayList有以下优点：

1.ArrayList长度可变，而Array长度固定。

2.在ArrayList中最后一个存储位置一定是list.size()-1，在Array中数据可能是部分填满的，因此程序员使用Array时必需持续跟踪最后一个使用的储存位置。

3.在ArrayList中，你可以通过一条语句插入或删除元素，元素会自动移动，然而在Array中插入或删除元素会需要你用代码移动剩下的元素。

集合API
-----
ArrayList类是一种集合API(Application Programming Interface)，是一个Java提供的库，大部分API都在java.util里。

集合与泛型
-----
Java的集合类主要负责保存、盛装和管理对象，因此集合类也被称为容器类。

集合类分为Set、List、Map和Queue四大体系。所有集合类都位于java.util包中，集合中只能保存对象的引用。集合类把它所含有的元素看成是Object的实例，这样方便但是也有隐患，即多个类型不同的元素被放入一个集合中，会增加集合访问时类型转换的困难，甚至会产生错误。

泛型的引入改善了这种情况，使用泛型来限制集合里元素的类型，并让集合记住元素的类型。这样可以允许编译器检查加入集合的元素类型，避免值类型不一致的错误。典型的泛型集合有List<T>, HashMap<K,V>等。

包类
-----
为了更好地组织类（Class），Java 提供了包机制，用于区别类名的命名空间。它把功能相似或相关的类或接口组织在同一个包中，方便类的查找和使用。

包语句的语法格式为：
```java
package pkg1[．pkg2[．pkg3…]];
```
大家看定义可能会有些晕头转向的。那么，我们来通过一个实例来说明一下包的实际作用。例如，我们假设一个Hello.java文件内容如下：
```java
package net.java.util;
public class Hello{
   ...
}
```
那么它的路径应该是 net/java/util/Hello.java 这样保存的。 Package(包) 的作用是把不同的 Java 程序分类保存，更方便的被其他 Java 程序调用。
明白了什么事包以后，我们就来学习一下如何创建和使用包。创建包的代码如下：

e.g.
```java
/* 文件名: Vehicle.java */
package vehicles;

interface Vehicle {
   public void price();
   public void fuel();
   ...
}
```
TIPS: 我们通常使用小写的字母来命名包，这是为了避免与类、接口名字的冲突。本例在vehicles包中加入一个接口（interface），而该接口的实现在此略而不表。

在我们需要使用包时，需要使用大名鼎鼎的import关键字。在 Java 源文件中 import 语句应位于 package 语句之后，所有类的定义之前，可以没有，也可以有多条，其语法格式为：

```java
import package1[.package2…].(classname|*);
```

自动封包拆包
-----
封包与拆包，听起来高大上而不知所云，其实就是java会自动把基本类型（如int, double等）封装成对象。

能够这么做的原因，是因为所有的基本类型都有一个与之对应的类，称为 Warpper，如 int对应Integer、char对应Character、void对应Void 和 boolean对应Boolean 等。

正常来讲，我们如果要将Integer与int相互转换时，需要调用intValue和valueOf这两个方法。但是在JDK 1.5之后，Java会隐式地自动调用他们。我们要做的只是键入如下代码：

e.g.
```java
//声明一个Integer对象
Integer num = 10;
//以上声明就是使用了自动封包，可以解析为
Integer num = new Integer(10);
```
但是需要注意的是，自动打包规范要求 boolean、byte、char类型数据 <=127、int和short数据介于 -128~127 之间的包装到固定的对象中，所以会出现这种情况，请大家一定注意：
```java
Integer a = 100;
Integer b = 100;
if (a == b)    // 成立
//但是
Integer a = 1000;
Integer b = 1000;
if (a == b)    // 不成立
```
小练习
-----
1.Consider writing a program that reads the lines of any text file into a sequential list of lines. Which of the following is a good reason to implement the list with an ArrayList of String objects rather than an array of String objects?

(A) The get and set methods of ArrayList are more convenient than the [] notation for arrays.

(B) The size method of ArrayList provides instant access to the length of the list.

(C) An ArrayList can contain objects of any type, which leads to greater generality.

(D) If any particular text file is unexpectedly long,the ArrayList will automatically be resized. The array, by contrast, may go out of bounds.

(E) The String methods are easier to use with an ArrayList than with an array.

2.Here is a method that locates the Student with the highest idNum:
```java
/**Precondition: ArraystuArrofStudentisinitialized. * @return Student with highest idNum
*/
public static Student locate(Student[] stuArr) {
/* method body */
}
```
Which of the following could replace method body so that the method works as intended?

I
```java
int
for (Student student : stuArr)
max = stuArr[0].getIdNum();
if (student.getIdNum() > max) {
  max = student.getIdNum();
  return student;
}
return stuArr[0];
```
II
```java
Student highestSoFar = stuArr[0];
int max = stuArr[0].getIdNum();
for (Student student : stuArr)
if(student.getIdNum() > max) {
  max = student.getIdNum();
  highestSoFar = student;
}
return highestSoFar;
```
III
```java
int maxPos = 0;
for(int i = 1; i < stuArr.length; i++)
if(stuArr[i].getIdNum() > stuArr[maxPos].getIdNum()) maxPos = i;
return stuArr[maxPos];
```
(A) I only

(B) II only

(C) III only

(D) I and III only

(E) II and III only
