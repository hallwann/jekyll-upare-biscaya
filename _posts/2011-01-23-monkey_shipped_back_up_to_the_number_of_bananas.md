---
author: upare
layout: post-blog
title: 小猴最多能运回多少根香蕉
thumbnail:
  - /assets/archives/6a613f12tw1e2ut8jywc5j.jpg
category:
  - blog
  - brainstorm
tag:
  - logic
description: 
---
一个小猴子边上有100根香蕉，它要走过50米才能到家，每次它最多搬50根香蕉，它每走1米就要吃掉一根，请问它最多能把多少根香蕉搬到家。

提示：他可以把香蕉放下往返的走，但是必须保证它每走一米都能有香蕉吃。

【分析】

小猴每次最多能够带50根香蕉，所以第一次要留在原地50根香蕉，假设第一次走n米后，再带n根香蕉返回，剩余的50-2 n根香蕉放在距家50-n米处，如图1所示。

![](/assets/archives/6a613f12tw1e2ut9cq7bqj.jpg)

图1 小猴走出n米后返回

根据上图可以分析得出，2n

![](/assets/archives/6a613f12tw1e2ut8jywc5j.jpg)

图2 小猴把所有香蕉搬到50-n米处

由原题可知小猴每次走出一段在返回后都要多吃几根香蕉，所以要想多搬回香蕉的办法就是尽量的少返回，而返回的原因是一次最多能够搬50根，当香蕉多于50根的时候一次不能搬尽，要返回再搬，所以第一次走出n米，搬回剩余的50根再返回距家50-n米处后，剩余100-3n根，根据上面的分析，100-3n要小于50。由于每次返回都要多消耗2n根，所以n要尽量小，即剩余的根数要尽量大且小于50。如下：

100-3n

得：n

所以第一次应走出17米后返回，剩余100 – 17\*3 = 49根，此时据家还有33米，所以到家最多能剩余16根香蕉。

【答案】

最多能剩余16根香蕉。

注意：找到恰当的返回点是本题的关键。一定要注意本题找这个折回点的具体方法和思路。