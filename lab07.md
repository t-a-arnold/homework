## *任务1*
## ***（2）***
## *****1.*****
IR：（Instructinon register）指令寄存器：存放当前正在执行的指令
PC：（program counter）      程序计数器：记录当前正在执行的指令
## *****2.*****
ACC：（accumulator）         累加器：存放指令的操作数或运算结果
## *****3.*****
Fetch the next instruction：    从RAM中获取指令到IR：   lod #3  
Decode the instruction：        DECODER将IR中的指令分成LOD和#3两部分
Get data if needed：            将3存放到ALU中
Execute the instruction：       将3存放到ACC中
## *****4.*****
Fetch the next instruction：    从RAM中获取指令到IR：   ADD W  
Decode the instruction：        DECODER将IR中指令分成LOD和W两部分
Get data if needed：            将W中的数取到ALU中
Execute the instruction：       将W和3相加，并把值存在ACC中
## *****5.*****
两者在Get data if needed一步有差异，前者从指令中取数，后者在RAM中取
## ***（3）***
## *****1.*****
00010100 00000111   :0001表示最后面八位二进制所表示的是数而不是地址，0100表示操作为LOD，00000111表示十进制下的7
## *****2.*****
第一位为1表示是数据，为0表示是指令
## *****3.*****
8
## *****4.*****
>#include<stdio.h>

>int main()

>{

>   int w=3,x=7;

>   int y=x+w;

>}
## *任务2*
## ***（1）***
## *****1.*****
将x的值一直减一直到为1
## *****2.*****
>#include<stdio.h>

>int main()

>{

>   int x=3;

>   while(x>1)

>       x--;

>}
## ***（2）***
## *****1.*****
>#include<stdio.h>

>int main()

>{

>   int y=0,x=1;;

>   while(x<=10)

>   {    

>       y+=x;

>       x++;

>   }

>}
## *****2.*****
00  LOD #0
02  STO Y
04  LOD #10
06  STO X
08  JMZ 22
10  ADD Y
12  STO Y
14  LOD X  
16  SUB #1
18  STO X
20  JMP 08
22  HLT


## *****3.*****
区别：机器语言不易懂
联系：具有同样的结构，都是通过指令对数据的操作