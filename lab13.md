## *贪吃蛇实验报告*

## *思路：*

## ***1.初始化***

>	char map[12][13]={
>		"************",  
>		"*XXXXH     *",  
>		"*          *",  
>		"*          *",  
>		"*          *",  
>		"*     $    *",  
>		"*          *",  
>		"*          *",  
>		"*          *",  
>		"*          *",  
>		"*          *",  
>		"************"}; 
>
>	char map_1[12][13]={
>		"************",  
>		"*          *",  
>		"*          *",  
>		"*  Game    *",  
>		"*    Over  *",  
>		"*      !!! *",  
>		"*          *",  
>		"*          *",  
>		"*          *",  
>		"*          *",  
>		"*          *",  
>		"************"}; 

>	char step;//存放每步 

>	int body[2][150]={{1,1,1,1,1},{5,4,3,2,1}};//存放整条蛇的坐标 

>	int longth=5;//存放蛇的长度 

>	int award[2]={5,6};//奖品坐标 

>	int newhead[2];//存放每次的新头坐标 

>	char nhchar;//新头坐标上的char值 

>	pr(map);

## ***2.进入循环***

>	while(1)

>	{

>		//输入移动方式，并计算出新头的坐标放在newhead中 

>		step=getchar();

>		switch (step)

>		{

>			case 'w':

>				newhead[0]=body[0][0]-1;

>				newhead[1]=body[1][0];

>				break;


>			case 's':

>				newhead[0]=body[0][0]+1;

>				newhead[1]=body[1][0];

>				break;

>			case 'a':

>				newhead[0]=body[0][0];

>				newhead[1]=body[1][0]-1;

>				break;

>			case 'd':

>				newhead[0]=body[0][0];

>				newhead[1]=body[1][0]+1;

>				break;

>		}

>		nhchar=map[newhead[0]][newhead[1]];

>		//分情况进入不同函数中 

>		if((nhchar=='X')||(nhchar=='*'))//撞墙，吃自己，或者90度折返 
		
>       {
		
 >       	pr(map_1);
		
>        	break;
		
>        }
		
>       if(nhchar==' ')//没有特殊情况 
		
>      	move(map,newhead,body,longth);
		
>     if(nhchar=='$')//吃到奖品 
		
>        {
		
>        	ate(map,newhead,body,&longth);
		
>        	newa(map,100-longth);
		
>        }
		
>        pr(map);

>	} 

>} 


## ***3.自顶而下，编写pr,ate,newa,move程序***

## *****void pr()*****

>void pr(char map[][13])

>{

>	//输出表格 

>	for(int i=0;i<=11;i++)

>	{

>		for(int j=0;j<=12;j++)

>			printf("%c",map[i][j]);

>		printf("\n");

>	}

>}

## *****void move()*****

>void move(char map[][13],int newhead[],int body[][150],int longth)

>{

>	//(map中)头变'X'，新头变'H'，尾处变空格		(body中)从旧头，到旧尾前一个，全部后退一格，头坐标变新头

>	map[newhead[0]][newhead[1]]='H';

>	map[body[0][0]][body[1][0]]='X';

>	map[body[0][longth-1]][body[1][longth-1]]=' ';

>	for(int i=longth-2;i>=0;i--)

>	{

>		body[0][i+1]=body[0][i];

>		body[1][i+1]=body[1][i];

>	}

>	body[0][0]=newhead[0];

>	body[1][0]=newhead[1];

>}

## *****void ate()*****

>void ate(char map[][13],int newhead[],int body[][150],int *longth)

>{

>	//(map中)头变'X'，食物变'H'，	（数组body）longth++，数据全后移一位，新头坐标变表头 

>	map[body[0][0]][body[1][0]]='X';

>	map[newhead[0]][newhead[1]]='H';

>	for(int i=*longth-1;i>=0;i--)

>	{

>		body[0][i+1]=body[0][i];

>		body[1][i+1]=body[1][i];

>	}

>	(*longth)++;

>	body[0][0]=newhead[0];

>	body[1][0]=newhead[1];

>}

## *****void newa()*****

>void newa(char map[][13],int a)

>{

>	//随机生成1~（100-longth）内的数k，从左到右，从上到下，找第k个空格变成$ 

>	int num=0;

>	int s=1;

>	int t=rand()%a+1;

>	for(int i=1;i<=10;i++) 

>	{

>		for(int j=1;j<=10;j++)

>		{

>			if(s==0)

>				continue;

>			if(map[i][j]==' ')

>			{

>				num++;

>				if(num==t)

>				{

>					map[i][j]='$';

>					s=0;

>				}

>			}

>		}

>	}

>}

## *最终效果： *

![](https://github.com/t-a-arnold/swi-homework/blob/gh-pages/images/12.11-1.gif?raw=true)