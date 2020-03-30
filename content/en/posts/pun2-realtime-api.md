---
title: "PUN2常用API介紹"
date: 2020-03-30T17:36:15+08:00
description: "如果想自行設計遊戲登入的方法與遊戲大廳就看下去吧！"
draft: false
hideToc: false
enableToc: true
enableTocContent: true
author: iLYuSha
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

如果還沒加入PUN可以參考上一篇，[Photon Unity Networkings 測試](../pun2-test)

## 連線設定
### 連線前設定AppId
由於我的PUN專案為了能連上中國內地，因此使用了兩個獨立的應用程式，`AppId`一般都直接在`PhotonServerSettings`設定，如果要做到能自由切換應用程式ID，可以透過下列方法：
```C#
PhotonNetwork.PhotonServerSettings.AppSettings.AppIdRealtime = "replace with your own AppId";
PhotonNetwork.NetworkingClient.AppId = PhotonNetwork.PhotonServerSettings.AppSettings.AppIdRealtime;
```
這樣就能實作讓玩家或是程序判定是否要連上中國區的Photon Server。
### 連線前設定NameServerHost
由於Photon獨立的中國區的Server，因此在名稱伺服器這邊也要一併修改，`NameServerHost`一般都直接宣告，但也能根據玩家或程序選擇直接在連線前修改：
```C#
PhotonNetwork.NetworkingClient.NameServerHost = "ns.exitgames.com"; // 國際
PhotonNetwork.NetworkingClient.NameServerHost = "ns.photonengine.cn"; // 中國
```
中國的連線服務需要額外向Photon申請才能使用。
### 連接名稱伺服器
完成前面的設定就能開始連線名稱伺服器
```C#
PhotonNetwork.NetworkingClient.ConnectToNameServer();
```
## 地區選擇
