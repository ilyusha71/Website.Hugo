---
title: "【哆啦A夢牧場物語】事件線"
date: 2020-04-16T09:45:33+08:00
description: "大雄等人在牧場生活發生的各種事件"
draft: false
hideToc: true
enableToc: true
enableTocContent: true
author: 伊琉沙 AKA 哇咔咔
authorEmoji: 👩🏿‍🚀
tags: 
- 劇情
series:
- 哆啦A夢牧場物語
categories:
- 哆啦A夢
image: images/post/Season_of_Story/Sprite/icon_301010600.png
---
<mark>以下為整理中的事件，整理完成會歸檔</mark>
`如果電話亭`能查詢的事件請參考[劇情線](../doraemon-story-index/#劇情線)。

## 引導教學事件

### 釣魚教學
+ 事件ID：`81100001`
+ 觸發地點：[大雄牧場](../doraemon-story-map#大雄牧場)（`10000`）

![大雄牧場](/images/post/Season_of_Story/Map/10000.png)
+ 觸發時間條件📆
    + 開始時間：第1年春季5日`06:00`
---
席菲送釣竿
---
+ 選項1：釣到旗魚我就拿過來喔！❤️❤️❤️❤️❤️
+ 選項2：我會去河邊釣釣看！

### 捕蟲教學
+ 事件ID：`81160003` 必要物品 捕蟲網 // 購買捕蟲網後 離開雜貨店觸發 肯的捕蟲教學
+ 觸發地點：[萬物鎮西](../doraemon-story-map#萬物鎮西)（`11200`）

![萬物鎮西](/images/post/Season_of_Story/Map/11200.png)


## 第二年販售種子上架
+ 事件ID：`81160002`
+ 觸發地點：[大雄牧場](../doraemon-story-map#大雄牧場)（`10000`）

![大雄牧場](/images/post/Season_of_Story/Map/10000.png)
+ 觸發時間條件📆
    + 開始時間：第2年春季1日`06:00`
---
哆啦敲門告知雜貨店販售增加


## 建築建造與擴建事件
```C#
public static int GetConstructionStartEventId(int parent_building_id, int level)
{
    return 10000000 + parent_building_id * 1000 + level * 100;
}

// Token: 0x060028C5 RID: 10437 RVA: 0x000A979F File Offset: 0x000A7B9F
public static int GetConstructionEndEventId(int parent_building_id, int level)
{
    return 10000000 + parent_building_id * 1000 + level * 100 + 1;
}
public static bool CheckBuildableMaker(int parent_building_id)
{
    BuildingModel buildingModel = SingletonMonoBehaviour<UserManager>.Instance.User.Farm.GetBuildingModel(parent_building_id);
    if (buildingModel != null)
    {
        return false;
    }
    switch (parent_building_id)
    {
    case 132:
        buildingModel = SingletonMonoBehaviour<UserManager>.Instance.User.Farm.GetBuildingModel(122);
        return buildingModel != null && buildingModel.Level >= 2;
    case 133:
    case 134:
    case 135:
        buildingModel = SingletonMonoBehaviour<UserManager>.Instance.User.Farm.GetBuildingModel(121);
        return buildingModel != null && buildingModel.Level >= 2;
    default:
        return true;
    }
}
```
### 寬闊的家擴建
<table>
    <thead>
        <tr>
            <td>Lv.0</td>
            <td>Lv.1</td>
        </tr>
    </thead>
    <tr>
        <td><img src= "/images/post/Season_of_Story/Sprite/icon_201080010.png"></td>
        <td><img src= "/images/post/Season_of_Story/Sprite/icon_201080011.png"></td>
    </tr>
</table>

+ 擴建開始事件ID：`10120100`
+ 擴建完成事件ID：`10120101`
+ 優先度：`100`
+ 解鎖項目：
    + 可使用`廚房`
    + 可使用`冰箱`


### 巨大的家擴建
<table>
    <thead>
        <tr>
            <td>Lv.1</td>
            <td>Lv.2</td>
        </tr>
    </thead>
    <tr>
        <td><img src= "/images/post/Season_of_Story/Sprite/icon_201080011.png"></td>
        <td><img src= "/images/post/Season_of_Story/Sprite/icon_201080012.png"></td>
    </tr>
</table>

+ 擴建開始事件ID：`10120200`
+ 擴建完成事件ID：`10120201`
+ 優先度：`100`
+ 解鎖項目：
    + [木工店](../doraemon-story-shop-hammer-carpenter-shop)解鎖[建造](../doraemon-story-shop-hammer-carpenter-shop#建造)項目
        +`溫室`
    + 支線劇情[鎮長第2話 獎勵事件：獲得天氣箱](../doraemon-story-09#獲得天氣箱)

### 寬闊的動物小屋擴建
<table>
    <thead>
        <tr>
            <td>Lv.0</td>
            <td>Lv.1</td>
        </tr>
    </thead>
    <tr>
        <td><img src= "/images/post/Season_of_Story/Sprite/icon_201080020.png"></td>
        <td><img src= "/images/post/Season_of_Story/Sprite/icon_201080021.png"></td>
    </tr>
</table>

+ 擴建開始事件ID：`10121100`
+ 擴建完成事件ID：`10121101`
+ 優先度：`100`
+ 解鎖項目：
    + 可飼養的牛羊從`5頭`增加至`10頭`。
    + 牛羊可在動物小屋`生產`幼崽。
    + [動物商店](../doraemon-story-shop-gouter-mawk-livestock)解鎖[動物鈴](../doraemon-story-shop-gouter-mawk-livestock/#動物鈴)販售項目：
        + `牛鈴`
        + `羊鈴`

### 巨大的動物小屋擴建
<table>
    <thead>
        <tr>
            <td>Lv.1</td>
            <td>Lv.2</td>
        </tr>
    </thead>
    <tr>
        <td><img src= "/images/post/Season_of_Story/Sprite/icon_201080021.png"></td>
        <td><img src= "/images/post/Season_of_Story/Sprite/icon_201080022.png"></td>
    </tr>
</table>

+ 擴建開始事件ID：`10121200`
+ 擴建完成事件ID：`10121201`
+ 優先度：`100`
+ 解鎖項目：
    + 可飼養的牛羊從`10頭`增加至`20頭`。
    + 牛羊生產區從`1處`增加至`2處`。
    + [動物商店](../doraemon-story-shop-gouter-mawk-livestock)解鎖[動物鈴](../doraemon-story-shop-gouter-mawk-livestock/#動物鈴)販售項目：
        + `引導鈴`（1/2條件）
    + [打鐵店](../doraemon-story-shop-anvil-blacksmith-shop)解鎖[機器](../doraemon-story-shop-anvil-blacksmith-shop#機器)販售項目：
        + `優格機`
        + `起士機`
        + `毛線機`

### 寬闊的雞小屋擴建
<table>
    <thead>
        <tr>
            <td>Lv.0</td>
            <td>Lv.1</td>
        </tr>
    </thead>
    <tr>
        <td><img src= "/images/post/Season_of_Story/Sprite/icon_201080030.png"></td>
        <td><img src= "/images/post/Season_of_Story/Sprite/icon_201080031.png"></td>
    </tr>
</table>

+ 擴建開始事件ID：`10122100`
+ 擴建完成事件ID：`10122101`
+ 優先度：`100`
+ 解鎖項目：
    + 可飼養的雞從`5頭`增加至`10頭`。
    + 雞可在雞小屋`孵蛋`。
    + [小雞商店](../doraemon-story-shop-cuckoo-house-chickens)解鎖[動物鈴](../doraemon-story-shop-cuckoo-house-chickens/#動物鈴)販售項目：
        + `雞鈴`

### 巨大的雞小屋擴建
<table>
    <thead>
        <tr>
            <td>Lv.1</td>
            <td>Lv.2</td>
        </tr>
    </thead>
    <tr>
        <td><img src= "/images/post/Season_of_Story/Sprite/icon_201080031.png"></td>
        <td><img src= "/images/post/Season_of_Story/Sprite/icon_201080032.png"></td>
    </tr>
</table>

+ 擴建開始事件ID：`10122200`
+ 擴建完成事件ID：`10122201`
+ 優先度：`100`
+ 解鎖項目：
    + 可飼養的雞從`10頭`增加至`20頭`。
    + 雞孵蛋區從`1處`增加至`2處`。
    + [動物商店](../doraemon-story-shop-gouter-mawk-livestock)解鎖[動物鈴](../doraemon-story-shop-gouter-mawk-livestock/#動物鈴)販售項目：
        + `引導鈴`（1/2條件）
    + [打鐵店](../doraemon-story-shop-anvil-blacksmith-shop)解鎖[機器](../doraemon-story-shop-anvil-blacksmith-shop#機器)販售項目：
        + `美乃滋機`

### 溫室建造
<table>
    <thead>
        <tr>
            <td>Lv.0</td>
            <td>Lv.1</td>
        </tr>
    </thead>
    <tr>
        <td><img src= "/images/post/Season_of_Story/Building/12300.png"></td>
        <td><img src= "/images/post/Season_of_Story/Sprite/icon_201080040.png"></td>
    </tr>
</table>

+ 擴建開始事件ID：`10123100`
+ 擴建完成事件ID：`10123100`
+ 優先度：`100`
+ 解鎖項目：

### 馬小屋建造
<table>
    <thead>
        <tr>
            <td>Lv.0</td>
            <td>Lv.1</td>
        </tr>
    </thead>
    <tr>
        <td><img src= "/images/post/Season_of_Story/Building/12400.png"></td>
        <td><img src= "/images/post/Season_of_Story/Sprite/icon_201080070.png"></td>
    </tr>
</table>

+ 擴建開始事件ID：`10124100`
+ 擴建完成事件ID：`10124101`
+ 優先度：`100`
+ 解鎖項目：
    + 支線劇情[馬第1話 寄養小馬！](../doraemon-story-13/#第1話-寄養小馬)（`40001001`）

### 雞小屋的筒倉建造
<table>
    <thead>
        <tr>
            <td>Lv.0</td>
            <td>Lv.1</td>
        </tr>
    </thead>
    <tr>
        <td><img src= "/images/post/Season_of_Story/Building/12500.png"></td>
        <td><img src= "/images/post/Season_of_Story/Sprite/icon_201080060.png"></td>
    </tr>
</table>

+ 擴建開始事件ID：`10125100`
+ 擴建完成事件ID：`10125101`
+ 優先度：`100`
+ 解鎖項目：
    + [木工店](../doraemon-story-shop-hammer-carpenter-shop)解鎖[擴建](../doraemon-story-shop-hammer-carpenter-shop#擴建雞小屋)項目：
        + `寬闊的雞小屋`

### 動物小屋的筒倉建造
<table>
    <thead>
        <tr>
            <td>Lv.0</td>
            <td>Lv.1</td>
        </tr>
    </thead>
    <tr>
        <td><img src= "/images/post/Season_of_Story/Building/12600.png"></td>
        <td><img src= "/images/post/Season_of_Story/Sprite/icon_201080050.png"></td>
    </tr>
</table>

+ 擴建開始事件ID：`10126100`
+ 擴建完成事件ID：`10126101`
+ 優先度：`100`
+ 解鎖項目：
    + [木工店](../doraemon-story-shop-hammer-carpenter-shop)解鎖[擴建](../doraemon-story-shop-hammer-carpenter-shop#擴建動物小屋)項目：
        + `寬闊的動物小屋`

### 資材儲放屋建造
<table>
    <thead>
        <tr>
            <td>Lv.0</td>
            <td>Lv.1</td>
        </tr>
    </thead>
    <tr>
        <td><img src= "/images/post/Season_of_Story/Building/12900.png"></td>
        <td><img src= "/images/post/Season_of_Story/Sprite/icon_201080080.png"></td>
    </tr>
</table>

+ 擴建開始事件ID：`10129100`
+ 擴建完成事件ID：`10129101`
+ 優先度：`100`
+ 解鎖項目：

## 日常事件
### 老人聊天
+ 事件ID：`70020001`
+ 觸發地點：[萬物鎮西](../doraemon-story-map#萬物鎮西)（`11200`）

![萬物鎮西](/images/post/Season_of_Story/Map/11200.png)
+ 天氣條件：`遇上暴風雨、下雨、下雪不觸發`
+ NPC好感度💝總和條件
<table>
    <thead>
        <tr>
            <td>合計15❤️</td>
        </tr>
    </thead>
    <tr>
        <td>帕絲琪</td>
        <td>布魯</td>
        <td>優</td>
    </tr>
    <tr>
        <td><img src= "/images/post/Season_of_Story/Sprite/icon_201041060.png"></td>
        <td><img src= "/images/post/Season_of_Story/Sprite/icon_201041110.png"></td>
        <td><img src= "/images/post/Season_of_Story/Sprite/icon_201041120.png"></td>
    </tr>
    <tr>
        <td><img src= "/images/post/Season_of_Story/Sprite/icon_201060060.png"></td>
        <td><img src= "/images/post/Season_of_Story/Sprite/icon_201060060.png"></td>
        <td><img src= "/images/post/Season_of_Story/Sprite/icon_201060060.png"></td>
    </tr>
</table>

### 婦女聊天
+ 事件ID：`70020002`
+ 觸發地點：`萬物鎮西`（`11300`）

![萬物鎮西](/images/post/Season_of_Story/Map/11300.png)
+ 天氣條件：`遇上暴風雨、下雨、下雪不觸發`
+ NPC好感度💝總和條件
<table>
    <thead>
        <tr>
            <td>合計9❤️</td>
        </tr>
    </thead>
    <tr>
        <td>靜香</td>
        <td>赫蓮</td>
        <td>埃蒂</td>
    </tr>
    <tr>
        <td><img src= "/images/post/Season_of_Story/Sprite/icon_201041020.png"></td>
        <td><img src= "/images/post/Season_of_Story/Sprite/icon_201041080.png"></td>
        <td><img src= "/images/post/Season_of_Story/Sprite/icon_201041170.png"></td>
    </tr>
    <tr>
        <td><img src= "/images/post/Season_of_Story/Sprite/icon_201060030.png"></td>
        <td><img src= "/images/post/Season_of_Story/Sprite/icon_201060030.png"></td>
        <td><img src= "/images/post/Season_of_Story/Sprite/icon_201060030.png"></td>
    </tr>
</table>