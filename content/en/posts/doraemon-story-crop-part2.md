---
title: 播種
date: 2020-04-03T16:25:02+08:00
description: 播種的方法與種子的品質轉換
draft: false
hideToc: false
enableToc: false
enableTocContent: true
author: 伊琉沙 AKA 哇咔咔
authorEmoji: 👩🏿‍🚀
tags: 
- 耕作
- 作物
series:
- 哆啦A夢牧場物語
categories:
- 哆啦A夢
image: images/post/Season_of_Story/Sprite/ground_90310010.png
libraries:
- katex
---
<mark>最後更新：2020/05/04</mark>

## 播種
+ `播種`是將`作物種子`播撒在[耕作地面](../doraemon-story-mod-ground/#耕作地面)的動作，為`耕作`過程的`第二步`。
    + `作物種子`可以透過[雜貨店](../doraemon-story-shop-20700-knick-knacks-general-store/#作物種子)購買或[種子機](../)製作。
    + [耕作地面](../doraemon-story-mod-ground/#耕作地面)只允許播撒`當季作物`或`常年作物`的種子。
        + 在[溫室]()的[耕作地面](../doraemon-story-mod-ground/#耕作地面)則以溫室裡面的季節決定。
        + 需要注意的是，非`常年作物`換季時會`枯萎`，`播種`前最好計算作物的`收成天數`。
+ `播種`後，`種子`的`品質⭐️`會轉換為作物的[品質分](../doraemon-story-mod-crop/#品質分)。
    + `品質⭐️`為遊戲中[品質等級](../doraemon-story-mod-item/#品質等級)的呈現方式。
        + `⭐️0.5`為最低品質，[品質等級](../doraemon-story-mod-item/#品質等級)為`1`。
        + [品質等級](../doraemon-story-mod-item/#品質等級)每增加一級，`品質⭐️`增加`0.5⭐️`。
    + [品質分](../doraemon-story-mod-crop/#品質分)為作物在[耕作地面](../doraemon-story-mod-ground/#耕作地面)生長時的隱藏數值。
        + [品質分初始值](../doraemon-story-mod-crop/#作物模板)為`1`。
        + [最大品質分](../doraemon-story-mod-crop/#最大品質分)為`500`。
+ `播種`時不需使用任何工具，但大雄得到[超人手套](../doraemon-story-tool-hoe)後能進行更大範圍的`播種`。

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

## 分類索引
<table>
    <thead>
        <tr>
            <td colspan="10">耕作</td>        
        </tr>
    </thead>
    <tr>
        <td align="center"><a href="../doraemon-story-crop-part1"><img width="64px" src= "/images/post/Season_of_Story/Sprite/ground_90310000.png">耕地</a></td>
        <td align="center"><a href="../doraemon-story-crop-part2"><img width="64px" src= "/images/post/Season_of_Story/Sprite/ground_90310010.png">播種</a></td>
        <td align="center"><a href="../doraemon-story-crop-part3"><img width="64px" src= "/images/post/Season_of_Story/Sprite/ground_90310020.png">施肥</a></td>
        <td align="center"><a href="../doraemon-story-crop-part4"><img width="64px" src= "/images/post/Season_of_Story/Sprite/ground_90310021.png">澆水</a></td>        
        <td align="center"><a href="../doraemon-story-crop-part5"><img width="103px" src= "/images/post/Season_of_Story/Sprite/Crop_90120602.png">成長</a></td>
        <td align="center"><a href="../doraemon-story-crop-part6"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_1001030.png">收成收割</a></td>
        <td align="center"><a href="../#溫室種植"><img width="64px" src= "/images/post/Season_of_Story/Texture2D/tex_bg_1230_020.png">溫室種植</a></td>
    </tr>
    <tr>
        <td align="center"><a href="../doraemon-story-tool-hoe"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_1001005.png">鋤頭</a></td>
        <td align="center" colspan="2"><a href="../doraemon-story-secret-gadget-farming/#超人手套"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_1002130.png">超人手套</a></td>
        <td align="center"><a href="../doraemon-story-tool-watering-can"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_1001025.png">澆水壺</a></td>
        <td align="center"><a href="../doraemon-story-secret-gadget-farming/#瞬間成長劑"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_1104080.png">瞬間成長劑</a></td>
        <td align="center"><a href="../doraemon-story-tool-scythe"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_1001035.png">鐮刀</a></td>
        <td align="center"><a href="../doraemon-story-secret-gadget-farming/#季節罐頭"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_1104000.png">季節罐頭</a></td>
    </tr>
    <tr>
        <td></td>
        <td align="center"><a href="../doraemon-story-shop-20700-knick-knacks-general-store/#作物種子"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_2000501.png">作物種子</a></td>
        <td align="center"><a href="../doraemon-story-shop-20700-knick-knacks-general-store/#肥料"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_1103001.png">肥料</a></td>
        <td align="center"><a href="../doraemon-story-secret-gadget-farming/#迷你雨雲"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_7063010.png">迷你雨雲</a></td>
        <td align="center"><a href="../doraemon-story-crop-grow"><img width="113px" src= "/images/post/Season_of_Story/Sprite/Crop_90110405.png">成長資料</a></td>
        <td align="center"><a href="../doraemon-story-shipping-prices-crops"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_3000205.png">出貨價格</a></td>
        <td></td>
    </tr>
</table>
