# **色彩表示技术科普博客**
目前使用最广泛的（适用于人眼）的色彩表示法当然是RGB方法了，至于这个方法是什么首先我们看下百度是怎么定义的
### **RGB的定义**
RGB色彩模式是工业界的一种颜色标准，是通过对红(R)、绿(G)、蓝(B)三个颜色通道的变化以及它们相互之间的叠加来得到各式各样的颜色的，RGB即是代表红、绿、蓝三个通道的颜色，这个标准几乎包括了人类视力所能感知的所有颜色，是目前运用最广的颜色系统之一。

### ****
或许你还看不懂，那么上个图就更好了

![](https://upload.wikimedia.org/wikipedia/commons/thumb/a/a6/%E9%A1%8F%E8%89%B2%E5%8A%A0%E6%B3%95.svg/330px-%E9%A1%8F%E8%89%B2%E5%8A%A0%E6%B3%95.svg.png)

就像图中所表示的那样，红绿蓝两两混合组成了黄紫青，全部加在一起变成了白，当然，色彩斑斓的世界不止这几种颜色，其他的颜色又怎么表示呢？
还是看图：

![](https://github.com/t-a-arnold/swi-homework/blob/gh-pages/images/%E5%9B%BElab04-1.png?raw=true)

这么渐变的混合后，各种颜色便表现了出来，可见，三原色确实能表示全部颜色，那么怎么把它数字化呢？

![](https://github.com/t-a-arnold/swi-homework/blob/gh-pages/images/lab04-2.gif?raw=true)

或许你注意到了第三行的奇怪的如#00FF00的编码，它便是每种颜色的编码，比如00FF00便对应绿色。

怎么对应呢？其实应该这样拆分这个编码，即00；FF；00.
每两个组成一个16进制数，第一个00表示红色的量为0，FF表示绿色有255，第二个00表示蓝色的量也是0
因此这编码应该对应纯绿色，事实也的确如此，因此诸如#00FFFF的我们便很快识别出这是青色了，至于更多编码，
还要你有一定美术功底才能一眼看出，当然，简单的16进制数还是要熟悉的。
本期博客就到此为止了，读者是否看懂了呢？