---
title: "【哆啦A夢牧場物語】雜貨店 小玩意兒"
date: 2020-04-04T19:00:26+08:00
description: 雜貨店販售商品大全
draft: false
hideToc: false
enableToc: false
enableTocContent: true
author: 伊琉沙 AKA 哇咔咔
authorEmoji: 👩🏿‍🚀
tags: 
- MOD
- 作物
series:
- 哆啦A夢牧場物語
categories:
- 哆啦A夢
- 商店
image: images/post/story_sprite/icon_301170000.png
---
## 遊戲資源
+ 以下圖示儲存在Sprite資料夾下，對應檔名為`icon_` + `mItemId`+`.png`，`mItemId`可透過`ItemData.text`取得。
+ 以下參數為TextAsset資料夾下`VarietyShopData.text`的轉換的部分資料。

## 雜貨店MOD資料庫
+ 雜貨店資料檔：`VarietyShopData.text`
+ 雜貨店資料類：`CVarietyShopData`
    + 雜貨店資料結構：`SVarietyShopData`
        + 商品ID：`mVarietyId`
        + 物品ID：`mItemId`
        + 價格：`mPrice`
        + 販售季節：`mSeason`
            + 雜貨店只會販售當季的種子。
        + 首年販售：`mIsFirstYear`
            + 非首年販售的商品會在第二年春季開始販售。
        + DLC索引：`mDLCIndex`
+ 商店功能集成介面：`ShopMasterCollection`
    + 商店模版設定：`Setup()`
    + 取得雜貨店所有商品資料的方法：`GetAllVarietyShopDatas()`
    + 取得雜貨店首年販售商品資料的方法：`GetFirstYearVarietyShopDatas()`
+ 商店主模板類：`ShopMasterModel`
    + 商品ID：`Id` = `CVarietyShopData.SVarietyShopData.mVarietyId`
    + 物品ID：`ItemId` = `CVarietyShopData.SVarietyShopData.mItemId`
    + 販售價格：`Price` = `CVarietyShopData.SVarietyShopData.mPrice`
    + 販售季節：`Season` = `CVarietyShopData.SVarietyShopData.mSeason`
    + DLC索引：`DLCIndex` = `CVarietyShopData.SVarietyShopData.mDLCIndex`
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
    3. `AddVarietyShopResponse(ResponseModel root, NpcModel npc)`
    4. `CreateVarietyShopResponse(NpcModel npc, int season, string choice_text)`
    5. `GetVarietyShopItemDatas(int season)`
        + `ShopMasterCollection.GetAllVarietyShopDatas()`
        + `ShopMasterCollection.GetFirstYearVarietyShopDatas()`

## 雜貨店
+ 營業時間
    + 星期日：15點~20點
    + 星期一：15點~20點
    + 星期二：15點~20點
    + 星期三：15點~20點
    + 星期五：15點~20點
    + 星期六：15點~20點
+ 公休日
    + 星期四

### 主要角色
<table>
    <tr>
        <td><img width= "100px" src= "/images/post/story_sprite/icon_201041170.png"></td>
        <td>埃蒂</td>
        <td>緹拉兒的媽媽</td>
    </tr>
    <tr>
        <td><img width= "100px" src= "/images/post/story_sprite/icon_201041180.png"></td>
        <td>涅萊爾</td>
        <td>緹拉兒的爸爸</td>
    </tr>
    <tr>
        <td><img width= "100px" src= "/images/post/story_sprite/icon_201041190.png"></td>
        <td>緹拉兒</td>
        <td>埃蒂的女兒</td>
    </tr>
</table>

## 雜貨店商品資料
+ [作物種子](#作物種子)：37種
    + [春季種子](#春季種子)：10種
    + [夏季種子](#夏季種子)：13種
    + [秋季種子](#秋季種子)：8種
    + [冬季種子](#冬季種子)：4種
    + [四季種子](#四季種子)：2種
+ [肥料](#肥料)：2種
+ [工具](#工具)：1種
+ [背包](#背包)：2種
+ [DLC](#dlc)：2種

### 作物種子
#### 春季種子
<table>
    <thead>
        <tr>
            <td>商品ID</td>
            <td></td>
            <td>商品名稱</td>
            <td>販售價格</td>
            <td>販售季節</td>
            <td>首年販售</td>
        </tr>
    </thead>
    <tr>
        <td>100100</td>
        <td><img width= "64px" src= "/images/post/story_sprite/icon_2000100.png"></td>
        <td>蕪菁種子</td>
        <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">30</td>
        <td>春季</td>
        <td>✔</td>
    </tr>
    <tr>
        <td>100101</td>
        <td><img width= "64px" src= "/images/post/story_sprite/icon_2000101.png"></td>
        <td>馬鈴薯種子</td>
        <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">50</td>
        <td>春季</td>
        <td>✔</td>
    </tr>
    <tr>
        <td>100102</td>
        <td><img width= "64px" src= "/images/post/story_sprite/icon_2000102.png"></td>
        <td>高麗菜種子</td>
        <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">90</td>
        <td>春季</td>
        <td></td>
    </tr>
    <tr>
        <td>100103</td>
        <td><img width= "64px" src= "/images/post/story_sprite/icon_2000103.png"></td>
        <td>小黃瓜種子</td>
        <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">80</td>
        <td>春季</td>
        <td></td>
    </tr>
    <tr>
        <td>100104</td>
        <td><img width= "64px" src= "/images/post/story_sprite/icon_2000104.png"></td>
        <td>草莓種子</td>
        <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">150</td>
        <td>春季</td>
        <td></td>
    </tr>
    <tr>
        <td>100105</td>
        <td><img width= "64px" src= "/images/post/story_sprite/icon_2000105.png"></td>
        <td>白花椰菜種子</td>
        <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">80</td>
        <td>春季</td>
        <td></td>
    </tr>
    <tr>
        <td>100106</td>
        <td><img width= "64px" src= "/images/post/story_sprite/icon_2000106.png"></td>
        <td>豌豆種子</td>
        <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">80</td>
        <td>春季</td>
        <td></td>
    </tr>
    <tr>
        <td>100108</td>
        <td><img width= "64px" src= "/images/post/story_sprite/icon_2000108.png"></td>
        <td>瑪格麗特種子</td>
        <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">40</td>
        <td>春季</td>
        <td>✔</td>
    </tr>
    <tr>
        <td>100110</td>
        <td><img width= "64px" src= "/images/post/story_sprite/icon_2000110.png"></td>
        <td>彩鐘花種子</td>
        <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">70</td>
        <td>春季</td>
        <td></td>
    </tr>
    <tr>
        <td>100111</td>
        <td><img width= "64px" src= "/images/post/story_sprite/icon_2000111.png"></td>
        <td>康乃馨種子</td>
        <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">80</td>
        <td>春季</td>
        <td></td>
    </tr>
</table>

+ 商品特性：
    + 是否為物品實體：✔。
    + 是否為單一物品：✘。
    + 只能購買一次：✘。
    + 是否需要庫存空間：✔。

#### 夏季種子
<table>
    <thead>
        <tr>
            <td>商品ID</td>
            <td></td>
            <td>商品名稱</td>
            <td>販售價格</td>
            <td>販售季節</td>
            <td>首年販售</td>
        </tr>
    </thead>
    <tr>
        <td>100200</td>
        <td><img width= "64px" src= "/images/post/story_sprite/icon_2000200.png"></td>
        <td>玉米種子</td>
        <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">140</td>
        <td>夏季</td>
        <td>✔</td>
    </tr>
    <tr>
        <td>100201</td>
        <td><img width= "64px" src= "/images/post/story_sprite/icon_2000201.png"></td>
        <td>洋蔥種子</td>
        <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">30</td>
        <td>夏季</td>
        <td></td>
    </tr>
    <tr>
        <td>100202</td>
        <td><img width= "64px" src= "/images/post/story_sprite/icon_2000202.png"></td>
        <td>南瓜種子</td>
        <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">20</td>
        <td>夏季</td>
        <td></td>
    </tr>
    <tr>
        <td>100203</td>
        <td><img width= "64px" src= "/images/post/story_sprite/icon_2000203.png"></td>
        <td>西瓜種子</td>
        <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">40</td>
        <td>夏季</td>
        <td></td>
    </tr>
    <tr>
        <td>100204</td>
        <td><img width= "64px" src= "/images/post/story_sprite/icon_2000204.png"></td>
        <td>番茄種子</td>
        <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">110</td>
        <td>夏季</td>
        <td>✔</td>
    </tr>
    <tr>
        <td>100205</td>
        <td><img width= "64px" src= "/images/post/story_sprite/icon_2000205.png"></td>
        <td>哈密瓜種子</td>
        <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">140</td>
        <td>夏季</td>
        <td></td>
    </tr>
    <tr>
        <td>100206</td>
        <td><img width= "64px" src= "/images/post/story_sprite/icon_2000206.png"></td>
        <td>鳳梨種子</td>
        <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">100</td>
        <td>夏季</td>
        <td></td>
    </tr>
    <tr>
        <td>100207</td>
        <td><img width= "64px" src= "/images/post/story_sprite/icon_2000207.png"></td>
        <td>甜椒種子</td>
        <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">80</td>
        <td>夏季</td>
        <td></td>
    </tr>
    <tr>
        <td>100210</td>
        <td><img width= "64px" src= "/images/post/story_sprite/icon_2000210.png"></td>
        <td>向日葵種子</td>
        <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">80</td>
        <td>夏季</td>
        <td>✔</td>
    </tr>
    <tr>
        <td>100211</td>
        <td><img width= "64px" src= "/images/post/story_sprite/icon_2000211.png"></td>
        <td>牽牛花種子</td>
        <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">40</td>
        <td>夏季</td>
        <td></td>
    </tr>
    <tr>
        <td>100213</td>
        <td><img width= "64px" src= "/images/post/story_sprite/icon_2000213.png"></td>
        <td>百合花種子</td>
        <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">70</td>
        <td>夏季</td>
        <td></td>
    </tr>
    <tr>
        <td>100214</td>
        <td><img width= "64px" src= "/images/post/story_sprite/icon_2000214.png"></td>
        <td>木槿種子</td>
        <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">40</td>
        <td>夏季</td>
        <td></td>
    </tr>
    <tr>
        <td>100215</td>
        <td><img width= "64px" src= "/images/post/story_sprite/icon_2000215.png"></td>
        <td>紅玫瑰種子</td>
        <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">50</td>
        <td>夏季</td>
        <td></td>
    </tr>
</table>

+ 商品特性：
    + 是否為物品實體：✔。
    + 是否為單一物品：✘。
    + 只能購買一次：✘。
    + 是否需要庫存空間：✔。

#### 秋季種子
<table>
    <thead>
        <tr>
            <td>商品ID</td>
            <td></td>
            <td>商品名稱</td>
            <td>販售價格</td>
            <td>販售季節</td>
            <td>首年販售</td>
        </tr>
    </thead>
    <tr>
        <td>100300</td>
        <td><img width= "64px" src= "/images/post/story_sprite/icon_2000300.png"></td>
        <td>牛蒡種子</td>
        <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">50</td>
        <td>秋季</td>
        <td></td>
    </tr>
    <tr>
        <td>100301</td>
        <td><img width= "64px" src= "/images/post/story_sprite/icon_2000301.png"></td>
        <td>胡蘿蔔種子</td>
        <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">80</td>
        <td>秋季</td>
        <td>✔</td>
    </tr>
    <tr>
        <td>100302</td>
        <td><img width= "64px" src= "/images/post/story_sprite/icon_2000302.png"></td>
        <td>地瓜種子</td>
        <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">40</td>
        <td>秋季</td>
        <td>✔</td>
    </tr>
    <tr>
        <td>100303</td>
        <td><img width= "64px" src= "/images/post/story_sprite/icon_2000303.png"></td>
        <td>菠菜種子</td>
        <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">30</td>
        <td>秋季</td>
        <td></td>
    </tr>
    <tr>
        <td>100304</td>
        <td><img width= "64px" src= "/images/post/story_sprite/icon_2000304.png"></td>
        <td>茄子種子</td>
        <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">70</td>
        <td>秋季</td>
        <td></td>
    </tr>
    <tr>
        <td>100305</td>
        <td><img width= "64px" src= "/images/post/story_sprite/icon_2000305.png"></td>
        <td>青椒種子</td>
        <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">90</td>
        <td>秋季</td>
        <td></td>
    </tr>
    <tr>
        <td>100306</td>
        <td><img width= "64px" src= "/images/post/story_sprite/icon_2000306.png"></td>
        <td>撫子花種子</td>
        <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">50</td>
        <td>秋季</td>
        <td>✔</td>
    </tr>
    <tr>
        <td>100307</td>
        <td><img width= "64px" src= "/images/post/story_sprite/icon_2000307.png"></td>
        <td>非洲菊種子</td>
        <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">90</td>
        <td>秋季</td>
        <td></td>
    </tr>
</table>

+ 商品特性：
    + 是否為物品實體：✔。
    + 是否為單一物品：✘。
    + 只能購買一次：✘。
    + 是否需要庫存空間：✔。

#### 冬季種子
<table>
    <thead>
        <tr>
            <td>商品ID</td>
            <td></td>
            <td>商品名稱</td>
            <td>販售價格</td>
            <td>販售季節</td>
            <td>首年販售</td>
        </tr>
    </thead>
    <tr>
        <td>100400</td>
        <td><img width= "64px" src= "/images/post/story_sprite/icon_2000400.png"></td>
        <td>白蘿蔔種子</td>
        <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">20</td>
        <td>冬季</td>
        <td>✔</td>
    </tr>
    <tr>
        <td>100401</td>
        <td><img width= "64px" src= "/images/post/story_sprite/icon_2000401.png"></td>
        <td>白菜種子</td>
        <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">80</td>
        <td>冬季</td>
        <td></td>
    </tr>
    <tr>
        <td>100402</td>
        <td><img width= "64px" src= "/images/post/story_sprite/icon_2000402.png"></td>
        <td>花椰菜種子</td>
        <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">60</td>
        <td>冬季</td>
        <td></td>
    </tr>
    <tr>
        <td>100404</td>
        <td><img width= "64px" src= "/images/post/story_sprite/icon_2000404.png"></td>
        <td>雪花蓮種子</td>
        <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">50</td>
        <td>冬季</td>
        <td>✔</td>
    </tr>
</table>

+ 商品特性：
    + 是否為物品實體：✔。
    + 是否為單一物品：✘。
    + 只能購買一次：✘。
    + 是否需要庫存空間：✔。

#### 四季種子
<table>
    <thead>
        <tr>
            <td>商品ID</td>
            <td></td>
            <td>商品名稱</td>
            <td>販售價格</td>
            <td>販售季節</td>
            <td>首年販售</td>
        </tr>
    </thead>
    <tr>
        <td>100500</td>
        <td><img width= "64px" src= "/images/post/story_sprite/icon_1101000.png"></td>
        <td>牧草種子</td>
        <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">30</td>
        <td>四季</td>
        <td>✔</td>
    </tr>
    <tr>
        <td>100501</td>
        <td><img width= "64px" src= "/images/post/story_sprite/icon_2000501.png"></td>
        <td>小麥種子</td>
        <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">50</td>
        <td>四季</td>
        <td>✔</td>
    </tr>
</table>

+ 商品特性：
    + 是否為物品實體：✔。
    + 是否為單一物品：✘。
    + 只能購買一次：✘。
    + 是否需要庫存空間：✔。

### 肥料
<table>
    <thead>
        <tr>
            <td>商品ID</td>
            <td></td>
            <td>商品名稱</td>
            <td>販售價格</td>
            <td>販售季節</td>
            <td>首年販售</td>
        </tr>
    </thead>
    <tr>
        <td>100500</td>
        <td><img width= "64px" src= "/images/post/story_sprite/icon_1103000.png"></td>
        <td>肥料</td>
        <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">20</td>
        <td>四季</td>
        <td>✔</td>
    </tr>
    <tr>
        <td>100501</td>
        <td><img width= "64px" src= "/images/post/story_sprite/icon_1103001.png"></td>
        <td>高級肥料</td>
        <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">40</td>
        <td>四季</td>
        <td>✔</td>
    </tr>
</table>

+ 商品特性：
    + 是否為物品實體：✔。
    + 是否為單一物品：✘。
    + 只能購買一次：✘。
    + 是否需要庫存空間：✔。

### 工具
<table>
    <thead>
        <tr>
            <td>商品ID</td>
            <td></td>
            <td>商品名稱</td>
            <td>販售價格</td>
            <td>販售季節</td>
            <td>首年販售</td>
        </tr>
    </thead>
    <tr>
        <td>200000</td>
        <td><img width= "64px" src= "/images/post/story_sprite/icon_1001140.png"></td>
        <td>捕蟲網</td>
        <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">2000</td>
        <td>四季</td>
        <td>✔</td>
    </tr>
</table>

+ 商品特性：
    + 是否為物品實體：✔。
    + 是否為單一物品：✔。
    + 只能購買一次：✔。
    + 是否需要庫存空間：✔。

### 背包
<table>
    <thead>
        <tr>
            <td>商品ID</td>
            <td></td>
            <td>商品名稱</td>
            <td>販售價格</td>
            <td>販售季節</td>
            <td>首年販售</td>
            <td>庫存空間</td>
        </tr>
    </thead>
    <tr>
        <td>---</td>
        <td><img width= "64px" src= "/images/post/story_sprite/icon_1003000.png"></td>
        <td>背包</td>
        <td>初始裝備</td>
        <td>---</td>
        <td>---</td>
        <td>8</td>
    </tr>
    <tr>
        <td>200100</td>
        <td><img width= "64px" src= "/images/post/story_sprite/icon_1003001.png"></td>
        <td>大背包</td>
        <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">6000</td>
        <td>四季</td>
        <td>✔</td>
        <td>16</td>
    </tr>
    <tr>
        <td>200101</td>
        <td><img width= "64px" src= "/images/post/story_sprite/icon_1003002.png"></td>
        <td>巨大背包</td>
        <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">12000</td>
        <td>四季</td>
        <td>✔</td>
        <td>24</td>
    </tr>
</table>

+ 商品特性：
    + 是否為物品實體：✘。
    + 是否為單一物品：✔。
    + 只能購買一次：✔。
    + 是否需要庫存空間：✘。

### DLC
<table>
    <thead>
        <tr>
            <td>商品ID</td>
            <td></td>
            <td>商品名稱</td>
            <td>販售價格</td>
            <td>販售季節</td>
            <td>首年販售</td>
        </tr>
    </thead>
    <tr>
        <td>300004</td>
        <td><img width= "64px" src= "/images/post/story_sprite/icon_1106004.png"></td>
        <td>春季蔬菜組</td>
        <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">0</td>
        <td>四季</td>
        <td>✔</td>
    </tr>
    <tr>
        <td>300100</td>
        <td><img width= "64px" src= "/images/post/story_sprite/icon_1106009.png"></td>
        <td>亞緬的預訂品</td>
        <td><img align="left" src= "/images/post/story_sprite/Icon_Money_01.png">0</td>
        <td>四季</td>
        <td>✔</td>
    </tr>
</table>

+ 商品特性：
    + 是否為物品實體：✘。
    + 是否為單一物品：✔。
    + 只能購買一次：✔。
    + 是否需要庫存空間：✘。
+ 春季蔬菜組
    + 這是歐林先生幫忙準備的種子組。有`蕪菁`、`馬鈴薯`、`高麗菜`、`草莓`等4種植物種子
    + 購買後去找`緹拉兒`領取，種子各有20個。
+ 亞緬的預訂品
    + 購買後觸發鎮長`亞緬`的劇情
    + 大雄不管選`看看`或`不看`都能獲得哆啦A夢銅像
    + 哆啦A夢之後都會給`疲勞膏`與`瞬間成長劑`各五個