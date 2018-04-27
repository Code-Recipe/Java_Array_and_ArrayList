<notice>教程读者请不要直接阅读本文件，因为诸多功能在此无法正常使用，请移步至[程谱 coderecipe.cn](https://coderecipe.cn/learn/4)学习完整教程。如果您喜欢我们的教程，请在右上角给我们一个“Star”，谢谢您的支持！</notice>
二维数组
======

欢迎来到程谱社区！😁 我们是一群留学生，致力于搭建一个系统而又不枯燥的零基础入门编程学习平台。希望大家能多多支持我们，如果发现我们的不足之处也欢迎联系我们~

这是程谱Java教程数组与数组列表单元的的第3章，主要为大家讲解二维数组。请大家进行学习！

定义二维数组
-----
二维数组，顾名思义，就是具有两个维度的数组。我们之前学习的一维数组中，数组中的元素只有唯一一个序号index来表示它的位置。而在二维数组中，有了行和列的区别。只有知道了行和列，才可以确定一个元素的位置。因此，二维数组经常用来代表矩阵等数据结构。大家也可以用数学中学习的矩阵和二维数组进行类比，在脑中形象化这一对象。

了解了什么是二维数组后，我们就来尝试定义一个新的二维数组。如下代码可以创建一个空的二维数组：
```java
E[][] name = new E[a][b];
```
其中，E是类型名，a、b是数组的长度。

用二维数组来表示矩阵
-----
由于二维数组和矩阵之间紧密的关系，我们经常使用二维数组来代表矩阵。比如说，如果我们想要用二维数组输出如下图形：

* 1 0 0 0
* 0 2 0 0
* 0 0 3 0
* 0 0 0 4

代码应该如下所示：

e.g.
```java
//创建一个二维数组
int arr[][] = new int[4][4];
//初始化二维数组
arr[0][0] = 1;
arr[1][1] = 2;
arr[2][2] = 3;
arr[3][3] = 4;
//输出二维数组
for(int i=0; i<4; i++){
  for(int j=0; j<4; j++){
    System.out.print(arr[i][j]+" ");    
  }
    System.out.println();   
}
```

处理二维数组
-----
其实，看完了上面那个实例，相信大家也已经对二维数组的处理有所了解了。没错，二维数组访问的方法就是这样的：
```java
name[r][c];
//r代表row行，c代表column列。
```
而遍历二维数组的方法，也在上一个实例中有所展示了。其实和一维数组差不多，只需要两个循环相互嵌套即可。
为了方便大家理解，我们这里再举一个遍历二维数组的例子。这个例子会把一个10x10的二维数组n的所有数值改为100。

e.g.
```java
Integer[][] n = new Integer[10][10];
for(int i = 0; i < n.length; i++){
  for(int j = 0;j < n.length; j++){
    n[i][j] = 100;
  }
}
```

小练习
-----
1.Consider a class that has this private instance variable:
```java
private int[][] mat;
```
The class has the following method, alter.
```java
public void alter(int c) {
  for (int i = 0; i < mat.length; i++)
    for (int j = c + 1; j < mat[0].length; j++)
      mat[i][j-1] = mat[i][j];
}
```
If a 3×4 matrixmatis
* 1357
* 2468
* 3579

then alter(1) will change mat to

(A)
* 1577
* 2688
* 3799

(B)
* 157
* 268
* 379

(C)
* 1357
* 3579

(D)
* 1357
* 3579
* 3579

(E)
* 1777
* 2888
* 3999

下面的内容要按一下才会显示：
<cr type="hidden"><notice>隐藏内容功能在此无法正常显示，请移步至[程谱 coderecipe.cn](https://coderecipe.cn/learn/4)查看。</notice>A</cr>
2.Consider the following method that will alter the matrix mat:
```
/** @param mat the initialized matrix * @param row the row number
*/
public static void matStuff(int[][] mat, int row)
{
  int numCols = mat[0].length;
  for (int col = 0; col < numCols; col++)
    mat[row][col] = row;
```
Suppose mat is originally
* 1490
* 2786
* 5143

After the method call matStuff(mat,2), matrix mat will be

(A)
* 1490
* 2786
* 2222

(B)
* 1490
* 2222
* 5143

(C)
* 2222
* 2222
* 2222

(D)
* 1420
* 2726
* 5123

(E)
* 1290
* 2286
* 5243

下面的内容要按一下才会显示：
<cr type="hidden"><notice>隐藏内容功能在此无法正常显示，请移步至[程谱 coderecipe.cn](https://coderecipe.cn/learn/4)查看。</notice>A</cr>
