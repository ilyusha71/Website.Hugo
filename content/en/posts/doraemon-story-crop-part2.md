---
title: "作物施肥效果"
date: 2020-04-03T17:16:52+08:00
description: 作物的施肥效果對作物品質的影響
draft: false
hideToc: false
enableToc: false
enableTocContent: true
author: 伊琉沙 AKA 哇咔咔
authorEmoji: 👩🏿‍🚀
tags: 
- 作物
series:
- 哆啦A夢牧場物語
categories:
- 哆啦A夢
image: images/post/Season_of_Story/Sprite/icon_1103001.png
libraries:
- katex
---
<mark>最後更新：2020/04/27</mark>

## 耕種系統與作物圖鑑
<table>
    <thead>
        <tr>
            <td colspan="10">耕種系統與作物圖鑑</td>        
        </tr>
    </thead>
    <tr>
        <td align="center"><a href="../doraemon-story-shop-20700-knick-knacks-general-store/#作物種子"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_2000100.png">作物種子</a></td>
        <td align="center"><a href="../doraemon-story-crop-part1"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_1001000.png">播種與收成</a></td>
        <td align="center"><a href="../#鋤頭選用"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_1001005.png">鋤頭選用</a></td>
        <td align="center"><a href="../#澆水壺選用"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_1001025.png">澆水壺選用</a></td>
        <td align="center"><a href="../doraemon-story-crop-part2"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_1103001.png">施肥效果</a></td>
        <td align="center"><a href="../doraemon-story-crop-part3"><img width="136px" src= "/images/post/Season_of_Story/Sprite/Crop_90110402.png">成長過程</a></td>
        <td align="center"><a href="../doraemon-story-crop-grow"><img width="113px" src= "/images/post/Season_of_Story/Sprite/Crop_90110405.png">成長資料</a></td>
        <td align="center"><a href="../doraemon-story-shipping-prices-crops"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_3000205.png">出貨價格</a></td>
        <td align="center"><a href="../#溫室種植"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_1104000.png">溫室種植</a></td>
    </tr>
</table>

## 作物施肥效果
+ 一開始從雜貨店買的種子品質都是⭐️0.5，如果不施肥，則作物收成的時候仍會是⭐️0.5。
+ 若要讓作物的品質上升，在遊戲中可以選擇`肥料`或`高級肥料`來進行施肥。
+ 高級肥料的價格是一般肥料的`兩倍`，但`施肥效果`也是兩倍。

### 肥料販售資訊
<table>
    <thead>
        <tr>
            <td></td>
            <td>物品名稱</td>
            <td>販售價格</td>
        </tr>
    </thead>
    <tr>
        <td><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_1103000.png"></td>
        <td>肥料</td>
        <td><img align="left" src= "/images/post/Season_of_Story/Sprite/Icon_Money_01.png">20</td>
    </tr>
    <tr>
        <td><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_1103001.png"></td>
        <td>高級肥料</td>
        <td><img align="left" src= "/images/post/Season_of_Story/Sprite/Icon_Money_01.png">40</td>
    </tr>
</table>

### 肥料效果源代碼
```C#
private static readonly Dictionary<int, float> UpgradeValueTable = new Dictionary<int, float>
{
    {
        Item.ID_FERTILIZER,
        100f
    },
    {
        Item.ID_HIGH_QUALITY_FERTILIZER,
        200f
    }
};
```

### 施肥品質提升計算公式
品質提升方法（`CropModel.Upgrade(int item_id)`）：
```C#
public void Upgrade(int item_id)
{
    if (this.CanHarvest || this.IsWithered)
    {
        return;
    }
    this.mQuality += Mathf.CeilToInt(Crop.GetUpgradeValue(item_id) / (float)this.Master.HarvestDays);
    if (this.mQuality > Crop.MAX_QUALITY)
    {
        this.mQuality = Crop.MAX_QUALITY;
    }
}
```
品質提升方法的計算公式：
$$提升的品質分=無條件進位（\dfrac {肥料效果}{收成天數}）$$

#### 草莓的施肥提升比較
以雜貨店買的***草莓種子***為例，草莓的收成天數（`CropMasterModel.HarvestDays`）為15天：
*******
若全程使用一般肥料，則每天品質均增加7分，成熟時品質為106分，採收後的草莓為⭐️1.5。
$$一般肥料提升的品質分=無條件進位（\dfrac {一般肥料效果}{收成天數}）=無條件進位（\dfrac {100}{15}）=7$$
*******
若改用高級肥料，每天品質則增加14分，成熟時品質為211分，採收後的草莓為⭐️2.5。
$$高級肥料提升的品質分=無條件進位（\dfrac {高級肥料效果}{收成天數}）=無條件進位（\dfrac {200}{15}）=14$$
*******
<mark>事實上，根據作物資料的分析結果，在遊戲中所有作物在收成後最多都只會增加2⭐️。</mark>
亦即全程使用高級肥料，也要進行三次播種才會變成⭐️5（注意每次播種都會先降0.5⭐️）。
+ 第一次播種到收成：`⭐️0.5`→`⭐️2.5`
+ 第二次播種到收成：`⭐️2`→`⭐️4`
+ 第三次播種到收成：`⭐️3.5`→`⭐️5`