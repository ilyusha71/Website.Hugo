---
title: "在網站中使用Google Fonts"
date: 2020-03-24T12:00:06+08:00
description: "Google Fonts雲端字體的設定與使用"
draft: false
hideToc: false
enableToc: true
enableTocContent: true
author: iLYuSha
authorEmoji: 👩🏿‍🚀
tags: 
- font
series:
-
categories:
-
image: images/feature-dora/img_tutorial_npc_talk.png
---
## 選擇合適的字體
### Step 1 前往Goole Fonts網站
[Goole Fonts](https://fonts.google.com/)
### Step 2 選擇語言
中文的部分除了繁體與簡體之外還有支援香港字形。
按照習慣選擇 `Chinese (Traditional)`。
### Step 3 選擇字體
目前繁體字體只提供下列兩種字體：
* `Noto Sans TC`（<font face="Noto Sans TC">思源黑體</font>）
* `Noto Serif TC`（<font face="Noto Serif TC">思源宋體</font>）
進入字體頁面可以輸入內容看看預覽效果，調整大小與粗細。
### Step 4 產生樣式
調整完成點選網站右上角的 `SELECT THIS FONT`，會在右下角跳出樣式窗口，在此窗口還可以在 `CUSTOMIZE` 進一步設置樣式支援的粗細與語系。
## 設定Google Fonts
### 標準設置
在 `STANDARD` 應該會出現類似下面代碼的樣式：
{{< highlight html >}}
<link href="https://fonts.googleapis.com/css?family=Noto+Sans+TC&display=swap&subset=chinese-traditional" rel="stylesheet">
{{< /highlight >}}

將這段代碼複製到網站的 `[head]` 與 `[/head]` 之間。
### @import設置
切換 `@import`會出現：
{{< highlight CSS >}}
@import url('https://fonts.googleapis.com/css?family=Noto+Sans+TC&display=swap&subset=chinese-traditional');
{{< /highlight >}}
將 `@import` 這段放入 `[style]` 與 `[/style]` 之間。

## zzo主題設置
在zzo主題設置上僅需要兩個步驟，此處以 `Noto Sans TC` 為例：
### 修改 font.toml
在 `root/data/font.toml` 這個位置找到 `font.toml` ，修改預設字體內容：
{{< highlight toml >}}
title_font = "\"Noto Sans TC\", sans-serif"
content_font = "\"Noto Sans TC\", serif"
{{< /highlight >}}

### 添加修改head
在 `root/layouts/partials/head/custom-head.html` 這個位置找到 `custom-head.htm` ，加載下列樣式。
{{< highlight html >}}
<link href="https://fonts.googleapis.com/css?family=Noto+Sans+TC&display=swap&subset=chinese-traditional" rel="stylesheet">
{{< /highlight >}}