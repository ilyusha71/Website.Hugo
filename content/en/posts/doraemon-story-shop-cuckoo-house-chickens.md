---
title: "【哆啦A夢牧場物語】小雞商店 咕咕之家"
date: 2020-04-06T23:27:02+08:00
description: 小雞商店販售商品大全
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
image: images/post/story_sprite/icon_301080200.png
---
## 遊戲資源
+ 以下圖示儲存在Sprite資料夾下，對應檔名為`icon_` + `mItemId`+`.png`，`mItemId`可透過`ItemData.text`取得。
+ 以下參數為TextAsset資料夾下`ChickenShopData.text`的轉換的部分資料。

## 小雞商店MOD資料庫
+ 小雞商店資料檔：`ChickenShopData.text`
+ 小雞商店資料類：`CChickenShopData`
    + 小雞商店資料結構：`SChickenShopData`
        + 商品ID：`mId`
        + 物品ID：`mItemId`
        + 價格：`mPrice`
        + 是否陳列：`mIsDisplay`
            + 只有商品會陳列在商店的上架列表中。
+ 商店功能集成介面：`ShopMasterCollection`
    + 商店模版設定：`Setup()`
    + 取得小雞商店所有不陳列的資料：`GetAllNotDisplayChickenShopDatas()`
        + 動物販售。
    + 取得小雞商店所有陳列的資料：`GetAllDisplayChickenShopDatas()`
        + 商品販售。
+ 商店主模板類：`ShopMasterModel`
    + 商品ID：`Id` = `CChickenShopData.SChickenShopData.mId`
    + 物品ID：`ItemId` = `CChickenShopData.SChickenShopData.mItemId`
    + 販售價格：`Price` = `CChickenShopData.SChickenShopData.mPrice`
    + 販售季節：`Season` = -1
    + DLC索引：`DLCIndex` = -1
    + 事件ID：`EventId` = -1
+ 商品模板類：`ShopItemDataModel`，商店上架的商品實例。
    + 商品ID：`Id` = `ShopMasterModel.Id`
    + 物品ID：`ItemId` = `ShopMasterModel.ItemId`
    + 商品名稱：`Name` = `ItemModel.Name`
    + 商品描述：`Description` = `ItemModel.Description`
    + 商品價格：`Price` = `ShopMasterModel.Price`
    + 圖集ID：`AtlasId` = `ItemMasterModel.AtlasId`
    + 圖片ID：`SpriteId` = `ItemModel.Id`
    + 是否為物品模板：`IsItemModel`
    + 是否為單一物品：`IsSingleItem`
    + 只能購買一次：`CanBuyOnce`
    + 是否需要庫存空間：`IsNeedToEmptyInventory`
+ 物品定義類：`Item`
    + 動物鈴能否販售的方法：`CanSaleBell(int item_id)`

### 調用狀態
+ 牧場工作狀態：`FarmWorkState`
    1. `BeginCallback(ICommandHolderObject collided_obj, ICommand stacked_command)`
    2. `CreateWorkResponse()`
    3. `AddChickenShopResponse(ResponseModel root, NpcModel npc, Transform talker_node)`
        + `ShopMasterCollection.GetAllNotDisplayChickenShopDatas()`
        + `ConvertAnimalShopItemDatas(ShopMasterModel[] animal_shop_datas)`
        + `ShopMasterCollection.GetAllDisplayChickenShopDatas()`

## 小雞商店商品資料
+ [`動物`](#動物)：1種
+ [`動物餵食`](#動物餵食)：2種
+ [`動物鈴`](#動物鈴)：1種

### 動物
<table>
    <thead>
        <tr>
            <td>商品ID</td>
            <td>動物ID</td>
            <td></td>
            <td>動物名稱</td>
            <td>販售價格</td>
            <td></td>
            <td>動物名稱</td>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>900102</td>
            <td>114</td>
            <td><img width= "96px" src= "/images/post/story_sprite/icon_201031150.png"></td>
            <td>小雞崽兒</td>
            <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">2000</td>
            <td><img width= "96px" src= "/images/post/story_sprite/icon_201031140.png"></td>
            <td>雞</td>
        </tr>
    </tbody>
</table>

### 動物餵食
<table>
    <thead>
        <tr>
            <td>商品ID</td>
            <td>物品ID</td>
            <td></td>
            <td>商品名稱</td>
            <td>販售價格</td>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>100104</td>
            <td>1101010</td>
            <td><img width= "64px" src= "/images/post/story_sprite/icon_1101010.png"></td>
            <td>雞飼料</td>
            <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">10</td>
        </tr>
        <tr>
            <td>100106</td>
            <td>1101050</td>
            <td><img width= "64px" src= "/images/post/story_sprite/icon_1101050.png"></td>
            <td>動物用點心</td>
            <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">20</td>
        </tr>
    </tbody>
</table>

+ 商品特性：
    + 是否為物品實體：✔。
    + 是否為單一物品：✘。
    + 只能購買一次：✘。
    + 是否需要庫存空間：✔。

### 動物鈴
<table>
    <thead>
        <tr>
            <td>商品ID</td>
            <td>物品ID</td>
            <td></td>
            <td>商品名稱</td>
            <td>販售價格</td>
            <td>功能</td>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>100111</td>
            <td>1001152</td>
            <td><img width= "64px" src= "/images/post/story_sprite/icon_1001152.png"></td>
            <td>雞鈴</td>
            <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">5000</td>
            <td>搖鈴後，雞會往大雄的位置移動。<br>持續8分鐘。</td>
        </tr>
    </tbody>
</table>

+ 商品特性：
    + 是否為物品實體：✔。
    + 是否為單一物品：✔。
    + 只能購買一次：✔。
    + 是否需要庫存空間：✔。

#### 動物鈴解鎖條件
<table>
    <tr>
        <td rowspan="2"><img src= "/images/post/story_sprite/icon_201080031.png"></td>
        <td><img width= "64px" src= "/images/post/story_sprite/icon_1001152.png"></td>
    </tr>
    <tr>
        <td>+ 寬闊的雞小屋<br>建完後才會在小雞商店上架。</td>
    </tr>
</table>

### 00
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
            <td>工程期間</td>
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