---
title: "【哆啦A夢牧場物語】牧場動物的情感度"
date: 2020-04-11T14:26:33+08:00
description: "哪些因素會影響動物的情感與壓力？"
draft: false
hideToc: false
enableToc: false
enableTocContent: true
author: 伊琉沙 AKA 哇咔咔
authorEmoji: 👩🏿‍🚀
tags: 
- 動物
series:
- 哆啦A夢牧場物語
categories:
- 哆啦A夢
image: images/post/Season_of_Story/Sprite/icon_201173001.png
libraries:
- katex
---
## 好感度與情感度
+ [好感度💝](../doraemon-story-likabilitydegree/)分為`10級`，以不同顏色的❤️表示，主要表示NPC對大雄的好感程度。
    + 好感度💝的增加主要來自`送禮🎁`。
+ [情感度💗](../doraemon-story-affectiondegree/)分為`20級`，以半顆與整顆❤️表示，主要表示牧場動物與大雄的情感程度。
    + 情感度💗的增加主要來自大雄在牧場的`照顧`。

### 情感值😸
情感值😸（`mAffectionDegree`）是情感度💗的數值化，上限值為`1000`。
```C#
public int AffectionDegreeRate
{
    get
    {
        return (this.mAffectionDegree != 1000) ? (this.mAffectionDegree / Animal.AFFECTION_DEGREE_CONVERSION_RATE + 1) : 20;
    }
}
```
情感值😸對情感度💗為`線性成長`，轉換公式如下：
$$若情感值😸為1000，則情感度💗為20。$$
$$若非，情感度💗=\dfrac{情感值😸}{情感轉換率}+1$$

#### 情感度量化表
<table>
    <thead>
        <tr>
            <td>情感值😸下限</td>
            <td>情感度💗</td>
            <td colspan="2">❤️</td>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>0</td>
            <td>1</td>
            <td>❤️0.5</td>
            <td><img  align="left" src= "/images/post/Icon_Heart_Half.png"></td>
        </tr>
        <tr>
            <td>50</td>
            <td>2</td>
            <td>❤️1</td>
            <td><img  align="left" src= "/images/post/Icon_Heart_Full.png"></td>
        </tr>
        <tr>
            <td>100</td>
            <td>3</td>
            <td>❤️1.5</td>
            <td><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Half.png"></td>
        </tr>
        <tr>
            <td>150</td>
            <td>4</td>
            <td>❤️2</td>
            <td><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"></td>
        </tr>
        <tr>
            <td>200</td>
            <td>5</td>
            <td>❤️2.5</td>
            <td><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Half.png"></td>
        </tr>
        <tr>
            <td>250</td>
            <td>6</td>
            <td>❤️3</td>
            <td><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"></td>
        </tr>
        <tr>
            <td>300</td>
            <td>7</td>
            <td>❤️3.5</td>
            <td><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Half.png"></td>
        </tr>
        <tr>
            <td>350</td>
            <td>8</td>
            <td>❤️4</td>
            <td><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"></td>
        </tr>
        <tr>
            <td>400</td>
            <td>9</td>
            <td>❤️4.5</td>
            <td><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Half.png"></td>
        </tr>
        <tr>
            <td>450</td>
            <td>10</td>
            <td>❤️5</td>
            <td><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"></td>
        </tr>
        <tr>
            <td>500</td>
            <td>11</td>
            <td>❤️5.5</td>
            <td><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Half.png"></td>
        </tr>
        <tr>
            <td>550</td>
            <td>12</td>
            <td>❤️6</td>
            <td><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"></td>
        </tr>
        <tr>
            <td>600</td>
            <td>13</td>
            <td>❤️6.5</td>
            <td><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Half.png"></td>
        </tr>
        <tr>
            <td>650</td>
            <td>14</td>
            <td>❤️7</td>
            <td><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"></td>
        </tr>
        <tr>
            <td>700</td>
            <td>15</td>
            <td>❤️7.5</td>
            <td><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Half.png"></td>
        </tr>
        <tr>
            <td>750</td>
            <td>16</td>
            <td>❤️8</td>
            <td><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"></td>
        </tr>
        <tr>
            <td>800</td>
            <td>17</td>
            <td>❤️8.5</td>
            <td><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Half.png"></td>
        </tr>
        <tr>
            <td>850</td>
            <td>18</td>
            <td>❤️9</td>
            <td><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"></td>
        </tr>
        <tr>
            <td>900</td>
            <td>19</td>
            <td>❤️9.5</td>
            <td><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Half.png"></td>
        </tr>
        <tr>
            <td>950</td>
            <td>20</td>
            <td>❤️10</td>
            <td><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"><img  align="left" src= "/images/post/Icon_Heart_Full.png"></td>
        </tr>
    </tbody>
</table>

### 壓力值🙀
壓力值🙀可視為動物的健康狀態，在遊戲中是隱藏數值，可透過安裝相關[MOD](../doraemon-story-mod-install)查看。
+ 壓力值🙀最低為`0`。
+ 壓力值🙀達到`60`以上時將會`生病`（動物旁邊會出現藍色閃電的圖示），此時放牧與生病的結算時間會重新計時。
+ 當動物處於生病狀態時，壓力值🙀會持續上升，不盡早處理病情將會[惡化](#生病)。
+ 壓力值🙀達到`500`以上時，動物會`死亡`。

#### 恢復健康
恢復健康的方法就是降低壓力值🙀：
+ 當動物處於生病狀態且壓力值🙀降至低於`50`時，動物將恢復為健康狀態。
+ 當動物處於生病狀態時，可透過醫院購買`動物用藥`[餵動物吃藥](#餵動物吃藥)。

## 影響動物情感與壓力的因素
### 與動物說話
```C#
public ResponseModel Talk()
{
    if (!this.mIsTalked)
    {
        this.AddAffection((this.mAnimalId != 102) ? 2 : 4);
        this.AddStress(Animal.GetTalkAddStressValue(this.mAnimalId));
    }
    string talkMessage = this.TalkMessage;
    return new ResponseModel(talkMessage, 100);
}
```
+ 情感值😸：`+2` / `+4`（咪咪）
+ 壓力值🙀：`-4` / `-12`（雞與小雞崽兒）
+ [若超過3天沒跟動物說話](#每日結束計算)

### 餵食動物用點心
```C#
public void Snack()
{
    if (!this.mHasSnack)
    {
        this.AddAffection((this.mAnimalId != 102) ? 1 : 4);
        this.AddStress(-4);
    }
}
```
+ 情感值😸：`+1` / `+4`（咪咪）
+ 壓力值🙀：`-4`

### 幫動物刷毛
```C#
public void Brush()
{
    if (!this.mIsBrushed)
    {
        this.AddAffection(2);
        this.AddStress(-4);
    }
}
```
+ 情感值😸：`+2`
+ 壓力值🙀：`-4`

### 餵動物吃藥
只有在動物`生病`的時候才能`餵藥`。
```C#
public void UseMedicine()
{
    if (this.mIsSick && !this.mIsUseMedicine)
    {
        this.mIsUseMedicine = true;
        this.AddAffection(1);
        this.AddStress(-50);
    }
}
```
+ 情感值😸：`+1`
+ 壓力值🙀：`-50`

### 收穫
+ `牛`可收穫`牛奶`
+ `羊`可收穫`羊毛`
+ `雞`可收穫`雞蛋`
```C#
public ItemModel Harvest(TimeModel now_time)
{
    if (this.CanHarvest)
    {
        this.mIsHarvested = true;
        this.AddAffection(2);
        this.AddStress(-4);
        this.mHarvestedTime = new TimeModel(now_time.Year, now_time.Season, now_time.Day, now_time.DayOfWeek, now_time.Hour, now_time.Minute);
        return this.mHarvestItem;
    }
    return null;
}
```
+ 情感值😸：`+2`
+ 壓力值🙀：`-4`

### 每日結束計算
每日結束時會進行感情與壓力結算，但若動物離家出走則跳過今日結算，同時計算時間不會重置會持續累計至下一日結束。
```C#
 if (this.mNotTalkCountStartTime.GetDiffDateMinutes(now_time) >= Animal.NOT_TALK_PENALTY_MINUTES && !this.mIsPregnant)
{
    this.AddAffection((this.mAnimalId != 102) ? -1 : -1);
    this.AddStress(4);
}
if (!this.mIsGrazing && (this.mHasFeedTime == null || this.mHasFeedTime.GetDiffDateMinutes(now_time) >= Time.CALC_DAY_MINUTES))
{
    this.AddAffection(-5);
    this.AddStress(50);
}
else
{
    this.AddAffection(2);
    this.AddStress(-4);
    this.mHasFeedTime = null;
}
```
+ 若超過3天沒跟動物說話
    + 情感值😸：`-1`
    + 壓力值🙀：`+4`
+ 若動物在小屋一天沒飼料：
    + 情感值😸：`-5`
    + 壓力值🙀：`+50`
+ 除此之外（在小屋吃飼料或放牧）
    + 情感值😸：`+2`
    + 壓力值🙀：`-4`

### 放牧計算
放牧的`感情`與`壓力`計算與動物類型有關，分為兩大類型：
+ `家畜`
    + 牛
    + 羊
    + 雞
+ `寵物`
    + 狗
    + 馬
    + 貓（咪咪）

#### 放牧計算條件
放牧的計算是以`10分鐘`為單位，而放牧的結算則是以每`1小時`一次，所以每次放牧的結算時間不一定為整點，並分為三個時段：
 + `日間`
    + 6點至19點
 + `夜間`
    + 19點至24點
 + `半夜`
    + 0點至6點

需注意的是結算的效果會以本次放牧的開始時間作為依據而非結算時間，每次結算的時間將為下一次放牧的開始時間：
例如6點40分進行結算，其情感值😸與壓力值🙀的增減會以5點40分作為計算基準點，故本次結算會依半夜的效果計算。

#### 結算效果
+ 家畜（`牛`、`羊`、`雞`）
    + 6點至19點
        + 情感值😸：`+1` / `-1`（下雨）
        + 壓力值🙀：`-1` / `0`（下雨）
    + 19點至24點
        + 情感值😸：`0` / `-1`（下雨）
        + 壓力值🙀：`0` / `0`（下雨）
    + 0點至6點
        + 情感值😸：`-2` / `-3`（下雨）
        + 壓力值🙀：`2` / `3`（下雨）
+ 寵物（`狗`、`馬`、`貓`）
    + 6點至19點
        + 情感值😸：`+1` / `0`（下雨）
        + 壓力值🙀：`-1` / `1`（下雨）
    + 19點至24點
        + 情感值😸：`0` / `0`（下雨）
        + 壓力值🙀：`0` / `1`（下雨）
    + 0點至6點
        + 情感值😸：`0` / `0`（下雨）
        + 壓力值🙀：`1` / `1`（下雨）

### 放牧遭遇天災
```C#
public void GrazingWhenDisaster()
{
    if (!this.mIsGrazing)
    {
        return;
    }
    this.mGrazingCount = 0;
    this.AddAffection(-20);
    this.AddStress(20);
}
```
+ 情感值😸：`-20`
+ 壓力值🙀：`+20`
---
放牧的計算過程是以`10分鐘`為單位，若遭遇天災則會立即產生上列效果。
此時放牧的計時會重新刷新，但放牧的開始時間不會刷新。
亦即原定6點40分進行結算，如果在6點20分遭遇天災，則放牧的計時重新刷新，結算時間將推遲至7點20分，但此次結算的放牧開始時間仍為5點40分。

### 生病
```C#
public void StepSickCount()
{
    if (!this.mIsSick)
    {
        return;
    }
    this.mSickCount++;
    if (this.mSickCount == 6)
    {
        this.mSickCount = 0;
        this.AddAffection(0);
        this.AddStress(1);
    }
}
```
每`1小時`觸發一次，觸發以`10分鐘`為單位不一定為整點觸發：
+ 情感值😸：`0`
+ 壓力值🙀：`+1`