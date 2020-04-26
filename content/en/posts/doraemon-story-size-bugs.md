---
title: "44種蟲類尺寸大小"
date: 2020-04-26T22:06:12+08:00
description: 44種蟲類各品質尺寸大小
draft: false
hideToc: false
enableToc: false
enableTocContent: true
author: 伊琉沙 AKA 哇咔咔
authorEmoji: 👩🏿‍🚀
tags: 
- 尺寸大小
- 蟲類
series:
- 哆啦A夢牧場物語
categories:
- 哆啦A夢
image: images/post/Season_of_Story/Sprite/icon_6000159.png
libraries:
- katex
---
## 尺寸大小
+ [所有物品尺寸大小索引](../doraemon-story-index/#尺寸大小)
+ 各品質物品的`尺寸大小`為`最小尺寸`與`最大尺寸`的線性插值。

### 源代碼
```C#
private float CalculateSizeFromQuality()
{
    if (this.Master.MaxSize == 0f)
    {
        return 0f;
    }
    float num = (this.Master.MaxSize - this.Master.MinSize) / (float)Item.MAX_QUALITY;
    float num2 = this.Master.MinSize + num * (float)this.mQuality;
    return (float)Mathf.FloorToInt(num2 * 10f) / 10f;
}
```
### 計算公式
$$尺寸差值 = （\dfrac {最大尺寸-最小尺寸}{品質級數}），品質級數=10$$
$$線性插值 = （最小尺寸 +尺寸差值 \times 品質等級）$$
$$尺寸大小 = \dfrac{無條件捨去（線性插值\times 10）}{10}$$

### 蟲類
+ `物品ID`=`6000000`+`蟲類ID`
+ 蟲類尺寸大小單位為`公釐`。
+ 以`尺寸大小`遞減排序：
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
            <td align="center">159</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000159.png"></td>
            <td align="center">亞歷珊卓皇后鳥翼蝶</td>
            <td align="center">240.4</td>
            <td align="center">245</td>
            <td align="center">249.6</td>
            <td align="center">254.3</td>
            <td align="center">258.9</td>
            <td align="center">263.5</td>
            <td align="center">268.2</td>
            <td align="center">272.8</td>
            <td align="center">277.4</td>
            <td align="center">282.1</td>
        </tr>
        <tr>
            <td align="center">122</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000122.png"></td>
            <td align="center">紅頸鳳蝶</td>
            <td align="center">191.8</td>
            <td align="center">197</td>
            <td align="center">202.2</td>
            <td align="center">207.3</td>
            <td align="center">212.5</td>
            <td align="center">217.7</td>
            <td align="center">222.8</td>
            <td align="center">228</td>
            <td align="center">233.2</td>
            <td align="center">238.4</td>
        </tr>
        <tr>
            <td align="center">134</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000134.png"></td>
            <td align="center">赫克力士長戟大兜蟲</td>
            <td align="center">109.1</td>
            <td align="center">117</td>
            <td align="center">124.9</td>
            <td align="center">132.9</td>
            <td align="center">140.8</td>
            <td align="center">148.7</td>
            <td align="center">156.7</td>
            <td align="center">164.6</td>
            <td align="center">172.5</td>
            <td align="center">180.5</td>
        </tr>
        <tr>
            <td align="center">160</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000160.png"></td>
            <td align="center">日本天蠶</td>
            <td align="center">120.4</td>
            <td align="center">126.4</td>
            <td align="center">132.4</td>
            <td align="center">138.3</td>
            <td align="center">144.3</td>
            <td align="center">150.3</td>
            <td align="center">156.2</td>
            <td align="center">162.2</td>
            <td align="center">168.2</td>
            <td align="center">174.2</td>
        </tr>
        <tr>
            <td align="center">182</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000182.png"></td>
            <td align="center">蜈蚣</td>
            <td align="center">87.3</td>
            <td align="center">94.5</td>
            <td align="center">101.7</td>
            <td align="center">108.9</td>
            <td align="center">116.1</td>
            <td align="center">123.3</td>
            <td align="center">130.5</td>
            <td align="center">137.7</td>
            <td align="center">144.9</td>
            <td align="center">152.1</td>
        </tr>
        <tr>
            <td align="center">126</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000126.png"></td>
            <td align="center">閃蝶</td>
            <td align="center">105</td>
            <td align="center">109.5</td>
            <td align="center">113.9</td>
            <td align="center">118.4</td>
            <td align="center">122.9</td>
            <td align="center">127.3</td>
            <td align="center">131.8</td>
            <td align="center">136.2</td>
            <td align="center">140.7</td>
            <td align="center">145.2</td>
        </tr>
        <tr>
            <td align="center">158</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000158.png"></td>
            <td align="center">大白斑蝶</td>
            <td align="center">114.7</td>
            <td align="center">117.3</td>
            <td align="center">119.9</td>
            <td align="center">122.5</td>
            <td align="center">125.1</td>
            <td align="center">127.7</td>
            <td align="center">130.3</td>
            <td align="center">132.9</td>
            <td align="center">135.5</td>
            <td align="center">138.2</td>
        </tr>
        <tr>
            <td align="center">104</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000104.png"></td>
            <td align="center">烏鴉鳳蝶</td>
            <td align="center">104.4</td>
            <td align="center">107.1</td>
            <td align="center">109.8</td>
            <td align="center">112.5</td>
            <td align="center">115.2</td>
            <td align="center">117.9</td>
            <td align="center">120.6</td>
            <td align="center">123.3</td>
            <td align="center">126</td>
            <td align="center">128.7</td>
        </tr>
        <tr>
            <td align="center">125</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000125.png"></td>
            <td align="center">無霸勾蜓</td>
            <td align="center">74.7</td>
            <td align="center">80.2</td>
            <td align="center">85.7</td>
            <td align="center">91.2</td>
            <td align="center">96.7</td>
            <td align="center">102.2</td>
            <td align="center">107.7</td>
            <td align="center">113.2</td>
            <td align="center">118.7</td>
            <td align="center">124.3</td>
        </tr>
        <tr>
            <td align="center">133</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000133.png"></td>
            <td align="center">高卡薩斯南洋大兜蟲</td>
            <td align="center">93.6</td>
            <td align="center">96.8</td>
            <td align="center">100</td>
            <td align="center">103.2</td>
            <td align="center">106.4</td>
            <td align="center">109.6</td>
            <td align="center">112.8</td>
            <td align="center">116</td>
            <td align="center">119.2</td>
            <td align="center">122.5</td>
        </tr>
        <tr>
            <td align="center">157</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000157.png"></td>
            <td align="center">弱水斑蛺蝶</td>
            <td align="center">92.2</td>
            <td align="center">95.3</td>
            <td align="center">98.3</td>
            <td align="center">101.4</td>
            <td align="center">104.4</td>
            <td align="center">107.5</td>
            <td align="center">110.5</td>
            <td align="center">113.6</td>
            <td align="center">116.6</td>
            <td align="center">119.7</td>
        </tr>
        <tr>
            <td align="center">127</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000127.png"></td>
            <td align="center">大水青蛾</td>
            <td align="center">76.1</td>
            <td align="center">78.1</td>
            <td align="center">80.1</td>
            <td align="center">82</td>
            <td align="center">84</td>
            <td align="center">86</td>
            <td align="center">87.9</td>
            <td align="center">89.9</td>
            <td align="center">91.9</td>
            <td align="center">93.9</td>
        </tr>
        <tr>
            <td align="center">120</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000120.png"></td>
            <td align="center">螳螂</td>
            <td align="center">61.5</td>
            <td align="center">64.9</td>
            <td align="center">68.4</td>
            <td align="center">71.8</td>
            <td align="center">75.3</td>
            <td align="center">78.7</td>
            <td align="center">82.1</td>
            <td align="center">85.6</td>
            <td align="center">89</td>
            <td align="center">92.5</td>
        </tr>
        <tr>
            <td align="center">124</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000124.png"></td>
            <td align="center">綠胸晏蜓</td>
            <td align="center">55.1</td>
            <td align="center">59</td>
            <td align="center">62.9</td>
            <td align="center">66.8</td>
            <td align="center">70.8</td>
            <td align="center">74.7</td>
            <td align="center">78.6</td>
            <td align="center">82.5</td>
            <td align="center">86.4</td>
            <td align="center">90.4</td>
        </tr>
        <tr>
            <td align="center">103</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000103.png"></td>
            <td align="center">鳳蝶</td>
            <td align="center">65.9</td>
            <td align="center">68.2</td>
            <td align="center">70.5</td>
            <td align="center">72.9</td>
            <td align="center">75.2</td>
            <td align="center">77.5</td>
            <td align="center">79.9</td>
            <td align="center">82.2</td>
            <td align="center">84.5</td>
            <td align="center">86.9</td>
        </tr>
        <tr>
            <td align="center">105</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000105.png"></td>
            <td align="center">中華劍角蝗</td>
            <td align="center">52.7</td>
            <td align="center">56.2</td>
            <td align="center">59.7</td>
            <td align="center">63.2</td>
            <td align="center">66.8</td>
            <td align="center">70.3</td>
            <td align="center">73.8</td>
            <td align="center">77.3</td>
            <td align="center">80.8</td>
            <td align="center">84.4</td>
        </tr>
        <tr>
            <td align="center">132</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000132.png"></td>
            <td align="center">獨角仙</td>
            <td align="center">60.6</td>
            <td align="center">63.1</td>
            <td align="center">65.6</td>
            <td align="center">68.1</td>
            <td align="center">70.6</td>
            <td align="center">73.1</td>
            <td align="center">75.6</td>
            <td align="center">78.1</td>
            <td align="center">80.6</td>
            <td align="center">83.2</td>
        </tr>
        <tr>
            <td align="center">135</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000135.png"></td>
            <td align="center">日本大鍬形蟲</td>
            <td align="center">45.1</td>
            <td align="center">49</td>
            <td align="center">53</td>
            <td align="center">56.9</td>
            <td align="center">60.9</td>
            <td align="center">64.8</td>
            <td align="center">68.7</td>
            <td align="center">72.7</td>
            <td align="center">76.6</td>
            <td align="center">80.6</td>
        </tr>
        <tr>
            <td align="center">138</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000138.png"></td>
            <td align="center">高砂深山鍬形蟲</td>
            <td align="center">42.8</td>
            <td align="center">46.4</td>
            <td align="center">50.1</td>
            <td align="center">53.7</td>
            <td align="center">57.4</td>
            <td align="center">61</td>
            <td align="center">64.6</td>
            <td align="center">68.3</td>
            <td align="center">71.9</td>
            <td align="center">75.6</td>
        </tr>
        <tr>
            <td align="center">136</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000136.png"></td>
            <td align="center">鋸鍬形蟲</td>
            <td align="center">36.8</td>
            <td align="center">41.1</td>
            <td align="center">45.3</td>
            <td align="center">49.6</td>
            <td align="center">53.9</td>
            <td align="center">58.1</td>
            <td align="center">62.4</td>
            <td align="center">66.6</td>
            <td align="center">70.9</td>
            <td align="center">75.2</td>
        </tr>
        <tr>
            <td align="center">137</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000137.png"></td>
            <td align="center">扁鍬形蟲</td>
            <td align="center">30.3</td>
            <td align="center">35.2</td>
            <td align="center">40.1</td>
            <td align="center">45</td>
            <td align="center">50</td>
            <td align="center">54.9</td>
            <td align="center">59.8</td>
            <td align="center">64.7</td>
            <td align="center">69.6</td>
            <td align="center">74.6</td>
        </tr>
        <tr>
            <td align="center">128</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000128.png"></td>
            <td align="center">日本油蟬</td>
            <td align="center">53.6</td>
            <td align="center">55.2</td>
            <td align="center">56.7</td>
            <td align="center">58.3</td>
            <td align="center">59.9</td>
            <td align="center">61.4</td>
            <td align="center">63</td>
            <td align="center">64.5</td>
            <td align="center">66.1</td>
            <td align="center">67.7</td>
        </tr>
        <tr>
            <td align="center">130</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000130.png"></td>
            <td align="center">斑透翅蟬</td>
            <td align="center">53.4</td>
            <td align="center">54.8</td>
            <td align="center">56.2</td>
            <td align="center">57.5</td>
            <td align="center">58.9</td>
            <td align="center">60.3</td>
            <td align="center">61.6</td>
            <td align="center">63</td>
            <td align="center">64.4</td>
            <td align="center">65.8</td>
        </tr>
        <tr>
            <td align="center">107</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000107.png"></td>
            <td align="center">黃鉤蛺蝶</td>
            <td align="center">51.4</td>
            <td align="center">52.7</td>
            <td align="center">53.9</td>
            <td align="center">55.2</td>
            <td align="center">56.5</td>
            <td align="center">57.7</td>
            <td align="center">59</td>
            <td align="center">60.2</td>
            <td align="center">61.5</td>
            <td align="center">62.8</td>
        </tr>
        <tr>
            <td align="center">121</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000121.png"></td>
            <td align="center">飛蝗</td>
            <td align="center">37.8</td>
            <td align="center">40.5</td>
            <td align="center">43.2</td>
            <td align="center">45.9</td>
            <td align="center">48.6</td>
            <td align="center">51.3</td>
            <td align="center">54</td>
            <td align="center">56.7</td>
            <td align="center">59.4</td>
            <td align="center">62.1</td>
        </tr>
        <tr>
            <td align="center">155</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000155.png"></td>
            <td align="center">寬翅紡織娘</td>
            <td align="center">39.1</td>
            <td align="center">41</td>
            <td align="center">42.9</td>
            <td align="center">44.8</td>
            <td align="center">46.7</td>
            <td align="center">48.6</td>
            <td align="center">50.5</td>
            <td align="center">52.4</td>
            <td align="center">54.3</td>
            <td align="center">56.3</td>
        </tr>
        <tr>
            <td align="center">181</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000181.png"></td>
            <td align="center">奇異海蟑螂</td>
            <td align="center">34.1</td>
            <td align="center">36.2</td>
            <td align="center">38.2</td>
            <td align="center">40.3</td>
            <td align="center">42.3</td>
            <td align="center">44.4</td>
            <td align="center">46.4</td>
            <td align="center">48.5</td>
            <td align="center">50.5</td>
            <td align="center">52.6</td>
        </tr>
        <tr>
            <td align="center">100</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000100.png"></td>
            <td align="center">斑緣點粉蝶</td>
            <td align="center">40.9</td>
            <td align="center">42</td>
            <td align="center">43.2</td>
            <td align="center">44.3</td>
            <td align="center">45.5</td>
            <td align="center">46.6</td>
            <td align="center">47.7</td>
            <td align="center">48.9</td>
            <td align="center">50</td>
            <td align="center">51.2</td>
        </tr>
        <tr>
            <td align="center">129</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000129.png"></td>
            <td align="center">日本暮蟬</td>
            <td align="center">37.2</td>
            <td align="center">38.6</td>
            <td align="center">40</td>
            <td align="center">41.5</td>
            <td align="center">42.9</td>
            <td align="center">44.3</td>
            <td align="center">45.8</td>
            <td align="center">47.2</td>
            <td align="center">48.6</td>
            <td align="center">50.1</td>
        </tr>
        <tr>
            <td align="center">131</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000131.png"></td>
            <td align="center">寒蟬</td>
            <td align="center">40.5</td>
            <td align="center">41.4</td>
            <td align="center">42.2</td>
            <td align="center">43.1</td>
            <td align="center">43.9</td>
            <td align="center">44.8</td>
            <td align="center">45.6</td>
            <td align="center">46.5</td>
            <td align="center">47.3</td>
            <td align="center">48.2</td>
        </tr>
        <tr>
            <td align="center">101</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000101.png"></td>
            <td align="center">白粉蝶</td>
            <td align="center">33</td>
            <td align="center">34.6</td>
            <td align="center">36.2</td>
            <td align="center">37.8</td>
            <td align="center">39.4</td>
            <td align="center">41</td>
            <td align="center">42.6</td>
            <td align="center">44.2</td>
            <td align="center">45.8</td>
            <td align="center">47.5</td>
        </tr>
        <tr>
            <td align="center">156</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000156.png"></td>
            <td align="center">蟋蟀</td>
            <td align="center">15.7</td>
            <td align="center">19.1</td>
            <td align="center">22.5</td>
            <td align="center">25.9</td>
            <td align="center">29.3</td>
            <td align="center">32.6</td>
            <td align="center">36</td>
            <td align="center">39.4</td>
            <td align="center">42.8</td>
            <td align="center">46.2</td>
        </tr>
        <tr>
            <td align="center">162</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000162.png"></td>
            <td align="center">吉丁蟲</td>
            <td align="center">25.8</td>
            <td align="center">27.7</td>
            <td align="center">29.6</td>
            <td align="center">31.6</td>
            <td align="center">33.5</td>
            <td align="center">35.4</td>
            <td align="center">37.4</td>
            <td align="center">39.3</td>
            <td align="center">41.2</td>
            <td align="center">43.2</td>
        </tr>
        <tr>
            <td align="center">123</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000123.png"></td>
            <td align="center">螢火蟲</td>
            <td align="center">23.2</td>
            <td align="center">25.3</td>
            <td align="center">27.4</td>
            <td align="center">29.5</td>
            <td align="center">31.6</td>
            <td align="center">33.7</td>
            <td align="center">35.8</td>
            <td align="center">37.9</td>
            <td align="center">40</td>
            <td align="center">42.1</td>
        </tr>
        <tr>
            <td align="center">153</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000153.png"></td>
            <td align="center">蝗蟲</td>
            <td align="center">27.7</td>
            <td align="center">29.3</td>
            <td align="center">30.8</td>
            <td align="center">32.4</td>
            <td align="center">34</td>
            <td align="center">35.5</td>
            <td align="center">37.1</td>
            <td align="center">38.6</td>
            <td align="center">40.2</td>
            <td align="center">41.8</td>
        </tr>
        <tr>
            <td align="center">106</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000106.png"></td>
            <td align="center">斑蝗</td>
            <td align="center">27.8</td>
            <td align="center">28.7</td>
            <td align="center">29.6</td>
            <td align="center">30.5</td>
            <td align="center">31.4</td>
            <td align="center">32.2</td>
            <td align="center">33.1</td>
            <td align="center">34</td>
            <td align="center">34.9</td>
            <td align="center">35.8</td>
        </tr>
        <tr>
            <td align="center">108</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000108.png"></td>
            <td align="center">螻蛄</td>
            <td align="center">29.5</td>
            <td align="center">30.2</td>
            <td align="center">30.8</td>
            <td align="center">31.5</td>
            <td align="center">32.2</td>
            <td align="center">32.8</td>
            <td align="center">33.5</td>
            <td align="center">34.1</td>
            <td align="center">34.8</td>
            <td align="center">35.5</td>
        </tr>
        <tr>
            <td align="center">154</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000154.png"></td>
            <td align="center">鈴蟲</td>
            <td align="center">17.4</td>
            <td align="center">18.6</td>
            <td align="center">19.9</td>
            <td align="center">21.1</td>
            <td align="center">22.4</td>
            <td align="center">23.6</td>
            <td align="center">24.8</td>
            <td align="center">26.1</td>
            <td align="center">27.3</td>
            <td align="center">28.6</td>
        </tr>
        <tr>
            <td align="center">102</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000102.png"></td>
            <td align="center">蜜蜂</td>
            <td align="center">12.8</td>
            <td align="center">13.4</td>
            <td align="center">14</td>
            <td align="center">14.6</td>
            <td align="center">15.3</td>
            <td align="center">15.9</td>
            <td align="center">16.5</td>
            <td align="center">17.1</td>
            <td align="center">17.7</td>
            <td align="center">18.4</td>
        </tr>
        <tr>
            <td align="center">180</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000180.png"></td>
            <td align="center">鼠婦</td>
            <td align="center">11</td>
            <td align="center">11.8</td>
            <td align="center">12.6</td>
            <td align="center">13.4</td>
            <td align="center">14.2</td>
            <td align="center">15</td>
            <td align="center">15.8</td>
            <td align="center">16.6</td>
            <td align="center">17.4</td>
            <td align="center">18.2</td>
        </tr>
        <tr>
            <td align="center">161</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000161.png"></td>
            <td align="center">艷金龜</td>
            <td align="center">13.6</td>
            <td align="center">14</td>
            <td align="center">14.4</td>
            <td align="center">14.9</td>
            <td align="center">15.3</td>
            <td align="center">15.7</td>
            <td align="center">16.2</td>
            <td align="center">16.6</td>
            <td align="center">17</td>
            <td align="center">17.5</td>
        </tr>
        <tr>
            <td align="center">183</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000183.png"></td>
            <td align="center">螞蟻</td>
            <td align="center">6.8</td>
            <td align="center">7.4</td>
            <td align="center">8</td>
            <td align="center">8.6</td>
            <td align="center">9.2</td>
            <td align="center">9.8</td>
            <td align="center">10.4</td>
            <td align="center">11</td>
            <td align="center">11.6</td>
            <td align="center">12.3</td>
        </tr>
        <tr>
            <td align="center">109</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000109.png"></td>
            <td align="center">七星瓢蟲</td>
            <td align="center">5.4</td>
            <td align="center">5.8</td>
            <td align="center">6.2</td>
            <td align="center">6.6</td>
            <td align="center">7</td>
            <td align="center">7.3</td>
            <td align="center">7.7</td>
            <td align="center">8.1</td>
            <td align="center">8.5</td>
            <td align="center">8.9</td>
        </tr>
        <tr>
            <td align="center">110</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_6000110.png"></td>
            <td align="center">黃色瓢蟲</td>
            <td align="center">4.3</td>
            <td align="center">4.5</td>
            <td align="center">4.6</td>
            <td align="center">4.8</td>
            <td align="center">5</td>
            <td align="center">5.1</td>
            <td align="center">5.3</td>
            <td align="center">5.4</td>
            <td align="center">5.6</td>
            <td align="center">5.8</td>
        </tr>
    </tbody>
</table>
