---
title: "【哆啦A夢牧場物語】物品的品質"
date: 2020-04-03T16:22:12+08:00
description: 物品的品質資料
draft: false
hideToc: false
enableToc: false
enableTocContent: true
author: 伊琉沙 AKA 哇咔咔
authorEmoji: 👩🏿‍🚀
tags: 
- MOD
series:
- 哆啦A夢牧場物語
categories:
- 哆啦A夢
image: images/post/story_sprite/icon_301001000.png
libraries:
- katex
---
## 物品MOD資料庫
+ 物品資料檔：`ItemData.text`
+ 物品資料類：`CItemData`，讀取TextAsset的物品二進制資料`ItemData.text`。
    + 物品的資料結構：`CItemData.SItemData`
        + 物品ID：`CItemData.SItemData.mItemId`
        + 價格：`CItemData.SItemData.mPrice`
        + 作物ID：`CItemData.SItemData.mCropId`
+ 物品模組類：`ItemMasterModel`，取得物品的資料結構並記錄所有物品參數的`基本值`。
    + 物品ID：`ItemMasterModel.Id` = `CItemData.SItemData.mItemId`
    + 基本售價：`ItemMasterModel.BaseSellingPrice` = `CItemData.SItemData.mPrice`
    + 體力回復：`ItemMasterModel.RecoveryValue`
    + 具有品質等級：`ItemMasterModel.HasQuality`
    + 名稱ID：`ItemMasterModel.NameId`
    + 描述ID：`ItemMasterModel.DescriptionId`
    + 最小尺寸：`ItemMasterModel.MinSize`
    + 最大尺寸：`ItemMasterModel.MaxSize`
+ 物品實體類：`ItemModel`，顯示目前遊戲中各項物品參數的`實際值`與具體的`計算方法`。
    + 堆疊數量：`ItemModel.Count`
    + 品質等級：`ItemModel.Quality`，[品質等級與★級對照表](../doraemon-story-item-part1/#品質等級與級對照表)
    + 售價：`ItemModel.SellingPrice`，依`品質等級`高低而定。
+ 物品定義類：`Item`，定義物品資料調用的相關參數。
    + 最大堆疊數：`Item.MAX_STACK`
    + 售價倍率：`Item.SELLING_PRICE_RATE`，常數值：`1.13`

## 物品的品質
在`《哆啦A夢：大雄的牧場物語》`中，大多數的物品都具有品質等級（`ItemMasterModel.mHasQuality`），例如`礦石`、`作物`、`魚`、`昆蟲`、`料理`，少部分物品則無品質等級，例如`工具`、`肥料`、`野生蔬果`、`食譜`。

### 品質等級 ItemModel.Quality
+ 遊戲中的品質等級以`★級`顯示品質的優劣程度。
    + 若物品具有品質等級則初始值為1（`ItemModel.mQuality`）， 對應★級為0.5★
    + 最大品質等級（`Item.MAX_QUALITY`）為10級。

### 品質等級與★級對照表
| **品質等級** | **1** | **2** | **3** | **4** | **5** | **6** | **7** | **8** | **9** | **10** |
| :----------: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :----: |
|     ★ 級     | 0.5★  |  1★   | 1.5★  |  2★   | 2.5★  |  3★   | 3.5★  |  4★   | 4.5★  |   5★   |