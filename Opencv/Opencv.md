# ？

直方图:图像像素分布的统计直方图，将其趋于同等，则为均衡化。

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

###inRange

取某个范围像素，白色显示。

### imread

打开图像文件

flag = -1:8位深度，原通道

flag = 0:8位深度，1通道

flag = 1:8位深度，3通道

flag  = 2:原深度，1通道

flag = 3:原深度，3通道

flag = 4:8位深度，3通道

###Range()

读取矩阵行列

```c++
Range()；
```



###Canny

![image-20200426213157385](G:\Note\Note\Opencv\image-20200426213157385.png)





###Rect

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

#图像预处理

##直方图均衡化

```c++
merge()
```

# 颜色识别

##1.彩色打开

```c++
imread("",3);
```

##2.图像预处理

####直方图均衡化

由于是三通道彩色

要分开均衡化(HSV空间考虑处理V即可)

```c++
vector<Mat> imgSplit;
```

```c++
split(src,imgSplit) 
```

```c++
    equalizeHist(imgHSVsplit[0],imgHSVsplit[0]);
    equalizeHist(imgHSVsplit[1],imgHSVsplit[1]);
    equalizeHist(imgHSVsplit[2],imgHSVsplit[2]);
```

合并

```c++
merge(imgSplit,imgInput);
```

####其它处理

##3.换成HSV模型

```c++
cvtColor(OriginalArray,InputArray,type)
```

## 4.取值范围



## 5.降噪处理



白色

0

180

0

26

234

255



黄色

17

51

0

255

44

255



绿色

52

86

69

255

25

255



蓝色

92

138

76

255

160

255



灰色

0

180

0

255

191









# 阈值处理

阈值：图像分割的标尺；

# 霍夫变换

## 霍夫直线变换：

```c++
HoughLInes(
inputAr//八位灰度
           out)
//输出极坐标。
    //有经验开发者使用
```

```c++
HoughLInesP(
inputAr;//输入矩阵
outPUtAr;//输出矩阵
double rho;//生成极坐标时候的像素扫描步长
double theta;//生成极坐标时候的角度步长，一般取cv_pi/180
int threshold;//阈值/
double minLineLength = 0;//最小直线长度
double maxLineGap = 0;//最大间隔)
    //输出平面坐标(x,y,x1,y2);
```

# 轮廓发现



```
findContours(
inputAr;//输入矩阵
outputArofArs;//轮廓的数组
outputAr;//轮廓=点的集合
int mode,//轮廓返回模式
int method;//发现方法
Point offset = Point()//轮廓像素位移
)
```

![image-20200413220811874](G:\Note\Note\Opencv\image-20200413220811874.png)

```
drawContours(
outputOutputArray ;//输出矩阵
outputArOfAr ;//轮廓的数组，全部轮廓
int contourldx;//轮廓索引
const Scalar & color;//轮廓线条颜色
int lineType;//线的类型；
inputArray ;//输入轮廓，点集合
int max; //
Point ; //
)
```

![image-20200413220918381](G:\Note\Note\Opencv\image-20200413220918381.png)

## 轮廓框出

![image-20200413222201621](G:\Note\Note\Opencv\image-20200413222201621.png)

```
approxPolyDP();
```

![image-20200413222447238](G:\Note\Note\Opencv\image-20200413222447238.png)

```

```

![image-20200413222504898](G:\Note\Note\Opencv\image-20200413222504898.png)

```c++

```

![image-20200413222529445](G:\Note\Note\Opencv\image-20200413222529445.png)

```

```

```

```

![image-20200414001033412](G:\Note\Note\Opencv\image-20200414001033412.png)

```

```

![image-20200414001205900](G:\Note\Note\Opencv\image-20200414001205900.png)

```

```











# 滤波

在图像处理中，尽可能消除图片中的噪声，消除噪声就需要用到滤波，在本次opencv学习中，学习了三个滤波方式。

（1）平均滤波，就是将一个区域内的像素值求和取平均值，然后用这个平均值替换区域中心的像素值。

blur(源Mat对象,目标Mat对象,Size对象,Point对象)//Size对象用来确定区域大小，Point对象如果x,y都是-1则表示更新区域中心的像素。

（2）高斯滤波，也是将一个区域的像素值求取平均值替换区域中心的像素值，但是是加权平均，权重按照二维正态分布。

GaussianBlur(源Mat对象,目标Mat对象,Size对象,x方向正太分布参数,y方向正太分布参数)

（3）中值滤波，之前的两个滤波都有个问题，如果区域中有极端值，很可能影响滤波效果，中值滤波采用区域中的中值来替换，有利于克服椒盐噪声。

medianBlur(源Mat对象,目标Mat对象,int size)//这里的size表示正方形区域的边长

（4）双边滤波，之前的滤波还有个问题，他们都会把轮廓给模糊了，有一些区域之间相差较大的像素，这往往能看出轮廓，所以如果我们给个限制范围，如果两点间的像素值差距大于这个范围就不滤波了，保留图像轮廓

bilateralFilter(源Mat对象,目标Mat对象,int 区域半径,int 限制范围,int space)//space是当区域半径给的是0时，用来计算区域范围的，一般情况下没用，随便给个数就行。





size_t

```

```

line

circe



# 卷积

![image-20200429221003804](G:\Note\Note\Opencv\image-20200429221003804.png)



![image-20200429221321875](G:\Note\Note\Opencv\image-20200429221321875.png)



卷积和叫算子

![image-20200429221726823](G:\Note\Note\Opencv\image-20200429221726823.png)



# 直线斜率





