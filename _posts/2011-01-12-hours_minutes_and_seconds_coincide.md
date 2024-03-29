---
author: upare
layout: post-blog
title: 时、分和秒针重合问题
thumbnail:
  - /assets/archives/6a613f12jw1e2d17h013lj.jpg
category:
  - blog
  - brainstorm
tag:
  - logic
description: 
---
24小时之中，时、分和秒针重合时候有几次？都分别是什么时间？

【分析】

（1）1小时内，时针和分针只会重合一次，因为分针会移动一周，而时针只会移动5格，期间两指针能且只能重合一次。

（2）因为时针每12分钟才移动一格，所以每次移动后，会有11分59秒的时间来等待分针来汇合；同样，分针每60秒移动一格，每次移动后，会有59秒的时间来等待秒针来汇合。

（3）一天有24小时，但每小时，时针超前分针的格数不同，1点超前5格，2点超前10格，……。问题出来了，以每个整点为起点，需要计算时针需要移动多少格（分钟）才能与时针重合？

列方程：H=S+H/12；

其中：H：分针需要移动的格数（分钟）；S：时针超前分针的格数；注意H/12一定是整除，不需要小数。

解得：H=12×S/11，这里除法依旧是整除。

知道了需要多久分针能与时针汇合，剩下秒针就好办了，分针不动，静静的等待秒针H秒就OK了。

（4）解法：循环24（0～23）小时，计算出每个整点，时针超前分针多少格数，然后计算与时针重合后需要的分钟数，再加上同样数目的秒数，就能够计算出具体的时间了。

编程输出三针重合的时间，代码如下（以C语言为例）：

`#includevoid main(){for(int s = 0; s < 24; s += 1){for(int f = 0; f < 60; f += 1){if(f==( int )( ( float ) f / 12.0 ) + (s % 12 * 5 ) ){printf("%d : %d :%d ", s, f, f);}}}}`

输出结果：

`00 : 00 :0001 : 05 :0502 : 10 :1003 : 16 :1604 : 21 :2105 : 27 :2706 : 32 :3207 : 38 :3808 : 43 :4309 : 49 :4910 : 54 :5411 : 59 :5912 : 00 :0013 : 05 :0514 : 10 :1015 : 16 :1616 : 21 :2117 : 27 :2718 : 32 :3219 : 38 :3820 : 43 :4321 : 49 :4922 : 54 :5423 : 59 :59`

其中11 : 59 :59和12 : 00 :00及23 : 59 :59和00 : 00 :00是重复的，所以只有22次。

当然这里是粗略的计算，即秒针划过分针就算，精确度要低，误差在一秒之内，通过上面的结果也可以看出，分针的数值和秒针的数值都是一样的，而实际则不然，例如01 : 05 :05，秒针肯定准确的指向了5，但是分值已经偏离了5，只是秒针要在分针上划过，所以也可算作重合，如果，精确的计算，即分针、秒针和时针都精确的指向了时钟表面的某一刻度时的答案如下：

当秒针 != 0 时，可以肯定的是分针不会指向钟面上任何一个刻度(也就是说分针是指向刻度间的空白地方)。同理:

当分针 !=0 时，可以肯定的是时针不会指向钟面上的任何一个刻度(也就是说时针是指向刻度间的空白地方)

所以至少有一个推断是正常的：除了00：00：00 之外。三针重合的那个时刻肯定不是整数秒，也就是说，在任何一分钟内，分针与秒针重合的那一瞬间肯定是指向刻度间的空白处。要满足这些条件，会解出一些不存在的时间(无限位小数的集合)，所以，只有00：00：00 三个指针会完全重合。

虽然两种答案迥然不同，但是这两者却同时体现了一种精神，就是要求面试者要有较强的分析和观察能力。可以把两种不同的结果归结于两家时钟的区别，而不是思想的区别，第一家的时钟在01 : 05 :05如图1所示。而第二家的时钟如图2所示。

![](/assets/archives/6a613f12jw1e2d17h013lj.jpg)

图1 粗制的钟表

![](/assets/archives/6a613f12jw1e2d196r0a1j.jpg)

图2 精细的钟表

要理解其中一种解法，不要再去斤斤计较谁家的时钟是什么样子，因为现在的产品种类繁多，不要在计较这种东西上浪费时间，面试时只要给出正确答案，和解析过程，而不用细究时钟的工作原理。

【答案】

（1）粗略计算时22次，时间为：

00 : 00 :00

01 : 05 :05

02 : 10 :10

03 : 16 :16

04 : 21 :21

05 : 27 :27

06 : 32 :32

07 : 38 :38

08 : 43 :43

09 : 49 :49

10 : 54 :54

12 : 00 :00

13 : 05 :05

14 : 10 :10

15 : 16 :16

16 : 21 :21

17 : 27 :27

18 : 32 :32

19 : 38 :38

20 : 43 :43

21 : 49 :49

22 : 54 :54

（2）精细计算只有两次，一次是00:00:00，另一次是12:00:00。