---
title: "43種魚類尺寸大小"
date: 2020-04-26T22:06:12+08:00
description: 43種魚類各品質尺寸大小
draft: false
hideToc: false
enableToc: false
enableTocContent: true
author: 伊琉沙 AKA 哇咔咔
authorEmoji: 👩🏿‍🚀
tags: 
- 尺寸大小
- 釣魚
series:
- 哆啦A夢牧場物語
categories:
- 哆啦A夢
image: images/post/Season_of_Story/Sprite/icon_5000187.png
libraries:
- katex
---
<mark>最後更新：2020/04/27</mark>

## 尺寸計算
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

### 魚類
+ `物品ID`=`5000000`+`魚類ID`
+ 魚類尺寸大小單位為`公分`。
+ 以`尺寸大小`遞減排序：
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
            <td align="center">187</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000187.png"></td>
            <td align="center">皇帶魚</td>
            <td align="center">327</td>
            <td align="center">417.9</td>
            <td align="center">508.8</td>
            <td align="center">599.7</td>
            <td align="center">690.6</td>
            <td align="center">781.5</td>
            <td align="center">872.4</td>
            <td align="center">963.3</td>
            <td align="center">1054.2</td>
            <td align="center">1145.1</td>
        </tr>
        <tr>
            <td align="center">127</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000127.png"></td>
            <td align="center">旗魚</td>
            <td align="center">313.2</td>
            <td align="center">336.2</td>
            <td align="center">359.2</td>
            <td align="center">382.3</td>
            <td align="center">405.3</td>
            <td align="center">428.3</td>
            <td align="center">451.4</td>
            <td align="center">474.4</td>
            <td align="center">497.4</td>
            <td align="center">520.5</td>
        </tr>
        <tr>
            <td align="center">190</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000190.png"></td>
            <td align="center">大尾魚</td>
            <td align="center">220.7</td>
            <td align="center">246.5</td>
            <td align="center">272.3</td>
            <td align="center">298.1</td>
            <td align="center">323.9</td>
            <td align="center">349.7</td>
            <td align="center">375.5</td>
            <td align="center">401.3</td>
            <td align="center">427.1</td>
            <td align="center">452.9</td>
        </tr>
        <tr>
            <td align="center">165</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000165.png"></td>
            <td align="center">鮪魚</td>
            <td align="center">233.9</td>
            <td align="center">254.6</td>
            <td align="center">275.3</td>
            <td align="center">296.1</td>
            <td align="center">316.8</td>
            <td align="center">337.5</td>
            <td align="center">358.3</td>
            <td align="center">379</td>
            <td align="center">399.7</td>
            <td align="center">420.5</td>
        </tr>
        <tr>
            <td align="center">126</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000126.png"></td>
            <td align="center">鯊魚</td>
            <td align="center">284.6</td>
            <td align="center">298.8</td>
            <td align="center">312.9</td>
            <td align="center">327.1</td>
            <td align="center">341.3</td>
            <td align="center">355.4</td>
            <td align="center">369.6</td>
            <td align="center">383.7</td>
            <td align="center">397.9</td>
            <td align="center">412.1</td>
        </tr>
        <tr>
            <td align="center">189</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000189.png"></td>
            <td align="center">巨狗脂鯉</td>
            <td align="center">110.2</td>
            <td align="center">122.2</td>
            <td align="center">134.2</td>
            <td align="center">146.2</td>
            <td align="center">158.3</td>
            <td align="center">170.3</td>
            <td align="center">182.3</td>
            <td align="center">194.3</td>
            <td align="center">206.3</td>
            <td align="center">218.4</td>
        </tr>
        <tr>
            <td align="center">188</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000188.png"></td>
            <td align="center">皺鰓鯊</td>
            <td align="center">122.6</td>
            <td align="center">130.8</td>
            <td align="center">139</td>
            <td align="center">147.1</td>
            <td align="center">155.3</td>
            <td align="center">163.5</td>
            <td align="center">171.6</td>
            <td align="center">179.8</td>
            <td align="center">188</td>
            <td align="center">196.2</td>
        </tr>
        <tr>
            <td align="center">146</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000146.png"></td>
            <td align="center">白帶魚</td>
            <td align="center">89.4</td>
            <td align="center">96.4</td>
            <td align="center">103.4</td>
            <td align="center">110.4</td>
            <td align="center">117.4</td>
            <td align="center">124.4</td>
            <td align="center">131.4</td>
            <td align="center">138.4</td>
            <td align="center">145.4</td>
            <td align="center">152.4</td>
        </tr>
        <tr>
            <td align="center">167</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000167.png"></td>
            <td align="center">鰤魚</td>
            <td align="center">86.9</td>
            <td align="center">93.7</td>
            <td align="center">100.6</td>
            <td align="center">107.4</td>
            <td align="center">114.3</td>
            <td align="center">121.1</td>
            <td align="center">127.9</td>
            <td align="center">134.8</td>
            <td align="center">141.6</td>
            <td align="center">148.5</td>
        </tr>
        <tr>
            <td align="center">123</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000123.png"></td>
            <td align="center">鰻魚</td>
            <td align="center">56.9</td>
            <td align="center">62.7</td>
            <td align="center">68.5</td>
            <td align="center">74.4</td>
            <td align="center">80.2</td>
            <td align="center">86</td>
            <td align="center">91.9</td>
            <td align="center">97.7</td>
            <td align="center">103.5</td>
            <td align="center">109.4</td>
        </tr>
        <tr>
            <td align="center">184</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000184.png"></td>
            <td align="center">日本花鱸</td>
            <td align="center">65.4</td>
            <td align="center">69.3</td>
            <td align="center">73.2</td>
            <td align="center">77.1</td>
            <td align="center">81.1</td>
            <td align="center">85</td>
            <td align="center">88.9</td>
            <td align="center">92.8</td>
            <td align="center">96.7</td>
            <td align="center">100.7</td>
        </tr>
        <tr>
            <td align="center">104</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000104.png"></td>
            <td align="center">鯛魚</td>
            <td align="center">32.2</td>
            <td align="center">39.6</td>
            <td align="center">46.9</td>
            <td align="center">54.3</td>
            <td align="center">61.6</td>
            <td align="center">69</td>
            <td align="center">76.3</td>
            <td align="center">83.7</td>
            <td align="center">91</td>
            <td align="center">98.4</td>
        </tr>
        <tr>
            <td align="center">122</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000122.png"></td>
            <td align="center">鱧魚</td>
            <td align="center">47.7</td>
            <td align="center">53</td>
            <td align="center">58.3</td>
            <td align="center">63.6</td>
            <td align="center">69</td>
            <td align="center">74.3</td>
            <td align="center">79.6</td>
            <td align="center">84.9</td>
            <td align="center">90.2</td>
            <td align="center">95.6</td>
        </tr>
        <tr>
            <td align="center">103</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000103.png"></td>
            <td align="center">花鯰</td>
            <td align="center">43.9</td>
            <td align="center">49.3</td>
            <td align="center">54.7</td>
            <td align="center">60.1</td>
            <td align="center">65.5</td>
            <td align="center">70.9</td>
            <td align="center">76.3</td>
            <td align="center">81.7</td>
            <td align="center">87.1</td>
            <td align="center">92.5</td>
        </tr>
        <tr>
            <td align="center">140</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000140.png"></td>
            <td align="center">鮭魚</td>
            <td align="center">45.3</td>
            <td align="center">49.8</td>
            <td align="center">54.3</td>
            <td align="center">58.8</td>
            <td align="center">63.3</td>
            <td align="center">67.8</td>
            <td align="center">72.3</td>
            <td align="center">76.8</td>
            <td align="center">81.3</td>
            <td align="center">85.8</td>
        </tr>
        <tr>
            <td align="center">180</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000180.png"></td>
            <td align="center">鯉魚</td>
            <td align="center">43.2</td>
            <td align="center">47.5</td>
            <td align="center">51.9</td>
            <td align="center">56.2</td>
            <td align="center">60.6</td>
            <td align="center">64.9</td>
            <td align="center">69.2</td>
            <td align="center">73.6</td>
            <td align="center">77.9</td>
            <td align="center">82.3</td>
        </tr>
        <tr>
            <td align="center">182</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000182.png"></td>
            <td align="center">章魚</td>
            <td align="center">45.7</td>
            <td align="center">49.8</td>
            <td align="center">53.8</td>
            <td align="center">57.9</td>
            <td align="center">62</td>
            <td align="center">66</td>
            <td align="center">70.1</td>
            <td align="center">74.1</td>
            <td align="center">78.2</td>
            <td align="center">82.3</td>
        </tr>
        <tr>
            <td align="center">163</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000163.png"></td>
            <td align="center">燈籠魚</td>
            <td align="center">55.5</td>
            <td align="center">58.4</td>
            <td align="center">61.3</td>
            <td align="center">64.1</td>
            <td align="center">67</td>
            <td align="center">69.9</td>
            <td align="center">72.7</td>
            <td align="center">75.6</td>
            <td align="center">78.5</td>
            <td align="center">81.4</td>
        </tr>
        <tr>
            <td align="center">143</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000143.png"></td>
            <td align="center">骨舌魚</td>
            <td align="center">46.2</td>
            <td align="center">49.8</td>
            <td align="center">53.3</td>
            <td align="center">56.9</td>
            <td align="center">60.4</td>
            <td align="center">64</td>
            <td align="center">67.5</td>
            <td align="center">71.1</td>
            <td align="center">74.6</td>
            <td align="center">78.2</td>
        </tr>
        <tr>
            <td align="center">144</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000144.png"></td>
            <td align="center">鰹魚</td>
            <td align="center">48.2</td>
            <td align="center">51.2</td>
            <td align="center">54.1</td>
            <td align="center">57.1</td>
            <td align="center">60</td>
            <td align="center">63</td>
            <td align="center">65.9</td>
            <td align="center">68.9</td>
            <td align="center">71.8</td>
            <td align="center">74.8</td>
        </tr>
        <tr>
            <td align="center">141</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000141.png"></td>
            <td align="center">虹鱒</td>
            <td align="center">27.9</td>
            <td align="center">32.4</td>
            <td align="center">36.9</td>
            <td align="center">41.4</td>
            <td align="center">45.9</td>
            <td align="center">50.4</td>
            <td align="center">54.9</td>
            <td align="center">59.4</td>
            <td align="center">63.9</td>
            <td align="center">68.4</td>
        </tr>
        <tr>
            <td align="center">161</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000161.png"></td>
            <td align="center">河豚</td>
            <td align="center">34</td>
            <td align="center">37.8</td>
            <td align="center">41.6</td>
            <td align="center">45.4</td>
            <td align="center">49.2</td>
            <td align="center">53</td>
            <td align="center">56.8</td>
            <td align="center">60.6</td>
            <td align="center">64.4</td>
            <td align="center">68.3</td>
        </tr>
        <tr>
            <td align="center">101</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000101.png"></td>
            <td align="center">巨大紅點鮭</td>
            <td align="center">31.9</td>
            <td align="center">35.4</td>
            <td align="center">38.9</td>
            <td align="center">42.4</td>
            <td align="center">45.9</td>
            <td align="center">49.4</td>
            <td align="center">52.9</td>
            <td align="center">56.4</td>
            <td align="center">59.9</td>
            <td align="center">63.4</td>
        </tr>
        <tr>
            <td align="center">186</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000186.png"></td>
            <td align="center">比目魚</td>
            <td align="center">34.9</td>
            <td align="center">37.7</td>
            <td align="center">40.5</td>
            <td align="center">43.3</td>
            <td align="center">46.2</td>
            <td align="center">49</td>
            <td align="center">51.8</td>
            <td align="center">54.6</td>
            <td align="center">57.4</td>
            <td align="center">60.3</td>
        </tr>
        <tr>
            <td align="center">124</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000124.png"></td>
            <td align="center">食人魚</td>
            <td align="center">23.1</td>
            <td align="center">26.6</td>
            <td align="center">30.1</td>
            <td align="center">33.6</td>
            <td align="center">37.1</td>
            <td align="center">40.6</td>
            <td align="center">44.1</td>
            <td align="center">47.6</td>
            <td align="center">51.1</td>
            <td align="center">54.7</td>
        </tr>
        <tr>
            <td align="center">100</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000100.png"></td>
            <td align="center">仙女鱒</td>
            <td align="center">20.8</td>
            <td align="center">23.3</td>
            <td align="center">25.8</td>
            <td align="center">28.3</td>
            <td align="center">30.8</td>
            <td align="center">33.2</td>
            <td align="center">35.7</td>
            <td align="center">38.2</td>
            <td align="center">40.7</td>
            <td align="center">43.2</td>
        </tr>
        <tr>
            <td align="center">162</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000162.png"></td>
            <td align="center">螃蟹</td>
            <td align="center">31.1</td>
            <td align="center">32.4</td>
            <td align="center">33.7</td>
            <td align="center">35.1</td>
            <td align="center">36.4</td>
            <td align="center">37.7</td>
            <td align="center">39.1</td>
            <td align="center">40.4</td>
            <td align="center">41.7</td>
            <td align="center">43.1</td>
        </tr>
        <tr>
            <td align="center">125</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000125.png"></td>
            <td align="center">鱉</td>
            <td align="center">22.3</td>
            <td align="center">24.5</td>
            <td align="center">26.6</td>
            <td align="center">28.8</td>
            <td align="center">31</td>
            <td align="center">33.1</td>
            <td align="center">35.3</td>
            <td align="center">37.4</td>
            <td align="center">39.6</td>
            <td align="center">41.8</td>
        </tr>
        <tr>
            <td align="center">181</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000181.png"></td>
            <td align="center">鯽魚</td>
            <td align="center">25.9</td>
            <td align="center">27.5</td>
            <td align="center">29.1</td>
            <td align="center">30.8</td>
            <td align="center">32.4</td>
            <td align="center">34</td>
            <td align="center">35.7</td>
            <td align="center">37.3</td>
            <td align="center">38.9</td>
            <td align="center">40.6</td>
        </tr>
        <tr>
            <td align="center">145</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000145.png"></td>
            <td align="center">鯖魚</td>
            <td align="center">25.2</td>
            <td align="center">26.9</td>
            <td align="center">28.6</td>
            <td align="center">30.3</td>
            <td align="center">32</td>
            <td align="center">33.7</td>
            <td align="center">35.4</td>
            <td align="center">37.1</td>
            <td align="center">38.8</td>
            <td align="center">40.5</td>
        </tr>
        <tr>
            <td align="center">105</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000105.png"></td>
            <td align="center">剝皮魚</td>
            <td align="center">23.8</td>
            <td align="center">25.5</td>
            <td align="center">27.2</td>
            <td align="center">28.9</td>
            <td align="center">30.6</td>
            <td align="center">32.3</td>
            <td align="center">34</td>
            <td align="center">35.7</td>
            <td align="center">37.4</td>
            <td align="center">39.2</td>
        </tr>
        <tr>
            <td align="center">185</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000185.png"></td>
            <td align="center">竹莢魚</td>
            <td align="center">14.7</td>
            <td align="center">17.2</td>
            <td align="center">19.8</td>
            <td align="center">22.3</td>
            <td align="center">24.9</td>
            <td align="center">27.4</td>
            <td align="center">29.9</td>
            <td align="center">32.5</td>
            <td align="center">35</td>
            <td align="center">37.6</td>
        </tr>
        <tr>
            <td align="center">106</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000106.png"></td>
            <td align="center">烏賊</td>
            <td align="center">14.3</td>
            <td align="center">16.3</td>
            <td align="center">18.3</td>
            <td align="center">20.3</td>
            <td align="center">22.3</td>
            <td align="center">24.2</td>
            <td align="center">26.2</td>
            <td align="center">28.2</td>
            <td align="center">30.2</td>
            <td align="center">32.2</td>
        </tr>
        <tr>
            <td align="center">142</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000142.png"></td>
            <td align="center">香魚</td>
            <td align="center">22.7</td>
            <td align="center">23.8</td>
            <td align="center">24.8</td>
            <td align="center">25.9</td>
            <td align="center">26.9</td>
            <td align="center">28</td>
            <td align="center">29</td>
            <td align="center">30.1</td>
            <td align="center">31.1</td>
            <td align="center">32.2</td>
        </tr>
        <tr>
            <td align="center">128</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000128.png"></td>
            <td align="center">沙丁魚</td>
            <td align="center">12.9</td>
            <td align="center">14.6</td>
            <td align="center">16.3</td>
            <td align="center">18</td>
            <td align="center">19.7</td>
            <td align="center">21.4</td>
            <td align="center">23.1</td>
            <td align="center">24.8</td>
            <td align="center">26.5</td>
            <td align="center">28.2</td>
        </tr>
        <tr>
            <td align="center">129</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000129.png"></td>
            <td align="center">沙鮻</td>
            <td align="center">9.9</td>
            <td align="center">11.6</td>
            <td align="center">13.3</td>
            <td align="center">15</td>
            <td align="center">16.8</td>
            <td align="center">18.5</td>
            <td align="center">20.2</td>
            <td align="center">21.9</td>
            <td align="center">23.6</td>
            <td align="center">25.4</td>
        </tr>
        <tr>
            <td align="center">166</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000166.png"></td>
            <td align="center">蝦</td>
            <td align="center">13.6</td>
            <td align="center">14.8</td>
            <td align="center">16.1</td>
            <td align="center">17.3</td>
            <td align="center">18.6</td>
            <td align="center">19.8</td>
            <td align="center">21</td>
            <td align="center">22.3</td>
            <td align="center">23.5</td>
            <td align="center">24.8</td>
        </tr>
        <tr>
            <td align="center">102</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000102.png"></td>
            <td align="center">泥鰍</td>
            <td align="center">8.5</td>
            <td align="center">10.3</td>
            <td align="center">12.1</td>
            <td align="center">13.9</td>
            <td align="center">15.7</td>
            <td align="center">17.5</td>
            <td align="center">19.3</td>
            <td align="center">21.1</td>
            <td align="center">22.9</td>
            <td align="center">24.7</td>
        </tr>
        <tr>
            <td align="center">183</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000183.png"></td>
            <td align="center">金魚</td>
            <td align="center">6.5</td>
            <td align="center">7.8</td>
            <td align="center">9.1</td>
            <td align="center">10.4</td>
            <td align="center">11.7</td>
            <td align="center">13</td>
            <td align="center">14.3</td>
            <td align="center">15.6</td>
            <td align="center">16.9</td>
            <td align="center">18.2</td>
        </tr>
        <tr>
            <td align="center">121</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000121.png"></td>
            <td align="center">小龍蝦</td>
            <td align="center">6.8</td>
            <td align="center">8</td>
            <td align="center">9.1</td>
            <td align="center">10.3</td>
            <td align="center">11.4</td>
            <td align="center">12.6</td>
            <td align="center">13.7</td>
            <td align="center">14.9</td>
            <td align="center">16</td>
            <td align="center">17.2</td>
        </tr>
        <tr>
            <td align="center">160</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000160.png"></td>
            <td align="center">西太公魚</td>
            <td align="center">6</td>
            <td align="center">6.5</td>
            <td align="center">6.9</td>
            <td align="center">7.4</td>
            <td align="center">7.9</td>
            <td align="center">8.3</td>
            <td align="center">8.8</td>
            <td align="center">9.2</td>
            <td align="center">9.7</td>
            <td align="center">10.2</td>
        </tr>
        <tr>
            <td align="center">164</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000164.png"></td>
            <td align="center">海天使</td>
            <td align="center">1.5</td>
            <td align="center">1.8</td>
            <td align="center">2.1</td>
            <td align="center">2.4</td>
            <td align="center">2.7</td>
            <td align="center">3</td>
            <td align="center">3.3</td>
            <td align="center">3.6</td>
            <td align="center">3.9</td>
            <td align="center">4.2</td>
        </tr>
        <tr>
            <td align="center">120</td>
            <td align="center"><img width= "64px" src= "/images/post/Season_of_Story/Sprite/icon_5000120.png"></td>
            <td align="center">青鱂魚</td>
            <td align="center">1.4</td>
            <td align="center">1.7</td>
            <td align="center">2</td>
            <td align="center">2.3</td>
            <td align="center">2.6</td>
            <td align="center">2.9</td>
            <td align="center">3.2</td>
            <td align="center">3.5</td>
            <td align="center">3.8</td>
            <td align="center">4.1</td>
        </tr>
    </tbody>
</table>

## 分類索引
<table>
    <thead>
        <tr>
            <td colspan="10">尺寸大小</td>        
        </tr>
    </thead>
    <tr>
        <td align="center"><a href="../doraemon-story-size-bugs"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_6000159.png">蟲類</a></td>    
        <td align="center"><a href="../doraemon-story-size-fishes"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_5000187.png">魚類</a></td> 
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