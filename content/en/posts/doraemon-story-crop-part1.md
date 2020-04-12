---
title: "【哆啦A夢牧場物語】作物播種與收成的品質計算"
date: 2020-04-03T16:25:02+08:00
description: 作物播種與收成的品質計算方法
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
image: images/post/story_sprite/icon_301051200.png
libraries:
- katex
---
## 相關分析
+ [【哆啦A夢牧場物語】作物播種與收成的品質計算](../doraemon-story-crop-part1)
+ [【哆啦A夢牧場物語】肥料對作物的品質影響](../doraemon-story-crop-part2)
+ [【哆啦A夢牧場物語】作物的成長過程與相關計算](../doraemon-story-crop-part3)

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

## 作物的品質分
當`種子`播種後，會變成地上的莊稼（`GroundModel.mCrop`），莊稼的實體資料為作物實體類（`CropModel`）。
而種子品質等級（`ItemModel.mQuality`）則會轉換為作物品質分（`CropModel.mQuality`）；直到作物收成時才會再根據最後的作物品質分轉換為作物品質等級（`CropModel.Quality`）。
+ 作物的最低品質（`Crop.MIN_QUALITY`）為1分。
+ 作物的最高品質（`Crop.MAX_QUALITY`）為500分。
### 播種品質轉換公式
播種方法（`GroundModel.SowSeed(int crop_id, int item_quality)`）：
```C#
public void SowSeed(int crop_id, int item_quality)
{
	if (this.HasCrop || this.Type != Ground.TypeEnum.Cultivated)
	{
		return;
	}
	int quality = (item_quality - 2) * Crop.QUALITY_CONVERSION_RATE;
	this.mCrop = new CropModel(crop_id, quality);
}
```
```C#
public CropModel(int id, int quality)
{
    this.mId = id;
    this.mQuality = Mathf.Clamp(quality, Crop.MIN_QUALITY, Crop.MAX_QUALITY);
}
```
播種方法的品質轉換公式：
$$作物品質分=（種子品質等級-2）\times{作物品質轉換率}$$
$$作物品質轉換率=\dfrac {最大品質分}{最大品質等級}=\dfrac {500}{10}=50$$
### 播種品質轉換量化表
| **種子品質★** | **★0.5** | **★1** | **★1.5** | **★2** | **★2.5** | **★3** | **★3.5** | **★4** | **★4.5** | **★5** |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| 種子品質等級 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 |
| 作物品質分 | 0 | 0 | 50 | 100 | 150 | 200 | 250 | 300 | 350 | 400 |
| 作物品質★ | ★0.5 | ★0.5 | ★1 | ★1.5 | ★2 | ★2.5 | ★3 | ★3.5 | ★4 | ★4.5 |

所以`種子`播種後品質就會直接先降1級，相當於品質★降★0.5。

### 作物收成品質轉換公式
作物的品質等級（`CropModel.Quality`）讀取子：
```C#
public int Quality
{
    get
    {
        return (this.mQuality != Crop.MAX_QUALITY) ? (this.mQuality / Crop.QUALITY_CONVERSION_RATE + 1) : Item.MAX_QUALITY;
    }
}
```
作物品質等級轉換公式：
$$作物品質等級=\dfrac{作物品質分}{作物品質轉換率}+1$$
### 收成品質轉換量化表
| **作物品質分** | **1~49** | **50~99** | **100~149** | **150~199** | **200~249** | **250~299** | **300~349** | **350~399** | **400~449** | **450~500** |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| 作物品質等級 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 |
| 作物品質★ | ★0.5 | ★1 | ★1.5 | ★2 | ★2.5 | ★3 | ★3.5 | ★4 | ★4.5 | ★5 |