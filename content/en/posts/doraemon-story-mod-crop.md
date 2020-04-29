---
title: 農耕與作物MOD
date: 2020-03-28T17:25:02+08:00
description: 收成、收割與鐮刀的使用
draft: false
hideToc: false
enableToc: false
enableTocContent: true
author: 伊琉沙 AKA 哇咔咔
authorEmoji: 👩🏿‍🚀
tags: 
- MOD
- 作物
series:
- 哆啦A夢牧場物語
categories:
- 哆啦A夢
image: images/post/Season_of_Story/Sprite/icon_1001000.png
libraries:
- katex
---
<mark>最後更新：2020/04/29</mark>


## 作物MOD資料庫
+ 作物資料檔：`CropData.text`
+ 作物資料類：`CCropData`
    + 作物資料結構：`SCropData`
        + 作物ID：`mCropId`
        + 名稱ID：`mNameId`
        + 收穫次數：`mHarvestCount`
        + 成長階數：`mStep`
        + 減少階數：`mReduceStep`
        + 收成天數：`mHarvestDays`
        + 生長季節：`mSeason`
            + `0`為春季生長、`1`為夏季生長、`2`為秋季生長、`3`為冬季生長、`-1`為四季皆生長。
        + 是否收割：`mCanReap`
        + 圖集ID：`mAtlasId`
        + 圖片ID：`mSpriteId`
        + 物品ID：`mItemId`
        + 種子ID：`mSeedItemId`
+ 作物主模板類：`CropMasterModel`
    + 作物ID：`CropMasterModel.CropId` = `CCropData.SCropData.mCropId`
    + 收穫次數：`CropMasterModel.HarvestCount` = `CCropData.SCropData.mHarvestCount`
    + 成長階數：`CropMasterModel.Step` = `CCropData.SCropData.mStep`
    + 減少階數：`CropMasterModel.ReduceStep` = `CCropData.SCropData.mReduceStep`
    + 收成天數：`CropMasterModel.HarvestDays` = `CCropData.SCropData.mHarvestDays`
    + 生長季節：`CropMasterModel.Season` = `CCropData.SCropData.mSeason`
    + 是否收割：`CropMasterModel.CanReap` = `CCropData.SCropData.mCanReap`
+ 作物模板類`CropModel`，土裡作物的實例。
    + 成長方法：`CropModel.Grow()`
    + 減少成長方法：`CropModel.GrowStep()`
    + 成長值：`CropModel.Growth`
    + 品質分：`CropModel.Quality`
+ 作物定義類：`Crop`
    + 最低品質分：`MIN_QUALITY`，常數值：`1`
    + 最高品質分：`Crop.MAX_QUALITY`，常數值：`500`
    + 品質轉換率：`Crop.QUALITY_CONVERSION_RATE`，常數值：`50`


    + 播種方法：`GroundModel.SowSeed(int crop_id, int item_quality)`
    + 莊稼：`GroundModel.mCrop`
    + 作物模板類：`CropModel`
    + 作物品質分：`CropModel.mQuality`
    + 作物品質等級：`CropModel.Quality`
    + 作物最低品質分：`Crop.MIN_QUALITY`
    + 作物最高品質分：`Crop.MAX_QUALITY`

## 農地模板類
+ 農地模板類：`GroundModel @02000567`
    + [澆水方法](../doraemon-story-mod-crop/#澆水方法)：`GroundModel.Wet() : void @06002EC9`
    + [播種方法](../doraemon-story-mod-crop/#播種方法)：`GroundModel.SowSeed(int, int) : void @06002ECB`
    + [施肥方法](../doraemon-story-mod-crop/#施肥方法)：`GroundModel.Fertilize(int) : void @06002ECC`
    + [收成方法](../doraemon-story-mod-crop/#收成方法)：`GroundModel.HarvestCrop() : void @06002ECD`
    + [收割方法](../doraemon-story-mod-crop/#收割方法)：`GroundModel.MowCrop() : void @06002ECE`

### 澆水方法
```C#
public void Wet()
{
	if (this.IsWet || !this.HasCrop)
	{
		return;
	}
	this.mType = Ground.TypeEnum.Wet;
	this.Crop.Grow();
}
```
### 播種方法
```C#
public void SowSeed(int crop_id, int item_quality)
{
    if (this.HasCrop || this.Type != Ground.TypeEnum.Cultivated)
    {
        return;
    }
    int quality = (item_quality - 2) * Define.Crop.QUALITY_CONVERSION_RATE;
    this.mCrop = new CropModel(crop_id, quality);
}
```
### 施肥方法
```C#
public void Fertilize(int item_id)
{
	if (this.IsFertilized || !this.HasCrop)
	{
		return;
	}
	this.mFertilizerId = item_id;
	this.Crop.Upgrade(item_id);
}
```
### 收成方法
```C#
public void HarvestCrop()
{
    if (this.HasCrop && this.Crop.CanRepeat)
    {
        this.Crop.ReduceGrowth();
    }
    else
    {
        this.mCrop = null;
    }
    this.mType = Ground.TypeEnum.Cultivated;
    this.mFertilizerId = -1;
}
```
### 收割方法
```C#
public void MowCrop()
{
    if (this.HasCrop)
    {
        this.mCrop = null;
    }
    this.mType = Ground.TypeEnum.Cultivated;
    this.mFertilizerId = -1;
}
```

## 作物主模板類
+ 作物主模板類：`CropMasterModel @02000583`
    + 收成天數：`CropMasterModel.HarvestDays : int @17000909`
    + 成長階數：`CropMasterModel.Step : int @17000907`
    + 減少階數：`CropMasterModel.ReduceStep : int @17000908`

## 作物模板類
+ 作物模板類：`CropModel @02000558`
    + [作物模板](../doraemon-story-mod-crop/#作物模板)`CropModel.CropModel(int, int) : void @06002D9B`
    + [成長值](../doraemon-story-mod-crop/#成長值)：`CropModel.Growth : int @170007C3`
    + [品質等級](../doraemon-story-mod-crop/#品質等級)：`CropModel.Quality : int @170007C5`
    + [能否收成判斷方法](../doraemon-story-mod-crop/#能否收成判斷方法)：`CropModel.CanHarvest : bool @170007CB`
    + [成長方法](../doraemon-story-mod-crop/#成長方法)：`CropModel.Grow() : void @06002DA8`
    + [成長減少方法](../doraemon-story-mod-crop/#成長減少方法)：`CropModel.ReduceGrowth() : void @06002DA9`
    + [成長進階方法](../doraemon-story-mod-crop/#成長進階方法)：`CropModel.GrowStep() : void @06002DAA`
    + [品質提升方法](../doraemon-story-mod-crop/#品質提升方法)：`CropModel.Upgrade(int) : void @06002DAB`
    + [品質分](../doraemon-story-mod-crop/#品質分)：`CropModel.mQuality : int @04002908`

### 作物模板
```C#
public CropModel(int id, int quality)
{
    this.mId = id;
    this.mQuality = Mathf.Clamp(quality, Crop.MIN_QUALITY, Crop.MAX_QUALITY);
}
```
### 成長值
```C#
private int mGrowth;
public int Growth
{
    get
    {
        return this.mGrowth;
    }
}
```
### 品質等級
```C#
public int Quality
{
    get
    {
        return (this.mQuality != Crop.MAX_QUALITY) ? (this.mQuality / Crop.QUALITY_CONVERSION_RATE + 1) : Item.MAX_QUALITY;
    }
}
```
### 能否收成判斷方法
```C#
public bool CanHarvest
{
	get
	{
		return !this.IsWithered && this.mGrowth == this.Master.HarvestDays;
	}
}
```
### 成長方法
```C#
public void Grow()
{
	if (!this.CanHarvest && !this.IsWithered)
	{
		this.mGrowth++;
	}
}
```
### 成長減少方法
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
### 成長進階方法
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
### 品質提升方法
```C#
public void Upgrade(int item_id)
{
    if (this.CanHarvest || this.IsWithered)
    {
        return;
    }
    this.mQuality += Mathf.CeilToInt(Crop.GetUpgradeValue(item_id) / (float)this.Master.HarvestDays);
    if (this.mQuality > Crop.MAX_QUALITY)
    {
        this.mQuality = Crop.MAX_QUALITY;
    }
}
```
### 品質分
```C#
private int mQuality;
```


# 定義
## 作物類
+ 作物類：`Crop @0200044B`
    + [最小品質分](../doraemon-story-mod-crop/#最小品質分)：`Define.Crop.MIN_QUALITY : int @04001CB9`
    + [最大品質分](../doraemon-story-mod-crop/#最大品質分)：`Define.Crop.MAX_QUALITY : int @04001CBA`
    + [品質轉換率](../doraemon-story-mod-crop/#品質轉換率)：`Define.Crop.QUALITY_CONVERSION_RATE : int @04001CBB`
    + [施肥品質提升表](../doraemon-story-mod-crop/#施肥品質提升表)：`Define.Crop.UpgradeValueTable : Dictionary<int, float> @04001CBD`

### 最小品質分
```C#
public static readonly int MIN_QUALITY = 1;
```
### 最大品質分
```C#
public static readonly int MAX_QUALITY = 500;
```
### 品質轉換率
```C#
public static readonly int QUALITY_CONVERSION_RATE = Crop.MAX_QUALITY / Item.MAX_QUALITY;
```
### 施肥品質提升表
```C#
private static readonly Dictionary<int, float> UpgradeValueTable = new Dictionary<int, float>
{
    {
        Item.ID_FERTILIZER,
        100f
    },
    {
        Item.ID_HIGH_QUALITY_FERTILIZER,
        200f
    }
};
```