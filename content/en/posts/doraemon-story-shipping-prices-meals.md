---
title: "88種料理出貨價格"
date: 2020-04-05T20:01:03+08:00
description: 88種料理各品質出貨價格
draft: false
hideToc: false
enableToc: false
enableTocContent: true
author: 伊琉沙 AKA 哇咔咔
authorEmoji: 👩🏿‍🚀
tags: 
- 出貨價格
- 料理
series:
- 哆啦A夢牧場物語
categories:
- 哆啦A夢
image: images/post/Season_of_Story/Sprite/icon_3300901.png
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

### 料理出貨價格
+ `物品ID`=`3300000`+`ID`
+ 以`出貨價格`遞減排序：
<table>
    <thead>
        <tr>
            <td align="center">ID</td>
            <td align="center"></td>
            <td align="center">&emsp;料&emsp;理&emsp;名&emsp;稱&emsp;</td>
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
            <td align="center">+187</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300187.png"></td>
            <td align="center">深海魚包燒烤</td>
            <td align="center">4150</td>
            <td align="center">4690</td>
            <td align="center">5300</td>
            <td align="center">5989</td>
            <td align="center">6768</td>
            <td align="center">7648</td>
            <td align="center">8643</td>
            <td align="center">9767</td>
            <td align="center">11037</td>
            <td align="center">12472</td>
        </tr>
        <tr>
            <td align="center">+188</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300188.png"></td>
            <td align="center">大尾魚漢堡排</td>
            <td align="center">4020</td>
            <td align="center">4543</td>
            <td align="center">5134</td>
            <td align="center">5802</td>
            <td align="center">6557</td>
            <td align="center">7410</td>
            <td align="center">8374</td>
            <td align="center">9463</td>
            <td align="center">10694</td>
            <td align="center">12085</td>
        </tr>
        <tr>
            <td align="center">+185</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300185.png"></td>
            <td align="center">皇帶魚祭典</td>
            <td align="center">3920</td>
            <td align="center">4430</td>
            <td align="center">5006</td>
            <td align="center">5657</td>
            <td align="center">6393</td>
            <td align="center">7225</td>
            <td align="center">8165</td>
            <td align="center">9227</td>
            <td align="center">10427</td>
            <td align="center">11783</td>
        </tr>
        <tr>
            <td align="center">+186</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300186.png"></td>
            <td align="center">甲魚鍋</td>
            <td align="center">3580</td>
            <td align="center">4046</td>
            <td align="center">4572</td>
            <td align="center">5167</td>
            <td align="center">5839</td>
            <td align="center">6599</td>
            <td align="center">7457</td>
            <td align="center">8427</td>
            <td align="center">9523</td>
            <td align="center">10761</td>
        </tr>
        <tr>
            <td align="center">+169</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300169.png"></td>
            <td align="center">生魚片船</td>
            <td align="center">2720</td>
            <td align="center">3074</td>
            <td align="center">3474</td>
            <td align="center">3926</td>
            <td align="center">4437</td>
            <td align="center">5014</td>
            <td align="center">5666</td>
            <td align="center">6403</td>
            <td align="center">7236</td>
            <td align="center">8177</td>
        </tr>
        <tr>
            <td align="center">+155</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300155.png"></td>
            <td align="center">芙蓉蛋</td>
            <td align="center">2280</td>
            <td align="center">2577</td>
            <td align="center">2913</td>
            <td align="center">3292</td>
            <td align="center">3720</td>
            <td align="center">4204</td>
            <td align="center">4751</td>
            <td align="center">5369</td>
            <td align="center">6067</td>
            <td align="center">6856</td>
        </tr>
        <tr>
            <td align="center">+138</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300138.png"></td>
            <td align="center">潘趣酒</td>
            <td align="center">1790</td>
            <td align="center">2023</td>
            <td align="center">2286</td>
            <td align="center">2584</td>
            <td align="center">2920</td>
            <td align="center">3300</td>
            <td align="center">3729</td>
            <td align="center">4214</td>
            <td align="center">4762</td>
            <td align="center">5382</td>
        </tr>
        <tr>
            <td align="center">+106</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300106.png"></td>
            <td align="center">春季沙拉</td>
            <td align="center">1770</td>
            <td align="center">2001</td>
            <td align="center">2262</td>
            <td align="center">2557</td>
            <td align="center">2890</td>
            <td align="center">3266</td>
            <td align="center">3691</td>
            <td align="center">4171</td>
            <td align="center">4714</td>
            <td align="center">5327</td>
        </tr>
        <tr>
            <td align="center">+152</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300152.png"></td>
            <td align="center">醃泡鮪魚</td>
            <td align="center">1700</td>
            <td align="center">1921</td>
            <td align="center">2171</td>
            <td align="center">2454</td>
            <td align="center">2774</td>
            <td align="center">3135</td>
            <td align="center">3543</td>
            <td align="center">4004</td>
            <td align="center">4525</td>
            <td align="center">5114</td>
        </tr>
        <tr>
            <td align="center">+129</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300129.png"></td>
            <td align="center">茶碗蒸</td>
            <td align="center">1660</td>
            <td align="center">1876</td>
            <td align="center">2120</td>
            <td align="center">2396</td>
            <td align="center">2708</td>
            <td align="center">3061</td>
            <td align="center">3459</td>
            <td align="center">3909</td>
            <td align="center">4418</td>
            <td align="center">4993</td>
        </tr>
        <tr>
            <td align="center">+151</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300151.png"></td>
            <td align="center">燈籠魚鍋</td>
            <td align="center">1610</td>
            <td align="center">1820</td>
            <td align="center">2057</td>
            <td align="center">2325</td>
            <td align="center">2628</td>
            <td align="center">2970</td>
            <td align="center">3357</td>
            <td align="center">3794</td>
            <td align="center">4288</td>
            <td align="center">4846</td>
        </tr>
        <tr>
            <td align="center">+108</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300108.png"></td>
            <td align="center">秋季沙拉</td>
            <td align="center">1590</td>
            <td align="center">1797</td>
            <td align="center">2031</td>
            <td align="center">2296</td>
            <td align="center">2595</td>
            <td align="center">2933</td>
            <td align="center">3315</td>
            <td align="center">3746</td>
            <td align="center">4233</td>
            <td align="center">4784</td>
        </tr>
        <tr>
            <td align="center">+154</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300154.png"></td>
            <td align="center">旗魚排</td>
            <td align="center">1540</td>
            <td align="center">1741</td>
            <td align="center">1968</td>
            <td align="center">2224</td>
            <td align="center">2514</td>
            <td align="center">2841</td>
            <td align="center">3211</td>
            <td align="center">3629</td>
            <td align="center">4101</td>
            <td align="center">4635</td>
        </tr>
        <tr>
            <td align="center">+176</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300176.png"></td>
            <td align="center">荷包蛋佐松露</td>
            <td align="center">1500</td>
            <td align="center">1695</td>
            <td align="center">1916</td>
            <td align="center">2166</td>
            <td align="center">2448</td>
            <td align="center">2767</td>
            <td align="center">3127</td>
            <td align="center">3534</td>
            <td align="center">3994</td>
            <td align="center">4514</td>
        </tr>
        <tr>
            <td align="center">+116</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300116.png"></td>
            <td align="center">炒青菜</td>
            <td align="center">1470</td>
            <td align="center">1662</td>
            <td align="center">1879</td>
            <td align="center">2124</td>
            <td align="center">2401</td>
            <td align="center">2714</td>
            <td align="center">3067</td>
            <td align="center">3466</td>
            <td align="center">3917</td>
            <td align="center">4427</td>
        </tr>
        <tr>
            <td align="center">+107</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300107.png"></td>
            <td align="center">夏季沙拉</td>
            <td align="center">1440</td>
            <td align="center">1628</td>
            <td align="center">1840</td>
            <td align="center">2080</td>
            <td align="center">2351</td>
            <td align="center">2657</td>
            <td align="center">3003</td>
            <td align="center">3394</td>
            <td align="center">3836</td>
            <td align="center">4335</td>
        </tr>
        <tr>
            <td align="center">+104</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300104.png"></td>
            <td align="center">咖哩</td>
            <td align="center">1430</td>
            <td align="center">1616</td>
            <td align="center">1827</td>
            <td align="center">2065</td>
            <td align="center">2334</td>
            <td align="center">2638</td>
            <td align="center">2981</td>
            <td align="center">3369</td>
            <td align="center">3807</td>
            <td align="center">4302</td>
        </tr>
        <tr>
            <td align="center">+119</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300119.png"></td>
            <td align="center">筑前煮</td>
            <td align="center">1280</td>
            <td align="center">1447</td>
            <td align="center">1636</td>
            <td align="center">1849</td>
            <td align="center">2090</td>
            <td align="center">2362</td>
            <td align="center">2670</td>
            <td align="center">3018</td>
            <td align="center">3411</td>
            <td align="center">3855</td>
        </tr>
        <tr>
            <td align="center">+123</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300123.png"></td>
            <td align="center">法式醬糜</td>
            <td align="center">1140</td>
            <td align="center">1289</td>
            <td align="center">1457</td>
            <td align="center">1647</td>
            <td align="center">1862</td>
            <td align="center">2105</td>
            <td align="center">2379</td>
            <td align="center">2689</td>
            <td align="center">3039</td>
            <td align="center">3435</td>
        </tr>
        <tr>
            <td align="center">+170</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300170.png"></td>
            <td align="center">地中海風醋醃魚</td>
            <td align="center">1130</td>
            <td align="center">1277</td>
            <td align="center">1444</td>
            <td align="center">1632</td>
            <td align="center">1845</td>
            <td align="center">2085</td>
            <td align="center">2357</td>
            <td align="center">2664</td>
            <td align="center">3011</td>
            <td align="center">3403</td>
        </tr>
        <tr>
            <td align="center">+161</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300161.png"></td>
            <td align="center">鱔魚凍</td>
            <td align="center">1120</td>
            <td align="center">1266</td>
            <td align="center">1431</td>
            <td align="center">1618</td>
            <td align="center">1829</td>
            <td align="center">2067</td>
            <td align="center">2336</td>
            <td align="center">2640</td>
            <td align="center">2984</td>
            <td align="center">3372</td>
        </tr>
        <tr>
            <td align="center">+128</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300128.png"></td>
            <td align="center">大阪燒</td>
            <td align="center">1110</td>
            <td align="center">1255</td>
            <td align="center">1419</td>
            <td align="center">1604</td>
            <td align="center">1813</td>
            <td align="center">2049</td>
            <td align="center">2316</td>
            <td align="center">2618</td>
            <td align="center">2959</td>
            <td align="center">3344</td>
        </tr>
        <tr>
            <td align="center">+167</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300167.png"></td>
            <td align="center">南蠻漬</td>
            <td align="center">1110</td>
            <td align="center">1255</td>
            <td align="center">1419</td>
            <td align="center">1604</td>
            <td align="center">1813</td>
            <td align="center">2049</td>
            <td align="center">2316</td>
            <td align="center">2618</td>
            <td align="center">2959</td>
            <td align="center">3344</td>
        </tr>
        <tr>
            <td align="center">+121</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300121.png"></td>
            <td align="center">八寶菜</td>
            <td align="center">1090</td>
            <td align="center">1232</td>
            <td align="center">1393</td>
            <td align="center">1575</td>
            <td align="center">1780</td>
            <td align="center">2012</td>
            <td align="center">2274</td>
            <td align="center">2570</td>
            <td align="center">2905</td>
            <td align="center">3283</td>
        </tr>
        <tr>
            <td align="center">+126</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300126.png"></td>
            <td align="center">普羅旺斯雜燴</td>
            <td align="center">1090</td>
            <td align="center">1232</td>
            <td align="center">1393</td>
            <td align="center">1575</td>
            <td align="center">1780</td>
            <td align="center">2012</td>
            <td align="center">2274</td>
            <td align="center">2570</td>
            <td align="center">2905</td>
            <td align="center">3283</td>
        </tr>
        <tr>
            <td align="center">+111</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300111.png"></td>
            <td align="center">燉菜</td>
            <td align="center">1060</td>
            <td align="center">1198</td>
            <td align="center">1354</td>
            <td align="center">1531</td>
            <td align="center">1731</td>
            <td align="center">1957</td>
            <td align="center">2212</td>
            <td align="center">2500</td>
            <td align="center">2825</td>
            <td align="center">3193</td>
        </tr>
        <tr>
            <td align="center">+110</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300110.png"></td>
            <td align="center">三明治</td>
            <td align="center">1050</td>
            <td align="center">1187</td>
            <td align="center">1342</td>
            <td align="center">1517</td>
            <td align="center">1715</td>
            <td align="center">1938</td>
            <td align="center">2190</td>
            <td align="center">2475</td>
            <td align="center">2797</td>
            <td align="center">3161</td>
        </tr>
        <tr>
            <td align="center">+103</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300103.png"></td>
            <td align="center">天婦羅</td>
            <td align="center">1040</td>
            <td align="center">1176</td>
            <td align="center">1329</td>
            <td align="center">1502</td>
            <td align="center">1698</td>
            <td align="center">1919</td>
            <td align="center">2169</td>
            <td align="center">2451</td>
            <td align="center">2770</td>
            <td align="center">3131</td>
        </tr>
        <tr>
            <td align="center">+109</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300109.png"></td>
            <td align="center">冬季沙拉</td>
            <td align="center">1010</td>
            <td align="center">1142</td>
            <td align="center">1291</td>
            <td align="center">1459</td>
            <td align="center">1649</td>
            <td align="center">1864</td>
            <td align="center">2107</td>
            <td align="center">2381</td>
            <td align="center">2691</td>
            <td align="center">3041</td>
        </tr>
        <tr>
            <td align="center">+901</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300901.png"></td>
            <td align="center">古怪的料理</td>
            <td align="center">1000</td>
            <td align="center">1130</td>
            <td align="center">1277</td>
            <td align="center">1444</td>
            <td align="center">1632</td>
            <td align="center">1845</td>
            <td align="center">2085</td>
            <td align="center">2357</td>
            <td align="center">2664</td>
            <td align="center">3011</td>
        </tr>
        <tr>
            <td align="center">+118</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300118.png"></td>
            <td align="center">炸起司</td>
            <td align="center">950</td>
            <td align="center">1074</td>
            <td align="center">1214</td>
            <td align="center">1372</td>
            <td align="center">1551</td>
            <td align="center">1753</td>
            <td align="center">1981</td>
            <td align="center">2239</td>
            <td align="center">2531</td>
            <td align="center">2861</td>
        </tr>
        <tr>
            <td align="center">+144</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300144.png"></td>
            <td align="center">焗豆</td>
            <td align="center">870</td>
            <td align="center">984</td>
            <td align="center">1112</td>
            <td align="center">1257</td>
            <td align="center">1421</td>
            <td align="center">1606</td>
            <td align="center">1815</td>
            <td align="center">2051</td>
            <td align="center">2318</td>
            <td align="center">2620</td>
        </tr>
        <tr>
            <td align="center">+156</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300156.png"></td>
            <td align="center">燉魚</td>
            <td align="center">870</td>
            <td align="center">984</td>
            <td align="center">1112</td>
            <td align="center">1257</td>
            <td align="center">1421</td>
            <td align="center">1606</td>
            <td align="center">1815</td>
            <td align="center">2051</td>
            <td align="center">2318</td>
            <td align="center">2620</td>
        </tr>
        <tr>
            <td align="center">+125</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300125.png"></td>
            <td align="center">火上鍋</td>
            <td align="center">860</td>
            <td align="center">972</td>
            <td align="center">1099</td>
            <td align="center">1242</td>
            <td align="center">1404</td>
            <td align="center">1587</td>
            <td align="center">1794</td>
            <td align="center">2028</td>
            <td align="center">2292</td>
            <td align="center">2590</td>
        </tr>
        <tr>
            <td align="center">+131</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300131.png"></td>
            <td align="center">焗烤</td>
            <td align="center">860</td>
            <td align="center">972</td>
            <td align="center">1099</td>
            <td align="center">1242</td>
            <td align="center">1404</td>
            <td align="center">1587</td>
            <td align="center">1794</td>
            <td align="center">2028</td>
            <td align="center">2292</td>
            <td align="center">2590</td>
        </tr>
        <tr>
            <td align="center">+130</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300130.png"></td>
            <td align="center">千層麵</td>
            <td align="center">800</td>
            <td align="center">904</td>
            <td align="center">1022</td>
            <td align="center">1155</td>
            <td align="center">1306</td>
            <td align="center">1476</td>
            <td align="center">1668</td>
            <td align="center">1885</td>
            <td align="center">2131</td>
            <td align="center">2409</td>
        </tr>
        <tr>
            <td align="center">+141</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300141.png"></td>
            <td align="center">水果沙拉</td>
            <td align="center">800</td>
            <td align="center">904</td>
            <td align="center">1022</td>
            <td align="center">1155</td>
            <td align="center">1306</td>
            <td align="center">1476</td>
            <td align="center">1668</td>
            <td align="center">1885</td>
            <td align="center">2131</td>
            <td align="center">2409</td>
        </tr>
        <tr>
            <td align="center">+168</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300168.png"></td>
            <td align="center">泥鰍鍋</td>
            <td align="center">800</td>
            <td align="center">904</td>
            <td align="center">1022</td>
            <td align="center">1155</td>
            <td align="center">1306</td>
            <td align="center">1476</td>
            <td align="center">1668</td>
            <td align="center">1885</td>
            <td align="center">2131</td>
            <td align="center">2409</td>
        </tr>
        <tr>
            <td align="center">+183</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300183.png"></td>
            <td align="center">鰤魚燉蘿蔔</td>
            <td align="center">780</td>
            <td align="center">882</td>
            <td align="center">997</td>
            <td align="center">1127</td>
            <td align="center">1274</td>
            <td align="center">1440</td>
            <td align="center">1628</td>
            <td align="center">1840</td>
            <td align="center">2080</td>
            <td align="center">2351</td>
        </tr>
        <tr>
            <td align="center">+181</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300181.png"></td>
            <td align="center">義式水煮魚</td>
            <td align="center">720</td>
            <td align="center">814</td>
            <td align="center">920</td>
            <td align="center">1040</td>
            <td align="center">1176</td>
            <td align="center">1329</td>
            <td align="center">1502</td>
            <td align="center">1698</td>
            <td align="center">1919</td>
            <td align="center">2169</td>
        </tr>
        <tr>
            <td align="center">+122</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300122.png"></td>
            <td align="center">夾餡沙丁魚</td>
            <td align="center">700</td>
            <td align="center">791</td>
            <td align="center">894</td>
            <td align="center">1011</td>
            <td align="center">1143</td>
            <td align="center">1292</td>
            <td align="center">1460</td>
            <td align="center">1650</td>
            <td align="center">1865</td>
            <td align="center">2108</td>
        </tr>
        <tr>
            <td align="center">+162</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300162.png"></td>
            <td align="center">河豚鍋</td>
            <td align="center">700</td>
            <td align="center">791</td>
            <td align="center">894</td>
            <td align="center">1011</td>
            <td align="center">1143</td>
            <td align="center">1292</td>
            <td align="center">1460</td>
            <td align="center">1650</td>
            <td align="center">1865</td>
            <td align="center">2108</td>
        </tr>
        <tr>
            <td align="center">+177</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300177.png"></td>
            <td align="center">煸炒沙拉</td>
            <td align="center">690</td>
            <td align="center">780</td>
            <td align="center">882</td>
            <td align="center">997</td>
            <td align="center">1127</td>
            <td align="center">1274</td>
            <td align="center">1440</td>
            <td align="center">1628</td>
            <td align="center">1840</td>
            <td align="center">2080</td>
        </tr>
        <tr>
            <td align="center">+174</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300174.png"></td>
            <td align="center">油封料理</td>
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
            <td align="center">+132</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300132.png"></td>
            <td align="center">法式鹹派</td>
            <td align="center">640</td>
            <td align="center">724</td>
            <td align="center">819</td>
            <td align="center">926</td>
            <td align="center">1047</td>
            <td align="center">1184</td>
            <td align="center">1338</td>
            <td align="center">1512</td>
            <td align="center">1709</td>
            <td align="center">1932</td>
        </tr>
        <tr>
            <td align="center">+120</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300120.png"></td>
            <td align="center">披薩</td>
            <td align="center">620</td>
            <td align="center">701</td>
            <td align="center">793</td>
            <td align="center">897</td>
            <td align="center">1014</td>
            <td align="center">1146</td>
            <td align="center">1295</td>
            <td align="center">1464</td>
            <td align="center">1655</td>
            <td align="center">1871</td>
        </tr>
        <tr>
            <td align="center">+135</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300135.png"></td>
            <td align="center">鯷魚熱沾醬</td>
            <td align="center">620</td>
            <td align="center">701</td>
            <td align="center">793</td>
            <td align="center">897</td>
            <td align="center">1014</td>
            <td align="center">1146</td>
            <td align="center">1295</td>
            <td align="center">1464</td>
            <td align="center">1655</td>
            <td align="center">1871</td>
        </tr>
        <tr>
            <td align="center">+153</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300153.png"></td>
            <td align="center">乾燒明蝦</td>
            <td align="center">620</td>
            <td align="center">701</td>
            <td align="center">793</td>
            <td align="center">897</td>
            <td align="center">1014</td>
            <td align="center">1146</td>
            <td align="center">1295</td>
            <td align="center">1464</td>
            <td align="center">1655</td>
            <td align="center">1871</td>
        </tr>
        <tr>
            <td align="center">+139</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300139.png"></td>
            <td align="center">印度咖喱角</td>
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
        <tr>
            <td align="center">+148</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300148.png"></td>
            <td align="center">焗烤濃湯</td>
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
        <tr>
            <td align="center">+100</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300100.png"></td>
            <td align="center">蘋果派</td>
            <td align="center">570</td>
            <td align="center">645</td>
            <td align="center">729</td>
            <td align="center">824</td>
            <td align="center">932</td>
            <td align="center">1054</td>
            <td align="center">1192</td>
            <td align="center">1347</td>
            <td align="center">1523</td>
            <td align="center">1721</td>
        </tr>
        <tr>
            <td align="center">+143</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300143.png"></td>
            <td align="center">草莓奶油蛋糕</td>
            <td align="center">570</td>
            <td align="center">645</td>
            <td align="center">729</td>
            <td align="center">824</td>
            <td align="center">932</td>
            <td align="center">1054</td>
            <td align="center">1192</td>
            <td align="center">1347</td>
            <td align="center">1523</td>
            <td align="center">1721</td>
        </tr>
        <tr>
            <td align="center">+159</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300159.png"></td>
            <td align="center">磅蛋糕</td>
            <td align="center">560</td>
            <td align="center">633</td>
            <td align="center">716</td>
            <td align="center">810</td>
            <td align="center">916</td>
            <td align="center">1036</td>
            <td align="center">1171</td>
            <td align="center">1324</td>
            <td align="center">1497</td>
            <td align="center">1692</td>
        </tr>
        <tr>
            <td align="center">+166</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300166.png"></td>
            <td align="center">法式香煎魚排</td>
            <td align="center">550</td>
            <td align="center">622</td>
            <td align="center">703</td>
            <td align="center">795</td>
            <td align="center">899</td>
            <td align="center">1016</td>
            <td align="center">1149</td>
            <td align="center">1299</td>
            <td align="center">1468</td>
            <td align="center">1659</td>
        </tr>
        <tr>
            <td align="center">+137</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300137.png"></td>
            <td align="center">醋漬蘿蔔絲</td>
            <td align="center">540</td>
            <td align="center">611</td>
            <td align="center">691</td>
            <td align="center">781</td>
            <td align="center">883</td>
            <td align="center">998</td>
            <td align="center">1128</td>
            <td align="center">1275</td>
            <td align="center">1441</td>
            <td align="center">1629</td>
        </tr>
        <tr>
            <td align="center">+157</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300157.png"></td>
            <td align="center">蒙布朗</td>
            <td align="center">530</td>
            <td align="center">599</td>
            <td align="center">677</td>
            <td align="center">766</td>
            <td align="center">866</td>
            <td align="center">979</td>
            <td align="center">1107</td>
            <td align="center">1251</td>
            <td align="center">1414</td>
            <td align="center">1598</td>
        </tr>
        <tr>
            <td align="center">+172</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300172.png"></td>
            <td align="center">鱉肉鍋</td>
            <td align="center">530</td>
            <td align="center">599</td>
            <td align="center">677</td>
            <td align="center">766</td>
            <td align="center">866</td>
            <td align="center">979</td>
            <td align="center">1107</td>
            <td align="center">1251</td>
            <td align="center">1414</td>
            <td align="center">1598</td>
        </tr>
        <tr>
            <td align="center">+149</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300149.png"></td>
            <td align="center">起司蛋糕</td>
            <td align="center">520</td>
            <td align="center">588</td>
            <td align="center">665</td>
            <td align="center">752</td>
            <td align="center">850</td>
            <td align="center">961</td>
            <td align="center">1086</td>
            <td align="center">1228</td>
            <td align="center">1388</td>
            <td align="center">1569</td>
        </tr>
        <tr>
            <td align="center">+136</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300136.png"></td>
            <td align="center">青蔬濃湯</td>
            <td align="center">490</td>
            <td align="center">554</td>
            <td align="center">627</td>
            <td align="center">709</td>
            <td align="center">802</td>
            <td align="center">907</td>
            <td align="center">1025</td>
            <td align="center">1159</td>
            <td align="center">1310</td>
            <td align="center">1481</td>
        </tr>
        <tr>
            <td align="center">+150</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300150.png"></td>
            <td align="center">蘋果塔</td>
            <td align="center">490</td>
            <td align="center">554</td>
            <td align="center">627</td>
            <td align="center">709</td>
            <td align="center">802</td>
            <td align="center">907</td>
            <td align="center">1025</td>
            <td align="center">1159</td>
            <td align="center">1310</td>
            <td align="center">1481</td>
        </tr>
        <tr>
            <td align="center">+180</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300180.png"></td>
            <td align="center">西西里風薄切生魚</td>
            <td align="center">490</td>
            <td align="center">554</td>
            <td align="center">627</td>
            <td align="center">709</td>
            <td align="center">802</td>
            <td align="center">907</td>
            <td align="center">1025</td>
            <td align="center">1159</td>
            <td align="center">1310</td>
            <td align="center">1481</td>
        </tr>
        <tr>
            <td align="center">+124</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300124.png"></td>
            <td align="center">關東煮</td>
            <td align="center">460</td>
            <td align="center">520</td>
            <td align="center">588</td>
            <td align="center">665</td>
            <td align="center">752</td>
            <td align="center">850</td>
            <td align="center">961</td>
            <td align="center">1086</td>
            <td align="center">1228</td>
            <td align="center">1388</td>
        </tr>
        <tr>
            <td align="center">+145</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300145.png"></td>
            <td align="center">美式鬆餅</td>
            <td align="center">460</td>
            <td align="center">520</td>
            <td align="center">588</td>
            <td align="center">665</td>
            <td align="center">752</td>
            <td align="center">850</td>
            <td align="center">961</td>
            <td align="center">1086</td>
            <td align="center">1228</td>
            <td align="center">1388</td>
        </tr>
        <tr>
            <td align="center">+178</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300178.png"></td>
            <td align="center">西式炸魚條</td>
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
        <tr>
            <td align="center">+146</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300146.png"></td>
            <td align="center">胡桃麵包</td>
            <td align="center">420</td>
            <td align="center">475</td>
            <td align="center">537</td>
            <td align="center">607</td>
            <td align="center">686</td>
            <td align="center">776</td>
            <td align="center">877</td>
            <td align="center">992</td>
            <td align="center">1121</td>
            <td align="center">1267</td>
        </tr>
        <tr>
            <td align="center">+158</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300158.png"></td>
            <td align="center">蘆薈優格</td>
            <td align="center">420</td>
            <td align="center">475</td>
            <td align="center">537</td>
            <td align="center">607</td>
            <td align="center">686</td>
            <td align="center">776</td>
            <td align="center">877</td>
            <td align="center">992</td>
            <td align="center">1121</td>
            <td align="center">1267</td>
        </tr>
        <tr>
            <td align="center">+165</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300165.png"></td>
            <td align="center">艾草麵包</td>
            <td align="center">420</td>
            <td align="center">475</td>
            <td align="center">537</td>
            <td align="center">607</td>
            <td align="center">686</td>
            <td align="center">776</td>
            <td align="center">877</td>
            <td align="center">992</td>
            <td align="center">1121</td>
            <td align="center">1267</td>
        </tr>
        <tr>
            <td align="center">+101</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300101.png"></td>
            <td align="center">草莓牛奶</td>
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
            <td align="center">+160</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300160.png"></td>
            <td align="center">鰹魚生魚片</td>
            <td align="center">409</td>
            <td align="center">463</td>
            <td align="center">524</td>
            <td align="center">593</td>
            <td align="center">671</td>
            <td align="center">759</td>
            <td align="center">858</td>
            <td align="center">970</td>
            <td align="center">1097</td>
            <td align="center">1240</td>
        </tr>
        <tr>
            <td align="center">+102</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300102.png"></td>
            <td align="center">烏龍麵</td>
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
            <td align="center">+133</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300133.png"></td>
            <td align="center">奶油玉米</td>
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
            <td align="center">+182</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300182.png"></td>
            <td align="center">香煎魚肉</td>
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
            <td align="center">+140</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300140.png"></td>
            <td align="center">焦糖杏仁</td>
            <td align="center">380</td>
            <td align="center">430</td>
            <td align="center">486</td>
            <td align="center">550</td>
            <td align="center">622</td>
            <td align="center">703</td>
            <td align="center">795</td>
            <td align="center">899</td>
            <td align="center">1016</td>
            <td align="center">1149</td>
        </tr>
        <tr>
            <td align="center">+115</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300115.png"></td>
            <td align="center">炸薯條</td>
            <td align="center">370</td>
            <td align="center">419</td>
            <td align="center">474</td>
            <td align="center">536</td>
            <td align="center">606</td>
            <td align="center">685</td>
            <td align="center">775</td>
            <td align="center">876</td>
            <td align="center">990</td>
            <td align="center">1119</td>
        </tr>
        <tr>
            <td align="center">+147</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300147.png"></td>
            <td align="center">銅鑼燒</td>
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
            <td align="center">+112</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300112.png"></td>
            <td align="center">地瓜甜點</td>
            <td align="center">350</td>
            <td align="center">396</td>
            <td align="center">448</td>
            <td align="center">507</td>
            <td align="center">573</td>
            <td align="center">648</td>
            <td align="center">733</td>
            <td align="center">829</td>
            <td align="center">937</td>
            <td align="center">1059</td>
        </tr>
        <tr>
            <td align="center">+105</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300105.png"></td>
            <td align="center">餅乾</td>
            <td align="center">310</td>
            <td align="center">351</td>
            <td align="center">397</td>
            <td align="center">449</td>
            <td align="center">508</td>
            <td align="center">575</td>
            <td align="center">650</td>
            <td align="center">735</td>
            <td align="center">831</td>
            <td align="center">940</td>
        </tr>
        <tr>
            <td align="center">+179</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300179.png"></td>
            <td align="center">糖醋鯉魚</td>
            <td align="center">310</td>
            <td align="center">351</td>
            <td align="center">397</td>
            <td align="center">449</td>
            <td align="center">508</td>
            <td align="center">575</td>
            <td align="center">650</td>
            <td align="center">735</td>
            <td align="center">831</td>
            <td align="center">940</td>
        </tr>
        <tr>
            <td align="center">+173</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300173.png"></td>
            <td align="center">甘露煮</td>
            <td align="center">270</td>
            <td align="center">306</td>
            <td align="center">346</td>
            <td align="center">391</td>
            <td align="center">442</td>
            <td align="center">500</td>
            <td align="center">565</td>
            <td align="center">639</td>
            <td align="center">723</td>
            <td align="center">817</td>
        </tr>
        <tr>
            <td align="center">+127</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300127.png"></td>
            <td align="center">西班牙香蒜蝦</td>
            <td align="center">260</td>
            <td align="center">294</td>
            <td align="center">333</td>
            <td align="center">377</td>
            <td align="center">427</td>
            <td align="center">483</td>
            <td align="center">546</td>
            <td align="center">617</td>
            <td align="center">698</td>
            <td align="center">789</td>
        </tr>
        <tr>
            <td align="center">+163</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300163.png"></td>
            <td align="center">糖煮水果</td>
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
            <td align="center">+184</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300184.png"></td>
            <td align="center">梅漬小黃瓜</td>
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
            <td align="center">+117</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300117.png"></td>
            <td align="center">布丁</td>
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
            <td align="center">+164</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300164.png"></td>
            <td align="center">山蔬炒蛋</td>
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
            <td align="center">+175</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300175.png"></td>
            <td align="center">味噌煮鯖魚</td>
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
            <td align="center">+171</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300171.png"></td>
            <td align="center">山珍魚包燒烤</td>
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
            <td align="center">+142</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300142.png"></td>
            <td align="center">烤地瓜</td>
            <td align="center">70</td>
            <td align="center">80</td>
            <td align="center">91</td>
            <td align="center">103</td>
            <td align="center">117</td>
            <td align="center">133</td>
            <td align="center">151</td>
            <td align="center">171</td>
            <td align="center">194</td>
            <td align="center">220</td>
        </tr>
        <tr>
            <td align="center">+900</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_3300900.png"></td>
            <td align="center">看起來很難吃的料理</td>
            <td align="center">10</td>
            <td align="center">12</td>
            <td align="center">14</td>
            <td align="center">16</td>
            <td align="center">19</td>
            <td align="center">22</td>
            <td align="center">25</td>
            <td align="center">29</td>
            <td align="center">33</td>
            <td align="center">38</td>
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
