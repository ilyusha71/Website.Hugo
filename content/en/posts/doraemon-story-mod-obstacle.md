---
title: 障礙MOD
date: 2020-05-01T17:25:02+08:00
description: 障礙MOD
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
image: images/post/Season_of_Story/Sprite/icon_301010000.png
libraries:
- katex
---
<mark>最後更新：2020/05/01</mark>

# 障礙MOD
# 定義
## 障礙類
+ 障礙類：`Obstacle @0200048F`
    + [類型枚舉](../doraemon-story-mod-obstacle/#類型枚舉)：`TypeEnum @02000490`

### 類型枚舉
```C#
public enum TypeEnum
{
    // Token: 0x040020DC RID: 8412
    Tree,
    // Token: 0x040020DD RID: 8413
    FruitTree,
    // Token: 0x040020DE RID: 8414
    Rock,
    // Token: 0x040020DF RID: 8415
    Stump,
    // Token: 0x040020E0 RID: 8416
    Branch
}
```