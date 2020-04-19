---
title: "【哆啦A夢牧場物語】NPC與動物與大雄的好感度"
date: 2020-03-25T23:52:31+08:00
description: "好感度的累積方法以及各等級好感度的所需積分"
draft: false
hideToc: false
enableToc: false
enableTocContent: true
author: 伊琉沙 AKA 哇咔咔
authorEmoji: 👩🏿‍🚀
tags: 
series:
- 哆啦A夢牧場物語
categories:
- 哆啦A夢
image: images/feature-dora/icon_201100013.png
---
## 好感度與情感度
+ [好感度💝](../doraemon-story-likabilitydegree/)分為`10級`，以不同顏色的❤️表示，主要表示NPC對大雄的好感程度。
    + 好感度💝的增加主要來自`送禮🎁`。
+ [情感度💗](../doraemon-story-affectiondegree/)分為`20級`，以半顆與整顆❤️表示，主要表示牧場動物與大雄的情感程度。
    + 情感度💗的增加主要來自大雄在牧場的`照顧`。

### 好感值🥰
好感值🥰是好感度💝的數值化，上限值為`10000`。
好感值🥰對好感度💝為`非線性成長`。

#### 好感度量化表
好感度💝對應的好感值🥰範圍在`鎮民`與`野生動物`之間存在差異。
<table>
    <thead>
        <tr>
            <td colspan="2">好感值🥰下限</td>
            <td rowspan="2">好感度💝</td>
            <td rowspan="2">❤️</td>
        </tr>        
        <tr>
            <td>鎮民</td>
            <td>野生動物</td>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>0</td>
            <td>0</td>
            <td>1</td>
            <td><img src= "/images/post/Season_of_Story/Sprite/icon_201060010.png"></td>
        </tr>
        <tr>
            <td>100</td>
            <td>100</td>
            <td>2</td>
            <td><img src= "/images/post/Season_of_Story/Sprite/icon_201060020.png"></td>
        </tr>
        <tr>
            <td>400</td>
            <td>200</td>
            <td>3</td>
            <td><img src= "/images/post/Season_of_Story/Sprite/icon_201060030.png"></td>
        </tr>
        <tr>
            <td>900</td>
            <td>400</td>
            <td>4</td>
            <td><img src= "/images/post/Season_of_Story/Sprite/icon_201060040.png"></td>
        </tr>
        <tr>
            <td>1700</td>
            <td>700</td>
            <td>5</td>
            <td><img src= "/images/post/Season_of_Story/Sprite/icon_201060060.png"></td>
        </tr>
        <tr>
            <td>2800</td>
            <td>1100</td>
            <td>6</td>
            <td><img src= "/images/post/Season_of_Story/Sprite/icon_201060050.png"></td>
        </tr>
        <tr>
            <td>4200</td>
            <td>1700</td>
            <td>7</td>
            <td><img src= "/images/post/Season_of_Story/Sprite/icon_201060070.png"></td>
        </tr>
        <tr>
            <td>5900</td>
            <td>2600</td>
            <td>8</td>
            <td><img src= "/images/post/Season_of_Story/Sprite/icon_201060080.png"></td>
        </tr>
        <tr>
            <td>7900</td>
            <td>3800</td>
            <td>9</td>
            <td><img src= "/images/post/Season_of_Story/Sprite/icon_201060090.png"></td>
        </tr>
        <tr>
            <td>10000</td>
            <td>5000</td>
            <td>10</td>
            <td><img src= "/images/post/Season_of_Story/Sprite/icon_201060100.png"></td>
        </tr>
    </tbody>
</table>

## 關注
[銅鑼燒實驗牧場](https://www.facebook.com/dorayakifarm/?modal=admin_todo_tour)
[伊琉沙/ PC實測/哆啦A夢牧場物語](https://docs.google.com/spreadsheets/d/1DjAbwpy9XUwY5iAoWFtHbHDwEne82c33R1dH83Qb7eY/)

關於好感度的計算，我從源代碼反編譯找到了。
結果跟之前自己實機測試結果一致。
只是程式碼的所有數值計算比我的推測精確5倍！！！
![源代碼](/images/post/LikabilityDegreeData.png)

## 好感度的獲取方式與對應積分
* 打招呼 `(GREET)`
    * +5分
* 對話 `(TALK)`
    * +25分
* 送禮物 `(PRESENT)`
    * +5分
* 送喜好的禮物（會冒出3❤️） `(GOOD_PRESENT)`
    * +25分
* 送最愛的禮物（會冒出5❤️） `(FAVORITE_PRESENT)`
    * +60分
* 送討厭的禮物 `(BAD_PRESENT)`
    * -10分
* 參與慶典 `(PARTICIPATE_FESTIVAL)`
    * +10分

## 好感度積分
再來是好感度的基本分，從源代碼發現人物角色與野生動物的好感度標準分是不同的，這也是為什麼野生動物的好感度比較容易上升。

### 人物角色
* 1❤️
    * 0分
* 2❤️
    * 100分
* 3❤️  
    * 400分
* 4❤️ 
    * 900分
* 5❤️ 
    * 1700分
* 6❤️ 
    * 2800分
* 7❤️ 
    * 4200分
* 8❤️ 
    * 5900分
* 9❤️ 
    * 7900分
* 10❤️    
    * 10000分

### 野生動物
* 1❤️
    * 0分
* 2❤️
    * 100分
* 3❤️  
    * 200分
* 4❤️ 
    * 400分
* 5❤️ 
    * 700分
* 6❤️ 
    * 1100分
* 7❤️ 
    * 1700分
* 8❤️ 
    * 2600分
* 9❤️ 
    * 3800分
* 10❤️    
    * 5000分