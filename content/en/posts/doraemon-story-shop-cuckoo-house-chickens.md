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
image: images/post/Season_of_Story/Sprite/icon_301080200.png
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

### 調用狀態
+ 牧場工作狀態：`FarmWorkState`
    1. `BeginCallback(ICommandHolderObject collided_obj, ICommand stacked_command)`
    2. `CreateWorkResponse()`
    3. `AddChickenShopResponse(ResponseModel root, NpcModel npc, Transform talker_node)`
        + `ShopMasterCollection.GetAllNotDisplayChickenShopDatas()`
        + `ConvertAnimalShopItemDatas(ShopMasterModel[] animal_shop_datas)`
        + `ShopMasterCollection.GetAllDisplayChickenShopDatas()`

### 販售條件
+ 物品定義類：`Item`
    + 動物鈴販售解鎖：`CanSaleBell(int item_id)`

## 小雞商店
+ 營業時間
    + 星期日：9點~15點
    + 星期一：9點~15點
    + 星期三：9點~15點
    + 星期四：9點~15點
    + 星期六：9點~15點
+ 公休日
    + 星期二
    + 星期五

### 主要角色
<table>
    <tr>
        <td><img width= "100px" src= "/images/post/Season_of_Story/Sprite/icon_201041080.png"></td>
        <td>赫蓮</td>
        <td>肯的媽媽</td>
    </tr>
    <tr>
        <td><img width= "100px" src= "/images/post/Season_of_Story/Sprite/icon_201041090.png"></td>
        <td>奇克</td>
        <td>肯的哥哥</td>
    </tr>
    <tr>
        <td><img width= "100px" src= "/images/post/Season_of_Story/Sprite/icon_201041100.png"></td>
        <td>肯</td>
        <td>奇克的弟弟</td>
    </tr>
</table>

## 小雞商店商品資料
+ [動物](#動物)：1種
+ [動物餵食](#動物餵食)：2種
+ [動物鈴](#動物鈴)：1種

### 動物
<table>
    <thead>
        <tr>
            <td>商品ID</td>
            <td>動物ID</td>
            <td></td>
            <td>動物名稱</td>
            <td>販售價格</td>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>900102</td>
            <td>114</td>
            <td><img width= "96px" src= "/images/post/Season_of_Story/Sprite/icon_201031140.png"></td>
            <td>雞</td>
            <td><img align="left" src= "/images/post/Season_of_Story/Sprite/Icon_Money_01.png">2000</td>
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
            <td><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_1101010.png"></td>
            <td>雞飼料</td>
            <td><img align="left" src= "/images/post/Season_of_Story/Sprite/Icon_Money_01.png">10</td>
        </tr>
        <tr>
            <td>100106</td>
            <td>1101050</td>
            <td><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_1101050.png"></td>
            <td>動物用點心</td>
            <td><img align="left" src= "/images/post/Season_of_Story/Sprite/Icon_Money_01.png">20</td>
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
            <td><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_1001152.png"></td>
            <td>雞鈴</td>
            <td><img align="left" src= "/images/post/Season_of_Story/Sprite/Icon_Money_01.png">5000</td>
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
    <thead>
        <tr>
            <td>寬闊的雞小屋</td>
            <td>雞鈴</td>
        </tr>
    </thead>
    <tr>
        <td rowspan="2"><img src= "/images/post/Season_of_Story/Sprite/icon_201080031.png"></td>
        <td><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_1001152.png"></td>
    </tr>
    <tr>
        <td>+ <a href="../doraemon-story-shop-hammer-carpenter-shop#擴建雞小屋">寬闊的雞小屋</a><br>擴建完成後才會在小雞商店上架。</td>
    </tr>
</table>