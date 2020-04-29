---
title: "施肥與品質提升"
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
<mark>最後更新：2020/04/29</mark>

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

## 作物施肥
+ 一開始從[雜貨店](../doraemon-story-shop-20700-knick-knacks-general-store)買的種子品質都是⭐️0.5，如果不施肥，則作物[收成](../doraemon-story-crop-part6)的時候仍會是⭐️0.5。
+ 若要讓作物的[品質上升](../doraemon-story-crop-part3/#品質提升計算公式)，在遊戲中可以選擇`肥料`或`高級肥料`來進行施肥。
+ `高級肥料`的價格是一般`肥料`的`兩倍`，但`施肥效果`也是兩倍。
    + 參考[施肥品質提升表](../doraemon-story-mod-crop/#施肥品質提升表)。

### 肥料
+ 肥料的取得途徑：
    1. [雜貨店](../doraemon-story-shop-20700-knick-knacks-general-store/#肥料)購買。
    2. 透過[釣魚](../doraemon-story-live-fishing)獲得。
    3. 跑腿任務獎勵。

<table>
    <thead>
        <tr>
            <td align="center"></td>
            <td align="center">物品名稱</td>
            <td align="center">販售價格</td>
            <td align="center">肥料效果</td>
        </tr>
    </thead>
    <tr>
        <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_1103000.png"></td>
        <td align="center">肥料</td>
        <td align="center"><img align="left" src= "/images/post/Season_of_Story/Sprite/Icon_Money_01.png">20</td>
        <td align="center">100</td>
    </tr>
    <tr>
        <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_1103001.png"></td>
        <td align="center">高級肥料</td>
        <td align="center"><img align="left" src= "/images/post/Season_of_Story/Sprite/Icon_Money_01.png">40</td>
        <td align="center">200</td>
    </tr>
</table>

### 品質提升計算公式
+ 參考[施肥方法](../doraemon-story-mod-crop/#施肥方法)
+ 參考[品質提升方法](../doraemon-story-mod-crop/#品質提升方法)。

$$提升的品質分=無條件進位（\dfrac {肥料效果}{收成天數}）$$

#### 鳳梨的施肥效果比較
+ 以[雜貨店](../doraemon-story-shop-20700-knick-knacks-general-store)買的⭐️0.5`鳳梨種子`來測試。
+ 已知鳳梨的`收成天數`為`13天`。

##### 使用肥料
若全程使用`肥料`，每天[品質分](../doraemon-story-mod-crop/#品質分)均增加`8分`，`成熟`時[品質分](../doraemon-story-mod-crop/#品質分)為`105分`，[收成](../doraemon-story-crop-part6)後的鳳梨為`⭐️1.5`。
$$肥料提升的品質分=無條件進位(\dfrac {肥料效果}{收成天數})=無條件進位(\dfrac {100}{13})=8$$
$$成熟時品質分=1+(收成天數\times肥料提升的品質分)=1+(13\times8)=105$$

##### 使用高級肥料
若改用`高級肥料`，每天[品質分](../doraemon-story-mod-crop/#品質分)則增加`16分`，`成熟`時[品質分](../doraemon-story-mod-crop/#品質分)為`209分`，採收後的鳳梨為`⭐️2.5`。
$$高級肥料提升的品質分=無條件進位(\dfrac {高級肥料效果}{收成天數})=無條件進位(\dfrac {200}{13})=16$$
$$成熟時品質分=1+(收成天數\times高級肥料提升的品質分)=1+(13\times16)=209$$

### 結論
事實上，計算遊戲中37種作物[成長資料](../doraemon-story-crop-grow)的數據結果表明，在[收成](../doraemon-story-crop-part6)後最多都只會增加`2⭐️`。
亦即全程使用`高級肥料`，也要進行三次[播種](../doraemon-story-crop-part2)才會變成`⭐️5`（注意每次[播種](../doraemon-story-crop-part2)都會先降`0.5⭐️`）。
+ 第一次[播種](../doraemon-story-crop-part2)到[收成](../doraemon-story-crop-part6)：`⭐️0.5`→`⭐️2.5`
+ 第二次[播種](../doraemon-story-crop-part2)到[收成](../doraemon-story-crop-part6)：`⭐️2`→`⭐️4`
+ 第三次[播種](../doraemon-story-crop-part2)到[收成](../doraemon-story-crop-part6)：`⭐️3.5`→`⭐️5`

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
+ 蓄力段數越高消耗的體力越多，但施肥的範圍也越大。

<table>
    <thead>
        <tr>
            <td align="center">蓄力段數</td>            
            <td align="center">體力消耗</td>
            <td align="center">施肥範圍</td>
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