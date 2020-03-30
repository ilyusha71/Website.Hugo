---
title: "Photon Unity Networkings 測試"
date: 2020-03-30T17:02:00+08:00
description: "第一次使用Photon做網路遊戲就上手"
draft: false
hideToc: false
enableToc: true
enableTocContent: true
author: 伊琉沙 AKA 哇咔咔
authorEmoji: 👩🏿‍🚀
tags: 
- Photon
- Networking
series:
- 遊戲開發
categories:
- Unity
image: images/feature/module.svg
---
### 實作環境
+ Unity2018.3.0f2
+ PUN 2.17
+ Photon lib 4.1.3.0
## 下載最新版PUN2
以下的設置與代碼使用PUN2，PUN舊版並不適用請注意！
先到Asset Store下載[PUN 2 - FREE](https://assetstore.unity.com/packages/tools/network/pun-2-free-119922)
## 創建PUN專案
連上[Photon Cloud](https://dashboard.photonengine.com/zh-TW/App/Create)建立新的應用程式，在`Photon Type`選擇`Photon Realtime`。
你可以在Photon Cloud的應用程式找到剛剛建立的應用程式，並複製`應用程式 ID`，這段ID的格式應該長成這樣：
```
1267d507-645b-4121-b3a7-d15b09158bc1
```
## 設定PUN專案
回到Unity，打開PUN Wizard：
`功能列`=>`Windows`=>`Photon Unity Networking`=>`PUN Wizard`
選擇`Locate PhotonServerSettings`，會出現下面的視窗（或在Inspector中顯示）。
![PhotonServerSettings](/images/post/PhotonServerSettings.png)
+ `App Id Reatime`填入Photon Cloud應用程式的ID
+ `Use Name Server`打勾
+ `Fixed Region`選填，可用作快速登錄的地區
## 快速測試
1. 在`Project`搜尋`DemoAsteroids-LobbyScene`與`DemoAsteroids-GameScene`兩個場景檔或透過以下路徑。
    + `Assets\Photon\PhotonUnityNetworking\Demos\DemoAsteroids`
2. 打開Build Settings：
    + `功能列`=>`Build Settings...`
    + 熱鍵：<kbd><kbd>CTRL</kbd> + <kbd>SHIFT</kbd> + <kbd>B</kbd></kbd>
3. 將場景檔拖曳到`Scenes In Build`，並將`DemoAsteroids-LobbyScene`移到首位。

以上，PUN的快速設定基本完成，可以Build並進行測試！