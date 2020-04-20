---
title: "席菲小姐的釣具店"
date: 2020-04-19T23:00:44+08:00
description: 釣具店販售資料大全
draft: false
hideToc: false
enableToc: false
enableTocContent: true
author: 伊琉沙 AKA 哇咔咔
authorEmoji: 👩🏿‍🚀
tags: 
- 動物
- MOD
series:
- 哆啦A夢牧場物語
categories:
- 哆啦A夢
- 商店
image: images/post/Season_of_Story/Building/21300.png
---
<mark>最後更新：2020/04/20</mark>

## 席菲小姐的釣具店
+ Tackle Shop / Sandy's Tackle Shop

### 地理
+ [濤濤海岬](../doraemon-story-map-10900-zazan-cape)
    + [席菲小姐的釣具店](../doraemon-story-map-10900-zazan-cape/#席菲小姐的釣具店)

![釣具店位置](/images/post/Season_of_Story/Map/21300.png)

### 劇情發展
<table>
    <tr>
        <td>08</td>
        <td align="center"><a href="../doraemon-story-08"><img src= "/images/post/Season_of_Story/Sprite/icon_201140090.png">釣具店</a></td>
        <td align="center"><img width="72px" src= "/images/post/Season_of_Story/Sprite/icon_201041250.png">席菲</td>
    </tr>
</table>

### 營業時間
<table>
    <thead>
        <tr>
            <td>營業時間</td>
            <td>上午</td>
            <td>下午</td>
            <td></td>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>星期日</td>
            <td>8點~12點</td>
            <td>14點~16點</td>
            <td rowspan="10"><img src= "/images/post/Season_of_Story/Scene/21300-opening-time.png"></td>
        </tr>
        <tr>
            <td>星期一</td>
            <td colspan="2">公休日</td>
        </tr>
        <tr>
            <td>星期二</td>
            <td>8點~12點</td>
            <td>14點~16點</td>
        </tr>
        <tr>
            <td>星期三</td>
            <td colspan="2">公休日</td>
        </tr>        
        <tr>
            <td>星期四</td>
            <td>8點~12點</td>
            <td>14點~16點</td>
        </tr>
        <tr>
            <td>星期五</td>
            <td colspan="2">公休日</td>
        </tr>
        <tr>
            <td>星期六</td>
            <td>8點~12點</td>
            <td>14點~16點</td>
        </tr>
     </tbody>
</table>

## 販售資料
+ [魚餌](../doraemon-story-shop-21300-sandy-tackle-shop/#魚餌)：2種

### 魚餌
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
            <td>100101</td>
            <td>1102000</td>
            <td><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_1102000.png"></td>
            <td>撒食餌</td>
            <td><img align="left" src= "/images/post/Season_of_Story/Sprite/Icon_Money_01.png">100</td>
        </tr>
        <tr>
            <td>100102</td>
            <td>1102001</td>
            <td><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_1102001.png"></td>
            <td>高級撒食餌</td>
            <td><img align="left" src= "/images/post/Season_of_Story/Sprite/Icon_Money_01.png">300</td>
        </tr>
    </tbody>
</table>

+ 商品特性：
    + 是否為物品實體：✔
    + 是否為單一物品：✘
    + 只能購買一次：✘
    + 是否需要庫存空間：✔

### 魚拓
當`大雄`帶著`大型魚類`進入釣具店時，`席菲`會幫忙製作`魚拓`。

<table>
    <thead>
        <tr>
            <td>大尾魚</td>
            <td>皺鰓鯊</td>
            <td>皇帶魚</td>
            <td>巨狗脂鯉</td>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><img src= "/images/post/Season_of_Story/Sprite/icon_5000190.png"></td>
            <td><img src= "/images/post/Season_of_Story/Sprite/icon_5000188.png"></td>
            <td><img src= "/images/post/Season_of_Story/Sprite/icon_5000187.png"></td>
            <td><img src= "/images/post/Season_of_Story/Sprite/icon_5000189.png"></td>
        </tr>
        <tr>
            <td><img src= "/images/post/Season_of_Story/Texture2D/tex_goods_21300.png"></td>
            <td><img src= "/images/post/Season_of_Story/Texture2D/tex_goods_21310.png"></td>
            <td><img src= "/images/post/Season_of_Story/Texture2D/tex_goods_21320.png"></td>
            <td><img src= "/images/post/Season_of_Story/Texture2D/tex_goods_21330.png"></td>
        </tr>
    </tbody>
</table>

## MOD資料庫
### 調用方法
+ 增加[釣具店](../doraemon-story-shop-21300-sandy-tackle-shop)商店響應方法：<br>`FarmWorkState.AddFishingTackleShopResponse(ResponseModel, NpcModel) : void @0600135C`
    + 取得[釣具店](../doraemon-story-shop-21300-sandy-tackle-shop/#販售資料)商品資料：<br>`FarmWorkState.GetFishingTackleShopItemDatas() : ShopItemDataModel[] @0600135D`

### 商店功能集成介面
+ 取得[釣具店](../doraemon-story-shop-21300-sandy-tackle-shop/#販售資料)商店所有資料：<br>`ShopMasterCollection.GetAllFishingTackleShopDatas() : ShopMasterModel[] @06002BEC`

### 商店模板
+ 商店主模板類：`ShopMasterModel`
    + [魚餌](../doraemon-story-shop-21300-sandy-tackle-shop/#魚餌)商店

### 商店資料
+ 釣具店商店資料類：`CFishingTackleShopData`
    + [魚餌](../doraemon-story-shop-21300-sandy-tackle-shop/#魚餌)

### 商品模板
+ 商品模板類：`ShopItemDataModel`
    + [魚餌](../doraemon-story-shop-21300-sandy-tackle-shop/#魚餌)