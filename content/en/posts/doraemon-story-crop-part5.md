---
title: "作物的成長過程"
date: 2020-04-03T17:37:16+08:00
description: 作物成長過程的相關計算
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
image: images/post/Season_of_Story/Sprite/Crop_90120602.png
libraries:
- katex
---
<mark>最後更新：2020/05/04</mark>

## 成長機制
+ 作物的`成長`會在[澆水](../doraemon-story-crop-part4/#澆水)之後立刻進行。
+ 作物的`成長機制`與作物[成長資料](../doraemon-story-crop-grow)的三個參數有關：
    + [收成天數](../doraemon-story-crop-part5/#收成天數)
    + [成長階數](../doraemon-story-crop-part5/#成長階數)
    + [減少階數](../doraemon-story-crop-part5/#減少階數)

### 收成天數
+ `收成天數`是作物從`種子`到`成熟`所需的天數。
+ 作物的`成長過程`是以[成長值](../doraemon-story-mod-crop/#成長值)計算。
    + 作物剛[播種](../doraemon-story-crop-part2)時，[成長值](../doraemon-story-mod-crop/#成長值)為`0`。
+ 每天作物在[澆水](../doraemon-story-crop-part4)後[成長值](../doraemon-story-mod-crop/#成長值)都會增加`1`。
    + 參考[成長方法](../doraemon-story-mod-crop/#成長方法)。
+ 當[成長值](../doraemon-story-mod-crop/#成長值)達到`收成天數`時，作物就算`成熟`，可以進行[收成收割](../doraemon-story-crop-part6)。
    + 參考[能否收成判斷方法](../doraemon-story-mod-crop/#能否收成判斷方法)。
+ 以收成天數為6天的`洋蔥`來說，洋蔥種子在第一天[播種](../doraemon-story-crop-part2)後，第六天就能`成熟`。
+ 由於作物的成長環節是在[澆水](../doraemon-story-crop-part4)之後，第一天澆水後，[成長值](../doraemon-story-mod-crop/#成長值)就會變成`1`，所以實際上經歷的`成長天數`只有5天。

$$成長天數=收成天數-1$$$$收成日=播種日+成長天數$$

### 成長階數
+ `成長階數`是作物在`成長過程`所需經歷的階段總數，也相當於作物外觀變化的總數。
    + 整個`成長過程`包含若干個`成長階段`與最終的`成熟階段`。
    + 作物的成長階數大多為4階至6階。
    + 在37種作物中，番茄擁有最多7階的成長階數，亦即6個`成長階段`與1個`成熟階段`。
+ `成長過程`的第1階段為剛[播種](../doraemon-story-crop-part2)時的`種子階段`，也是第一個`成長階段`。
    + 當作物經歷完所有的`成長階段`後就會進入`成長過程`的最後一個階段，`成熟階段`。
    + 當作物`成熟`時，作物就能進行[收成收割](../doraemon-story-crop-part6)。
+ `成長過程`每個階段所需最低的[成長值](../doraemon-story-mod-crop/#成長值)為`成長值門檻`，作物達到`成長值門檻`的那一天為該階段的`變化日`。

$$成長階段總數=成長階數-成熟階段$$

#### 成長階段的進階天數
+ 在作物成熟前，每個`成長階段`的`進階天數`將透過`收成天數`平均分配。
    + [成長進階方法](../doraemon-story-mod-crop/#成長進階方法)。
+ 若還有`剩餘天數`則從最後一個`成長階段`開始倒序分配，原理如下：
    1. `收成天數`平均分配後的天數為`基本進階天數`，分配完的餘數為`剩餘進階天數`。
    2. `剩餘進階天數`將依`成長階段`的順序`倒序`分配。
    3. 分配完成後可得出`進階天數`是否增加的`分界值`。
    4. 因此當作物的[成長值](../doraemon-story-mod-crop/#成長值)達到`分界值`後，每個`成長階段`的`進階天數`都會多1天。
+ 由於作物在[播種](../doraemon-story-crop-part2)的當天就能透過[澆水](../doraemon-story-crop-part4)進行成長，所以`種子階段`的`進階天數`實際上會少一天。
+ 最後所有`成長階段`的`進階天數`加總即是作物的`成長天數`。

$$基本進階天數=\dfrac{收成天數}{成長階段總數}$$
$$剩餘進階天數=收成天數-(基本進階天數\times成長階段總數)$$
$$分界值=(成長階段總數-剩餘進階天數)\times基本進階天數$$
$$成長天數=\sum_{成長階段}進階天數$$

#### 鳳梨的成長計算
+ 已知
    + 鳳梨的`收成天數`為`13天`。
    + 鳳梨的`成長階數`為`6`。
+ 可得
    + 鳳梨的`成長天數`為`12天`。
    + 鳳梨的`基本進階天數`為`2天`。
    + 鳳梨的`剩餘進階天數`為`3天`。
    + 鳳梨的`分界值`為`4`。

<table>
    <thead>
        <tr>
            <td align="center" colspan="5">成長階段</td>
            <td align="center">成熟階段</td>
        </tr>
    </thead>
    <tr>
            <td align="center" class="breadcrumb">第1階段</td>
            <td align="center" class="breadcrumb">第2階段</td>
            <td align="center" class="breadcrumb">第3階段</td>
            <td align="center" class="breadcrumb">第4階段</td>
            <td align="center" class="breadcrumb">第5階段</td>
            <td align="center" class="breadcrumb">第6階段</td>
    </tr>
    <tr>
    　<td align="center"><img src= "/images/post/Season_of_Story/Sprite/Crop_90120600.png"></td>
    　<td align="center"><img src= "/images/post/Season_of_Story/Sprite/Crop_90120601.png"></td>
    　<td align="center"><img src= "/images/post/Season_of_Story/Sprite/Crop_90120602.png"></td>
    　<td align="center"><img src= "/images/post/Season_of_Story/Sprite/Crop_90120603.png"></td>
    　<td align="center"><img src= "/images/post/Season_of_Story/Sprite/Crop_90120604.png"></td>
    　<td align="center"><img src= "/images/post/Season_of_Story/Sprite/Crop_90120605.png"></td>
    </tr>
    <tr>
        <td align="center" colspan="5" class="breadcrumb">進階天數</td>
        <td align="center" class="breadcrumb">成熟</td>
    </tr>
    <tr>
        <td align="center">1天</td>
        <td align="center">2天</td>
        <td align="center">3天</td>
        <td align="center">3天</td>
        <td align="center">3天</td>
        <td align="center"></td>
    </tr>
    <tr>
        <td align="center" colspan="6" class="breadcrumb">成長值範圍</td>
    </tr>
    <tr>
        <td align="center">0~1</td>
        <td align="center">2~3</td>
        <td align="center">4~6</td>
        <td align="center">7~9</td>
        <td align="center">10~12</td>
        <td align="center">13</td>
    </tr>
    <tr>
        <td align="center" colspan="6" class="breadcrumb">變化日</td>
    </tr>
    <tr>
        <td align="center">第1天</td>
        <td align="center">第2天</td>
        <td align="center">第4天</td>
        <td align="center">第7天</td>
        <td align="center">第10天</td>
        <td align="center">第13天</td>
    </tr>
</table>

### 減少階數
+ `減少階數`是`成長過程`減少的階段數。
    + 部分作物[播種](../doraemon-story-crop-part2)後能多次收穫，為`多穫作物`。
    + `多獲作物`[收成收割](../doraemon-story-crop-part6)後會留下`後續作物`，直到[收成](../doraemon-story-crop-part6)次數達到多穫的次數。
    + `後續作物`不會從`種子階段`重新成長，而是會根據`減少階數`從`成熟階段`進行`降階`。
        + 例如成長階數為`6`、減少階數為`2`，則`後續作物`會`降階`到第4階段重新成長。

#### 再收成天數
+ `後續作物`重新成長到[收成](../doraemon-story-crop-part6)的天數為`再收成天數`.
+ `再收成天數`為`降階`減少的成長天數，等同於`減少的成長值`或`減少的施肥次數`。 
    + 參考[成長減少方法](../doraemon-story-mod-crop/#成長減少方法)。
+ `再收成天數`可透過`成長過程`的參數反推求得，原理如下：
    1. `降階`減少的各階段`進階天數`可以直接從`減少階數`與`基本進階天數`的乘積求得。
    2. 由於`成長階段`的`進階天數`還包括分配後的`剩餘進階天數`，需要再將其補上。
    3. `剩餘進階天數`分配的階段數可能比`降階`的階段數還多，所以只需補充`降階`的部分即可。
    4. 這些補充的`進階天數`為`補充進階天數`。
+ 與[播種](../doraemon-story-crop-part2)時的狀況類似，[收成](../doraemon-story-crop-part6)後的`後續作物`當天也能再次[澆水](../doraemon-story-crop-part4)進行成長，因此`降階`後所處成長階段的`進階天數`也會少一天。
+ 同理`再成長天數`也會比`再收成天數`少一天。
+ `降階`後的[成長值](../doraemon-story-mod-crop/#成長值)可以透過`再收成天數`進行反推。

$$若剩餘進階天數<=減少階數$$$$補充進階天數=剩餘進階天數$$
$$若剩餘進階天數>減少階數$$$$補充進階天數=減少階數$$
$$再收成天數=(基本進階天數\times減少階數)+補充進階天數$$$$再成長天數=再收成天數-1$$
$$降階後的成長值={收成天數}-{再收成天數}$$

#### 鳳梨的重新成長計算
+ 已知
    + 鳳梨的`收成天數`為`13天`。
    + 鳳梨的`成長階數`為`6`。
+ 可得
    + 鳳梨的`成長天數`為`12天`。
    + 鳳梨的`基本進階天數`為`2天`。
    + 鳳梨的`剩餘進階天數`為`3天`。
+ 又知
    + 鳳梨的`減少階數`為`2`。
+ 可再得
    + 鳳梨的`補充進階天數`為`2天`。
    + 鳳梨的`再收成天數`為`6天`。
    + 鳳梨的`再成長天數`為`5天`。

<table>
    <thead>
    　  <tr>
            <td align="center" colspan="2">重新成長階段</td>
            <td align="center">成熟階段</td>
        </tr>
    </thead>
　  <tr>
        <td align="center" class="breadcrumb">第4階段</td>
        <td align="center" class="breadcrumb">第5階段</td>
        <td align="center" class="breadcrumb">第6階段</td>
    </tr>
　  <tr>
    　<td align="center"><img src= "/images/post/Season_of_Story/Sprite/Crop_90120603.png"></td>
    　<td align="center"><img src= "/images/post/Season_of_Story/Sprite/Crop_90120604.png"></td>
    　<td align="center"><img src= "/images/post/Season_of_Story/Sprite/Crop_90120605.png"></td>
    </tr>
    <tr>
        <td align="center" colspan="2" class="breadcrumb">進階天數</td>
        <td align="center" class="breadcrumb">成熟</td>
    </tr>
    <tr>
        <td align="center">2天</td>
        <td align="center">3天</td>
        <td align="center"></td>
    </tr>
    <tr>
        <td align="center" colspan="3" class="breadcrumb">成長值範圍</td>
    </tr>
    <tr>
        <td align="center">7~9</td>
        <td align="center">10~12</td>
        <td align="center">13</td>
    </tr>
    <tr>
        <td align="center" colspan="3" class="breadcrumb">變化日</td>
    </tr>
    <tr>
        <td align="center">第1天</td>
        <td align="center">第3天</td>
        <td align="center">第6天</td>
    </tr>
</table>

#### 品質分的減少
+ `後續作物`的[品質分](../doraemon-story-mod-crop/#品質分)減少程度與`降階`減少的階段數有關。
+ 然而[品質分](../doraemon-story-mod-crop/#品質分)的提升也與施用的`肥料`種類有關，
+ 因此減少的[品質分](../doraemon-story-mod-crop/#品質分)會以`高級肥料`的[施肥效果](../doraemon-story-crop-part3/#品質提升計算公式)進行反推。

$$減少的施肥次數=減少的成長值=再收成天數$$
$$減少的品質分=無條件進位(\dfrac {高級肥料效果}{收成天數})\times{減少的施肥次數}$$

+ 以鳳梨為例：
    + 假設[收成](../doraemon-story-crop-part6)時的[品質分](../doraemon-story-mod-crop/#品質分)為`254分`,`品質⭐️`相當於`⭐️3.0`。
    + `降階`後，`成長過程`從`第6階段`降為`第4階段`，減少的[成長值](../doraemon-story-mod-crop/#成長值)為`6`，亦即少了`6次`[施肥](../doraemon-story-crop-part3)的機會。
    + 根據[品質提升計算公式](../doraemon-story-crop-part3/#品質提升計算公式)，鳳梨6次施用`高級肥料`所增加的[品質分](../doraemon-story-mod-crop/#品質分)為`96分`。
    + 所以`降階`後[品質分](../doraemon-story-mod-crop/#品質分)會減少`96分`變成`158分`，`品質⭐️`為`⭐️2.0`。

## 總結
以鳳梨作為案例總結：
1. 已知鳳梨的`收成天數`為`13天`，每次澆水[成長值](../doraemon-story-mod-crop/#成長值)增加`1`，因此[收成](../doraemon-story-crop-part6)時[成長值](../doraemon-story-mod-crop/#成長值)為`13`。
2. 鳳梨初次[收成](../doraemon-story-crop-part6)後，土裡鳳梨的[成長值](../doraemon-story-mod-crop/#成長值)會降回到第7天的狀態，亦即[成長值](../doraemon-story-mod-crop/#成長值)為`7`。
3. 若初次[收成](../doraemon-story-crop-part6)前，鳳梨的成長全程使用`高級肥料`，則[品質分](../doraemon-story-mod-crop/#品質分)也會降回到第7天時的[品質分](../doraemon-story-mod-crop/#品質分)。
4. 因此成長過程在第7天的鳳梨還需要`6天`才會`成熟`。
5. 若這6天也都使用`高級肥料`，再次`成熟`時，[品質分](../doraemon-story-mod-crop/#品質分)也會與前次[收成](../doraemon-story-crop-part6)相同。

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
