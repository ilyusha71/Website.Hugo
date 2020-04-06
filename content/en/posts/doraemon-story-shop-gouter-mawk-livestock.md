---
title: "【哆啦A夢牧場物語】動物商店 古騰摩克"
date: 2020-04-06T23:25:25+08:00
description: 動物商店販售商品大全
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
image: images/post/story_sprite/icon_301120000.png
---
## 遊戲資源
+ 以下圖示儲存在Sprite資料夾下，對應檔名為`icon_` + `mItemId`+`.png`，`mItemId`可透過`ItemData.text`取得。
+ 以下參數為TextAsset資料夾下`CattleAndSheepShopData.text`的轉換的部分資料。

## 動物商店MOD資料庫
+ 動物商店資料檔：`CattleAndSheepShopData.text`
+ 動物商店資料類：`CCattleAndSheepShopData`
    + 動物商店資料結構：`SCattleAndSheepShopData`
        + 商品ID：`mId`
        + 物品ID：`mItemId`
        + 價格：`mPrice`
        + 是否陳列：`mIsDisplay`
            + 只有商品會陳列在商店的上架列表中。
+ 商店功能集成介面：`ShopMasterCollection`
    + 商店模版設定：`Setup()`
    + 取得動物商店所有不陳列的資料：`GetAllNotDisplayCattleAndSheepShopDatas()`
        + 動物販售。
    + 取得動物商店所有陳列的資料：`GetAllDisplayCattleAndSheepShopDatas()`
        + 商品販售。
+ 商店主模板類：`ShopMasterModel`
    + 商品ID：`Id` = `CCattleAndSheepShopData.SChickenShopData.mId`
    + 物品ID：`ItemId` = `CCattleAndSheepShopData.SChickenShopData.mItemId`
    + 販售價格：`Price` = `CCattleAndSheepShopData.SChickenShopData.mPrice`
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

### 調用狀態
+ 牧場工作狀態：`FarmWorkState`
    1. `BeginCallback(ICommandHolderObject collided_obj, ICommand stacked_command)`
    2. `CreateWorkResponse()`
    3. `AddCattleAndSheepShopResponse(ResponseModel root, NpcModel npc, Transform talker_node)`
        + `ShopMasterCollection.GetAllNotDisplayCattleAndSheepShopDatas()`
        + `ConvertAnimalShopItemDatas(ShopMasterModel[] animal_shop_datas)`
        + `ShopMasterCollection.GetAllDisplayCattleAndSheepShopDatas()`

## 動物商店商品資料
+ [`動物`](#動物)：2種
+ [`工具`](#工具)：3種
+ [`動物餵食`](#動物餵食)：2種
+ [`種子`](#種子)：2種
+ [`動物鈴`](#動物鈴)：2種

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
            <td>900100</td>
            <td>110</td>
            <td><img width= "96px" src= "/images/post/story_sprite/icon_201031110.png"></td>
            <td>小牛崽兒</td>
            <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">6000</td>
            <td><img width= "96px" src= "/images/post/story_sprite/icon_201031100.png"></td>
            <td>牛</td>
        </tr>
        <tr>
            <td>900101</td>
            <td>112</td>
            <td><img width= "96px" src= "/images/post/story_sprite/icon_201031130.png"></td>
            <td>小羊崽兒</td>
            <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">4000</td>
            <td><img width= "96px" src= "/images/post/story_sprite/icon_201031120.png"></td>
            <td>羊</td>
        </tr>
    </tbody>
</table>

### 工具
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
            <td>100100</td>
            <td>1001110</td>
            <td><img width= "64px" src= "/images/post/story_sprite/icon_1001110.png"></td>
            <td>刷子</td>
            <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">500</td>
        </tr>
        <tr>
            <td>100101</td>
            <td>1001120</td>
            <td><img width= "64px" src= "/images/post/story_sprite/icon_1001120.png"></td>
            <td>擠乳器</td>
            <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">1000</td>
        </tr>
        <tr>
            <td>100102</td>
            <td>1001130</td>
            <td><img width= "64px" src= "/images/post/story_sprite/icon_1001130.png"></td>
            <td>剃毛刀</td>
            <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">1000</td>
        </tr>
    </tbody>
</table>

+ 商品特性：
    + 是否為物品實體：✔。
    + 是否為單一物品：✔。
    + 只能購買一次：✔。
    + 是否需要庫存空間：✔。

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
            <td>100103</td>
            <td>1101000</td>
            <td><img width= "64px" src= "/images/post/story_sprite/icon_1101000.png"></td>
            <td>乾草</td>
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

### 動物種子
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
            <td>100107</td>
            <td>1101030</td>
            <td><img width= "64px" src= "/images/post/story_sprite/icon_1101030.png"></td>
            <td>牛種子</td>
            <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">3000</td>
        </tr>
        <tr>
            <td>100108</td>
            <td>1101040</td>
            <td><img width= "64px" src= "/images/post/story_sprite/icon_1101040.png"></td>
            <td>羊種子</td>
            <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">2000</td>
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
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>100109</td>
            <td>1001150</td>
            <td><img width= "64px" src= "/images/post/story_sprite/icon_1001150.png"></td>
            <td>牛鈴</td>
            <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">5000</td>
        </tr>
        <tr>
            <td>100110</td>
            <td>1001151</td>
            <td><img width= "64px" src= "/images/post/story_sprite/icon_1001151.png"></td>
            <td>羊鈴</td>
            <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">5000</td>
        </tr>
        <tr>
            <td>100112</td>
            <td>1001153</td>
            <td><img width= "64px" src= "/images/post/story_sprite/icon_1001153.png"></td>
            <td>引導鈴</td>
            <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">20000</td>
        </tr>
    </tbody>
</table>

+ 商品特性：
    + 是否為物品實體：✔。
    + 是否為單一物品：✔。
    + 只能購買一次：✔。
    + 是否需要庫存空間：✔。

#### 動物鈴上架條件
<table>
    <tr>
        <td rowspan="2"><img src= "/images/post/story_sprite/icon_201080021.png"></td>
        <td><img width= "64px" src= "/images/post/story_sprite/icon_1001150.png"></td>
        <td><img  width= "64px" src= "/images/post/story_sprite/icon_1001151.png"></td>
    </tr>
    <tr>
        <td colspan="2">+ 寬闊的動物小屋<br>建完後才會在動物商店上架。</td>
    </tr>
</table>
<table>
    <tr>
        <td rowspan="2"><img src= "/images/post/story_sprite/icon_201080022.png"></td>
        <td rowspan="2"><img src= "/images/post/story_sprite/icon_201080032.png"></td>
        <td><img  width= "64px" src= "/images/post/story_sprite/icon_1001153.png"></td>
    </tr>
    <tr>
        <td>+ 巨大的動物小屋<br>+ 巨大的雞小屋<br>建完後才會在動物商店上架。</td>
    </tr>
</table>