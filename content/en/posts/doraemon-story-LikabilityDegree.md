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
* 送喜好的禮物（會冒出3♥） `(GOOD_PRESENT)`
    * +25分
* 送最愛的禮物（會冒出5♥） `(FAVORITE_PRESENT)`
    * +60分
* 送討厭的禮物 `(BAD_PRESENT)`
    * -10分
* 參與慶典 `(PARTICIPATE_FESTIVAL)`
    * +10分

## 好感度積分
再來是好感度的基本分，從源代碼發現人物角色與野生動物的好感度標準分是不同的，這也是為什麼野生動物的好感度比較容易上升。

### 人物角色
* 1♥
    * 0分
* 2♥
    * 100分
* 3♥  
    * 400分
* 4♥ 
    * 900分
* 5♥ 
    * 1700分
* 6♥ 
    * 2800分
* 7♥ 
    * 4200分
* 8♥ 
    * 5900分
* 9♥ 
    * 7900分
* 10♥    
    * 10000分

### 野生動物
* 1♥
    * 0分
* 2♥
    * 100分
* 3♥  
    * 200分
* 4♥ 
    * 400分
* 5♥ 
    * 700分
* 6♥ 
    * 1100分
* 7♥ 
    * 1700分
* 8♥ 
    * 2600分
* 9♥ 
    * 3800分
* 10♥    
    * 5000分