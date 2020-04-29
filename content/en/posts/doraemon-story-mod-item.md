---
title: 物品MOD
date: 2020-03-26T17:25:02+08:00
description: 收成、收割與鐮刀的使用
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
image: images/post/Season_of_Story/Sprite/icon_1001000.png
libraries:
- katex
---
<mark>最後更新：2020/04/29</mark>

# 定義

## 物品模板類：
+ 物品模板類：`ItemModel @0200056E`
    + [品質等級](../doraemon-story-mod-item/#品質等級)：`ItemModel.Quality : int @17000837`

### 品質等級
```C#
public int Quality
{
	get
	{
		return this.mQuality;
	}
}
```

## 物品類
+ 物品類：`Item @02000469`
    + [最大品質等級](../doraemon-story-mod-item/#最大品質等級)：`Define.Item.MAX_QUALITY : int @04001E79`

### 最大品質等級
```C#
public static readonly int MAX_QUALITY = 10;
```
