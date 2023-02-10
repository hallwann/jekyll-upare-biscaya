---
author: upare
layout: post-blog
title: 布娃娃换装
thumbnail:
category:
  - blog
  - brainstorm
tag:
  - logic
description: 
---
晓芳有4个布娃娃，分别取名为玲玲、丽丽、宝宝和娜娜。布娃娃们都穿着裙子。有一天，晓芳把布娃娃们的上衣和裙子在它们中间互相调换了一下。

成为以下状况：

1、至少有一个娃娃穿着自己的上衣，至少有一个娃娃穿着自己的裙子。

2、穿着“穿玲玲上衣的娃娃”的裙子是宝宝。

3、穿着“穿丽丽上衣的娃娃”的裙子是玲玲。

4、穿着“穿娜娜裙子的娃娃”的裙子是丽丽。

那么，换穿之后，每个布娃娃分别穿着谁的上衣和裙子呢？

【分析】

假设条件4的“穿娜娜裙子的娃娃”的是娜娜的话，就成了“穿娜娜裙子的娃娃是娜娜”并且“穿娜娜裙子的娃娃是丽丽”，这就相互矛盾了。假设“穿娜娜裙子的娃娃”的是丽丽也是同样。所以那个娃娃应该是玲玲或者宝宝。

根据条件4，“穿娜娜裙子的娃娃”的是宝宝或者玲玲。所以，由条件1和4可知有以下几种可能性：

（1）

<table><tbody><tr><td></td><td>玲玲</td><td>丽丽</td><td>宝宝</td><td>娜娜</td></tr><tr><td>衣服</td><td>A</td><td>B</td><td>C</td><td>D</td></tr><tr><td>裙子</td><td>娜娜</td><td>玲玲</td><td>宝宝</td><td>丽丽</td></tr></tbody></table>

（2）

<table><tbody><tr><td></td><td>玲玲</td><td>丽丽</td><td>宝宝</td><td>娜娜</td></tr><tr><td>衣服</td><td>E</td><td>F</td><td>G</td><td>H</td></tr><tr><td>裙子</td><td>玲玲</td><td>宝宝</td><td>娜娜</td><td>丽丽</td></tr></tbody></table>

在假设（1）的情况下，根据2，C=玲玲、根据3，D=丽丽，不过，这样的话，穿自己衣服的娃娃就不存在了，所以这样的情况是不可能的。

在假设（2）的情况下，根据2，H是玲玲、根据3，E是丽丽，这样的话，穿自己衣服的娃娃就只能是G，是宝宝，所以剩下的F是娜娜。

【答案】

<table><tbody><tr><td></td><td>上衣</td><td>裙子</td></tr><tr><td>玲玲</td><td>丽丽</td><td>自己的</td></tr><tr><td>丽丽</td><td>娜娜</td><td>宝宝</td></tr><tr><td>宝宝</td><td>自己的</td><td>娜娜</td></tr><tr><td>娜娜</td><td>玲玲</td><td>丽丽</td></tr></tbody></table>