---
title: "37種作物出貨價格"
date: 2020-04-04T16:01:22+08:00
description: 37種作物各品質出貨價格
draft: false
hideToc: false
enableToc: false
enableTocContent: true
author: 伊琉沙 AKA 哇咔咔
authorEmoji: 👩🏿‍🚀
tags: 
- 出貨價格
- 作物
series:
- 哆啦A夢牧場物語
categories:
- 哆啦A夢
image: images/post/Season_of_Story/Sprite/icon_3000501.png
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

## 出貨價格
+ [物品出貨價格索引](../doraemon-story-index/#物品出貨價格索引)
+ `品質等級`為1的物品，`出貨價格`為`基本售價`。
+ `品質等級`超過1的物品，`出貨價格`會根據上一品質等級的出貨價格以`售價倍率`提升並無條件進位至整數。

### 源代碼
```C#
private int CalculateSellingPrice()
{
    if (this.Master.HasQuality)
    {
        int num = this.Master.BaseSellingPrice;
        for (int i = 0; i < this.mQuality - 1; i++)
        {
            num = Mathf.CeilToInt((float)num * Item.SELLING_PRICE_RATE);
        }
        return num;
    }
    return this.Master.BaseSellingPrice;
}
```
### 計算公式
$$品質等級：N=1$$$$出貨價格（N）=無條件進位（基本售價 \times 售價倍率），售價倍率=1.13$$
$$品質等級：N>1$$$$出貨價格（N）=無條件進位（出貨價格（N-1） \times 售價倍率）$$

### 作物出貨價格
+ `物品ID`=`3000000`+`作物ID`
+ [春季作物出貨價格](#春季作物出貨價格)：10種
+ [夏季作物出貨價格](#夏季作物出貨價格)：13種
+ [秋季作物出貨價格](#秋季作物出貨價格)：8種
+ [冬季作物出貨價格](#冬季作物出貨價格)：4種
+ [常年作物出貨價格](#常年作物出貨價格)：2種
    + `牧草`收成後的`乾草`為單一品質的物品。

#### 春季作物出貨價格
<table>
    <thead>
        <tr>
            <td align="center">ID</td>
            <td align="center"></td>
            <td align="center">&emsp;作&emsp;物&emsp;名&emsp;稱&emsp;</td>
            <td align="center">⭐️0.5</td>
            <td align="center">⭐️1.0</td>
            <td align="center">⭐️1.5</td>
            <td align="center">⭐️2.0</td>
            <td align="center">⭐️2.5</td>
            <td align="center">⭐️3.0</td>
            <td align="center">⭐️3.5</td>
            <td align="center">⭐️4.0</td>
            <td align="center">⭐️4.5</td>
            <td align="center">⭐️5.0</td>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td align="center">100</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3000100.png"></td>
            <td align="center">蕪菁</td>
            <td align="center">110</td>
            <td align="center">125</td>
            <td align="center">142</td>
            <td align="center">161</td>
            <td align="center">182</td>
            <td align="center">206</td>
            <td align="center">233</td>
            <td align="center">264</td>
            <td align="center">299</td>
            <td align="center">338</td>
        </tr>
        <tr>
            <td align="center">101</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3000101.png"></td>
            <td align="center">馬鈴薯</td>
            <td align="center">210</td>
            <td align="center">238</td>
            <td align="center">269</td>
            <td align="center">304</td>
            <td align="center">344</td>
            <td align="center">389</td>
            <td align="center">440</td>
            <td align="center">498</td>
            <td align="center">563</td>
            <td align="center">637</td>
        </tr>
        <tr>
            <td align="center">102</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3000102.png"></td>
            <td align="center">高麗菜</td>
            <td align="center">410</td>
            <td align="center">464</td>
            <td align="center">525</td>
            <td align="center">594</td>
            <td align="center">672</td>
            <td align="center">760</td>
            <td align="center">859</td>
            <td align="center">971</td>
            <td align="center">1098</td>
            <td align="center">1241</td>
        </tr>
        <tr>
            <td align="center">103</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3000103.png"></td>
            <td align="center">小黃瓜</td>
            <td align="center">120</td>
            <td align="center">136</td>
            <td align="center">154</td>
            <td align="center">175</td>
            <td align="center">198</td>
            <td align="center">224</td>
            <td align="center">254</td>
            <td align="center">288</td>
            <td align="center">326</td>
            <td align="center">369</td>
        </tr>
        <tr>
            <td align="center">104</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3000104.png"></td>
            <td align="center">草莓</td>
            <td align="center">240</td>
            <td align="center">272</td>
            <td align="center">308</td>
            <td align="center">349</td>
            <td align="center">395</td>
            <td align="center">447</td>
            <td align="center">506</td>
            <td align="center">572</td>
            <td align="center">647</td>
            <td align="center">732</td>
        </tr>
        <tr>
            <td align="center">105</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3000105.png"></td>
            <td align="center">白花椰菜</td>
            <td align="center">360</td>
            <td align="center">407</td>
            <td align="center">460</td>
            <td align="center">520</td>
            <td align="center">588</td>
            <td align="center">665</td>
            <td align="center">752</td>
            <td align="center">850</td>
            <td align="center">961</td>
            <td align="center">1086</td>
        </tr>
        <tr>
            <td align="center">106</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3000106.png"></td>
            <td align="center">豌豆</td>
            <td align="center">130</td>
            <td align="center">147</td>
            <td align="center">167</td>
            <td align="center">189</td>
            <td align="center">214</td>
            <td align="center">242</td>
            <td align="center">274</td>
            <td align="center">310</td>
            <td align="center">351</td>
            <td align="center">397</td>
        </tr>
        <tr>
            <td align="center">108</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3000108.png"></td>
            <td align="center">瑪格麗特</td>
            <td align="center">170</td>
            <td align="center">193</td>
            <td align="center">219</td>
            <td align="center">248</td>
            <td align="center">281</td>
            <td align="center">318</td>
            <td align="center">360</td>
            <td align="center">407</td>
            <td align="center">460</td>
            <td align="center">520</td>
        </tr>
        <tr>
            <td align="center">110</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3000110.png"></td>
            <td align="center">彩鐘花</td>
            <td align="center">320</td>
            <td align="center">362</td>
            <td align="center">410</td>
            <td align="center">464</td>
            <td align="center">525</td>
            <td align="center">594</td>
            <td align="center">672</td>
            <td align="center">760</td>
            <td align="center">859</td>
            <td align="center">971</td>
        </tr>
        <tr>
            <td align="center">111</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3000111.png"></td>
            <td align="center">康乃馨</td>
            <td align="center">360</td>
            <td align="center">407</td>
            <td align="center">460</td>
            <td align="center">520</td>
            <td align="center">588</td>
            <td align="center">665</td>
            <td align="center">752</td>
            <td align="center">850</td>
            <td align="center">961</td>
            <td align="center">1086</td>
        </tr>
    </tbody>
</table>

#### 夏季作物出貨價格
<table>
    <thead>
        <tr>
            <td align="center">ID</td>
            <td align="center"></td>
            <td align="center">&emsp;作&emsp;物&emsp;名&emsp;稱&emsp;</td>
            <td align="center">⭐️0.5</td>
            <td align="center">⭐️1.0</td>
            <td align="center">⭐️1.5</td>
            <td align="center">⭐️2.0</td>
            <td align="center">⭐️2.5</td>
            <td align="center">⭐️3.0</td>
            <td align="center">⭐️3.5</td>
            <td align="center">⭐️4.0</td>
            <td align="center">⭐️4.5</td>
            <td align="center">⭐️5.0</td>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td align="center">200</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3000200.png"></td>
            <td align="center">玉米</td>
            <td align="center">220</td>
            <td align="center">249</td>
            <td align="center">282</td>
            <td align="center">319</td>
            <td align="center">361</td>
            <td align="center">408</td>
            <td align="center">462</td>
            <td align="center">523</td>
            <td align="center">591</td>
            <td align="center">668</td>
        </tr>
        <tr>
            <td align="center">201</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3000201.png"></td>
            <td align="center">洋蔥</td>
            <td align="center">140</td>
            <td align="center">159</td>
            <td align="center">180</td>
            <td align="center">204</td>
            <td align="center">231</td>
            <td align="center">262</td>
            <td align="center">297</td>
            <td align="center">336</td>
            <td align="center">380</td>
            <td align="center">430</td>
        </tr>
        <tr>
            <td align="center">202</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3000202.png"></td>
            <td align="center">南瓜</td>
            <td align="center">90</td>
            <td align="center">102</td>
            <td align="center">116</td>
            <td align="center">132</td>
            <td align="center">150</td>
            <td align="center">170</td>
            <td align="center">193</td>
            <td align="center">219</td>
            <td align="center">248</td>
            <td align="center">281</td>
        </tr>
        <tr>
            <td align="center">203</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3000203.png"></td>
            <td align="center">西瓜</td>
            <td align="center">170</td>
            <td align="center">193</td>
            <td align="center">219</td>
            <td align="center">248</td>
            <td align="center">281</td>
            <td align="center">318</td>
            <td align="center">360</td>
            <td align="center">407</td>
            <td align="center">460</td>
            <td align="center">520</td>
        </tr>
        <tr>
            <td align="center">204</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3000204.png"></td>
            <td align="center">番茄</td>
            <td align="center">180</td>
            <td align="center">204</td>
            <td align="center">231</td>
            <td align="center">262</td>
            <td align="center">297</td>
            <td align="center">336</td>
            <td align="center">380</td>
            <td align="center">430</td>
            <td align="center">486</td>
            <td align="center">550</td>
        </tr>
        <tr>
            <td align="center">205</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3000205.png"></td>
            <td align="center">哈密瓜</td>
            <td align="center">660</td>
            <td align="center">746</td>
            <td align="center">843</td>
            <td align="center">953</td>
            <td align="center">1077</td>
            <td align="center">1218</td>
            <td align="center">1377</td>
            <td align="center">1557</td>
            <td align="center">1760</td>
            <td align="center">1989</td>
        </tr>
        <tr>
            <td align="center">206</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3000206.png"></td>
            <td align="center">鳳梨</td>
            <td align="center">250</td>
            <td align="center">283</td>
            <td align="center">320</td>
            <td align="center">362</td>
            <td align="center">410</td>
            <td align="center">464</td>
            <td align="center">525</td>
            <td align="center">594</td>
            <td align="center">672</td>
            <td align="center">760</td>
        </tr>
        <tr>
            <td align="center">207</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3000207.png"></td>
            <td align="center">甜椒</td>
            <td align="center">130</td>
            <td align="center">147</td>
            <td align="center">167</td>
            <td align="center">189</td>
            <td align="center">214</td>
            <td align="center">242</td>
            <td align="center">274</td>
            <td align="center">310</td>
            <td align="center">351</td>
            <td align="center">397</td>
        </tr>
        <tr>
            <td align="center">210</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3000210.png"></td>
            <td align="center">向日葵</td>
            <td align="center">360</td>
            <td align="center">407</td>
            <td align="center">460</td>
            <td align="center">520</td>
            <td align="center">588</td>
            <td align="center">665</td>
            <td align="center">752</td>
            <td align="center">850</td>
            <td align="center">961</td>
            <td align="center">1086</td>
        </tr>
        <tr>
            <td align="center">211</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3000211.png"></td>
            <td align="center">牽牛花</td>
            <td align="center">170</td>
            <td align="center">193</td>
            <td align="center">219</td>
            <td align="center">248</td>
            <td align="center">281</td>
            <td align="center">318</td>
            <td align="center">360</td>
            <td align="center">407</td>
            <td align="center">460</td>
            <td align="center">520</td>
        </tr>
        <tr>
            <td align="center">213</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3000213.png"></td>
            <td align="center">百合花</td>
            <td align="center">320</td>
            <td align="center">362</td>
            <td align="center">410</td>
            <td align="center">464</td>
            <td align="center">525</td>
            <td align="center">594</td>
            <td align="center">672</td>
            <td align="center">760</td>
            <td align="center">859</td>
            <td align="center">971</td>
        </tr>
        <tr>
            <td align="center">214</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3000214.png"></td>
            <td align="center">木槿</td>
            <td align="center">170</td>
            <td align="center">193</td>
            <td align="center">219</td>
            <td align="center">248</td>
            <td align="center">281</td>
            <td align="center">318</td>
            <td align="center">360</td>
            <td align="center">407</td>
            <td align="center">460</td>
            <td align="center">520</td>
        </tr>
        <tr>
            <td align="center">215</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3000215.png"></td>
            <td align="center">紅玫瑰</td>
            <td align="center">240</td>
            <td align="center">272</td>
            <td align="center">308</td>
            <td align="center">349</td>
            <td align="center">395</td>
            <td align="center">447</td>
            <td align="center">506</td>
            <td align="center">572</td>
            <td align="center">647</td>
            <td align="center">732</td>
        </tr>
    </tbody>
</table>

#### 秋季作物出貨價格
<table>
    <thead>
        <tr>
            <td align="center">ID</td>
            <td align="center"></td>
            <td align="center">&emsp;作&emsp;物&emsp;名&emsp;稱&emsp;</td>
            <td align="center">⭐️0.5</td>
            <td align="center">⭐️1.0</td>
            <td align="center">⭐️1.5</td>
            <td align="center">⭐️2.0</td>
            <td align="center">⭐️2.5</td>
            <td align="center">⭐️3.0</td>
            <td align="center">⭐️3.5</td>
            <td align="center">⭐️4.0</td>
            <td align="center">⭐️4.5</td>
            <td align="center">⭐️5.0</td>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td align="center">300</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3000300.png"></td>
            <td align="center">牛蒡</td>
            <td align="center">240</td>
            <td align="center">272</td>
            <td align="center">308</td>
            <td align="center">349</td>
            <td align="center">395</td>
            <td align="center">447</td>
            <td align="center">506</td>
            <td align="center">572</td>
            <td align="center">647</td>
            <td align="center">732</td>
        </tr>
        <tr>
            <td align="center">301</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3000301.png"></td>
            <td align="center">胡蘿蔔</td>
            <td align="center">360</td>
            <td align="center">407</td>
            <td align="center">460</td>
            <td align="center">520</td>
            <td align="center">588</td>
            <td align="center">665</td>
            <td align="center">752</td>
            <td align="center">850</td>
            <td align="center">961</td>
            <td align="center">1086</td>
        </tr>
        <tr>
            <td align="center">302</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3000302.png"></td>
            <td align="center">地瓜</td>
            <td align="center">60</td>
            <td align="center">68</td>
            <td align="center">77</td>
            <td align="center">88</td>
            <td align="center">100</td>
            <td align="center">113</td>
            <td align="center">128</td>
            <td align="center">145</td>
            <td align="center">164</td>
            <td align="center">186</td>
        </tr>
        <tr>
            <td align="center">303</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3000303.png"></td>
            <td align="center">菠菜</td>
            <td align="center">110</td>
            <td align="center">125</td>
            <td align="center">142</td>
            <td align="center">161</td>
            <td align="center">182</td>
            <td align="center">206</td>
            <td align="center">233</td>
            <td align="center">264</td>
            <td align="center">299</td>
            <td align="center">338</td>
        </tr>
        <tr>
            <td align="center">304</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3000304.png"></td>
            <td align="center">茄子</td>
            <td align="center">320</td>
            <td align="center">362</td>
            <td align="center">410</td>
            <td align="center">464</td>
            <td align="center">525</td>
            <td align="center">594</td>
            <td align="center">672</td>
            <td align="center">760</td>
            <td align="center">859</td>
            <td align="center">971</td>
        </tr>
        <tr>
            <td align="center">305</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3000305.png"></td>
            <td align="center">青椒</td>
            <td align="center">140</td>
            <td align="center">159</td>
            <td align="center">180</td>
            <td align="center">204</td>
            <td align="center">231</td>
            <td align="center">262</td>
            <td align="center">297</td>
            <td align="center">336</td>
            <td align="center">380</td>
            <td align="center">430</td>
        </tr>
        <tr>
            <td align="center">306</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3000306.png"></td>
            <td align="center">撫子花</td>
            <td align="center">210</td>
            <td align="center">238</td>
            <td align="center">269</td>
            <td align="center">304</td>
            <td align="center">344</td>
            <td align="center">389</td>
            <td align="center">440</td>
            <td align="center">498</td>
            <td align="center">563</td>
            <td align="center">637</td>
        </tr>
        <tr>
            <td align="center">307</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3000307.png"></td>
            <td align="center">非洲菊</td>
            <td align="center">450</td>
            <td align="center">509</td>
            <td align="center">576</td>
            <td align="center">651</td>
            <td align="center">736</td>
            <td align="center">832</td>
            <td align="center">941</td>
            <td align="center">1064</td>
            <td align="center">1203</td>
            <td align="center">1360</td>
        </tr>
    </tbody>
</table>

#### 冬季作物出貨價格
<table>
    <thead>
        <tr>
            <td align="center">ID</td>
            <td align="center"></td>
            <td align="center">&emsp;作&emsp;物&emsp;名&emsp;稱&emsp;</td>
            <td align="center">⭐️0.5</td>
            <td align="center">⭐️1.0</td>
            <td align="center">⭐️1.5</td>
            <td align="center">⭐️2.0</td>
            <td align="center">⭐️2.5</td>
            <td align="center">⭐️3.0</td>
            <td align="center">⭐️3.5</td>
            <td align="center">⭐️4.0</td>
            <td align="center">⭐️4.5</td>
            <td align="center">⭐️5.0</td>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td align="center">400</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3000400.png"></td>
            <td align="center">白蘿蔔</td>
            <td align="center">90</td>
            <td align="center">102</td>
            <td align="center">116</td>
            <td align="center">132</td>
            <td align="center">150</td>
            <td align="center">170</td>
            <td align="center">193</td>
            <td align="center">219</td>
            <td align="center">248</td>
            <td align="center">281</td>
        </tr>
        <tr>
            <td align="center">401</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3000401.png"></td>
            <td align="center">白菜</td>
            <td align="center">360</td>
            <td align="center">407</td>
            <td align="center">460</td>
            <td align="center">520</td>
            <td align="center">588</td>
            <td align="center">665</td>
            <td align="center">752</td>
            <td align="center">850</td>
            <td align="center">961</td>
            <td align="center">1086</td>
        </tr>
        <tr>
            <td align="center">402</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3000402.png"></td>
            <td align="center">花椰菜</td>
            <td align="center">90</td>
            <td align="center">102</td>
            <td align="center">116</td>
            <td align="center">132</td>
            <td align="center">150</td>
            <td align="center">170</td>
            <td align="center">193</td>
            <td align="center">219</td>
            <td align="center">248</td>
            <td align="center">281</td>
        </tr>
        <tr>
            <td align="center">404</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3000404.png"></td>
            <td align="center">雪花蓮</td>
            <td align="center">240</td>
            <td align="center">272</td>
            <td align="center">308</td>
            <td align="center">349</td>
            <td align="center">395</td>
            <td align="center">447</td>
            <td align="center">506</td>
            <td align="center">572</td>
            <td align="center">647</td>
            <td align="center">732</td>
        </tr>
    </tbody>
</table>

#### 常年作物出貨價格
<table>
    <thead>
        <tr>
            <td align="center">ID</td>
            <td align="center"></td>
            <td align="center">&emsp;作&emsp;物&emsp;名&emsp;稱&emsp;</td>
            <td align="center">出貨價格</td>
            <td align="center">物品ID</td>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td align="center">500</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_1101000.png"></td>
            <td align="center">乾草</td>
            <td align="center">10</td>
            <td align="center">1101000</td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <td align="center">ID</td>
            <td align="center"></td>
            <td align="center">&emsp;作&emsp;物&emsp;名&emsp;稱&emsp;</td>
            <td align="center">⭐️0.5</td>
            <td align="center">⭐️1.0</td>
            <td align="center">⭐️1.5</td>
            <td align="center">⭐️2.0</td>
            <td align="center">⭐️2.5</td>
            <td align="center">⭐️3.0</td>
            <td align="center">⭐️3.5</td>
            <td align="center">⭐️4.0</td>
            <td align="center">⭐️4.5</td>
            <td align="center">⭐️5.0</td>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td align="center">501</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3000501.png"></td>
            <td align="center">小麥</td>
            <td align="center">50</td>
            <td align="center">57</td>
            <td align="center">65</td>
            <td align="center">74</td>
            <td align="center">84</td>
            <td align="center">95</td>
            <td align="center">108</td>
            <td align="center">123</td>
            <td align="center">139</td>
            <td align="center">158</td>
        </tr>
    </tbody>
</table>