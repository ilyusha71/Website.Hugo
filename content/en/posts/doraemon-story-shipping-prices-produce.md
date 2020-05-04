---
title: "17種農產品出貨價格"
date: 2020-04-14T22:07:53+08:00
description: 17種農產品各品質出貨價格
draft: false
hideToc: false
enableToc: false
enableTocContent: true
author: 伊琉沙 AKA 哇咔咔
authorEmoji: 👩🏿‍🚀
tags: 
- 出貨價格
- 農產品
series:
- 哆啦A夢牧場物語
categories:
- 哆啦A夢
image: images/post/Season_of_Story/Sprite/icon_3400111.png
libraries:
- katex
---
<mark>最後更新：2020/04/27</mark>

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

### 牧場採集
<table>
    <thead>
        <tr>
            <td align="center">物品ID</td>
            <td align="center"></td>
            <td align="center">農產品名稱</td>
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
            <td align="center">3200100</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3200100.png"></td>
            <td align="center">雞蛋</td>
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
        <tr>
            <td align="center">3200101</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3200101.png"></td>
            <td align="center">牛奶</td>
            <td align="center">100</td>
            <td align="center">113</td>
            <td align="center">128</td>
            <td align="center">145</td>
            <td align="center">164</td>
            <td align="center">186</td>
            <td align="center">211</td>
            <td align="center">239</td>
            <td align="center">271</td>
            <td align="center">307</td>
        </tr>
        <tr>
            <td align="center">4100100</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_4100100.png"></td>
            <td align="center">羊毛</td>
            <td align="center">200</td>
            <td align="center">226</td>
            <td align="center">256</td>
            <td align="center">290</td>
            <td align="center">328</td>
            <td align="center">371</td>
            <td align="center">420</td>
            <td align="center">475</td>
            <td align="center">537</td>
            <td align="center">607</td>
        </tr>
        <tr>
            <td align="center">3200102</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3200102.png"></td>
            <td align="center">黃金雞蛋</td>
            <td align="center">100</td>
            <td align="center">113</td>
            <td align="center">128</td>
            <td align="center">145</td>
            <td align="center">164</td>
            <td align="center">186</td>
            <td align="center">211</td>
            <td align="center">239</td>
            <td align="center">271</td>
            <td align="center">307</td>
        </tr>
        <tr>
            <td align="center">3200103</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3200103.png"></td>
            <td align="center">黃金牛奶</td>
            <td align="center">200</td>
            <td align="center">226</td>
            <td align="center">256</td>
            <td align="center">290</td>
            <td align="center">328</td>
            <td align="center">371</td>
            <td align="center">420</td>
            <td align="center">475</td>
            <td align="center">537</td>
            <td align="center">607</td>
        </tr>
        <tr>
            <td align="center">4100102</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_4100102.png"></td>
            <td align="center">黃金羊毛</td>
            <td align="center">400</td>
            <td align="center">452</td>
            <td align="center">511</td>
            <td align="center">578</td>
            <td align="center">654</td>
            <td align="center">740</td>
            <td align="center">837</td>
            <td align="center">946</td>
            <td align="center">1069</td>
            <td align="center">1208</td>
        </tr>
    </tbody>
</table>

### 調理加工
<table>
    <thead>
        <tr>
            <td align="center">物品ID</td>
            <td align="center"></td>
            <td align="center">農產品名稱</td>
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
            <td align="center">3400107</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3400107.png"></td>
            <td align="center">美乃滋</td>
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
            <td align="center">3400108</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3400108.png"></td>
            <td align="center">奶油</td>
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
            <td align="center">3400112</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3400112.png"></td>
            <td align="center">麵包</td>
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
            <td align="center">3400111</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3400111.png"></td>
            <td align="center">黃金美乃滋</td>
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

### 機器加工
<table>
    <thead>
        <tr>
            <td align="center">物品ID</td>
            <td align="center"></td>
            <td align="center">農產品名稱</td>
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
            <td align="center">3400103</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3400103.png"></td>
            <td align="center">起司</td>
            <td align="center">150</td>
            <td align="center">170</td>
            <td align="center">193</td>
            <td align="center">219</td>
            <td align="center">248</td>
            <td align="center">281</td>
            <td align="center">318</td>
            <td align="center">360</td>
            <td align="center">407</td>
            <td align="center">460</td>
        </tr>
        <tr>
            <td align="center">3400104</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3400104.png"></td>
            <td align="center">優格</td>
            <td align="center">200</td>
            <td align="center">226</td>
            <td align="center">256</td>
            <td align="center">290</td>
            <td align="center">328</td>
            <td align="center">371</td>
            <td align="center">420</td>
            <td align="center">475</td>
            <td align="center">537</td>
            <td align="center">607</td>
        </tr>
        <tr>
            <td align="center">3400105</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3400105.png"></td>
            <td align="center">麵粉</td>
            <td align="center">150</td>
            <td align="center">170</td>
            <td align="center">193</td>
            <td align="center">219</td>
            <td align="center">248</td>
            <td align="center">281</td>
            <td align="center">318</td>
            <td align="center">360</td>
            <td align="center">407</td>
            <td align="center">460</td>
        </tr>
        <tr>
            <td align="center">4100101</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_4100101.png"></td>
            <td align="center">毛線</td>
            <td align="center">300</td>
            <td align="center">339</td>
            <td align="center">384</td>
            <td align="center">434</td>
            <td align="center">491</td>
            <td align="center">555</td>
            <td align="center">628</td>
            <td align="center">710</td>
            <td align="center">803</td>
            <td align="center">908</td>
        </tr>
        <tr>
            <td align="center">3400109</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3400109.png"></td>
            <td align="center">黃金起司</td>
            <td align="center">300</td>
            <td align="center">339</td>
            <td align="center">384</td>
            <td align="center">434</td>
            <td align="center">491</td>
            <td align="center">555</td>
            <td align="center">628</td>
            <td align="center">710</td>
            <td align="center">803</td>
            <td align="center">908</td>
        </tr>
        <tr>
            <td align="center">3400110</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3400110.png"></td>
            <td align="center">黃金優格</td>
            <td align="center">400</td>
            <td align="center">452</td>
            <td align="center">511</td>
            <td align="center">578</td>
            <td align="center">654</td>
            <td align="center">740</td>
            <td align="center">837</td>
            <td align="center">946</td>
            <td align="center">1069</td>
            <td align="center">1208</td>
        </tr>
        <tr>
            <td align="center">4100103</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_4100103.png"></td>
            <td align="center">黃金毛線</td>
            <td align="center">600</td>
            <td align="center">678</td>
            <td align="center">767</td>
            <td align="center">867</td>
            <td align="center">980</td>
            <td align="center">1108</td>
            <td align="center">1253</td>
            <td align="center">1416</td>
            <td align="center">1601</td>
            <td align="center">1810</td>
        </tr>
    </tbody>
</table>

## 分類索引
<table>
    <thead>
        <tr>
            <td colspan="10">出貨價格</td>        
        </tr>
    </thead>
    <tr>
        <td align="center"><a href="../doraemon-story-shipping-prices-bugs"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_6000133.png">蟲類</a></td>
        <td align="center"><a href="../doraemon-story-shipping-prices-fishes"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_5000190.png">魚類</a></td>
        <td align="center"><a href="../doraemon-story-shipping-prices-crops"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_3000205.png">作物</a></td>
        <td align="center"><a href="../doraemon-story-shipping-prices-meals"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_3300901.png">料理</a></td>    
        <td align="center"><a href="../doraemon-story-shipping-prices-produce"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_3400111.png">農產品</a></td>     
    </tr>
</table>
