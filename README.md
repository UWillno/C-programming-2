#   程序设计基础 上机2 控制结构程序设计  

一、实验目的及要求

1、熟悉CodeBlocks集成环境，掌握在该环境下进行程序编写和调试的步骤和方法。

2、掌握C语言中基本数据类型的使用方法。

3、掌握C语言中定义变量及对它们进行赋值的方法。

4、掌握C语言的各种类型的运算符、表达式的正确使用方法。

5、掌握基本的输入/输出函数的使用方法。

二、实验设备（环境）及要求

1、CodeBlocks集成开发环境

2、PTA程序设计类实验辅助教学平台www.pintia.cn

三、实验内容与步骤  

1、分段函数  

（1）题目    

编程计算下面的分段函数：

y=*e**x*−1 (0<x<1)

y=|x|+2 (3≤x≤4)

y=*s**in*(*x*2) (当x取其他值时)

（2）源代码  

```c
#include<stdio.h>
#include<math.h>

int main(void)
{
	double x,y;
	scanf("%lf",&x);
	if (x>0&&x<1)
	{
		y = exp(sqrt(x)) - 1;
	}
	else if (x>=3&&x<=4)
	{
		y = fabs(x) + 2;
	}
	else
	{
		y = sin(x * x);
	}
	printf("%lf", y);
	return 0;
}
```

（3）运行结果截屏  

2、判断闰年  

（1）题目

输入一个年份，判断其是否为闰年，若是闰年输出“yes”的信息，否则输出“no”的信息。

判断闰年的标准：能被4整除但不能被100整除，或者能被400整除的年份是闰年。

（2）源代码 

```C
#include<stdio.h>

int main(void)
{
	int a = 0;
	scanf("%d", &a);
	if (a%400==0||a%4==0&&a%100!=0)
	{
		printf("yes");
	}
	else
	{
		printf("no");
	}
	return 0;
}
```

（3）运行结果截屏  

3、统计学生成绩  

（1）题目

本题要求编写程序读入N个学生的百分制成绩，统计五分制成绩的分布。百分制成绩到五分制成绩的转换规则：

- 大于等于90分为A；
- 小于90且大于等于80为B；
- 小于80且大于等于70为C；
- 小于70且大于等于60为D；
- 小于60为E。

（2）源代码

```C
#include<stdio.h>

int main(void)
{
	int N, A = 0, B = 0, C = 0, D = 0, E = 0;
	scanf("%d", &N);
	int score;
	for (int i = 1; i <=N; i++)
	{
		scanf("%d", &score);
		if (score>=90)
		{
			A++;
		}
		else if (score>=80)
		{
			B++;
		}
		else if (score>=70)
		{
			C++;
		}
		else if (score>=60)
		{
			D++;
		}
		else
		{
			E++;
		}
	}
	printf("%d %d %d %d %d", A, B, C, D, E);
	return 0;
}
```

（3）运行结果截屏  

 4、身高预测  

（1）题目  

身高预测
每个做父母的都关心自己孩子成人后的身高，有关生理卫生知识与数理统计分析表明，影响小孩成人后的身高的因素包括遗传、饮食习惯与体育锻炼等。小孩成人后的身高与其父母的身高和自身的性别密切相关。
设faHeight为其父身高，moHeight为其母身高，身高(单位为cm)预测公式为：
男性成人时身高=(faHeight + moHeight)×0.54
女性成人时身高=(faHeight×0.923 + moHeight)/2
此外，如果喜爱体育锻炼，那么可增加身高2%；如果有良好的卫生饮食习惯，那么可增加身高1.5%。
编程从键盘输入用户的性别(用字符型变量sex存储，输入字符F表示女性，输入字符M表示男性)、是否喜爱体育锻炼(用字符型变量sports存储，输入字符Y表示喜爱，输入字符N表示不喜爱)、是否有良好的饮食习惯等条件(用字符型变量diet存储，输入字符Y表示良好，输入字符N表示不好)、父母身高(用实型变量存储，faHeight为其父身高，moHeight为其母身高)、，利用给定公式和身高预测方法对身高进行预测。

（2）源代码   

```C
#include<stdio.h>

int main(void)
{
	char sex,sport,eat;
	float father, mother,kid;
	scanf("%c,%c,%c,%f,%f", &sex, &sport, &eat, &father, &mother);
	if (sex=='M')
	{
		kid = (mother + father) * 0.54;
	}
	else
	{
		kid = (father * 0.923 + mother) / 2;
	}
	if (sport=='Y')
	{
		kid *= 1.02;
	}
	if (eat=='Y')
	{
		kid *= 1.015;
	}
	printf("%.1f", kid);
	return 0;
}
```

（3）运行结果截屏 

5、求老师和夫人的年龄  

（1）题目

一位同学问老师和老师夫人的年龄是多少，老师说：“我年龄的平方加上我夫人的年龄恰好等于1053，而我夫人年龄的平方加上我的年龄等于873。”试编程计算老师和其夫人的年龄。

（2）源代码

```c
#include<stdio.h>

int main(void)
{	
	int a, b;
	for(a=1; a < 100; a++)
	{
		for (b=1; b < 100; b++)
		{
			if ((a * a + b == 1053) && (b * b + a == 873))
			{
				goto flag;
			}
		}
	}
flag:
	printf("%d %d", a, b);
	return 0;
}
```

（3）运行结果截屏 

四、收获与体会

太简单了，不如玩原神。

五、额外

看清楚上机题目是不是一致的，不保证正确。  
