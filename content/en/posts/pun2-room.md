---
title: "PUN2實作玩家遊戲大廳與房間"
date: 2020-04-07T11:59:45+08:00
description: ""
draft: false
hideToc: false
enableToc: false
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
image: https://blog.photonengine.com/wp-content/uploads/2013/10/x_unitynetworking.jpg
---
### 實作環境
+ Unity2018.3.0f2
+ PUN 2.17
+ Photon lib 4.1.3.0
+ Photon Cloud Realtime App

## 遊戲大廳
延續前篇[PUN2實作玩家自選地區進行連線](../pun2-nameserver-region)，當成功進入地區伺服器後也就等同進入到該區域的遊戲大廳，此時在遊戲大廳之後的動作都只有這個地區伺服器的玩家能響應，大廳的各項功能方法都是`PhotonNetwork`類下面的靜態方法：

+ [建立房間](#建立房間)
+ [加入房間](#加入房間)

而相關的回傳方法在`IPunCallbacks`

### 建立房間
在PUN2中建立房間是非常簡單的事，根據`CreateRoom`的API有下列三種多載方法：
+ `CreateRoom (string roomName)`
+ `CreateRoom (string roomName, RoomOptions roomOptions, TypedLobby typedLobby)`
+ `CreateRoom (string roomName, RoomOptions roomOptions, TypedLobby typedLobby, string[] expectedUsers)`

傳入的基本參數
+ `roomName`：房間名稱
+ `roomOptions`：房間選項
+ `typedLobby`：大廳參數，房間建立的所屬大廳
+ `expectedUsers`：預期用戶，房間會保留位置給這個列表的玩家

回傳方法：
+ `OpCreateRoom`
    + 成功：
        + `OnCreatedRoom()`
        + `OnJoinedRoom()`
    + 失敗：
        + `OnCreateRoomFailed(short returnCode, string message)`

### 加入房間
加入房間的方法分為三種類型：
+ [加入房間](#加入房間)
+ [加入房間或建立房間](#加入房間或建立房間)
+ [加入隨機房間](#加入隨機房間)

#### 加入房間
+ `JoinRoom	(string roomName)`
+ `JoinRoom (string roomName, string[] expectedUsers)`

傳入的基本參數
+ `roomName`：房間名稱
+ `expectedUsers`：預期用戶，房間會保留位置給這個列表的玩家

回傳方法：
+ `OpJoinRoom`
    + 成功：
        + `OnJoinedRoom()`
    + 失敗：
        + `OnJoinRoomFailed(short returnCode, string message)`

#### 加入房間或建立房間
+ `JoinOrCreateRoom (string roomName, RoomOptions roomOptions, TypedLobby typedLobby)`
+ `JoinOrCreateRoom (string roomName, RoomOptions roomOptions, TypedLobby typedLobby, string[] expectedUsers)`

傳入的基本參數
+ `roomName`：房間名稱
+ `roomOptions`：房間選項
+ `typedLobby`：大廳參數，房間建立的所屬大廳
+ `expectedUsers`：預期用戶，房間會保留位置給這個列表的玩家

回傳方法：
+ `OpJoinRoom`
    + 成功：
        + `OnJoinedRoom()`
    + 失敗：
        + `OnJoinRoomFailed(short returnCode, string message);`
+ `OpJoinRoom`
    + 成功：
        + `OnJoinedRoom()`
    + 失敗：
        + `OnJoinRoomFailed(short returnCode, string message);`

#### 加入隨機房間
+ `JoinRandomRoom ()`
+ `JoinRandomRoom (Hashtable expectedCustomRoomProperties, byte expectedMaxPlayers)`
+ `JoinRandomRoom (Hashtable expectedCustomRoomProperties, byte expectedMaxPlayers, MatchmakingMode matchingType, TypedLobby typedLobby, string sqlLobbyFilter, string[] expectedUsers = null)`

前兩類的方法差別在於當玩家加入房間失敗時，`JoinRoom`會回傳`OnPhotonJoinRoomFailed`，而JoinOrCreateRoom會根據參數調用`CreateRoom`方法

