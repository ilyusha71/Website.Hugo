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
+ 觸發時間條件📆
    + 開始時間：每日`06:00`
    + 結束時間：每日`10:00`
+ 天氣條件：`遇上暴風雨、下雨、下雪不觸發`
+ NPC好感度💝總和條件
<table>
    <thead>
        <tr>
            <td>合計6❤️</td>
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
+ 觸發時間條件📆
    + 開始時間：每日`06:00`
    + 結束時間：每日`16:00`
+ NPC好感度💝總和條件
<table>
    <thead>
        <tr>
            <td>合計3❤️</td>
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

### 獎勵事件解鎖
+ `EventManager.UpdateActiveRewardEvent()`
+ 前置劇情：[鎮長第2話 被搶走了](#第2話-被搶走了)（`20004002`）
+ 在第2話中，亞緬要求大雄專心在牧場收穫更多的作物就會歸還道具。

#### 獲得超人手套
+ 事件ID：`20014001`
+ 優先度：`2`
+ 獎勵條件：作物圖鑑解鎖`3種`
<table>
    <thead>
        <tr>
            <td>持有者</td>
            <td>保管者</td>
            <td>秘密道具</td>
        </tr>
    </thead>
    <tr>
        <td><img src= "/images/post/story_sprite/icon_201041200.png"></td>
        <td><img src= "/images/post/story_sprite/icon_201041000.png"></td>
        <td><img src= "/images/post/story_sprite/icon_1002130.png"></td>
    </tr>
</table>

達成條件后的翌日，`亞緬`會到家門口將`超人手套`（`1002130`）還給`大雄`。
+ `超人手套`不會佔用物品空間。
+ 擁有`超人手套`後播種可蓄力到九格。
+ 取得`超人手套`後可前往`冷颼颼山`解救[小狗](../doraemon-story-12#第2話-幫助小狗吧)。

#### 獲得尋人手杖
+ 事件ID：`20014002`
+ 優先度：`2`
+ 獎勵條件：作物圖鑑解鎖`6種`
<table>
    <thead>
        <tr>
            <td>持有者</td>
            <td>保管者</td>
            <td>秘密道具</td>
        </tr>
    </thead>
    <tr>
        <td><img src= "/images/post/story_sprite/icon_201041200.png"></td>
        <td><img src= "/images/post/story_sprite/icon_201041010.png"></td>
        <td><img src= "/images/post/story_sprite/icon_1002030.png"></td>
    </tr>
</table>

達成條件后的翌日，`亞緬`會到家門口告知大雄`尋人手杖`（`1002030`）已經交給`哆啦A夢`。
+ `尋人手杖`屬於工具物品，佔用1格空間。
+ `尋人手杖`必須放在背包才可使用，使用時需指定一名NPC。

#### 獲得天氣箱
+ 事件ID：`20014003`
+ 優先度：`2`
+ 獎勵條件：作物圖鑑解鎖`12種`

達成條件后的翌日，`亞緬`會到家門口說明想要歸還`天氣箱`，但大雄目前的房子不夠大要等大雄的家擴建為`巨大的家`再來。

+ 事件ID：`20014006`
+ 優先度：`2`
+ 觸發地點：`大雄牧場`（`10000`）

![大雄牧場](/images/post/map/10000.png)
+ 前置劇情：
    + <mark>未知</mark>（`50000060`）
    + [巨大的家擴建完成](../doraemon-story-1/#巨大的家擴建完成)（`10120201`）
<table>
    <thead>
        <tr>
            <td>持有者</td>
            <td>保管者</td>
            <td>秘密道具</td>
        </tr>
    </thead>
    <tr>
        <td><img src= "/images/post/story_sprite/icon_201041200.png"></td>
        <td><img src= "/images/post/story_sprite/icon_201041000.png"></td>
        <td><img src= "/images/post/story_sprite/icon_1002190.png"></td>
    </tr>
</table>

巨大的家擴建完成的當天，`亞緬`會到家門口將`天氣箱`還給`大雄`。
+ `天氣箱`會安裝在`冰箱`旁邊。
+ `哆啦A夢`聽說拿回天氣箱後會來解說天氣箱的使用。
+ 大雄再去找哆啦A夢可以獲得`雨天卡`。
+ `天氣箱`是[鎮長第8話 最後的秘密道具](#第8話-最後的秘密道具)的必要物品。

#### 獲得人類火車套裝組
+ 事件ID：`20014004`
+ 優先度：`2`
+ 獎勵條件：作物圖鑑解鎖`18種`
<table>
    <thead>
        <tr>
            <td>持有者</td>
            <td>保管者</td>
            <td>秘密道具</td>
        </tr>
    </thead>
    <tr>
        <td><img src= "/images/post/story_sprite/icon_201041200.png"></td>
        <td><img src= "/images/post/story_sprite/icon_201041010.png"></td>
        <td><img src= "/images/post/story_sprite/icon_1002010.png"></td>
    </tr>
</table>

達成條件后的翌日，`亞緬`會到家門口告知大雄`人類火車套裝組`（`1002010`）已經交給`哆啦A夢`。
+ `人類火車套裝組`屬於工具物品，佔用1格空間。
+ `人類火車套裝組`必須放在背包才可使用。
+ 使用後，大雄僅能在地圖進行加速移動，不能進行其他動作。

### 第3話 給蘭奇的禮物
+ 事件ID：`20004003`
+ 優先度：`3`
+ 觸發地點：`萬物鎮西`（`11200`）

![萬物鎮西](/images/post/map/11200.png)
+ 前置劇情：[鎮長第2話 被搶走了！](#第2話-被搶走了)（`20004002`）
    + 間隔天數：`2天`
+ 觸發時間條件📆
    + 開始時間：每日`06:00`
    + 結束時間：每日`16:00`
+ 天氣條件：`遇上暴風雨、下雨、下雪不觸發`
+ NPC好感度💝總和條件
<table>
    <thead>
        <tr>
            <td>合計8❤️</td>
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
+ 觸發時間條件📆
    + 開始時間：每日`06:00`
    + 結束時間：每日`12:00`
+ NPC好感度💝總和條件
<table>
    <thead>
        <tr>
            <td>合計8❤️</td>
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
+ 觸發時間條件📆
    + 開始時間：每日`06:00`
    + 結束時間：每日`12:00`
+ NPC好感度💝總和條件
<table>
    <thead>
        <tr>
            <td>合計10❤️</td>
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
+ 觸發時間條件📆
    + 開始時間：每日`06:00`
    + 結束時間：每日`12:00`
+ NPC好感度💝總和條件
<table>
    <thead>
        <tr>
            <td>合計11❤️</td>
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
+ 觸發時間條件📆
    + 開始時間：每日`06:00`
    + 結束時間：每日`12:00`
+ NPC好感度💝總和條件
<table>
    <thead>
        <tr>
            <td>合計9❤️</td>
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
+ 觸發時間條件📆
    + 開始時間：每日`06:00`
    + 結束時間：每日`12:00`
+ NPC好感度💝總和條件
<table>
    <thead>
        <tr>
            <td>合計10❤️</td>
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
    <thead>
        <tr>
            <td>天氣箱</td>
            <td>取得途徑</td>
        </tr>
    </thead>
    <tr>
        <td><img src= "/images/post/story_sprite/icon_1002190.png"></td>
        <td><a href="../doraemon-story-09#獲得天氣箱">鎮長第2話 獎勵事件：獲得天氣箱</a></td>
    </tr>
</table>

![結局](/images/post/story_texture2d/EventImage_2500.png)