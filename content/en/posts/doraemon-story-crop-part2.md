---
title: 播種與超人手套的使用
date: 2020-04-03T16:25:02+08:00
description: 播種與超人手套的使用
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

## 播種
+ 作物在播種前必須滿足兩項條件：
    1. 空的`農地`，可以透過[耕地](../doraemon-story-crop-part1)翻新農地。
    2. `作物種子`，取得方式有二：
        1. 可在[雜貨店](../doraemon-story-shop-20700-knick-knacks-general-store/#作物種子)進行購買。
        2. 透過[種子機](../)製作。
+ `農地`只允許播種`當季作物`或`常年作物`的種子。
    + 在`溫室`的環境下也必須轉換特定季節。
+ 需要特別注意的是，非`常年`成長的作物換季時會`枯萎`，播種前最好計算作物的`收成天數`。
+ 播種後，`種子`的`品質⭐️`會轉換為作物的[品質分](../doraemon-story-mod-crop/#品質分)。
    + `品質⭐️`為遊戲中[品質等級](../doraemon-story-mod-item/#品質等級)的呈現方式。
        + `⭐️0.5`為最低品質，[品質等級](../doraemon-story-mod-item/#品質等級)為`1`。
        + [品質等級](../doraemon-story-mod-item/#品質等級)每增加一級，`品質⭐️`增加`0.5⭐️`。
    + [品質分](../doraemon-story-mod-crop/#品質分)為作物在`農地`生長時的隱藏數值。
        + [品質分初始值](../doraemon-story-mod-crop/#作物模板)為`1`。
        + [最大品質分](../doraemon-story-mod-crop/#最大品質分)為`500`。
+ [品質分](../doraemon-story-mod-crop/#品質分)需要透過[施肥](../doraemon-story-crop-part3)才會增加。
+ 直到[收成](../doraemon-story-crop-part6)時才會再轉換回來。

### 播種品質轉換公式
+ 參考[播種方法](../doraemon-story-mod-crop/#播種方法)。
+ [品質轉換率](../doraemon-story-mod-crop/#品質轉換率)是作物[最大品質分](../doraemon-story-mod-crop/#最大品質分)與物品[最大品質等級](../doraemon-story-mod-item/#最大品質等級)的比，為一個常數：`50`。

$$品質分=(種子品質等級-2)\times{品質轉換率}$$
$$品質轉換率=\dfrac {作物最大品質分}{物品最大品質等級}=\dfrac {500}{10}=50$$

### 播種品質轉換量化表
<table>
    <thead>
        <tr>
            <td>種子品質⭐️</td>
            <td>種子品質等級</td>
            <td>作物品質分</td>
            <td>作物品質⭐️</td>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>⭐️0.5</td>
            <td>1</td>
            <td>0</td>
            <td>⭐️0.5</td>
        </tr>
        <tr>
            <td>⭐️1</td>
            <td>2</td>
            <td>0</td>
            <td>⭐️0.5</td>
        </tr>
        <tr>
            <td>⭐️1.5</td>
            <td>3</td>
            <td>50</td>
            <td>⭐️1</td>
        </tr>
        <tr>
            <td>⭐️2</td>
            <td>4</td>
            <td>100</td>
            <td>⭐️1.5</td>
        </tr>
        <tr>
            <td>⭐️2.5</td>
            <td>5</td>
            <td>150</td>
            <td>⭐️2</td>
        </tr>
        <tr>
            <td>⭐️3</td>
            <td>6</td>
            <td>200</td>
            <td>⭐️2.5</td>
        </tr>
        <tr>
            <td>⭐️3.5</td>
            <td>7</td>
            <td>250</td>
            <td>⭐️3</td>
        </tr>
        <tr>
            <td>⭐️4</td>
            <td>8</td>
            <td>300</td>
            <td>⭐️3.5</td>
        </tr>
        <tr>
            <td>⭐️4.5</td>
            <td>9</td>
            <td>350</td>
            <td>⭐️4</td>
        </tr>
        <tr>
            <td>⭐️5</td>
            <td>10</td>
            <td>400</td>
            <td>⭐️4.5</td>
        </tr>
    </tbody>
</table>

所以`種子`播種後作物的[品質等級](../doraemon-story-mod-crop/#品質等級)就會直接先降`1級`，相當於`品質⭐️`降`0.5⭐️`。

#### 超人手套蓄力效果
<table>
    <thead>
        <tr>
            <td align="center">超人手套</td>
        </tr>
    </thead>
    <tr>
        <td align="center"><img width="100px" src= "/images/post/Season_of_Story/Sprite/icon_1002130.png"></td>
    </tr>
</table>

+ `超人手套`可以在劇情[鎮長第2話 獎勵事件：獲得超人手套](../doraemon-story-09/#獲得超人手套)取得。
+ 蓄力分為`Lv.1`至`Lv.3`三段。
+ 蓄力段數越高消耗的體力越多，但播種的範圍也越大。

<table>
    <thead>
        <tr>
            <td align="center">蓄力段數</td>            
            <td align="center">體力消耗</td>
            <td align="center">播種範圍</td>
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