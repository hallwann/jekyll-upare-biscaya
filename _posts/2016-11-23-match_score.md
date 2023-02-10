---
author: upare
title: 比赛得分
thumbnail:
category:
  - blog
  - brainstorm
tag:
  - logic
description: 
---
三个班的代表队进行N（N≥2）次篮班比赛，每次第一名得A分，第二名得B分，第三名得C分（A、B、C为整数，且A&gt;B&gt;C&gt;0）。现已知这N次比赛中甲班共得20分，乙班共得10分，丙班共得9分，且最后一次乙班得了A分，那么第一次得了B分的是哪个班？

【分析】

N次比赛共得20+10+9=39，39=3?13，所以共进行了3次比赛，每次比赛共得13分，即A+B+C=13。

因为甲班3次比赛共得20分，20?3=6…2，所以A≥7，A，B，C可能组合为7、5、1；7、4、2；8、4、1；8、3、2；9、3、1，考虑到3次比赛得20分，只有A=8、B=4、C=1时才有可能。

【答案】

三个班3次比赛的得分如下表

<table><tr><td></td><td>甲班</td><td>乙班</td><td>丙班</td></tr><tr><td>第一次</td><td>8</td><td>1</td><td>4</td></tr><tr><td>第二次</td><td>8</td><td>1</td><td>4</td></tr><tr><td>第三次</td><td>4</td><td>8</td><td>1</td></tr><tr><td>总分</td><td>20</td><td>10</td><td>9</td></tr></table>

【趣味链接】

请求离婚

有个二等兵决定退伍，就对长官诉说了自己的想法。

他的长官不想让他退伍，就问他：“你结婚了没有？”

二等兵回答说：“还没有，长官。但我已经订婚了。”

结婚其实没有必要，”长官试图说服他，“部队就是你的妻子啊，她能给你衣服穿，给你食物和住房，把你的身体养得这样棒，还时时陪伴着你。你还能有什么要求呢？”

“我想要离婚，长官！”