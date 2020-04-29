---
title: "收成、收割與鐮刀的使用"
date: 2020-04-28T17:25:02+08:00
description: 收成、收割與鐮刀的使用
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
image: images/post/Season_of_Story/Sprite/icon_1001000.png
libraries:
- katex
---
<mark>最後更新：2020/04/30</mark>

## 農耕與作物
<table>
    <thead>
        <tr>
            <td colspan="10">農耕與作物</td>        
        </tr>
    </thead>
    <tr>
        <td align="center"><a href="../doraemon-story-crop-part1"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_1001000.png">耕地</a></td>
        <td align="center"><a href="../doraemon-story-crop-part2"><img width="98px" src= "/images/post/Season_of_Story/Sprite/Crop_90110400.png">播種</a></td>
        <td align="center"><a href="../doraemon-story-crop-part3"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_1103001.png">施肥</a></td>
        <td align="center"><a href="../doraemon-story-crop-part4"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_1001020.png">澆水</a></td>        
        <td align="center"><a href="../doraemon-story-crop-part5"><img width="136px" src= "/images/post/Season_of_Story/Sprite/Crop_90110402.png">成長</a></td>
        <td align="center"><a href="../doraemon-story-crop-part6"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_1001030.png">收成收割</a></td>
        <td align="center"><a href="../doraemon-story-shipping-prices-crops"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_3000205.png">出貨價格</a></td>
    </tr>
    <tr>
        <td align="center"><a href="../doraemon-story-crop-part1/#鋤頭"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_1001005.png">鋤頭</a></td>
        <td align="center"><a href="../doraemon-story-shop-20700-knick-knacks-general-store/#作物種子"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_2000501.png">作物種子</a></td>
        <td align="center"><a href="../doraemon-story-shop-20700-knick-knacks-general-store/#肥料"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_1103000.png">肥料</a></td>
        <td align="center"><a href="../doraemon-story-crop-part4/#澆水壺"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_1001025.png">澆水壺</a></td>        
        <td align="center"><a href="../doraemon-story-crop-grow"><img width="113px" src= "/images/post/Season_of_Story/Sprite/Crop_90110405.png">成長資料</a></td>
        <td align="center"><a href="../doraemon-story-crop-part6/#鐮刀"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_1001035.png">鐮刀</a></td>
        <td align="center"><a href="../#溫室種植"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_1104000.png">溫室種植</a></td>
    </tr>
</table>

## 收成
+ 作物[成長](../doraemon-story-crop-part5)到`成熟階段`即可進行收成。
+ 收成後，作物的[品質分](../doraemon-story-mod-crop/#品質分)會轉換為作物的`品質⭐️`。
    + `品質⭐️`為遊戲中[品質等級](../doraemon-story-mod-item/#品質等級)的呈現方式。
        + `⭐️0.5`為最低品質，[品質等級](../doraemon-story-mod-item/#品質等級)為`1`。
        + [品質等級](../doraemon-story-mod-item/#品質等級)每增加一級，`品質⭐️`增加`0.5⭐️`。
    + [品質分](../doraemon-story-mod-crop/#品質分)為作物在`農地`生長時的隱藏數值。
        + [品質分初始值](../doraemon-story-mod-crop/#作物模板)為`1`。
        + [最大品質分](../doraemon-story-mod-crop/#最大品質分)為`500`。
+ 需要特別注意的是，非`常年作物`換季時會`枯萎`，所以當季作物務必要在當季30日以前收成。

### 克魯波克魯的幫忙
+ `克魯波克魯`到齊後，可以委託`婭卡`幫忙收成。

<table>
    <thead>
        <tr>
            <td align="center">婭卡</td>
        </tr>
    </thead>
    <tr>
        <td align="center"><img width="100px" src= "/images/post/Season_of_Story/Sprite/icon_201041260.png"></td>
    </tr>
</table>

### 收成品質轉換公式
+ 若收成時作物[品質分](../doraemon-story-mod-crop/#品質分)已達[最大品質分](../doraemon-story-mod-crop/#最大品質分)（`500`）時，作物[品質等級](../doraemon-story-mod-crop/#品質等級)為物品的[最大品質等級](../doraemon-story-mod-item/#最大品質等級)（`10`）。
+ 若非，則以下列公式計算，其中，[品質轉換率](../doraemon-story-mod-crop/#品質轉換率)是作物[最大品質分](../doraemon-story-mod-crop/#最大品質分)與物品[最大品質等級](../doraemon-story-mod-item/#最大品質等級)的比，為一個常數：`50`。

$$作物品質等級=\dfrac{品質分}{品質轉換率}+1$$
$$品質轉換率=\dfrac {作物最大品質分}{物品最大品質等級}=\dfrac {500}{10}=50$$

### 收成品質轉換量化表
<table>
    <thead>
        <tr>
            <td>品質分範圍</td>
            <td>品質等級</td>
            <td>品質⭐️</td>
            <td></td>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>1~49</td>
            <td>1</td>
            <td>⭐️0.5</td>
            <td><img align="left" width="36px" src= "/images/post/Icon_Star_Half.png"></td>
        </tr>
        <tr>
            <td>50~99</td>
            <td>2</td>
            <td>⭐️1.0</td>
            <td><img align="left" width="36px" src= "/images/post/Icon_Star_Full.png"></td>
        </tr>
        <tr>
            <td>100~149</td>
            <td>3</td>
            <td>⭐️1.5</td>
            <td><img align="left" width="36px" src= "/images/post/Icon_Star_Full.png"><img align="left" width="36px" src= "/images/post/Icon_Star_Half.png"></td>
        </tr>
        <tr>
            <td>150~199</td>
            <td>4</td>
            <td>⭐️2.0</td>
            <td><img align="left" width="36px" src= "/images/post/Icon_Star_Full.png"><img align="left" width="36px" src= "/images/post/Icon_Star_Full.png"></td>
        </tr>
        <tr>
            <td>200~249</td>
            <td>5</td>
            <td>⭐️2.5</td>
            <td><img align="left" width="36px" src= "/images/post/Icon_Star_Full.png"><img align="left" width="36px" src= "/images/post/Icon_Star_Full.png"><img align="left" width="36px" src= "/images/post/Icon_Star_Half.png"></td>
        </tr>
        <tr>
            <td>250~299</td>
            <td>6</td>
            <td>⭐️3.0</td>
            <td><img align="left" width="36px" src= "/images/post/Icon_Star_Full.png"><img align="left" width="36px" src= "/images/post/Icon_Star_Full.png"><img align="left" width="36px" src= "/images/post/Icon_Star_Full.png"></td>
        </tr>
        <tr>
            <td>300~349</td>
            <td>7</td>
            <td>⭐️3.5</td>
            <td><img align="left" width="36px" src= "/images/post/Icon_Star_Full.png"><img align="left" width="36px" src= "/images/post/Icon_Star_Full.png"><img align="left" width="36px" src= "/images/post/Icon_Star_Full.png"><img align="left" width="36px" src= "/images/post/Icon_Star_Half.png"></td>
        </tr>
        <tr>
            <td>350~399</td>
            <td>8</td>
            <td>⭐️4.0</td>
            <td><img align="left" width="36px" src= "/images/post/Icon_Star_Full.png"><img align="left" width="36px" src= "/images/post/Icon_Star_Full.png"><img align="left" width="36px" src= "/images/post/Icon_Star_Full.png"><img align="left" width="36px" src= "/images/post/Icon_Star_Full.png"></td>
        </tr>
        <tr>
            <td>400~449</td>
            <td>9</td>
            <td>⭐️4.5</td>
            <td><img align="left" width="36px" src= "/images/post/Icon_Star_Full.png"><img align="left" width="36px" src= "/images/post/Icon_Star_Full.png"><img align="left" width="36px" src= "/images/post/Icon_Star_Full.png"><img align="left" width="36px" src= "/images/post/Icon_Star_Full.png"><img align="left" width="36px" src= "/images/post/Icon_Star_Half.png"></td>
        </tr>
        <tr>
            <td>450~500</td>
            <td>10</td>
            <td>⭐️5.0</td>
            <td><img align="left" width="36px" src= "/images/post/Icon_Star_Full.png"><img align="left" width="36px" src= "/images/post/Icon_Star_Full.png"><img align="left" width="36px" src= "/images/post/Icon_Star_Full.png"><img align="left" width="36px" src= "/images/post/Icon_Star_Full.png"><img align="left" width="36px" src= "/images/post/Icon_Star_Full.png"></td>
        </tr>
    </tbody>
</table>

## 收割
+ `常年`生長的作物，例如`乾草`與`小麥`需要收割才能收成。
+ `枯萎`的作物也需要透過收割才能清除。
+ 收割需使用[鐮刀](../doraemon-story-crop-part6/#鐮刀)，高等級的鐮刀能更快更大範圍的進行收割。

<table>
    <thead>
        <tr>
            <td align="center">乾草</td>
            <td align="center">小麥</td>
        </tr>
    </thead>
    <tr>
        <td align="center"><img width="100px" src= "/images/post/Season_of_Story/Sprite/Crop_90150003.png"></td>
        <td align="center"><img width="100px" src= "/images/post/Season_of_Story/Sprite/Crop_90150103.png"></td>
    </tr>
</table>

### 鐮刀
+ 鐮刀`等級`分為六等，`Lv.0`至`Lv.5`：
    + `Lv.0`：`破舊的鐮刀`
    + `Lv.1`：`銅鐮刀`
    + `Lv.2`：`鐵鐮刀`
    + `Lv.3`：`銀鐮刀`
    + `Lv.4`：`金鐮刀`
    + `Lv.5`：`輕輕鬆鬆鐮刀`
+ 鐮刀可以在[打鐵店](../doraemon-story-shop-21100-anvil-blacksmith-shop)進行[升級工具](../doraemon-story-shop-21100-anvil-blacksmith-shop/#升級工具)。

#### 鐮刀蓄力效果
<table>
    <thead>
        <tr>
            <td align="center">蓄力段數</td>            
            <td align="center">體力消耗</td>
            <td align="center">收割範圍</td>
        </tr>
    </thead>
    <tr>
        <td align="center">Lv.0</td>
        <td align="center">1</td>
        <td align="center">前方1格</td>
    </tr>
    <tr>
        <td align="center">Lv.1</td>
        <td align="center">2</td>
        <td align="center">前方2格</td>
    </tr>
    <tr>
        <td align="center">Lv.2</td>
        <td align="center">3</td>
        <td align="center">前方3格</td>
    </tr>
    <tr>
        <td align="center">Lv.3</td>
        <td align="center">4</td>
        <td align="center">前方9格</td>
    </tr>
</table>

#### 各等級鐮刀的收割效率
<table>
    <thead>
        <tr>
            <td align="center">鐮刀等級</td>
            <td align="center"></td>
            <td align="center">鐮刀名稱</td>
            <td align="center">蓄力速度</td>
            <td align="center">最大蓄力段數</td>            
            <td align="center">最大體力消耗</td>
            <td align="center">最大收割範圍</td>
        </tr>
    </thead>
    <tr>
        <td align="center">Lv.0</td>
        <td align="center"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_1001030.png"></td>
        <td align="center">破舊鐮刀</td>
        <td align="center">Lv.0</td>
        <td align="center">Lv.0</td>
        <td align="center">1</td>
        <td align="center">前方1格</td>
    </tr>
    <tr>
        <td align="center">Lv.1</td>
        <td align="center"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_1001031.png"></td>
        <td align="center">銅鐮刀</td>
        <td align="center">Lv.0</td>
        <td align="center">Lv.1</td>
        <td align="center">2</td>
        <td align="center">前方2格</td>
    </tr>
    <tr>
        <td align="center">Lv.2</td>
        <td align="center"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_1001032.png"></td>
        <td align="center">鐵鐮刀</td>
        <td align="center">Lv.0</td>
        <td align="center">Lv.2</td>
        <td align="center">3</td>
        <td align="center">前方3格</td>
    </tr>
    <tr>
        <td align="center">Lv.3</td>
        <td align="center"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_1001033.png"></td>
        <td align="center">銀鐮刀</td>
        <td align="center">Lv.1</td>
        <td align="center">Lv.2</td>
        <td align="center">3</td>
        <td align="center">前方3格</td>
    </tr>
    <tr>
        <td align="center">Lv.4</td>
        <td align="center"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_1001034.png"></td>
        <td align="center">金鐮刀</td>
        <td align="center">Lv.1</td>
        <td align="center">Lv.3</td>
        <td align="center">4</td>
        <td align="center">前方9格</td>
    </tr>
    <tr>
        <td align="center">Lv.5</td>
        <td align="center"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_1001035.png"></td>
        <td align="center">輕輕鬆鬆鐮刀</td>
        <td align="center">Lv.1</td>
        <td align="center">Lv.3</td>
        <td align="center">1</td>
        <td align="center">前方9格</td>
    </tr>
</table>