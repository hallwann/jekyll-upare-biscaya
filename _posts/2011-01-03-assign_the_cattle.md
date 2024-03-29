---
author: upare
layout: post-blog
title: 分牛
thumbnail:
category:
  - blog
  - brainstorm
tag:
  - logic
description: 
---
有个农民，一生养了不少牛。去世前留下遗嘱：

 “牛的总数的一半加半头给儿子，剩下牛的一半加半头给妻子，再剩下的一半加半头给女儿，再剩下的一半加半头宰杀犒劳帮忙的乡亲。”

农民去世后，他们按遗嘱分完后恰好一头不剩。他们各分了多少头牛？

【分析】

这类题最好用倒推法求解，从问题最后的结果开始，一步一步往前推，直到求出问题的答案。有些问题用此法解起来很简单，如用其他方法则很难实现。

例如本题，根据最后一头牛也没剩这个条件，可以肯定最后杀了一头牛。按遗嘱要求可知：

（1）最后的一头是分给女儿后的一半加半头，可知分给女儿前一共有x，女儿分到x/2 + 0.5，剩下x - （x / 2 + 0.5） = 1，可解得x = 3头，即分给女儿前总共3头，可知女儿分得2头。

 （2）假设分给妻子前剩余x头，妻子分得x/2 + 0.5，剩下x - （x / 2 + 0.5），根据（1）可知分给妻子后剩余3头，解得x = 7，即分给妻子前共有7头牛。可知妻子分得4头牛。

（3）假设分给儿子前剩余x头，儿子分得x/2 + 0.5，剩下x - （x / 2 + 0.5），根据（2）可知分给儿子后剩余7头，解得x = 15，即分给儿子前共有15头牛。可知儿子分得8头牛。

【答案】

儿子8头，妻子4头，女儿2头，乡亲1头。

注：倒推法，从问题最后的结果开始，一步一步往前推，直到求出问题的答案。有些问题用此法解起来很简单，如用其他方法则很难。