---
title: "【哆啦A夢牧場物語】木工店 咚吭噹"
date: 2020-04-15T23:00:44+08:00
description: 木工店販售商品大全
draft: false
hideToc: false
enableToc: false
enableTocContent: true
author: 伊琉沙 AKA 哇咔咔
authorEmoji: 👩🏿‍🚀
tags: 
- MOD
series:
- 哆啦A夢牧場物語
categories:
- 哆啦A夢
- 商店
image: images/post/story_sprite/icon_301140100.png
---
<mark>最後更新：2020/04/15</mark>
## 木工店MOD資料庫
+ 工藝商品模板類：`CraftShopItemDataModel`，商店上架的商品實例。
    + 商品ID：`Id`
    + 商品類型：`ItemType`
    + 物品ID：`ItemId`
    + 商品等級：`ItemLevel`
    + 商品名稱：`Name`
    + 商品描述：`Description`
    + 附加文字：`AppendText`
    + 商品價格：`Price`
    + 圖集ID：`AtlasId`
    + 圖片ID：`SpriteId`
    + 所需材料：`MaterialItems`
    + 分類：`Category`
    + 是否需要庫存空間：`IsNeedToEmptyInventory`
### 調用狀態
### 販售條件
+ 牧場工作狀態：`FarmWorkState`
    + 建築擴建條件：`CraftShopItemDataModel[] GetBuildingShopItemDatas()`

## 木工店商品資料
+ [建築](#建築)：11種
    + [擴建大雄的家](#擴建大雄的家)：2種
    + [擴建動物小屋](#擴建動物小屋)：2種
    + [擴建雞小屋](#擴建雞小屋)：2種
    + [建造](#建造)：5種
+ [材料](#材料)：種
+ [裝飾](../doraemon-story-shop-hammer-carpenter-shop-Deco)：種

### 建築
木工店進行建築的擴建或建造過程有下列條件：
+ 建築工程會從`潘特`接受委託後的下一個木工店營業日開始。
+ 非木工店營業時間將不計入`工程天數`並自動順延。
+ 木工店營業時間遇到慶典活動也不計入`工程天數`並自動順延。

#### 擴建大雄的家
<table>
    <thead>
        <tr>
            <td>商品ID</td>
            <td>建築ID</td>
            <td></td>
            <td>商品名稱</td>
            <td>材料1</td>
            <td>材料2</td>
            <td>材料3</td>
            <td>材料4</td>
            <td>材料5</td>
            <td>販售價格</td>
            <td>工程天數</td>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>---</td>
            <td>---</td>
            <td><img align="left" width= "100px" src= "/images/post/story_sprite/icon_201080010.png"></td>
            <td>簡陋的家</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
            <td>初始建築</td>
            <td>---</td>
        </tr>
        <tr>
            <td>100100</td>
            <td>12010</td>
            <td><img align="left" width= "100px" src= "/images/post/story_sprite/icon_201080011.png"></td>
            <td>寬闊的家</td>
            <td align="center" valign="middle"><img width= "48px" src= "/images/post/story_sprite/icon_7110000.png">48</td>
            <td align="center" valign="middle"><img width= "48px" src= "/images/post/story_sprite/icon_7110010.png">36</td>
            <td align="center" valign="middle"><img width= "48px" src= "/images/post/story_sprite/icon_7110020.png">27</td>
            <td align="center" valign="middle"><img width= "48px" src= "/images/post/story_sprite/icon_7111010.png">24</td>
            <td align="center" valign="middle"><img width= "48px" src= "/images/post/story_sprite/icon_4001001.png">41</td>
            <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">3200</td>
            <td>7 天</td>
        </tr>
        <tr>
            <td>100101</td>
            <td>12020</td>
            <td><img align="left" width= "100px" src= "/images/post/story_sprite/icon_201080012.png"></td>
            <td>巨大的家</td>
            <td align="center" valign="middle"><img width= "48px" src= "/images/post/story_sprite/icon_7110000.png">121</td>
            <td align="center" valign="middle"><img width= "48px" src= "/images/post/story_sprite/icon_7110010.png">88</td>
            <td align="center" valign="middle"><img width= "48px" src= "/images/post/story_sprite/icon_7110020.png">58</td>
            <td align="center" valign="middle"><img width= "48px" src= "/images/post/story_sprite/icon_4001003.png">30</td>
            <td align="center" valign="middle"><img width= "48px" src= "/images/post/story_sprite/icon_4001006.png">4</td>
            <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">15500</td>
            <td>7 天</td>
        </tr>
    </tbody>
</table>

##### 解鎖項目
+ `寬闊的家`擴建完成
    + 可使用`廚房`
    + 可使用`冰箱`
+ `巨大的家`擴建完成
    + `木工店`解鎖[建造](#建造)項目：`溫室`（1/1條件）

#### 擴建動物小屋
<table>
    <thead>
        <tr>
            <td>商品ID</td>
            <td>建築ID</td>
            <td></td>
            <td>商品名稱</td>
            <td>材料1</td>
            <td>材料2</td>
            <td>材料3</td>
            <td>材料4</td>
            <td>材料5</td>
            <td>販售價格</td>
            <td>工程天數</td>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>---</td>
            <td>---</td>
            <td><img align="left" width= "100px" src= "/images/post/story_sprite/icon_201080020.png"></td>
            <td>簡陋的動物小屋</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
            <td>初始建築</td>
            <td>---</td>
        </tr>
        <tr>
            <td>100103.</td>
            <td>12110</td>
            <td><img align="left" width= "100px" src= "/images/post/story_sprite/icon_201080021.png"></td>
            <td>寬闊的動物小屋</td>
            <td align="center" valign="middle"><img width= "48px" src= "/images/post/story_sprite/icon_7110000.png">60</td>
            <td align="center" valign="middle"><img width= "48px" src= "/images/post/story_sprite/icon_7110010.png">31</td>
            <td align="center" valign="middle"><img width= "48px" src= "/images/post/story_sprite/icon_7110020.png">19</td>
            <td align="center" valign="middle"><img width= "48px" src= "/images/post/story_sprite/icon_4001001.png">45</td>
            <td align="center" valign="middle"><img width= "48px" src= "/images/post/story_sprite/icon_4001000.png">46</td>
            <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">5900</td>
            <td>7 天</td>
        </tr>
        <tr>
            <td>100104</td>
            <td>12120</td>
            <td><img align="left" width= "100px" src= "/images/post/story_sprite/icon_201080022.png"></td>
            <td>巨大的動物小屋</td>
            <td align="center" valign="middle"><img width= "48px" src= "/images/post/story_sprite/icon_7110000.png">121</td>
            <td align="center" valign="middle"><img width= "48px" src= "/images/post/story_sprite/icon_7110010.png">146</td>
            <td align="center" valign="middle"><img width= "48px" src= "/images/post/story_sprite/icon_7110020.png">176</td>
            <td align="center" valign="middle"><img width= "48px" src= "/images/post/story_sprite/icon_4001003.png">45</td>
            <td align="center" valign="middle"><img width= "48px" src= "/images/post/story_sprite/icon_4001004.png">6</td>
            <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">30400</td>
            <td>7 天</td>
        </tr>
    </tbody>
</table>

##### 解鎖項目
+ `寬闊的動物小屋`擴建完成：
    + 可飼養的牛羊從`5頭`增加至`10頭`。
    + 牛羊可在動物小屋`生產`幼崽。
    + `動物商店`解鎖[動物鈴](../doraemon-story-shop-gouter-mawk-livestock/#動物鈴)販售：`牛鈴`（1/1條件）
    + `動物商店`解鎖[動物鈴](../doraemon-story-shop-gouter-mawk-livestock/#動物鈴)販售：`羊鈴`（1/1條件）
+ `巨大的動物小屋`擴建完成：
    + 可飼養的牛羊從`10頭`增加至`20頭`。
    + `動物商店`解鎖[動物鈴](../doraemon-story-shop-gouter-mawk-livestock/#動物鈴)販售：`引導鈴`（1/2條件）

#### 擴建雞小屋
<table>
    <thead>
        <tr>
            <td>商品ID</td>
            <td>建築ID</td>
            <td></td>
            <td>商品名稱</td>
            <td>材料1</td>
            <td>材料2</td>
            <td>材料3</td>
            <td>材料4</td>
            <td>材料5</td>
            <td>販售價格</td>
            <td>工程天數</td>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>---</td>
            <td>---</td>
            <td><img align="left" width= "100px" src= "/images/post/story_sprite/icon_201080030.png"></td>
            <td>簡陋的雞小屋</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
            <td>初始建築</td>
            <td>---</td>
        </tr>
        <tr>
            <td>100105</td>
            <td>12210</td>
            <td><img align="left" width= "100px" src= "/images/post/story_sprite/icon_201080031.png"></td>
            <td>寬闊的雞小屋</td>
            <td align="center" valign="middle"><img width= "48px" src= "/images/post/story_sprite/icon_7110000.png">40</td>
            <td align="center" valign="middle"><img width= "48px" src= "/images/post/story_sprite/icon_7110010.png">31</td>
            <td align="center" valign="middle"><img width= "48px" src= "/images/post/story_sprite/icon_7110020.png">32</td>
            <td align="center" valign="middle"><img width= "48px" src= "/images/post/story_sprite/icon_4001001.png">45</td>
            <td align="center" valign="middle"><img width= "48px" src= "/images/post/story_sprite/icon_4001000.png">41</td>
            <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">6400</td>
            <td>7 天</td>
        </tr>
        <tr>
            <td>100106</td>
            <td>12220</td>
            <td><img align="left" width= "100px" src= "/images/post/story_sprite/icon_201080032.png"></td>
            <td>巨大的雞小屋</td>
            <td align="center" valign="middle"><img width= "48px" src= "/images/post/story_sprite/icon_7110000.png">161</td>
            <td align="center" valign="middle"><img width= "48px" src= "/images/post/story_sprite/icon_7110010.png">110</td>
            <td align="center" valign="middle"><img width= "48px" src= "/images/post/story_sprite/icon_7110020.png">117</td>
            <td align="center" valign="middle"><img width= "48px" src= "/images/post/story_sprite/icon_4001003.png">36</td>
            <td align="center" valign="middle"><img width= "48px" src= "/images/post/story_sprite/icon_4001005.png">6</td>
            <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">26700</td>
            <td>7 天</td>
        </tr>
    </tbody>
</table>

##### 解鎖項目
+ `寬闊的雞小屋`擴建完成：
    + 可飼養的雞從`5頭`增加至`10頭`。
    + 雞可在雞小屋`孵蛋`。
    + `小雞商店`解鎖[動物鈴](../doraemon-story-shop-cuckoo-house-chickens/#動物鈴)販售：`雞鈴`（1/1條件）
+ `巨大的雞小屋`擴建完成：
    + 可飼養的雞從`10頭`增加至`20頭`。
    + `動物商店`解鎖[動物鈴](../doraemon-story-shop-gouter-mawk-livestock/#動物鈴)販售：`引導鈴`（1/2條件）

#### 建造
<table>
    <thead>
        <tr>
            <td>商品ID</td>
            <td>建築ID</td>
            <td></td>
            <td>商品名稱</td>
            <td>材料1</td>
            <td>材料2</td>
            <td>材料3</td>
            <td>材料4</td>
            <td>材料5</td>
            <td>販售價格</td>
            <td>工程天數</td>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>100107</td>
            <td>12610</td>
            <td><img align="left" width= "100px" src= "/images/post/story_sprite/icon_201080050.png"></td>
            <td>動物小屋的筒倉</td>
            <td align="center" valign="middle"><img width= "48px" src= "/images/post/story_sprite/icon_7110000.png">69</td>
            <td align="center" valign="middle"><img width= "48px" src= "/images/post/story_sprite/icon_7110010.png">48</td>
            <td align="center" valign="middle"><img width= "48px" src= "/images/post/story_sprite/icon_7110020.png">44</td>
            <td align="center" valign="middle"><img width= "48px" src= "/images/post/story_sprite/icon_4001002.png">35</td>
            <td align="center" valign="middle"><img width= "48px" src= "/images/post/story_sprite/icon_4001003.png">22</td>
            <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">9700</td>
            <td>3 天</td>
        </tr>
        <tr>
            <td>100108</td>
            <td>12510</td>
            <td><img align="left" width= "100px" src= "/images/post/story_sprite/icon_201080060.png"></td>
            <td>雞小屋的筒倉</td>
            <td align="center" valign="middle"><img width= "48px" src= "/images/post/story_sprite/icon_7110000.png">53</td>
            <td align="center" valign="middle"><img width= "48px" src= "/images/post/story_sprite/icon_7110010.png">55</td>
            <td align="center" valign="middle"><img width= "48px" src= "/images/post/story_sprite/icon_7110020.png">50</td>
            <td align="center" valign="middle"><img width= "48px" src= "/images/post/story_sprite/icon_4001002.png">40</td>
            <td align="center" valign="middle"><img width= "48px" src= "/images/post/story_sprite/icon_4001003.png">25</td>
            <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">10200</td>
            <td>3 天</td>
        </tr>
        <tr>
            <td>100109</td>
            <td>12910</td>
            <td><img align="left" width= "100px" src= "/images/post/story_sprite/icon_201080080.png"></td>
            <td>資材儲放屋</td>
            <td align="center" valign="middle"><img width= "48px" src= "/images/post/story_sprite/icon_7110000.png">48</td>
            <td align="center" valign="middle"><img width= "48px" src= "/images/post/story_sprite/icon_7110010.png">40</td>
            <td align="center" valign="middle"><img width= "48px" src= "/images/post/story_sprite/icon_7110020.png">29</td>
            <td align="center" valign="middle"><img width= "48px" src= "/images/post/story_sprite/icon_7111010.png">20</td>
            <td align="center" valign="middle"><img width= "48px" src= "/images/post/story_sprite/icon_4001001.png">27</td>
            <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">7000</td>
            <td>2 天</td>
        </tr>
        <tr>
            <td>100102</td>
            <td>12410</td>
            <td><img align="left" width= "100px" src= "/images/post/story_sprite/icon_201080070.png"></td>
            <td>馬小屋</td>
            <td align="center" valign="middle"><img width= "48px" src= "/images/post/story_sprite/icon_7110000.png">40</td>
            <td align="center" valign="middle"><img width= "48px" src= "/images/post/story_sprite/icon_7110010.png">31</td>
            <td align="center" valign="middle"><img width= "48px" src= "/images/post/story_sprite/icon_7110020.png">19</td>
            <td align="center" valign="middle"><img width= "48px" src= "/images/post/story_sprite/icon_7111010.png">12</td>
            <td align="center" valign="middle"><img width= "48px" src= "/images/post/story_sprite/icon_4001001.png">30</td>
            <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">5200</td>
            <td>5 天</td>
        </tr>
        <tr>
            <td>100110</td>
            <td>12310</td>
            <td><img align="left" width= "100px" src= "/images/post/story_sprite/icon_201080040.png"></td>
            <td>溫室</td>
            <td align="center" valign="middle"><img width= "48px" src= "/images/post/story_sprite/icon_7110000.png">242</td>
            <td align="center" valign="middle"><img width= "48px" src= "/images/post/story_sprite/icon_7110010.png">440</td>
            <td align="center" valign="middle"><img width= "48px" src= "/images/post/story_sprite/icon_7110020.png">352</td>
            <td align="center" valign="middle"><img width= "48px" src= "/images/post/story_sprite/icon_4001003.png">36</td>
            <td align="center" valign="middle"><img width= "48px" src= "/images/post/story_sprite/icon_4001007.png">12</td>
            <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">70500</td>
            <td>7 天</td>
        </tr>
    </tbody>
</table>

##### 解鎖項目
+ `動物小屋的筒倉`擴建完成：
    + `木工店`解鎖[擴建](#擴建動物小屋)項目：`寬闊的動物小屋`（1/1條件）
+ `雞小屋的筒倉`擴建完成：
    + `木工店`解鎖[擴建](#擴建雞小屋)項目：`寬闊的雞小屋`（1/1條件）
+ `馬小屋`擴建完成
+ `溫室`擴建完成