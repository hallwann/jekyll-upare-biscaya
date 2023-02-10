---
author: upare
title: 这是张什么牌
thumbnail:
category:
  - blog
  - brainstorm
tag:
  - logic
description: 
---
A先生、B先生、C先生他们知道桌子的抽屉里有16张扑克牌：

红桃：A、Q、4

黑桃：J、8、4、2、7、3

草花：K、Q、5、4、6

方块：A、5

约翰教授从这16张牌中挑出一张牌来，并把这张牌的点数告诉B先生，把这张牌的花色告诉C先生。这时，约翰教授问B先生和C先生：你们能从已知的点数或花色中推知这张牌是什么牌吗？于是，A先生听到如下的对话：

B先生：我不知道这张牌。

C先生：我知道你不知道这张牌。

B先生：现在我知道这张牌了。

C先生：我也知道了。

听罢以上的对话，A先生想了一想之后，就正确地推出这张牌是什么牌。

请问：这张牌是什么牌？

【分析】

（1）首先知道点数的B说不知道是哪张牌说明：点数只可能是不同花色的牌中有重复的A，Q，4，5之中的一个。各点重复情况如下：

A：红桃，方块

Q：红桃，草花

4：红桃，黑桃，草花

5：方块，草花

（2）接着知道花色的C说他知道B不知道哪张牌说明：该花色牌的所有点数应该是取自以上A，Q，4，5中，即该花色的牌不能含有其他点数，否则，B就会知道是哪张牌了。只有红桃和方块的牌满足条件，各点重复情况如下：

A：红桃，方块

Q：红桃，方块

4：红桃，方块

5：方块

（3）此时，通过C的第一句话B确定花色只能是红桃或方块，然后由自己已知的点数B说他现在知道此牌了，参照以上重复情况说明：点数A可排除，因为如果是A则红桃和方块中都有A则B不可能知道哪张牌，所以现在点数只在Q，4，5中，各点重复情况如下：

Q：红桃

4：红桃

5：方块

现在可以用迭代的方法，从B的角度看：

如果B拿的点数是Q，则C可以确定牌是红桃Q；

如果B拿的点数是4，则C可以确定牌是红桃4；

如果B拿的点数是5，则C可以确定牌是方块5；以上三种情况对于在B听完C的第一句话后说出他知道是哪张牌都是成立的，B拿到以上任意点数都可以说我知道了，似乎有多解，但最后C说：我也知道了。

从C的角度来看：牌只可能是红桃或方块，如果花色是红桃则显然通过以上迭代分析知红桃Q，4都满足，那么C显然此时应该是不能确定才对，既然他最后说也知道了答案，那么排除红桃的可能，牌只能是方块5。

【答案】

这张牌是方块5。