---
title: "【哆啦A夢牧場物語】鎮長劇情線"
date: 2020-04-15T15:26:37+08:00
description: "亞緬的劇情發展"
draft: false
hideToc: true
enableToc: true
enableTocContent: true
author: 伊琉沙 AKA 哇咔咔
authorEmoji: 👩🏿‍🚀
tags: 
- 劇情
series:
- 哆啦A夢牧場物語
categories:
- 哆啦A夢
image: images/post/story_sprite/icon_201140100.png
---
![鎮長劇情線](/images/post/story_texture2d/EventImage_2500.png)
## 鎮長
[全劇情線索引](../doraemon-story-index/#劇情線)
<table>
    <tr>
        <td>09</td>
        <td align="center"><a href="../doraemon-story-09"><img src= "/images/post/story_sprite/icon_201140100.png">鎮長</a></td>
        <td align="center"><img width="72px" src= "/images/post/story_sprite/icon_201041200.png">亞緬</td>
    </tr>
</table>

### 第1話 忙碌的孩子們
+ 事件ID：`20004001`
+ 優先度：`3`
+ 觸發地點：`萬物鎮西`（`11200`）

![萬物鎮西](/images/post/map/11200.png)
+ 前置劇情：看完佈告欄引導教學（`81001004`）
    + 間隔天數：`2天`
+ 觸發時間條件
    + 開始時間：每日`06:00`
    + 結束時間：每日`10:00`
+ 天氣條件：`遇上暴風雨、下雨、下雪不觸發`
+ NPC好感度總和條件
<table>
    <thead>
        <tr>
            <td>合計6♥</td>
        </tr>
    </thead>
    <tr>
        <td>靜香</td>
        <td>緹拉兒</td>
        <td>菈姆</td>
    </tr>
    <tr>
        <td><img src= "/images/post/story_sprite/icon_201041020.png"></td>
        <td><img src= "/images/post/story_sprite/icon_201041190.png"></td>
        <td><img src= "/images/post/story_sprite/icon_201041130.png"></td>
    </tr>
    <tr>
        <td><img src= "/images/post/story_sprite/icon_201060020.png"></td>
        <td><img src= "/images/post/story_sprite/icon_201060020.png"></td>
        <td><img src= "/images/post/story_sprite/icon_201060020.png"></td>
    </tr>
</table>

### 第2話 被搶走了！
+ 事件ID：`20004002`
+ 優先度：`3`
+ 觸發地點：`萬物鎮東`（`11300`）
    + `鎮長家`門口（`213.1`,`3.3`,`-131.9`）

![鎮長家門口](/images/post/map/11300-05.png)
+ 前置劇情：[鎮長第1話 忙碌的孩子們](#第1話-忙碌的孩子們)（`20004001`）
    + 間隔天數：`2天`
+ 觸發時間條件
    + 開始時間：每日`06:00`
    + 結束時間：每日`16:00`
+ NPC好感度總和條件
<table>
    <thead>
        <tr>
            <td>合計3♥</td>
        </tr>
    </thead>
    <tr>
        <td>亞緬</td>
    </tr>
    <tr>
        <td><img src= "/images/post/story_sprite/icon_201041200.png"></td>
    </tr>
    <tr>
        <td><img src= "/images/post/story_sprite/icon_201060030.png"></td>
    </tr>
</table>

在`EventManager.UpdateActiveRewardEvent()`方法中能找到，這一話劇情結束後會下列四個延伸劇情將解鎖：

#### 獲得超人手套
+ 事件ID：`20014001`
+ 優先度：`2`
<table>
    <tr>
        <td><img src= "/images/post/story_sprite/icon_201041200.png"></td>
        <td><img src= "/images/post/story_sprite/icon_201041000.png"></td>
        <td><img src= "/images/post/story_sprite/icon_1002130.png"></td>
    </tr>
</table>

+ 當牧場收成達到`3種`作物後，隔天一早觸發事件。
+ `亞緬`會親自到家門口將`超人手套`（`1002130`）給大雄。
+ 擁有`超人手套`後播種可蓄力到九格。
+ 取得`超人手套`後可前往`冷颼颼山`解救[小狗](../doraemon-story-12#第2話-幫助小狗吧)。

#### 獲得尋人手杖
+ 事件ID：`20014002`
+ 優先度：`2`
<table>
    <tr>
        <td><img src= "/images/post/story_sprite/icon_201041200.png"></td>
        <td><img src= "/images/post/story_sprite/icon_201041010.png"></td>
        <td><img src= "/images/post/story_sprite/icon_1002030.png"></td>
    </tr>
</table>

+ 當牧場收成達到`6種`作物後，隔天一早觸發事件。

#### 獲得天氣箱
+ 事件ID：`20014003`
+ 優先度：`2`
+ 當牧場收成達到`12種`作物後，隔天一早觸發事件。
+ `亞緬`會親自到家門口說明想要歸還`天氣箱`，但房子不夠大要等大雄的家擴建為`巨大的家`再來。
---
+ 事件ID：`20014006`
+ 優先度：`2`
+ 觸發地點：`大雄牧場`（`10000`）

![大雄牧場](/images/post/map/10000.png)
+ 前置劇情：
    + <mark>未知</mark>（`50000060`）
    + 巨大的家擴建完成（`10120201`）
<table>
    <tr>
        <td><img src= "/images/post/story_sprite/icon_201041200.png"></td>
        <td><img src= "/images/post/story_sprite/icon_201041000.png"></td>
        <td><img src= "/images/post/story_sprite/icon_1002190.png"></td>
    </tr>
</table>

+ `亞緬`會親自到家門口歸還`天氣箱`。
+ `哆啦A夢`聽說拿回天氣箱會來解說天氣箱的使用。
+ 大雄再去找哆啦A夢可以獲得`雨天卡`。

#### 獲得人類火車套裝組
+ 事件ID：`20014004`
+ 優先度：`2`
<table>
    <tr>
        <td><img src= "/images/post/story_sprite/icon_201041200.png"></td>
        <td><img src= "/images/post/story_sprite/icon_201041010.png"></td>
        <td><img src= "/images/post/story_sprite/icon_1002010.png"></td>
    </tr>
</table>

+ 當牧場收成達到`18種`作物後，隔天一早觸發事件。

### 第3話 給蘭奇的禮物
+ 事件ID：`20004003`
+ 優先度：`3`
+ 觸發地點：`萬物鎮西`（`11200`）

![萬物鎮西](/images/post/map/11200.png)
+ 前置劇情：[鎮長第2話 被搶走了！](#第2話-被搶走了)（`20004002`）
    + 間隔天數：`2天`
+ 觸發時間條件
    + 開始時間：每日`06:00`
    + 結束時間：每日`16:00`
+ 天氣條件：`遇上暴風雨、下雨、下雪不觸發`
+ NPC好感度總和條件
<table>
    <thead>
        <tr>
            <td>合計8♥</td>
        </tr>
    </thead>
    <tr>
        <td>蘭奇</td>
        <td>亞緬</td>
    </tr>
    <tr>
        <td><img src= "/images/post/story_sprite/icon_201041050.png"></td>
        <td><img src= "/images/post/story_sprite/icon_201041200.png"></td>
    </tr>
    <tr>
        <td><img src= "/images/post/story_sprite/icon_201060030.png"></td>
        <td><img src= "/images/post/story_sprite/icon_201060060.png"></td>
    </tr>
</table>

### 第4話 鎮長先生的工作是？
+ 事件ID：`20004004`
+ 優先度：`3`
+ 觸發地點：`萬物鎮東`（`11300`）
    + `鎮長家`門口（`213.1`,`3.3`,`-131.9`）

![鎮長家門口](/images/post/map/11300-05.png)
+ 前置劇情：[鎮長第3話 給蘭奇的禮物](#第3話-給蘭奇的禮物)（`20004003`）
    + 間隔天數：`2天`
+ 觸發時間條件
    + 開始時間：每日`06:00`
    + 結束時間：每日`12:00`
+ NPC好感度總和條件
<table>
    <thead>
        <tr>
            <td>合計8♥</td>
        </tr>
    </thead>
    <tr>
        <td>哆啦A夢</td>
        <td>亞緬</td>
    </tr>
    <tr>
        <td><img src= "/images/post/story_sprite/icon_201041010.png"></td>
        <td><img src= "/images/post/story_sprite/icon_201041200.png"></td>
    </tr>
    <tr>
        <td><img src= "/images/post/story_sprite/icon_201060030.png"></td>
        <td><img src= "/images/post/story_sprite/icon_201060060.png"></td>
    </tr>
</table>

### 第5話 給菈姆的禮物
+ 事件ID：`20004005`
+ 優先度：`3`
+ 觸發地點：`萬物鎮西`（`11200`）

![萬物鎮西](/images/post/map/11200.png)
+ 前置劇情：[鎮長第4話 鎮長先生的工作是？](#第4話-鎮長先生的工作是)（`20004004`）
    + 間隔天數：`2天`
+ 觸發時間條件
    + 開始時間：每日`06:00`
    + 結束時間：每日`12:00`
+ NPC好感度總和條件
<table>
    <thead>
        <tr>
            <td>合計10♥</td>
        </tr>
    </thead>
    <tr>
        <td>菈姆</td>
        <td>亞緬</td>
    </tr>
    <tr>
        <td><img src= "/images/post/story_sprite/icon_201041130.png"></td>
        <td><img src= "/images/post/story_sprite/icon_201041200.png"></td>
    </tr>
    <tr>
        <td><img src= "/images/post/story_sprite/icon_201060030.png"></td>
        <td><img src= "/images/post/story_sprite/icon_201060070.png"></td>
    </tr>
</table>

### 第6話 來自過去的信
+ 事件ID：`20004006`
+ 優先度：`3`
+ 觸發地點：`大雄牧場`（`10000`）

![大雄牧場](/images/post/map/10000.png)
+ 前置劇情：[鎮長第5話 給菈姆的禮物](#第5話-給菈姆的禮物)（`20004005`）
    + 間隔天數：`2天`
+ 觸發時間條件
    + 開始時間：每日`06:00`
    + 結束時間：每日`12:00`
+ NPC好感度總和條件
<table>
    <thead>
        <tr>
            <td>合計11♥</td>
        </tr>
    </thead>
    <tr>
        <td>亞緬</td>
        <td>帕絲琪</td>
    </tr>
    <tr>
        <td><img src= "/images/post/story_sprite/icon_201041200.png"></td>
        <td><img src= "/images/post/story_sprite/icon_201041060.png"></td>
    </tr>
    <tr>
        <td><img src= "/images/post/story_sprite/icon_201060080.png"></td>
        <td><img src= "/images/post/story_sprite/icon_201060030.png"></td>
    </tr>
</table>

### 第7話 屬於孩子們的日子
+ 事件ID：`20004007`
+ 優先度：`3`
+ 觸發地點：`大雄牧場`（`10000`）

![大雄牧場](/images/post/map/10000.png)
+ 前置劇情：[鎮長第6話 來自過去的信](#第5話-來自過去的信)（`20004006`）
    + 間隔天數：`2天`
+ 觸發時間條件
    + 開始時間：每日`06:00`
    + 結束時間：每日`12:00`
+ NPC好感度總和條件
<table>
    <thead>
        <tr>
            <td>合計9♥</td>
        </tr>
    </thead>
    <tr>
        <td>亞緬</td>
    </tr>
    <tr>
        <td><img src= "/images/post/story_sprite/icon_201041200.png"></td>
    </tr>
    <tr>
        <td><img src= "/images/post/story_sprite/icon_201060090.png"></td>
    </tr>
</table>

### 第8話 最後的秘密道具
+ 事件ID：`20004007`
+ 優先度：`3`
+ 觸發地點：`大雄牧場`（`10000`）

![大雄牧場](/images/post/map/10000.png)
+ 前置劇情：
    + [鎮長第7話 屬於孩子們的日子](#第7話-屬於孩子們的日子)（`20004007`）
    + [獲得人類火車套裝組 ](#獲得人類火車套裝組)（`20014004`）
+ 觸發時間條件
    + 開始時間：每日`06:00`
    + 結束時間：每日`12:00`
+ NPC好感度總和條件
<table>
    <thead>
        <tr>
            <td>合計10♥</td>
        </tr>
    </thead>
    <tr>
        <td>亞緬</td>
    </tr>
    <tr>
        <td><img src= "/images/post/story_sprite/icon_201041200.png"></td>
    </tr>
    <tr>
        <td><img src= "/images/post/story_sprite/icon_201060100.png"></td>
    </tr>
</table>

+ 必要物品：`天氣箱`（`1002190`）
<table>
    <tr>
        <td><img src= "/images/post/story_sprite/icon_1002190.png"></td>
    </tr>
</table>

![結局](/images/post/story_texture2d/EventImage_2500.png)