---
title: "克魯波克魯商店"
date: 2020-04-19T23:00:44+08:00
description: 克魯波克魯商店販售資料大全
draft: false
hideToc: false
enableToc: false
enableTocContent: true
author: 伊琉沙 AKA 哇咔咔
authorEmoji: 👩🏿‍🚀
tags: 
- NPC
- MOD
series:
- 哆啦A夢牧場物語
categories:
- 哆啦A夢
- 商店
image: images/post/Season_of_Story/Building/10500-21400.png
---
<mark>最後更新：2020/04/20</mark>

## 克魯波克魯商店
+ Koropokkur's Shop / Koropokkur's House

### 地理
+ [滾滾森林](../doraemon-story-map-10500-rolin-forest)
    + [克魯波克魯家](../doraemon-story-map-10500-rolin-forest/#克魯波克魯家)

![克魯波克魯家位置](/images/post/Season_of_Story/Map/21400.png)

### 劇情發展
<table>
    <tr>
        <td>11</td>
        <td align="center"><a href="../doraemon-story-11"><img src= "/images/post/Season_of_Story/Sprite/icon_201140120.png">克魯波克魯</a></td>
        <td align="center"><img width="72px" src= "/images/post/Season_of_Story/Sprite/icon_201041260.png">婭卡</td>
        <td align="center"><img width="72px" src= "/images/post/Season_of_Story/Sprite/icon_201041270.png">羅伊茲米</td>
        <td align="center"><img width="72px" src= "/images/post/Season_of_Story/Sprite/icon_201041280.png">多羅米</td>
        <td align="center"><img width="72px" src= "/images/post/Season_of_Story/Sprite/icon_201041290.png">琪倫</td>
        <td align="center"><img width="72px" src= "/images/post/Season_of_Story/Sprite/icon_201041300.png">奇薩拉姆</td>
    </tr>
</table>

## MOD資料庫
### 調用方法
+ 增加[克魯波克魯商店](../doraemon-story-shop-21400-koropokkur-house)響應方法：`FarmWorkState.AddFishingTackleShopResponse(ResponseModel, NpcModel) : void @0600135C`
    + 取得[克魯波克魯商品](../doraemon-story-shop-21400-koropokkur-house/#販售資料)資料：`FarmWorkState.GetFishingTackleShopItemDatas() : ShopItemDataModel[] @0600135D`

### 商店功能集成介面
+ 取得[克魯波克魯商店](../doraemon-story-shop-21400-koropokkur-house/#販售資料)資料：`ShopMasterCollection.GetAllFishingTackleShopDatas() : ShopMasterModel[] @06002BEC`

### 商店模板
+ 商店主模板類：`ShopMasterModel`
    + [克魯波克魯商店](../doraemon-story-shop-21400-koropokkur-house/#販售資料)

### 商店資料
+ [克魯波克魯商店](../doraemon-story-shop-21400-koropokkur-house/#販售資料)資料類：`CFishingTackleShopData`

### 商品模板
+ 商品模板類：`ShopItemDataModel`
    + [克魯波克魯商品](../doraemon-story-shop-21400-koropokkur-house/#販售資料)