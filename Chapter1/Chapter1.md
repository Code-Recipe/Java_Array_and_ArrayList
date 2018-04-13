<notice>教程读者请不要直接阅读本文件，因为诸多功能在此无法正常使用，请移步至[程谱 coderecipe.cn](https://coderecipe.cn/learn/1)学习完整教程。如果您喜欢我们的教程，请在右上角给我们一个“Star”，谢谢您的支持！</notice>
Java教程-
======

欢迎来到程谱社区！😁 我们是一群留学生，致力于搭建一个系统而又不枯燥的零基础入门编程学习平台。希望大家能多多支持我们，如果发现我们的不足之处也欢迎联系我们~

这是程谱Java数组与数组列表教程的第1章，主要为大家讲解数组（Array）。请大家进行学习！

数组的定义和数组值的存取
------
我们今天来讲一个Java语言中全新的对象：数组（Array）。

数组就是一个对象，将相同类型的一列类型数据放在这一个对象之中。大家不要被“数组”这个名字蒙蔽，这些数据不一定得是数字，而可以是任何类型的数据。比如说，我们可以把bus,trunk,car等数据全部放进一个叫做vehicle的数组中。

接下来，我们来看一看在Java语言中，如何定义一个数组：

e.g.
```java
double[] data;
```

或

```java
double data[];
```
这两行代码的意义是一样的，意味着我们定义了一个名字叫做data的数组，这个数组的类型为double型（也就是说存储在其中的数据都是double型的）。

在定义了数组之后，我们可以对其初始化，比如说，定义它的长度是15。定义数组长度的代码如下：

e.g.
```java
data = new double[15];
```
当然了，我们也可以在定义数组的同时就赋予它初始化的长度：
```java
double[] data = new double[15];
```
除了在初始化数组时定义它的长度，我们甚至可以在定义和初始化的时候直接往数组里面填数值：

e.g.
```java
int[] data = {1,2,3};
```
如果在初始化时直接往数组里填入了数值，那么这个时候数组的长度就会被自动识别（例如上例中，数组data的长度就已经默认为3），就不需要再写。这种初始化方法叫initializer list。

要是想访问数组内的某个元素（想得知在数组内某个位置的数值），可以使用以下代码（index是从0~数组内元素的数量-1的整数）：
```java
Element1 = arrayName[index];
```
如果想要写入或更改数组的某个元素也可以使用同理的方法：
```java
arrayName[index] = Element1;
```
需要注意的是，index超出范围会出现异常，抛出ArrayIndexOutOfBoundsException。

数组的长度
------
数组的长度是固定的，想要获取数组长度，可以使用以下代码：
```java
arrayName.length
```
TIPS：数组的长度不用()，字符串的长度要加()

e.g.
```java
//String
String str = “CodeRecipe”;
System.out.println(str.length());
//Array
int[] arr = {1,2,3,4,5};
System.out.println(arr.length);
```
说了那么多关于数组的知识和如何使用它的方法，我们来看一个实例来了解它的真正用处吧：

e.g.
```java
int array[] = {1,2,3};
	  for(int i = 0;i < 3;i ++)
        System.out.println("Hello "+array[i]);
```
以上代码运行后输出：
```java
Hello 1
Hello 2
Hello 3
```
为了让大家理解的更清楚一些，我们在这里再举几个更加实际的例子来说明数组究竟有多大的用处。

e.g.

比如说，根据大家在要表示10个学生的身高，我们可以这么做：
```java
double student1Weight = xxx;
double student2Weight = xxx;
…
double student10Weight = xxx;
```
然而，如果有100个学生这个代码就要长到100行了。
使用数组就可以极大地减轻我们的工作量。我们只需要以下一行代码：
```java
double studentWeight[] = {xxx,xxx,….,xxx};
```
当然，如果你认为数组完全可以用多个变量代替，那么你就会发现下面的事情不用数组很难做到：
```java
double studentWeight[] = {xxx,xxx,….,xxx};
for(int i = 0; i < 100;i++){
System.out.println(stndentWeight[i]);
}
```
数组的长度
------
通过我们之前学过的循环方法，我们可以遍历整个数组中的元素：

1.for循环遍历

e.g.
```
for(int i = 0;i<array.length;i++){
//对array[i]操作
}
```
2.for-each循环遍历

e.g.
```
int array[] = {1,2,3};
	    for( int i : array){
	        System.out.println(i);
	    }
```
这样就会把数组中的内容都输出出来。

TIPS:在for-each循环中不能增加或者减少数组的内容，不然可能会导致循环出现问题。
作为参数传递数组
----
Array被当做一种对象Object，他在被传递的时候传递的是Reference而不是值（具体后面会提到），所以Java不会把Array复制一份。传入后修改array的内容会导致原array变量读取出的是修改后的内容。比如下面这个例子：

e.g.
```
//我们这里有一个函数
public static void changeArray(int[] b){
for(int i = 0;i < b.length;i++)
b[i]+=3;
}
//在主函数里
int[] array = {1,2,3,4};
changeArray(array);
System.out.print(“The changed array is”);
for(int n:list) System.out.print(n+” ”);
//System.out.print也是输出用的函数，只是不换行
```
结果会输出
```
The change array is 4,5,6,7
```

小练习
------
1.Which of the following correctly initializes an array arr to contain four elements each with value 0?

I
```java
int[] arr = {0, 0, 0, 0};
```
II
```java
int[] arr = new int[4];
```
III
```java
int[] arr = new int[4];
for (int i = 0; i < arr.length; i++){
	arr[i] = 0;
}
```
(A) I only

(B) III only

(C) I and III only

(D) II and III only

(E) I, II, and III

下面的内容要按一下才会显示：
<cr type="hidden"><notice>隐藏内容功能在此无法正常显示，请移步至[程谱 coderecipe.cn](https://coderecipe.cn/learn/1)查看。</notice>E</cr>

2.Refer to the following codes egment. You may assume that arr is an array of int values.
```java
int sum = arr[0], i = 0; while (i < arr.length) {
i++;
sum += arr[i]; }
```
Which of the following will be the result of executing the segment?

(A) Sum of arr[0], arr[1], ..., arr[arr.length-1] will be stored in sum.

(B) Sum of arr[1], arr[2], ..., arr[arr.length-1] will be stored in sum.

(C) Sum of arr[0], arr[1], ..., arr[arr.length] will be stored in sum.

(D) An infinite loop will occur.

(E) A run-time error will occur.

下面的内容要按一下才会显示：
<cr type="hidden"><notice>隐藏内容功能在此无法正常显示，请移步至[程谱 coderecipe.cn](https://coderecipe.cn/learn/1)查看。</notice>E</cr>
