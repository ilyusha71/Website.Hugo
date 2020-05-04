---
title: "43種魚類出貨價格"
date: 2020-04-14T22:06:12+08:00
description: 43種魚類各品質出貨價格
draft: false
hideToc: false
enableToc: false
enableTocContent: true
author: 伊琉沙 AKA 哇咔咔
authorEmoji: 👩🏿‍🚀
tags: 
- 出貨價格
- 釣魚
series:
- 哆啦A夢牧場物語
categories:
- 哆啦A夢
image: images/post/Season_of_Story/Sprite/icon_5000190.png
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

### 魚類出貨價格
+ `物品ID`=`5000000`+`魚類ID`
+ 以`出貨價格`遞減排序：
<table>
    <thead>
        <tr>
            <td align="center">ID</td>
            <td align="center"></td>
            <td align="center">&emsp;魚&emsp;類&emsp;名&emsp;稱&emsp;</td>
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
            <td align="center">190</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000190.png"></td>
            <td align="center">大尾魚</td>
            <td align="center">2440</td>
            <td align="center">2758</td>
            <td align="center">3117</td>
            <td align="center">3523</td>
            <td align="center">3981</td>
            <td align="center">4499</td>
            <td align="center">5084</td>
            <td align="center">5745</td>
            <td align="center">6492</td>
            <td align="center">7336</td>
        </tr>
        <tr>
            <td align="center">187</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000187.png"></td>
            <td align="center">皇帶魚</td>
            <td align="center">2360</td>
            <td align="center">2667</td>
            <td align="center">3014</td>
            <td align="center">3406</td>
            <td align="center">3849</td>
            <td align="center">4350</td>
            <td align="center">4916</td>
            <td align="center">5556</td>
            <td align="center">6279</td>
            <td align="center">7096</td>
        </tr>
        <tr>
            <td align="center">188</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000188.png"></td>
            <td align="center">皺鰓鯊</td>
            <td align="center">2290</td>
            <td align="center">2588</td>
            <td align="center">2925</td>
            <td align="center">3306</td>
            <td align="center">3736</td>
            <td align="center">4222</td>
            <td align="center">4771</td>
            <td align="center">5392</td>
            <td align="center">6093</td>
            <td align="center">6886</td>
        </tr>
        <tr>
            <td align="center">189</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000189.png"></td>
            <td align="center">巨狗脂鯉</td>
            <td align="center">2210</td>
            <td align="center">2498</td>
            <td align="center">2823</td>
            <td align="center">3190</td>
            <td align="center">3605</td>
            <td align="center">4074</td>
            <td align="center">4604</td>
            <td align="center">5203</td>
            <td align="center">5880</td>
            <td align="center">6645</td>
        </tr>
        <tr>
            <td align="center">162</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000162.png"></td>
            <td align="center">螃蟹</td>
            <td align="center">1340</td>
            <td align="center">1515</td>
            <td align="center">1712</td>
            <td align="center">1935</td>
            <td align="center">2187</td>
            <td align="center">2472</td>
            <td align="center">2794</td>
            <td align="center">3158</td>
            <td align="center">3569</td>
            <td align="center">4033</td>
        </tr>
        <tr>
            <td align="center">165</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000165.png"></td>
            <td align="center">鮪魚</td>
            <td align="center">1070</td>
            <td align="center">1210</td>
            <td align="center">1368</td>
            <td align="center">1546</td>
            <td align="center">1747</td>
            <td align="center">1975</td>
            <td align="center">2232</td>
            <td align="center">2523</td>
            <td align="center">2851</td>
            <td align="center">3222</td>
        </tr>
        <tr>
            <td align="center">163</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000163.png"></td>
            <td align="center">燈籠魚</td>
            <td align="center">790</td>
            <td align="center">893</td>
            <td align="center">1010</td>
            <td align="center">1142</td>
            <td align="center">1291</td>
            <td align="center">1459</td>
            <td align="center">1649</td>
            <td align="center">1864</td>
            <td align="center">2107</td>
            <td align="center">2381</td>
        </tr>
        <tr>
            <td align="center">127</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000127.png"></td>
            <td align="center">旗魚</td>
            <td align="center">730</td>
            <td align="center">825</td>
            <td align="center">933</td>
            <td align="center">1055</td>
            <td align="center">1193</td>
            <td align="center">1349</td>
            <td align="center">1525</td>
            <td align="center">1724</td>
            <td align="center">1949</td>
            <td align="center">2203</td>
        </tr>
        <tr>
            <td align="center">126</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000126.png"></td>
            <td align="center">鯊魚</td>
            <td align="center">680</td>
            <td align="center">769</td>
            <td align="center">869</td>
            <td align="center">982</td>
            <td align="center">1110</td>
            <td align="center">1255</td>
            <td align="center">1419</td>
            <td align="center">1604</td>
            <td align="center">1813</td>
            <td align="center">2049</td>
        </tr>
        <tr>
            <td align="center">143</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000143.png"></td>
            <td align="center">骨舌魚</td>
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
            <td align="center">101</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000101.png"></td>
            <td align="center">巨大紅點鮭</td>
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
            <td align="center">167</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000167.png"></td>
            <td align="center">鰤魚</td>
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
            <td align="center">123</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000123.png"></td>
            <td align="center">鰻魚</td>
            <td align="center">510</td>
            <td align="center">577</td>
            <td align="center">653</td>
            <td align="center">738</td>
            <td align="center">834</td>
            <td align="center">943</td>
            <td align="center">1066</td>
            <td align="center">1205</td>
            <td align="center">1362</td>
            <td align="center">1540</td>
        </tr>
        <tr>
            <td align="center">124</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000124.png"></td>
            <td align="center">食人魚</td>
            <td align="center">390</td>
            <td align="center">441</td>
            <td align="center">499</td>
            <td align="center">564</td>
            <td align="center">638</td>
            <td align="center">721</td>
            <td align="center">815</td>
            <td align="center">921</td>
            <td align="center">1041</td>
            <td align="center">1177</td>
        </tr>
        <tr>
            <td align="center">104</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000104.png"></td>
            <td align="center">鯛魚</td>
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
            <td align="center">125</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000125.png"></td>
            <td align="center">鱉</td>
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
            <td align="center">166</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000166.png"></td>
            <td align="center">蝦</td>
            <td align="center">190</td>
            <td align="center">215</td>
            <td align="center">243</td>
            <td align="center">275</td>
            <td align="center">311</td>
            <td align="center">352</td>
            <td align="center">398</td>
            <td align="center">450</td>
            <td align="center">509</td>
            <td align="center">576</td>
        </tr>
        <tr>
            <td align="center">186</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000186.png"></td>
            <td align="center">比目魚</td>
            <td align="center">160</td>
            <td align="center">181</td>
            <td align="center">205</td>
            <td align="center">232</td>
            <td align="center">263</td>
            <td align="center">298</td>
            <td align="center">337</td>
            <td align="center">381</td>
            <td align="center">431</td>
            <td align="center">488</td>
        </tr>
        <tr>
            <td align="center">161</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000161.png"></td>
            <td align="center">河豚</td>
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
            <td align="center">102</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000102.png"></td>
            <td align="center">泥鰍</td>
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
            <td align="center">103</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000103.png"></td>
            <td align="center">花鯰</td>
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
            <td align="center">129</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000129.png"></td>
            <td align="center">沙鮻</td>
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
            <td align="center">146</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000146.png"></td>
            <td align="center">白帶魚</td>
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
            <td align="center">105</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000105.png"></td>
            <td align="center">剝皮魚</td>
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
            <td align="center">122</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000122.png"></td>
            <td align="center">鱧魚</td>
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
            <td align="center">142</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000142.png"></td>
            <td align="center">香魚</td>
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
            <td align="center">144</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000144.png"></td>
            <td align="center">鰹魚</td>
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
            <td align="center">164</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000164.png"></td>
            <td align="center">海天使</td>
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
            <td align="center">140</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000140.png"></td>
            <td align="center">鮭魚</td>
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
            <td align="center">141</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000141.png"></td>
            <td align="center">虹鱒</td>
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
            <td align="center">145</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000145.png"></td>
            <td align="center">鯖魚</td>
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
            <td align="center">100</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000100.png"></td>
            <td align="center">仙女鱒</td>
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
            <td align="center">181</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000181.png"></td>
            <td align="center">鯽魚</td>
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
            <td align="center">182</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000182.png"></td>
            <td align="center">章魚</td>
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
            <td align="center">180</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000180.png"></td>
            <td align="center">鯉魚</td>
            <td align="center">40</td>
            <td align="center">46</td>
            <td align="center">52</td>
            <td align="center">59</td>
            <td align="center">67</td>
            <td align="center">76</td>
            <td align="center">86</td>
            <td align="center">98</td>
            <td align="center">111</td>
            <td align="center">126</td>
        </tr>
        <tr>
            <td align="center">106</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000106.png"></td>
            <td align="center">烏賊</td>
            <td align="center">30</td>
            <td align="center">34</td>
            <td align="center">39</td>
            <td align="center">45</td>
            <td align="center">51</td>
            <td align="center">58</td>
            <td align="center">66</td>
            <td align="center">75</td>
            <td align="center">85</td>
            <td align="center">97</td>
        </tr>
        <tr>
            <td align="center">121</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000121.png"></td>
            <td align="center">小龍蝦</td>
            <td align="center">30</td>
            <td align="center">34</td>
            <td align="center">39</td>
            <td align="center">45</td>
            <td align="center">51</td>
            <td align="center">58</td>
            <td align="center">66</td>
            <td align="center">75</td>
            <td align="center">85</td>
            <td align="center">97</td>
        </tr>
        <tr>
            <td align="center">128</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000128.png"></td>
            <td align="center">沙丁魚</td>
            <td align="center">30</td>
            <td align="center">34</td>
            <td align="center">39</td>
            <td align="center">45</td>
            <td align="center">51</td>
            <td align="center">58</td>
            <td align="center">66</td>
            <td align="center">75</td>
            <td align="center">85</td>
            <td align="center">97</td>
        </tr>
        <tr>
            <td align="center">183</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000183.png"></td>
            <td align="center">金魚</td>
            <td align="center">30</td>
            <td align="center">34</td>
            <td align="center">39</td>
            <td align="center">45</td>
            <td align="center">51</td>
            <td align="center">58</td>
            <td align="center">66</td>
            <td align="center">75</td>
            <td align="center">85</td>
            <td align="center">97</td>
        </tr>
        <tr>
            <td align="center">184</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000184.png"></td>
            <td align="center">日本花鱸</td>
            <td align="center">30</td>
            <td align="center">34</td>
            <td align="center">39</td>
            <td align="center">45</td>
            <td align="center">51</td>
            <td align="center">58</td>
            <td align="center">66</td>
            <td align="center">75</td>
            <td align="center">85</td>
            <td align="center">97</td>
        </tr>
        <tr>
            <td align="center">185</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000185.png"></td>
            <td align="center">竹莢魚</td>
            <td align="center">30</td>
            <td align="center">34</td>
            <td align="center">39</td>
            <td align="center">45</td>
            <td align="center">51</td>
            <td align="center">58</td>
            <td align="center">66</td>
            <td align="center">75</td>
            <td align="center">85</td>
            <td align="center">97</td>
        </tr>
        <tr>
            <td align="center">120</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000120.png"></td>
            <td align="center">青鱂魚</td>
            <td align="center">20</td>
            <td align="center">23</td>
            <td align="center">26</td>
            <td align="center">30</td>
            <td align="center">34</td>
            <td align="center">39</td>
            <td align="center">45</td>
            <td align="center">51</td>
            <td align="center">58</td>
            <td align="center">66</td>
        </tr>
        <tr>
            <td align="center">160</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000160.png"></td>
            <td align="center">西太公魚</td>
            <td align="center">20</td>
            <td align="center">23</td>
            <td align="center">26</td>
            <td align="center">30</td>
            <td align="center">34</td>
            <td align="center">39</td>
            <td align="center">45</td>
            <td align="center">51</td>
            <td align="center">58</td>
            <td align="center">66</td>
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

<table>
    <thead>
        <tr>
            <td colspan="10">釣魚</td>        
        </tr>
    </thead>
    <tr>        
        <td align="center"><a href="../doraemon-story-live-fishing"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_1001060.png">釣魚資訊</a></td>
        <td align="center"><a href="../doraemon-story-tool-rod"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_1001065.png">釣竿</a></td>
        <td align="center"><a href="../doraemon-story-tool-land-fishing-rod"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_1001066.png">地底釣竿</a></td>
        <td align="center"><a href="../doraemon-story-size-fishes"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_5000187.png">尺寸大小</a></td>
        <td align="center"><a href="../doraemon-story-shipping-prices-fishes"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_5000190.png">出貨價格</a></td>
        <td align="center"><a href="../doraemon-story-shop-21300-sandy-tackle-shop/#魚拓"><img width="64px" src= "/images/post/Season_of_Story/Texture2D/tex_goods_21330.png">魚拓</a></td>
        <td align="center"><a href="../#魚料理"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_3300169.png">魚料理</a></td>
        <td align="center"><a href="../doraemon-story-interior-decorations-3/#標本"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_7026010.png">魚標本</a></td>
    </tr>
</table>
