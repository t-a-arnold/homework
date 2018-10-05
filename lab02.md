# **制作一个小游戏**

## **任务名:**
>做一个2d射击游戏

不说话，先给上最终最终效果GIF：

![](https://github.com/t-a-arnold/swi-homework/blob/gh-pages/images/gif1.gif?raw=true)


为此，我们先要下载一个制作游戏的平台：contrust2
下载网站为https://www.scirra.com/construct2

要参考官方的安装指南，而该工具仅是本课程的一个教学案例，free的版本已满足教学的要求，除非特别喜欢，请不要购买，不建议下载任何“解密版本”，可能是病毒。

下载安装完成后，启动contrust2

## **1.新建一个项目**
在页面的左上角如GIF般操作：
![](https://github.com/t-a-arnold/swi-homework/blob/gh-pages/images/gif2.gif?raw=true)


## **2.基本画面设计**
首先你需要一些图片作为资料：
1.玩家：![](https://github.com/t-a-arnold/swi-homework/blob/gh-pages/images/%E7%8E%A9%E5%AE%B6.png?raw=true)
2.爆炸：![](https://github.com/t-a-arnold/swi-homework/blob/gh-pages/images/%E7%88%86%E7%82%B8.png?raw=true)
3.怪物：![](https://github.com/t-a-arnold/swi-homework/blob/gh-pages/images/%E6%80%AA%E7%89%A9.png?raw=true)
4.子弹：![](https://github.com/t-a-arnold/swi-homework/blob/gh-pages/images/%E5%AD%90%E5%BC%B9.png?raw=true)
5.背景：![](https://github.com/t-a-arnold/swi-homework/blob/gh-pages/images/bg.png?raw=true)

把他们保存到本地，然后先把‘背景’如GIF中拖拽入画面中：
![](https://github.com/t-a-arnold/swi-homework/blob/gh-pages/images/GIF3.gif?raw=true)

然后把‘背景’调整大小直至铺满画布，你可以在上方工具栏中选取‘view’中‘zoom out’以获得更佳视角

## **3.管理图层**
contrust2中的图层功能使得一个个元素得以一层层地分开不至于混淆，‘背景’当然应该在最下层，要把其他对象如‘玩家’插入到‘背景’之“上”
该怎样做呢？在界面右侧如此操作
![](https://github.com/t-a-arnold/swi-homework/blob/gh-pages/images/gif4.gif?raw=true)
最后记得重新点下‘上层’，以使之后的操作在‘上层’进行。

然后拖拽‘玩家’等4个对象到画布，就可把他们弄到上层去了
你的最终效果应如此：
![](https://github.com/t-a-arnold/swi-homework/blob/gh-pages/images/%E5%9B%BE2.png?raw=true)

## **4.设计行为与事件**
光有对象可不够，还要让他们动起来(拥有‘行为’)和相互作用(拥有‘事件’)


### **在下面的操作中我们将学习‘对象行为’的添加**
使‘玩家’根据键盘的上下左右键运动，即添加'8direction'行为
![](https://github.com/t-a-arnold/swi-homework/blob/gh-pages/images/gif5.gif?raw=true)
然后使屏幕跟随‘玩家’，即添加‘scroll to’行为
![](https://github.com/t-a-arnold/swi-homework/blob/gh-pages/images/gif6.gif?raw=true)
然后像上面一样添加Bullet movement 和 Destroy outside layout到‘子弹’
添加Bullet movement到‘怪物’，Fade到‘爆炸’

然后如果点红圈内的按钮开始游戏
![](https://github.com/t-a-arnold/swi-homework/blob/gh-pages/images/%E5%9B%BE3.png?raw=true)
你将看到怪物太快而且爆炸消失得太慢，我们调整一下
![](https://github.com/t-a-arnold/swi-homework/blob/gh-pages/images/gif7.gif?raw=true)

### **然后添加第一个事件**
点击红圈中‘event sheet 1’以进入触发的设计页
![](https://github.com/t-a-arnold/swi-homework/blob/gh-pages/images/%E5%9B%BE1.png?raw=true)
事件由条件组成，测试是否满足某些条件，例如“空格键是否已关闭？”。如果满足所有这些条件，则事件的所有操作都会运行，
例如“创建项目符号对象”。运行后，任何子事件也会运行 - 然后可以测试更多条件，然后运行更多操作，然后运行更多子事件，
等等。使用此系统，我们可以为我们的游戏和应用程序构建复杂的功能。但是，我们不需要本教程中的子事件。

让我们再说一遍。简而言之，事件基本上如下所示：

是否符合所有条件？
---> 是：运行所有事件的动作。
---> 否：转到下一个事件（不包括任何子事件）。

这有点过于简单了。Construct 2提供了许多事件功能，可以涵盖您可能需要执行的许多不同操作。但是，就目前而言，这是一个思考它的好方法。

我们想让玩家总是看着鼠标。我们完成后会看起来像这样：
![](https://www.scirra.com/images/articles/alwayslookatmouse.png)

我们这样操作：
先添加对象：鼠标
双击画布以添加对象，选择‘mouse’并双击即可
然后添加事件的条件
![](https://github.com/t-a-arnold/swi-homework/blob/gh-pages/images/gif8.gif?raw=true)
然后是事件的操作
![](https://github.com/t-a-arnold/swi-homework/blob/gh-pages/images/gif9.gif?raw=true)


### **然后添加更多事件**
如果每个事件都像以前一样详细描述，那么这将是一个相当长的教程。让我们为下一个事件做一些简短的描述。请记住，添加条件或动作的步骤如下：

1.双击以插入新事件，或单击“ 添加操作”链接以添加操作。
2.双击条件/操作所在的对象
.3。双击所需的条件/操作。
4.输入参数（如果需要）。

从现在开始，事件将被描述为对象，然后是条件/操作，后跟任何参数。例如，我们刚刚插入的事件可以写成：

Add condition 系统 -> Every tick
Add action 玩家 -> Set angle towards position -> X: Mouse.X, Y: Mouse.Y

##### **让‘玩家’开枪**
Condition: Mouse -> On click -> Left clicked (默认)
Action: 玩家-> Spawn another object -> 对于 Object, 选‘子弹’. 对于Layer，选1

##### **使‘怪物’更聪明**
现在，怪物开始时只是向右。让我们让它们变得更有趣。首先，让我们以随机的角度开始它们。
Condition: System -> On start of Layout
Action: 怪物 -> Set angle -> random(360)

当他们离开画布时，他们仍会永远徘徊，再也不会被人看到。让我们把它们留在里面。
我们要做的是当他们离开画布时将他们指回玩家。
这样做有两件事：它们总是留在布局中，如果玩家静止不动，怪物就会出现在他们面前！
Condition: 怪物 -> Is outside layout
Action: 怪物 -> Set angle toward position -> 对于X, 玩家.X - 对于Y, 玩家.Y.

##### **让‘玩家’杀死‘怪物’**
Condition: 子弹 -> On collision with another object -> 怪物.
Action: 怪物 -> Destroy
Action: 子弹 -> Spawn another object -> 爆炸, layer 1
Action: 子弹 -> Destroy

## **享受成果**
我们可以运行游戏玩了，虽然不那么有趣，但是很有成就感——它是我做的！


## **总结**
通过自己根据新手指导做自己的第一个小游戏，我发现游戏的运行就是项目在玩家指挥下运行事件。
可能这个游戏还有很多不足，希望通过今后学习能做出更好的游戏。