# ？

直方图

# 类

## MAT

## Scalar

存储像素点值，

```
Scalar(255,255,255);
```





## Rect



## Point





# 函数

### cvtColor

转换色彩空间



#inRange



读取矩阵行列

```c++
Range()；
```

读取区域

```c++
Rect();
```



Mat 类提供了多种方便的方法来选择图像的局部区域。使用这些方法时需要 注意，这些方法并不进行内存的复制操作。如果将局部区域赋值给新的 Mat 对 象，新对象与原始对象共用相同的数据区域，不新申请内存，因此这些方法的执 行速度都比较快



读取视频类

```c++
VideoCapture ..;
```



读取一帧

```c++
VideoCapture cap;
Mat src;
cap >> src;
```



取对角线

```c++
Mat src.diag(int);
```



获取迭代器

```c++
Mat src;

CVIterector it = src.begin<type>();
```



Mat 时一个矩阵类型，可以用 << 输出,操作图像的同时是在操纵一些像素点。

Mat 总是公用同一个矩阵的数据。

