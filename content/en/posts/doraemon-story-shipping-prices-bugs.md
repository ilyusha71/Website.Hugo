---
title: "44種蟲類出貨價格"
date: 2020-04-14T22:01:12+08:00
description: 44種蟲類各品質出貨價格
draft: false
hideToc: false
enableToc: false
enableTocContent: true
author: 伊琉沙 AKA 哇咔咔
authorEmoji: 👩🏿‍🚀
tags: 
- 捕蟲
- 出貨價格
series:
- 哆啦A夢牧場物語
categories:
- 哆啦A夢
image: images/post/Season_of_Story/Sprite/icon_6000133.png
libraries:
- katex
---
<mark>最後更新：2020/04/27</mark>

## 捕蟲系統與蟲類圖鑑
<table>
    <thead>
        <tr>
            <td colspan="10">捕蟲系統與蟲類圖鑑</td>        
        </tr>
    </thead>
    <tr>        
        <td align="center"><a href="../#捕蟲資訊"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_1001140.png">捕蟲資訊</a></td>
        <td align="center"><a href="../doraemon-story-size-bugs"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_6000159.png">尺寸大小</a></td>
        <td align="center"><a href="../doraemon-story-shipping-prices-bugs"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_6000133.png">出貨價格</a></td>
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

### 蟲類出貨價格
+ `物品ID`=`6000000`+`蟲類ID`
+ 以`出貨價格`遞減排序：
<table>
    <thead>
        <tr>
            <td align="center">ID</td>
            <td align="center"></td>
            <td align="center">&emsp;蟲&emsp;類&emsp;名&emsp;稱&emsp;</td>
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
            <td align="center">133</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000133.png"></td>
            <td align="center">高卡薩斯南洋大兜蟲</td>
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
            <td align="center">134</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000134.png"></td>
            <td align="center">赫克力士長戟大兜蟲</td>
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
            <td align="center">135</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000135.png"></td>
            <td align="center">日本大鍬形蟲</td>
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
            <td align="center">122</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000122.png"></td>
            <td align="center">紅頸鳳蝶</td>
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
            <td align="center">126</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000126.png"></td>
            <td align="center">閃蝶</td>
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
            <td align="center">136</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000136.png"></td>
            <td align="center">鋸鍬形蟲</td>
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
            <td align="center">137</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000137.png"></td>
            <td align="center">扁鍬形蟲</td>
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
            <td align="center">138</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000138.png"></td>
            <td align="center">高砂深山鍬形蟲</td>
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
            <td align="center">159</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000159.png"></td>
            <td align="center">亞歷珊卓皇后鳥翼蝶</td>
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
            <td align="center">103</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000103.png"></td>
            <td align="center">鳳蝶</td>
            <td align="center">80</td>
            <td align="center">91</td>
            <td align="center">103</td>
            <td align="center">117</td>
            <td align="center">133</td>
            <td align="center">151</td>
            <td align="center">171</td>
            <td align="center">194</td>
            <td align="center">220</td>
            <td align="center">249</td>
        </tr>
        <tr>
            <td align="center">104</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000104.png"></td>
            <td align="center">烏鴉鳳蝶</td>
            <td align="center">80</td>
            <td align="center">91</td>
            <td align="center">103</td>
            <td align="center">117</td>
            <td align="center">133</td>
            <td align="center">151</td>
            <td align="center">171</td>
            <td align="center">194</td>
            <td align="center">220</td>
            <td align="center">249</td>
        </tr>
        <tr>
            <td align="center">107</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000107.png"></td>
            <td align="center">黃鉤蛺蝶</td>
            <td align="center">80</td>
            <td align="center">91</td>
            <td align="center">103</td>
            <td align="center">117</td>
            <td align="center">133</td>
            <td align="center">151</td>
            <td align="center">171</td>
            <td align="center">194</td>
            <td align="center">220</td>
            <td align="center">249</td>
        </tr>
        <tr>
            <td align="center">123</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000123.png"></td>
            <td align="center">螢火蟲</td>
            <td align="center">80</td>
            <td align="center">91</td>
            <td align="center">103</td>
            <td align="center">117</td>
            <td align="center">133</td>
            <td align="center">151</td>
            <td align="center">171</td>
            <td align="center">194</td>
            <td align="center">220</td>
            <td align="center">249</td>
        </tr>
        <tr>
            <td align="center">127</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000127.png"></td>
            <td align="center">大水青蛾</td>
            <td align="center">80</td>
            <td align="center">91</td>
            <td align="center">103</td>
            <td align="center">117</td>
            <td align="center">133</td>
            <td align="center">151</td>
            <td align="center">171</td>
            <td align="center">194</td>
            <td align="center">220</td>
            <td align="center">249</td>
        </tr>
        <tr>
            <td align="center">132</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000132.png"></td>
            <td align="center">獨角仙</td>
            <td align="center">80</td>
            <td align="center">91</td>
            <td align="center">103</td>
            <td align="center">117</td>
            <td align="center">133</td>
            <td align="center">151</td>
            <td align="center">171</td>
            <td align="center">194</td>
            <td align="center">220</td>
            <td align="center">249</td>
        </tr>
        <tr>
            <td align="center">157</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000157.png"></td>
            <td align="center">弱水斑蛺蝶</td>
            <td align="center">80</td>
            <td align="center">91</td>
            <td align="center">103</td>
            <td align="center">117</td>
            <td align="center">133</td>
            <td align="center">151</td>
            <td align="center">171</td>
            <td align="center">194</td>
            <td align="center">220</td>
            <td align="center">249</td>
        </tr>
        <tr>
            <td align="center">158</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000158.png"></td>
            <td align="center">大白斑蝶</td>
            <td align="center">80</td>
            <td align="center">91</td>
            <td align="center">103</td>
            <td align="center">117</td>
            <td align="center">133</td>
            <td align="center">151</td>
            <td align="center">171</td>
            <td align="center">194</td>
            <td align="center">220</td>
            <td align="center">249</td>
        </tr>
        <tr>
            <td align="center">160</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000160.png"></td>
            <td align="center">日本天蠶</td>
            <td align="center">80</td>
            <td align="center">91</td>
            <td align="center">103</td>
            <td align="center">117</td>
            <td align="center">133</td>
            <td align="center">151</td>
            <td align="center">171</td>
            <td align="center">194</td>
            <td align="center">220</td>
            <td align="center">249</td>
        </tr>
        <tr>
            <td align="center">100</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000100.png"></td>
            <td align="center">斑緣點粉蝶</td>
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
            <td align="center">101</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000101.png"></td>
            <td align="center">白粉蝶</td>
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
            <td align="center">102</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000102.png"></td>
            <td align="center">蜜蜂</td>
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
            <td align="center">105</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000105.png"></td>
            <td align="center">中華劍角蝗</td>
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
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000106.png"></td>
            <td align="center">斑蝗</td>
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
            <td align="center">108</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000108.png"></td>
            <td align="center">螻蛄</td>
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
            <td align="center">109</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000109.png"></td>
            <td align="center">七星瓢蟲</td>
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
            <td align="center">110</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000110.png"></td>
            <td align="center">黃色瓢蟲</td>
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
            <td align="center">120</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000120.png"></td>
            <td align="center">螳螂</td>
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
            <td align="center">121</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000121.png"></td>
            <td align="center">飛蝗</td>
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
            <td align="center">124</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000124.png"></td>
            <td align="center">綠胸晏蜓</td>
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
            <td align="center">125</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000125.png"></td>
            <td align="center">無霸勾蜓</td>
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
            <td align="center">128</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000128.png"></td>
            <td align="center">日本油蟬</td>
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
            <td align="center">129</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000129.png"></td>
            <td align="center">日本暮蟬</td>
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
            <td align="center">130</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000130.png"></td>
            <td align="center">斑透翅蟬</td>
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
            <td align="center">131</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000131.png"></td>
            <td align="center">寒蟬</td>
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
            <td align="center">153</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000153.png"></td>
            <td align="center">蝗蟲</td>
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
            <td align="center">154</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000154.png"></td>
            <td align="center">鈴蟲</td>
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
            <td align="center">155</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000155.png"></td>
            <td align="center">寬翅紡織娘</td>
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
            <td align="center">156</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000156.png"></td>
            <td align="center">蟋蟀</td>
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
            <td align="center">161</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000161.png"></td>
            <td align="center">艷金龜</td>
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
            <td align="center">162</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000162.png"></td>
            <td align="center">吉丁蟲</td>
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
            <td align="center">180</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000180.png"></td>
            <td align="center">鼠婦</td>
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
            <td align="center">181</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000181.png"></td>
            <td align="center">奇異海蟑螂</td>
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
            <td align="center">182</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000182.png"></td>
            <td align="center">蜈蚣</td>
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
            <td align="center">183</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000183.png"></td>
            <td align="center">螞蟻</td>
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
