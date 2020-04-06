---
title: "【哆啦A夢牧場物語】料理店 嚼嚼"
date: 2020-04-05T09:50:21+08:00
description: 料理店販售商品大全
draft: false
hideToc: false
enableToc: false
enableTocContent: true
author: 伊琉沙 AKA 哇咔咔
authorEmoji: 👩🏿‍🚀
tags: 
- MOD
- 食譜
- 料理
- 作物
series:
- 哆啦A夢牧場物語
categories:
- 哆啦A夢
- 商店
image: images/post/story_sprite/icon_301230000.png
---
## 遊戲資源
+ 以下圖示儲存在Sprite資料夾下，對應檔名為`icon_` + `mItemId`+`.png`，`mItemId`可透過`ItemData.text`取得。
+ 以下參數為TextAsset資料夾下`RestaurantShopData.text`的轉換的部分資料。

## 料理店MOD資料庫
+ 料理店資料檔：`RestaurantShopData.text`
+ 料理店資料類：`CRestaurantShopData`
    + 料理店資料結構：`SRestaurantShopData`
        + 商品ID：`mId`
        + 物品ID：`mItemId`
        + 價格：`mPrice`
        + 季節：`mSeason`
            + 料理店販售的食譜、料理、農產品會因季節變化而改變。
        + 權重：`mWeight`
            + 影響商品上架的機率。
+ 商店功能集成介面：`ShopMasterCollection`
    + 商店模版設定：`Setup()`
    + 取得料理店當季食譜的資料：`GetGroupedBySeasonCookingRecipeShopDatas(int season)`
    + 取得料理店當季料理的資料：`GetGroupedBySeasonDishShopDatas(int season)`
    + 取得料理店當季作物的資料：`GetGroupedBySeasonCropShopDatas(int season)`
    + 取得料理店所有調理器具的資料：`GetAllCookingToolShopDatas()`
    + 取得料理店的資料：`GetRestaurantShopData(int id)`
+ 料理店主模板類：`RestaurantShopMasterModel`，此類專用於`食譜販售`、`料理販售`與`農產品販售`。
    + 商品ID：`Id` = `CRestaurantShopData.SChickenShopData.mId`
    + 物品ID：`ItemId` = `CRestaurantShopData.SChickenShopData.mItemId`
    + 販售價格：`Price` = `CRestaurantShopData.SChickenShopData.mPrice`
    + 販售季節：`Season` = `CRestaurantShopData.SChickenShopData.mSeason`
    + 販售權重：`Weight` = `CRestaurantShopData.SChickenShopData.mWeight`
+ 料理店模板類：`RestaurantShopDataModel`
    + 食譜資料：`CookingRecipeShopItems`，商店上架的食譜實例。
    + 料理資料：`DishShopItems`，商店上架的料理實例。
    + 農產品資料：`CropShopItems`，商店上架的農產品實例。
    + 上架抽選方法：`GetLotteryRestaurantShopMasterDatas`
    + 食譜上架方法：`UpdateCookingRecipeShopItemDatas(bool is_refresh_data, int season)`
    + 料理上架方法：`UpdateDishShopItemDatas(bool is_refresh_data, int season)`
    + 農產品上架方法：`UpdateCropShopItemDatas(bool is_refresh_data, int season)`
+ 商店主模板類：`ShopMasterModel`，此類在料理店用於`調理器具販售`。
    + 商品ID：`Id` = `CRestaurantShopData.SChickenShopData.mId`
    + 物品ID：`ItemId` = `CRestaurantShopData.SChickenShopData.mItemId`
    + 販售價格：`Price` = `CRestaurantShopData.SChickenShopData.mPrice`
    + 販售季節：`Season` = `CRestaurantShopData.SChickenShopData.mSeason`
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
    3. `AddCookingShopResponse(ResponseModel root, NpcModel npc)`
        + `FarmModel.UpdateRestaurantShopData(TimeModel time)`
            + `RestaurantShopDataModel.UpdateShopDatas(TimeModel time)`
            + 食譜：`RestaurantShopDataModel.UpdateCookingRecipeShopItemDatas(bool is_refresh_data, int season)`
                + `ShopMasterCollection.GetGroupedBySeasonCookingRecipeShopDatas(int season)`
            + 料理：`RestaurantShopDataModel.UpdateDishShopItemDatas(bool is_refresh_data, int season)`
                + `ShopMasterCollection.GetGroupedBySeasonDishShopDatas(int season)`
            + 農產品：`RestaurantShopDataModel.UpdateCropShopItemDatas(bool is_refresh_data, int season)`
                + `ShopMasterCollection.GetGroupedBySeasonCropShopDatas(int season)`
        + `GetCookingToolShopItemDatas()`

## 料理店/嚼嚼餐廳商品資料
+ 營業時間
    + 星期日：12點~16點，18點~22點
    + 星期二：12點~16點，18點~22點
    + 星期三：12點~16點，18點~22點
    + 星期四：12點~16點，18點~22點
    + 星期六：12點~16點，18點~22點
+ 公休日
    + 星期一
    + 星期五

### 主要角色
<table>
    <tr>
        <td><img width= "100px" src= "/images/post/story_sprite/icon_201041230.png"></td>
        <td>萊斯特</td>
        <td>托蘭的丈夫</td>
    </tr>
    <tr>
        <td><img width= "100px" src= "/images/post/story_sprite/icon_201041240.png"></td>
        <td>托蘭</td>
        <td>萊斯特的妻子</td>
    </tr>
    <tr>
        <td><img width= "100px" src= "/images/post/story_sprite/icon_201041040.png"></td>
        <td>小夫</td>
        <td>餐廳打工仔</td>
    </tr>
</table>

## 料理店商品資料
+ [`食譜`](../doraemon-story-shop-cafe-delish-recipes)：89種
    + [`春季食譜`](../doraemon-story-shop-cafe-delish-recipes#春季食譜)：15種
    + [`夏季食譜`](../doraemon-story-shop-cafe-delish-recipes#夏季食譜)：14種
    + [`秋季食譜`](../doraemon-story-shop-cafe-delish-recipes#秋季食譜)：14種
    + [`冬季食譜`](../doraemon-story-shop-cafe-delish-recipes#冬季食譜)：14種
    + [`四季食譜`](../doraemon-story-shop-cafe-delish-recipes#四季食譜)：32種
+ [`料理`](../doraemon-story-shop-cafe-delish-meals)：86種
    + [`春季料理`](../doraemon-story-shop-cafe-delish-meals#春季料理)：22種
    + [`夏季料理`](../doraemon-story-shop-cafe-delish-meals#夏季料理)：22種
    + [`秋季料理`](../doraemon-story-shop-cafe-delish-meals#秋季料理)：21種
    + [`冬季料理`](../doraemon-story-shop-cafe-delish-meals#冬季料理)：21種
+ [`農產品`](../doraemon-story-shop-cafe-delish-produce)：35種
    + [`春季農產品`](../doraemon-story-shop-cafe-delish-produce#春季農產品)：7種
    + [`夏季農產品`](../doraemon-story-shop-cafe-delish-produce#夏季農產品)：8種
    + [`秋季農產品`](../doraemon-story-shop-cafe-delish-produce#秋季農產品)：6種
    + [`冬季農產品`](../doraemon-story-shop-cafe-delish-produce#冬季農產品)：3種
    + [`四季農產品`](../doraemon-story-shop-cafe-delish-produce#四季農產品)：11種
+ [`調理器具`](#調理器具)：5種

### 調理器具
+ 調理器具只能購買一次，已擁有的調理器具可以在`廚房`查看。

<table>
    <thead>
        <tr>
            <td>商店ID</td>
            <td></td>
            <td>調理器具名稱</td>
            <td>販售價格</td>
            <td>販售季節</td>
            <td>販售權重</td>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>400100</td>
            <td><img width= "64px" src= "/images/post/story_sprite/icon_9000100.png"></td>
            <td>鍋具組</td>
            <td>9800</td>
            <td>四季</td>
            <td>-1</td>
        </tr>
        <tr>
            <td>400101</td>
            <td><img width= "64px" src= "/images/post/story_sprite/icon_9000101.png"></td>
            <td>打蛋器</td>
            <td>2450</td>
            <td>四季</td>
            <td>-1</td>
        </tr>
        <tr>
            <td>400102</td>
            <td><img width= "64px" src= "/images/post/story_sprite/icon_9000102.png"></td>
            <td>烤箱</td>
            <td>3850</td>
            <td>四季</td>
            <td>-1</td>
        </tr>
        <tr>
            <td>400103</td>
            <td><img width= "64px" src= "/images/post/story_sprite/icon_9000103.png"></td>
            <td>擀麵棍</td>
            <td>2100</td>
            <td>四季</td>
            <td>-1</td>
        </tr>
        <tr>
            <td>400104</td>
            <td><img width= "64px" src= "/images/post/story_sprite/icon_9000104.png"></td>
            <td>平底鍋</td>
            <td>6300</td>
            <td>四季</td>
            <td>-1</td>
        </tr>
    </tbody>
</table>