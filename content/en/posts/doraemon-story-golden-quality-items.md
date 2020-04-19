---
title: "【哆啦A夢牧場物語】黃金雞蛋、黃金牛奶與黃金羊毛的取得條件"
date: 2020-04-15T15:09:26+08:00
description: 黃金雞蛋、黃金牛奶與黃金羊毛的取得條件
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
image: images/post/Season_of_Story/Sprite/icon_201171503.png
---
### 黃金品質原料取得條件
```C#
public class AnimalModel : INullableModel
{
    private bool IsSpecialHarvest
    {
        get
        {
            return this.IsVictory && this.AffectionDegreeRate == 20;
        }
    }
}
```
根據上列代碼，要收穫黃金品質的`雞蛋`、`牛奶`與`羊毛`必須滿足下列兩項條件：
+ 參與同類`動物競賽`獲得`冠軍`。
+ 動物`情感度`達到20，亦即❤️10。

<table>
    <thead>
        <tr>
            <td>動物</td>
            <td>條件</td>
            <td>黃金物品</td>
        </tr>
    </thead>
    <tr>
        <td rowspan="2"><img width="137px" src= "/images/post/Season_of_Story/Sprite/icon_201031140.png"></td>
        <td align="center"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><br>情感度達到❤️10</td>
        <td rowspan="2" align="center"><img width="72px" src= "/images/post/Season_of_Story/Sprite/icon_3200102.png">黃金雞蛋</td>
    </tr>
    <tr>
        <td align="center"><img src= "/images/post/Season_of_Story/Sprite/Icon_Crown_01.png">贏得養雞競賽</td>
    </tr>
        <thead>
        <tr>
            <td>動物</td>
            <td>條件</td>
            <td>黃金物品</td>
        </tr>
    </thead>
    <tr>
        <td rowspan="2"><img width="137px" src= "/images/post/Season_of_Story/Sprite/icon_201031100.png"></td>
        <td align="center"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><br>情感度達到❤️10</td>
        <td rowspan="2" align="center"><img width="72px" src= "/images/post/Season_of_Story/Sprite/icon_3200103.png">黃金牛奶</td>
    </tr>
    <tr>
        <td align="center"><img src= "/images/post/Season_of_Story/Sprite/Icon_Crown_01.png">贏得飼牛競賽</td>
    </tr>
        <thead>
        <tr>
            <td>動物</td>
            <td>條件</td>
            <td>黃金物品</td>
        </tr>
    </thead>
    <tr>
        <td rowspan="2"><img width="137px" src= "/images/post/Season_of_Story/Sprite/icon_201031120.png"></td>
        <td align="center"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><br>情感度達到❤️10</td>
        <td rowspan="2" align="center"><img width="72px" src= "/images/post/Season_of_Story/Sprite/icon_4100102.png">黃金羊毛</td>
    </tr>
    <tr>
        <td align="center"><img src= "/images/post/Season_of_Story/Sprite/Icon_Crown_01.png">贏得飼羊競賽</td>
    </tr>
</table>

### 加工農產品
透過`雞蛋`、`牛奶`與`羊毛`加工的部分農產品，若改用黃金品質的原料也會產生黃金品質的農產品。

#### 調理加工農產品
<table>
    <thead>
        <tr>
            <td>農產品</td>            
            <td>調理器具</td>
            <td colspan="2">原料</td>
        </tr>
    </thead>
    <tr>
        <td align="center"><img width="72px" src= "/images/post/Season_of_Story/Sprite/icon_3400111.png">黃金美乃滋</td>
        <td align="center"><img width="72px" src= "/images/post/Season_of_Story/Sprite/icon_9000101.png">打蛋器</td>
        <td align="center"><img width="72px" src= "/images/post/Season_of_Story/Sprite/icon_3200102.png">黃金雞蛋</td>
        <td align="center"><img width="72px" src= "/images/post/Season_of_Story/Sprite/icon_3400102.png">油</td>
    </tr>
</table>

#### 機器加工農產品
<table>
    <thead>
        <tr>
            <td>農產品</td>            
            <td>機器</td>
            <td>原料</td>
        </tr>
    </thead>
    <tr>
        <td align="center" valign="bottom"><img width="72px" src= "/images/post/Season_of_Story/Sprite/icon_3400109.png">黃金起司</td>        
        <td align="center" valign="bottom"><img width="137px" src= "/images/post/Season_of_Story/Sprite/icon_201080120.png">起司機</td>
        <td align="center" valign="bottom"><img width="72px" src= "/images/post/Season_of_Story/Sprite/icon_3200103.png">黃金牛奶</td>
    </tr>
    <tr>
        <td align="center" valign="bottom"><img width="72px" src= "/images/post/Season_of_Story/Sprite/icon_3400110.png">黃金優格</td>        
        <td align="center" valign="bottom"><img width="137px" src= "/images/post/Season_of_Story/Sprite/icon_201080130.png">優格機</td>
        <td align="center" valign="bottom"><img width="72px" src= "/images/post/Season_of_Story/Sprite/icon_3200103.png">黃金牛奶</td>
    </tr>
    <tr>
        <td align="center" valign="bottom"><img width="72px" src= "/images/post/Season_of_Story/Sprite/icon_4100103.png">黃金毛線</td>        
        <td align="center" valign="bottom"><img width="137px" src= "/images/post/Season_of_Story/Sprite/icon_201080140.png">毛線機</td>
        <td align="center" valign="bottom"><img width="72px" src= "/images/post/Season_of_Story/Sprite/icon_4100102.png">黃金羊毛</td>
    </tr>
</table>