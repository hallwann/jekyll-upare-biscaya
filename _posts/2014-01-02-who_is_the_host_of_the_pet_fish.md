---
author: upare
title: 谁是养鱼人
thumbnail:
category:
  - blog
  - brainstorm
tag:
  - logic
description: 
---
有一道据说是由爱因斯坦出的测试题，也有人说，这个世界上有98%的人不能答出正确答案，你是不是另外的2%呢？

题目是这样的：有五栋颜色不同的房子；这五栋房子主人国籍都不同；这五个人每一个人都只喝一种饮料、只抽一个牌子的香烟、只养一种宠物，而且各不相同；

英国人住在红色的房子里；

美国人养的宠物是狗；

丹麦人喝的饮料是茶；

绿色房子在白色房子的左边；

绿色房子主人只喝咖啡；

抽登喜路烟的人养了一只鸟；

黄色房子的主人抽VISIONS烟；

住在中栋那栋栋房子里的人只喝牛奶；

挪威人住第一栋房子；

抽Blends香烟的人住在养猫的人的旁边；

养马的人住在抽VISIONS烟的人的旁边；

抽555牌香烟的人只喝啤酒；

德国人抽PRINCE烟；

挪威人住在蓝色房子旁边的那栋房子里面；

抽Blends的人的邻居喝矿泉水。

需要找出的是，谁的宠物是鱼？

【分析】

我们用表格分析法来找到养鱼的人。从问题给出的条件，可以得到一个二维表格的信息（如下）：

<table border="1"><tbody><tr><td>-</td><td>第一栋</td><td>第二栋</td><td>第三栋</td><td>第四栋</td><td>第五栋</td></tr><tr><td>颜色</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>国籍</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>饮料</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>香烟</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>宠物</td><td></td><td></td><td></td><td></td><td></td></tr></tbody></table>

然后，只要将信息从提示的条件填入表格，就可以得到答案。

我们知道：“第三栋房子的人喝牛奶”，我们把牛奶填到栋相应位置，现在的图表如下：

<table border="1"><tbody><tr><td>-</td><td>第一栋</td><td>第二栋</td><td>第三栋</td><td>第四栋</td><td>第五栋</td></tr><tr><td>颜色</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>国籍</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>饮料</td><td></td><td></td><td>牛奶</td><td></td><td></td></tr><tr><td>香烟</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>宠物</td><td></td><td></td><td></td><td></td><td></td></tr></tbody></table>

接下来：“挪威人住第一栋房子”，所以我们把挪威人填到相应栋位置。

挪威人住蓝色房子隔壁”，因为挪威人是住在第一栋房子里的，所以他的隔壁只有第二栋，所以第二栋的颜色里面填进蓝色。

<table border="1"><tbody><tr><td>-</td><td>第一栋</td><td>第二栋</td><td>第三栋</td><td>第四栋</td><td>第五栋</td></tr><tr><td>颜色</td><td></td><td>蓝色</td><td></td><td></td><td></td></tr><tr><td>国籍</td><td>挪威人</td><td></td><td></td><td></td><td></td></tr><tr><td>饮料</td><td></td><td></td><td>牛奶</td><td></td><td></td></tr><tr><td>香烟</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>宠物</td><td></td><td></td><td></td><td></td><td></td></tr></tbody></table>

“绿色房子在白色房子左面”，从上面刚得到的表的信息，我们可以很容易看出绿色房子只可能在第三栋或第四栋。“绿色房子主人喝咖啡”。根据这个提示很快发现，因为第三栋主人喜欢的饮料已经填了牛奶，所以绿色的是第四栋房子。这次我们一共可以填三个空：第四栋房子是绿色的栋，住第四栋的人喝的是咖啡，第五栋房子是白色栋的。

<table border="1"><tbody><tr><td>-</td><td>第一栋</td><td>第二栋</td><td>第三栋</td><td>第四栋</td><td>第五栋</td></tr><tr><td>颜色</td><td></td><td>蓝色</td><td></td><td>绿色</td><td>白色</td></tr><tr><td>国籍</td><td>挪威人</td><td></td><td></td><td></td><td></td></tr><tr><td>饮料</td><td></td><td></td><td>牛奶</td><td>咖啡</td><td></td></tr><tr><td>香烟</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>宠物</td><td></td><td></td><td></td><td></td><td></td></tr></tbody></table>

“英国人住红色房子”。第一栋是挪威人的，不可能是红色。第二栋、第四栋、第五栋都已经确定不是红色的了。所以，第三栋房子是红色的，它的主人是英国人。理所当然，黄色的就被填在第一个空白处。

“黄色房子主人抽VISIONS香烟”。所以第一栋房子的主人的香烟就填上VISIONS。养马的人住抽VISIONS香烟的人隔壁”，所以第二栋房子的主人的宠物是马。

<table border="1"><tbody><tr><td>-</td><td>第一栋</td><td>第二栋</td><td>第三栋</td><td>第四栋</td><td>第五栋</td></tr><tr><td>颜色</td><td>黄色</td><td>蓝色</td><td>红色</td><td>绿色</td><td>白色</td></tr><tr><td>国籍</td><td>挪威人</td><td></td><td>英国人</td><td></td><td></td></tr><tr><td>饮料</td><td></td><td></td><td>牛奶</td><td>咖啡</td><td></td></tr><tr><td>香烟</td><td>VISIONS</td><td></td><td></td><td></td><td></td></tr><tr><td>宠物</td><td></td><td>马</td><td></td><td></td><td></td></tr></tbody></table>

“丹麦人喝茶”，第一栋是挪威人，排除掉，第三，第四栋，喝的饮料不是茶，答案就在第二栋和第五栋中间。

“抽555的人喝啤酒”，用上面的排除法，得到的又是第二栋或第五栋中的一个。“抽Blends香烟的邻居喝矿泉水”，从这个提示我们只能排除第一栋和第五栋。第一栋的主人抽的是VISIONS香烟，而第五栋的邻居是喝咖啡的。

如果前两个提示中的任意一个在第五栋的话，“抽Blends香烟的邻居喝矿泉水”，在第四栋的假设就不成立了，并且它们其中一个在第五栋的话，另一个就得在第二栋，开始，如果这样的话，“抽Blends香烟的邻居喝矿泉”在第三栋的假设也就不成立了。因为它们这两栋主人的的邻居的饮料都不是水。所以，第二栋房子的主人抽的是Blends，他的邻居就是第一栋，喜欢喝的饮料是矿泉水。“抽555的人喝啤酒。”就是第五栋了。

<table border="1"><tbody><tr><td>-</td><td>第一栋</td><td>第二栋</td><td>第三栋</td><td>第四栋</td><td>第五栋</td></tr><tr><td>颜色</td><td>黄色</td><td>蓝色</td><td>红色</td><td>绿色</td><td>白色</td></tr><tr><td>国籍</td><td>挪威人</td><td></td><td>英国人</td><td></td><td></td></tr><tr><td>饮料</td><td>矿泉水</td><td></td><td>牛奶</td><td>咖啡</td><td></td></tr><tr><td>香烟</td><td>VISIONS</td><td>Blends</td><td></td><td></td><td>555</td></tr><tr><td>宠物</td><td></td><td>马</td><td></td><td></td><td></td></tr></tbody></table>

第二栋的主人抽的香烟是Blends，所以可以确定是第五栋的人抽的是555香烟，喝的饮料是啤酒。喝茶的丹麦人自然就是第二栋的主人。

<table border="1"><tbody><tr><td>-</td><td>第一栋</td><td>第二栋</td><td>第三栋</td><td>第四栋</td><td>第五栋</td></tr><tr><td>颜色</td><td>黄色</td><td>蓝色</td><td>红色</td><td>绿色</td><td>白色</td></tr><tr><td>国籍</td><td>挪威人</td><td>丹麦人</td><td>英国人</td><td></td><td></td></tr><tr><td>饮料</td><td>矿泉水</td><td>茶</td><td>牛奶</td><td>咖啡</td><td>啤酒</td></tr><tr><td>香烟</td><td>VISIONS</td><td>Blends</td><td></td><td></td><td>555</td></tr><tr><td>宠物</td><td></td><td>马</td><td></td><td></td><td></td></tr></tbody></table>

接下来“德国人抽PrInce香烟”，前面三栋的主人不是德国人，最后一栋的主人抽的是555香烟。所以第四栋的主人是德国人，抽的烟是PrInce。

“美国人养狗”，前面四栋都被填满了其他国家的人，养狗的就是第五栋了：所以第五栋住的是美国人，宠物是狗。

“抽登喜路香烟的人养鸟”，没有香烟的就剩下第三栋了，所以第三栋的主人抽的是登喜路香烟，宠物是鸟。

<table border="1"><tbody><tr><td>-</td><td>第一栋</td><td>第二栋</td><td>第三栋</td><td>第四栋</td><td>第五栋</td></tr><tr><td>颜色</td><td>黄色</td><td>蓝色</td><td>红色</td><td>绿色</td><td>白色</td></tr><tr><td>国籍</td><td>挪威人</td><td>丹麦人</td><td>英国人</td><td>德国人</td><td>美国人</td></tr><tr><td>饮料</td><td>矿泉水</td><td>茶</td><td>牛奶</td><td>咖啡</td><td>啤酒</td></tr><tr><td>香烟</td><td>VISIONS</td><td>Blends</td><td>登喜路</td><td>PrInce</td><td>555</td></tr><tr><td>宠物</td><td></td><td>马</td><td>鸟</td><td></td><td>狗</td></tr></tbody></table>

“抽Blends香烟的人住在养猫的人隔壁”，抽Blends香烟的人在第一栋和第三栋，第三栋的主人养的是鸟，那猫就是第一栋主人的宠物了。现在只有第四栋的宠物还空白，他就是最后的答案“鱼是德国人养的”。

<table border="1"><tbody><tr><td>-</td><td>第一栋</td><td>第二栋</td><td>第三栋</td><td>第四栋</td><td>第五栋</td></tr><tr><td>颜色</td><td>黄色</td><td>蓝色</td><td>红色</td><td>绿色</td><td>白色</td></tr><tr><td>国籍</td><td>挪威人</td><td>丹麦人</td><td>英国人</td><td>德国人</td><td>美国人</td></tr><tr><td>饮料</td><td>矿泉水</td><td>茶</td><td>牛奶</td><td>咖啡</td><td>啤酒</td></tr><tr><td>香烟</td><td>VISIONS</td><td>Blends</td><td>登喜路</td><td>PrInce</td><td>555</td></tr><tr><td>宠物</td><td>猫</td><td>马</td><td>鸟</td><td>鱼</td><td>狗</td></tr></tbody></table>

【答案】

养鱼的是德国人。

【趣味链接】

没说明白

铁匠正在打铁，一个小孩好奇的站在旁边看着。铁匠有些厌烦，便拿出烧得通红的铁，凑到小孩面前想吓唬他。

小孩看着铁块，眨了眨眼睛说：“要是你给我一块钱，我就敢舔一舔它！”

铁匠觉得很可笑，马上掏出一块钱给了小孩。

小孩接过钱，举到眼前用舌头舔了一下，然后放进兜里走了……