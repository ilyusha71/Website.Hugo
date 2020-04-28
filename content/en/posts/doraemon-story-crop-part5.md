---
title: "作物成長過程"
date: 2020-04-03T17:37:16+08:00
description: 作物成長過程的相關計算
draft: false
hideToc: false
enableToc: false
enableTocContent: true
author: 伊琉沙 AKA 哇咔咔
authorEmoji: 👩🏿‍🚀
tags: 
- 作物
series:
- 哆啦A夢牧場物語
categories:
- 哆啦A夢
image: images/post/Season_of_Story/Sprite/Crop_90110401.png
libraries:
- katex
---
<mark>最後更新：2020/04/29</mark>

## 農耕與作物
<table>
    <thead>
        <tr>
            <td colspan="10">農耕與作物</td>        
        </tr>
    </thead>
    <tr>
        <td align="center"><a href="../doraemon-story-crop-part1"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_1001000.png">耕地</a></td>
        <td align="center"><a href="../doraemon-story-crop-part2"><img width="98px" src= "/images/post/Season_of_Story/Sprite/Crop_90110400.png">播種</a></td>
        <td align="center"><a href="../doraemon-story-crop-part3"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_1103001.png">施肥</a></td>
        <td align="center"><a href="../doraemon-story-crop-part4"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_1001020.png">澆水</a></td>        
        <td align="center"><a href="../doraemon-story-crop-part5"><img width="136px" src= "/images/post/Season_of_Story/Sprite/Crop_90110402.png">成長</a></td>
        <td align="center"><a href="../doraemon-story-crop-part6"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_1001030.png">收成收割</a></td>
        <td align="center"><a href="../doraemon-story-shipping-prices-crops"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_3000205.png">出貨價格</a></td>
    </tr>
    <tr>
        <td align="center"><a href="../doraemon-story-crop-part1/#鋤頭"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_1001005.png">鋤頭</a></td>
        <td align="center"><a href="../doraemon-story-shop-20700-knick-knacks-general-store/#作物種子"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_2000501.png">作物種子</a></td>
        <td align="center"><a href="../doraemon-story-shop-20700-knick-knacks-general-store/#肥料"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_1103000.png">肥料</a></td>
        <td align="center"><a href="../doraemon-story-crop-part4/#澆水壺"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_1001025.png">澆水壺</a></td>        
        <td align="center"><a href="../doraemon-story-crop-grow"><img width="113px" src= "/images/post/Season_of_Story/Sprite/Crop_90110405.png">成長資料</a></td>
        <td align="center"><a href="../doraemon-story-crop-part6/#鐮刀"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_1001035.png">鐮刀</a></td>
        <td align="center"><a href="../#溫室種植"><img width="64px" src= "/images/post/Season_of_Story/Sprite/icon_1104000.png">溫室種植</a></td>
    </tr>
</table>

## 作物的成長
+ 作物的成長機制與作物的三個參數有關：
    + [收成天數](../doraemon-story-crop-part5/#收成天數)
    + [成長階數](../doraemon-story-crop-part5/#成長階數)
    + [減少階數](../doraemon-story-crop-part5/#減少階數)

### 收成天數
+ 作物的成長天數是以`成長值`計算。
+ 每天作物在[澆水](../doraemon-story-crop-part4)後都會增加`成長值`。
+ 當`成長值`達到`收成天數`時，作物就能進行[收成收割](../doraemon-story-crop-part6)。

### 成長階數
+ 成長階數是作物從`種子`到`成熟`所經歷的階段總數，也相當於作物外觀的變化數，包含若干個`成長階段`與最終的`成熟階段`。
    + 目前作物的成長階數大多為4階至6個階。
    + 在37種作物中，番茄擁有最多7階的成長階數，亦即6個`成長階段`與1個`成熟階段`。
+ `成長階段`的計算從種子剛[播種](../doraemon-story-crop-part2)的時候算起，為第1階段。
+ 最後一個成長階段結束時即為作物的`成熟階段`。
+ 每個階段所需最低的`成長值`為`成長值門檻`。

#### 成長階段的成長天數
+ 在作物成熟前，每個`成長階段`的`成長天數`將透過`收成天數`平均分配。
+ 若還有`剩餘天數`則從最後一個`成長階段`開始倒序分配，原理如下：
    1. `收成天數`平均分配後的天數為`基本成長天數`，分配完的餘數為`剩餘成長天數`。
    2. `剩餘成長天數`將依`成長階段`的順序倒序分配。
    3. 分配完成後可得出`成長天數`是否增加的`分界值`。
    4. 因此當作物的`成長值`達到`分界值`後，每個`成長階段`的`成長天數`都會多1天。

---
$$成長階段總數=成長階數-1$$
$$基本成長天數=\dfrac{收成天數}{成長階段總數}$$
$$剩餘成長天數=收成天數-(基本成長天數\times成長階段總數)$$
$$分界值=(成長階段總數-剩餘成長天數)\times基本成長天數$$

#### 鳳梨的成長計算
+ 鳳梨的`收成天數`為`13天`。
+ 鳳梨的`成長階數`為`6`。
+ 鳳梨的`基本成長天數`為`2天`。
+ 鳳梨的`剩餘成長天數`為`3天`。
+ 鳳梨的`分界值`為`4`。

<table>
    <thead>
    　<tr>
            <td align="center" colspan="5">成長階段</td>
            <td align="center">成熟階段</td>
        </tr>
    </thead>
　<tr>
            <td align="center" class="breadcrumb">第1階段</td>
            <td align="center" class="breadcrumb">第2階段</td>
            <td align="center" class="breadcrumb">第3階段</td>
            <td align="center" class="breadcrumb">第4階段</td>
            <td align="center" class="breadcrumb">第5階段</td>
            <td align="center" class="breadcrumb">第6階段</td>
    </tr>
　<tr>
    　<td align="center"><img src= "/images/post/Season_of_Story/Sprite/Crop_90120600.png"></td>
    　<td align="center"><img src= "/images/post/Season_of_Story/Sprite/Crop_90120601.png"></td>
    　<td align="center"><img src= "/images/post/Season_of_Story/Sprite/Crop_90120602.png"></td>
    　<td align="center"><img src= "/images/post/Season_of_Story/Sprite/Crop_90120603.png"></td>
    　<td align="center"><img src= "/images/post/Season_of_Story/Sprite/Crop_90120604.png"></td>
    　<td align="center"><img src= "/images/post/Season_of_Story/Sprite/Crop_90120605.png"></td>
　</tr>
　<tr>
        <td align="center" colspan="5" class="breadcrumb">成長天數</td>
        <td align="center" class="breadcrumb">成熟</td>
    </tr>
　<tr>
        <td align="center">2天</td>
        <td align="center">2天</td>
        <td align="center">3天</td>
        <td align="center">3天</td>
        <td align="center">3天</td>
        <td align="center"></td>
    </tr>
　<tr>
        <td align="center" colspan="6" class="breadcrumb">成長值範圍</td>
    </tr>
　<tr>
        <td align="center">0~1</td>
        <td align="center">2~3</td>
        <td align="center">4~6</td>
        <td align="center">7~9</td>
        <td align="center">10~12</td>
        <td align="center">13</td>
    </tr>
</table>

#### 瞬間成長劑
+ `瞬間成長劑`的效果就是使作物的成長階段直接立即進入下一階段。
    + `成長值`的增加量等於`當前階段`與`下一階段`成長值門檻的差。
    + 因此使用在成長階數較少，收成天數較長的作物上收益較好。

<table>
    <thead>
        <tr>
            <td align="center">瞬間成長劑</td>
        </tr>
    </thead>
    <tr>
        <td align="center"><img width="100px" src= "/images/post/Season_of_Story/Sprite/icon_1104080.png"></td>
    </tr>
</table>

### 減少階數
+ 減少階數是`多次收穫作物`收成後，作物重新成長時減少的階段總數。
+ 減少的階段會從最後一個`成長階段`開始，亦即作物收成後，重新成長的作物會根據減少階數進行`降階`。
    + 例如成長階數為`6`、減少階數為`2`，則重新成長的作物會`降階`為第4階段。
+ `降階`減少的成長階段直接對應`成長值`與`成長天數`的減少量。
+ 減少的`成長天數`為作物重新成長的天數，即是`再收成天數`，也等同於少掉的`施肥次數`。  
+ `再收成天數`可透過`基本成長天數`與`剩餘成長天數`反推求得，原理如下：
    1. `降階`減少的成長天數可以直接從`減少階數`與`基本成長天數`的乘積求得。
    2. 由於降階是從最後的成長階段開始，需要再補上`剩餘成長天數`。
    3. 但只需補上減少階段的`剩餘成長天數`即可，這個天數為`補充天數`。

---
$$若剩餘成長天數<=減少階數$$$$補充天數=剩餘成長天數$$
$$若剩餘成長天數>減少階數$$$$補充天數=減少階數$$
$$再收成天數=(基本成長天數\times減少階數)+補充天數$$
$$降階後的成長值={收成天數}-{再收成天數}$$

#### 鳳梨的重新成長計算
+ 鳳梨的`收成天數`為`13天`。
+ 鳳梨的`成長階數`為`6`。
+ 鳳梨的`減少階數`為`2`。
+ 鳳梨的`基本成長天數`為`2天`。
+ 鳳梨的`剩餘成長天數`為`3天`。
+ 鳳梨的`補充天數`為`2天`。
+ 鳳梨的`再收成天數`為`6天`。

<table>
    <thead>
    　<tr>
            <td align="center" colspan="2">重新成長階段</td>
            <td align="center">成熟階段</td>
        </tr>
    </thead>
　<tr>
            <td align="center" class="breadcrumb">第4階段</td>
            <td align="center" class="breadcrumb">第5階段</td>
            <td align="center" class="breadcrumb">第6階段</td>
    </tr>
　<tr>
    　<td align="center"><img src= "/images/post/Season_of_Story/Sprite/Crop_90120603.png"></td>
    　<td align="center"><img src= "/images/post/Season_of_Story/Sprite/Crop_90120604.png"></td>
    　<td align="center"><img src= "/images/post/Season_of_Story/Sprite/Crop_90120605.png"></td>
　</tr>
　<tr>
        <td align="center" colspan="2" class="breadcrumb">成長天數</td>
        <td align="center" class="breadcrumb">成熟</td>
    </tr>
　<tr>
        <td align="center">3天</td>
        <td align="center">3天</td>
        <td align="center"></td>
    </tr>
　<tr>
        <td align="center" colspan="3" class="breadcrumb">成長值範圍</td>
    </tr>
　<tr>
        <td align="center">7~9</td>
        <td align="center">10~12</td>
        <td align="center">13</td>
    </tr>
</table>

#### 品質分的減少
+ 品質分的減少原理與`成長值`的減少相同，也與`降階`減少的成長階段有關。
+ 然而`品質分`的成長本身又與施用的肥料有關，所以減少的品質分會以`高級肥料`的效果進行計算。
+ `降階`的`品質分`計算公式如下

$$減少的品質分=無條件進位(\dfrac {高級肥料效果}{收成天數})\times{減少的施肥次數}$$

+ 以草莓為例：
    + 假設收成時的品質分為`253分`。
    + 成長階段從`第6階段`降為`第4階段`，一共少了`6天`的成長，亦即少了`6次`的施肥。
    + 根據[施肥品質分](../doraemon-story-crop-part2)的計算方法，草莓6次施用`高級肥料`所增加的`品質分`為`84分`。
    + 所以`品質分`會減少84分變成`169分`。

## 總結
以草莓作為例子總結：
1. 已知草莓的收成天數為`15天`，每次澆水成長值`+1`，因此收成時成長值為`15`。
2. 草莓收成後，土裡的草莓成長值會降回到第9天的狀態，亦即成長值為`9`。
3. 若草莓成長全程使用高級肥料，則品質分也會降回到第9天的品質分。
4. 因此成長階段在第9天的草莓還需要6天才會成熟。
5. 若這6天也都使用高級肥料，再次成熟時，品質分也會與上次收成相同。

## 源代碼
+ 作物主模板類：`CropMasterModel @02000583`
    + 收成天數：`CropMasterModel.HarvestDays : int @17000909`
    + 成長階數：`CropMasterModel.Step : int @17000907`
    + 減少階數：`CropMasterModel.ReduceStep : int @17000908`
+ 作物模板類：`CropModel @02000558`
    + 成長方法：`CropModel.Grow() : void @06002DA8`
    + 確認收成方法：`CropModel.CanHarvest : bool @170007CB`
    + 成長進階方法：`CropModel.GrowStep() : void @06002DAA`
    + 成長減少方法：`CropModel.ReduceGrowth() : void @06002DA9`

```C#
public void Grow()
{
	if (!this.CanHarvest && !this.IsWithered)
	{
		this.mGrowth++;
	}
}
public bool CanHarvest
{
	get
	{
		return !this.IsWithered && this.mGrowth == this.Master.HarvestDays;
	}
}
public void GrowStep()
{
	if (this.CanHarvest || this.IsWithered)
	{
		return;
	}
	int num2;
	int num = Math.DivRem(this.Master.HarvestDays, this.Master.Step - 1, out num2);
	int num3 = (this.Master.Step - 1 - num2) * num;
	if (this.mGrowth < num3)
	{
		this.mGrowth += num;
	}
	else
	{
		this.mGrowth += num + 1;
	}
	if (this.mGrowth > this.Master.HarvestDays)
	{
		this.mGrowth = this.Master.HarvestDays;
	}
}
public void ReduceGrowth()
{
    if (!this.CanRepeat && !this.IsWithered)
    {
        return;
    }
    int num2;
    int num = Math.DivRem(this.Master.HarvestDays, this.Master.Step - 1, out num2);
    num2 = ((num2 <= this.Master.ReduceStep) ? num2 : this.Master.ReduceStep);
    int num3 = num * this.Master.ReduceStep + num2;
    this.mGrowth -= num3;
    this.mQuality -= Mathf.CeilToInt(Crop.GetUpgradeValue(Item.ID_HIGH_QUALITY_FERTILIZER) / (float)this.Master.HarvestDays) * num3;
    if (this.mQuality < Crop.MIN_QUALITY)
    {
        this.mQuality = Crop.MIN_QUALITY;
    }
    this.mRepeatCount++;
}
```