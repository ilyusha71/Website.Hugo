---
title: "【哆啦A夢牧場物語】作物的成長過程與相關計算"
date: 2020-04-03T17:37:16+08:00
description: 作物的成長過程與相關計算
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
image: images/post/Season_of_Story/Sprite/Crop_90110405.png
libraries:
- katex
---
## 相關分析
+ [【哆啦A夢牧場物語】作物播種與收成的品質計算](../doraemon-story-crop-part1)
+ [【哆啦A夢牧場物語】肥料對作物的品質影響](../doraemon-story-crop-part2)
+ [【哆啦A夢牧場物語】作物的成長過程與相關計算](../doraemon-story-crop-part3)

## 作物的成長
根據`CropModel`的資料分析，作物的成長機制離不開下列三個參數：
+ 收成天數（`CropMasterModel.HarvestDays`）
+ 成長階數（`CropMasterModel.Step`）
+ 減少階數（`CropMasterModel.ReduceStep`）

### 收成天數
作物的成長過程是以成長值（`CropModel.mGrowth`）表示。
每天作物在澆水後都會進行成長（`CropModel.Grow()`），`成長值`+1。
```C#
public void Grow()
{
	if (!this.CanHarvest && !this.IsWithered)
	{
		this.mGrowth++;
	}
}
```
當成長值達到收成天數（`CropMasterModel.HarvestDays`）時，作物就能進行收成（`CropModel.CanHarvest`）。
```C#
public bool CanHarvest
{
	get
	{
		return !this.IsWithered && this.mGrowth == this.Master.HarvestDays;
	}
}
```
### 成長階數
成長階數（`CropMasterModel.Step`）是作物從種子到成熟需經歷的成長階段總數，也相當於作物外觀的變化。
+ 目前作物的成長階數大多為4到6個階段。
+ 在37種作物中，番茄擁有最多的七個成長階段。
+ 成長階段的初始階段為種子剛播種的時候，成長階段為第1階段。
+ 成長階段的最後階段為作物成熟的時候，如果成長階數是6，則作物成熟的成長階段為第6階段。
+ 透過成長進階方法`CropModel.GrowStep()`可以知道每個成長階段對應的`成長值`與門檻。
+ 由於剛播種的第一天就可以開始澆水成長（`成長值`為1），所以第1階段的持續天數會少1天。
+ `瞬間成長劑`的效果就是使作物直接立即進入下一階段，成長值的增加量等於現階段與下一階段的成長值門檻的差，因此使用在成長階數較少，收成天數較長的收益較好。
```C#
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
```
從代碼中，可以得知`num`為收成天數平均分配給成熟前的成長階段（所以為成長階數-1），亦即成熟前每個成長階段對應`成長值`的基本數量，而餘數`num2`則為平均分配的剩餘數量，將從最後的成長階段（除去成熟階段）開始分配，透過`num3`找出餘數分配完時對應成長階段的`成長值`。
#### 草莓的成長階段
+ 以草莓為例：
    + 草莓的收成天數為15天。
    + 草莓的成長階數為6。
+ 透過成長進階方法`CropModel.GrowStep()`，找出可得出草莓成長值對應的成長階段。
    + num = 3
    + num2 = 0
    + num3 = 15
<table border = "7">
　<tr>
        <td>第1階段</td>
        <td>第2階段</td>
        <td>第3階段</td>
        <td>第4階段</td>
        <td>第5階段</td>
        <td>第6階段</td>
    </tr>
　<tr>
    　<td><img src= "/images/post/Season_of_Story/Sprite/Crop_90110400.png"></td>
    　<td><img src= "/images/post/Season_of_Story/Sprite/Crop_90110401.png"></td>
    　<td><img src= "/images/post/Season_of_Story/Sprite/Crop_90110402.png"></td>
    　<td><img src= "/images/post/Season_of_Story/Sprite/Crop_90110403.png"></td>
    　<td><img src= "/images/post/Season_of_Story/Sprite/Crop_90110404.png"></td>
    　<td><img src= "/images/post/Season_of_Story/Sprite/Crop_90110405.png"></td>
　</tr>
　<tr>
        <td>2天</td>
        <td>3天</td>
        <td>3天</td>
        <td>3天</td>
        <td>3天</td>
        <td>---</td>
    </tr>
　<tr>
        <td>0~2</td>
        <td>3~5</td>
        <td>6~8</td>
        <td>9~11</td>
        <td>12~14</td>
        <td>15</td>
    </tr>
</table>

#### 鳳梨的成長階段
+ 再以鳳梨為例：
    + 鳳梨的收成天數為13天。
    + 鳳梨的成長階數為6。
+ 透過成長進階方法`CropModel.GrowStep()`，找出可得出鳳梨成長值對應的成長階段。
    + num = 2
    + num2 = 3
    + num3 = 4

<table border = "7">
　<tr>
        <td>第1階段</td>
        <td>第2階段</td>
        <td>第3階段</td>
        <td>第4階段</td>
        <td>第5階段</td>
        <td>第6階段</td>
    </tr>
　<tr>
    　<td><img src= "/images/post/Season_of_Story/Sprite/Crop_90120600.png"></td>
    　<td><img src= "/images/post/Season_of_Story/Sprite/Crop_90120601.png"></td>
    　<td><img src= "/images/post/Season_of_Story/Sprite/Crop_90120602.png"></td>
    　<td><img src= "/images/post/Season_of_Story/Sprite/Crop_90120603.png"></td>
    　<td><img src= "/images/post/Season_of_Story/Sprite/Crop_90120604.png"></td>
    　<td><img src= "/images/post/Season_of_Story/Sprite/Crop_90120605.png"></td>
　</tr>
　<tr>
        <td>1天</td>
        <td>2天</td>
        <td>3天</td>
        <td>3天</td>
        <td>3天</td>
        <td>---</td>
    </tr>
　<tr>
        <td>0~1</td>
        <td>2~3</td>
        <td>4~6</td>
        <td>7~9</td>
        <td>10~12</td>
        <td>13</td>
    </tr>
</table>

### 減少階數（降階）
減少階數（`CropMasterModel.ReduceStep`）是多次收穫作物收成後重新成長時應減少的成長階段數量。
亦即作物收成後，土裡的作物會根據減少階數`降階`到某個成長階段。
+ 單次收穫作物的減少階數為-1。
+ 多次收穫作物的減少階數為1或2。
+ `降階`減少的成長階段直接對應`成長值`與`品質分`的減少量。
---
以草莓為例：
+ 草莓的成長階數為6。
+ 草莓的減少階數為2。

當草莓收成後，土裡重新成長的草莓其成長階段會減少2階（`降階`）而變成第4階段，同時`成長值`與`品質分`也會同比例一併減少。

---
降階後的`成長值`與`品質分`可透過成長減少方法（`CropModel.ReduceGrowth()`）計算。
```C#
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
成長減少方法的公式：
$$num=\dfrac {收成天數}{成長階數}的商數$$
$$num2=\dfrac {收成天數}{成長階數}的餘數，若餘數大於減少階數則：num2=減少階數$$
$$num3=num\times減少階數+num2$$
透過計算可以發現`num3`所代表的意義可以為：
+ 降階後少掉的`成長天數`。
+ 降階後少掉的`施肥次數`。
+ 降階後`成長值`的減少量。
+ 降階後的`再收成天數`。
#### 成長值的減少
成長值減少的多寡與減少的成長階段有關。
+ 以草莓為例：
    + `降階`後的成長階段從`第6階段`降為`第4階段`。
    + 參考[草莓成長階段](#草莓的成長階段)的對應表，`成長值`自然也從第6階段的`15`變為第4階段的`9`。
+ 根據成長減少方法的計算公式：
$$草莓降階後的成長值={收成天數}-{再收成天數}={15}-{6}=9$$

### 品質分的減少
品質分的減少原理與`成長值`的減少相同，與`降階`減少的成長階段有關，然而`品質分`的成長本身又與施用的肥料有關，所以減少的品質分會以`高級肥料`的效果進行計算。
+ 以草莓為例：
    + 假設收成時的品質分為`253分`。
    + 成長階段從`第6階段`降為`第4階段`，一共少了`6天`的成長，亦即少了`6次`的施肥。
    + 根據[前篇](../doraemon-story-crop-part2)施肥品質分的計算方法，草莓6次施用高級肥料所增加的品質分為`84分`。
    + 所以`品質分`會減少84分變成`169分`。
+ 根據成長減少方法的計算公式，`降階`減少的`品質分`計算公式為：
$$無條件進位（\dfrac {高級肥料效果}{收成天數}）\times{減少的施肥次數}$$
$$草莓降階後的品質分=253-無條件進位（\dfrac {200}{15}）\times6=253-84=169$$

## 總結
以草莓作為例子總結：
1. 已知草莓的收成天數為`15天`，每次澆水成長值`+1`，因此收成時成長值為`15`。
2. 草莓收成後，土裡的草莓成長值會降回到第9天的狀態，亦即成長值為`9`。
3. 若草莓成長全程使用高級肥料，則品質分也會降回到第9天的品質分。
4. 因此成長階段在第9天的草莓還需要6天才會成熟。
5. 若這6天也都使用高級肥料，再次成熟時，品質分也會與上次收成相同。