---
title: "PUN2實作玩家自選地區進行連線"
date: 2020-03-31T15:49:25+08:00
description: "如果你不想要讓Photon直接判斷連接地區可以參考咱的研究"
draft: false
hideToc: true
enableToc: true
enableTocContent: true
author: 伊琉沙 AKA 哇咔咔
authorEmoji: 👩🏿‍🚀
tags: 
- Photon
- NameServer
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

### PUN2 相關筆記
+ 關於PUN2的設置方法參考：[PUN2 快速上手](../pun2-basic-test)
+ 關於PUN2的Realtime API參考：[PUN2 Realtime API 筆記](../pun2-realtime-api-note)
## 連線前設定
由於咱的PUN專案為了提供中國內地網友測試，所以開通了Photon的中國伺服器（中國地區的連線服務需要額外向Photon申請才能使用），由於這項功能是針對單一應用程式使用，所以為了將中國伺服器的連線納入使用，因此會有兩組appId。
### 導入Realtime的命名空間
在本次的實作中會使用到`RegionHandler`，必須在連線腳本中導入相關的命名空間。
```C#
using Photon.Realtime;
```
### 設定應用程式ID（AppId）
`AppId`一般都直接在`PhotonServerSettings`設定，無須在代碼中重新設定，除非遊戲還進行分區限制，例如開通了中國地區的伺服器，此時可以在正式連線前讓玩家進行選擇，請在調用連線方法前加入下列代碼，即可重新指定`AppId`。
```C#
// 重設 AppId
PhotonNetwork.PhotonServerSettings.AppSettings.AppIdRealtime = "replace with your own AppId";
// 初始化 AppId，這一行無論有沒有重設 AppId 都是必要的。
PhotonNetwork.NetworkingClient.AppId = PhotonNetwork.PhotonServerSettings.AppSettings.AppIdRealtime;
```
### 設定名稱伺服器（NameServerHost）
連線前必須指定名稱伺服器，請在調用連線方法前加入下列代碼：
```C#
PhotonNetwork.NetworkingClient.NameServerHost = "ns.exitgames.com";
```
若使用中國地區伺服器，名稱伺服器則為：
```C#
PhotonNetwork.NetworkingClient.NameServerHost = "ns.photonengine.cn";
```
如果不加這一段代碼，預設的`NameServerHost`會是 ***ns.exitgames.com***。
### 連接名稱伺服器
完成前面的設定後，即可透過下列代碼調用與名稱伺服器的連線。
```C#
PhotonNetwork.NetworkingClient.ConnectToNameServer();
```
此時觀察`ClientState`會變成`ConnectingToNameServer`，當連線與加密完成後會變成`ConnectedToNameServer`。
### 選擇名稱伺服器
透過遊戲介面的設計來調用不同的連線設定，即可讓玩家自行選擇名稱伺服器，參考以下範例。
```C#
public void ConnectInternationServer()
{
    PhotonNetwork.PhotonServerSettings.AppSettings.AppIdRealtime = "6799355d-d8ce-4acd-b64f-688c4a368ccf"; // TODO: replace with your own AppId
    PhotonNetwork.NetworkingClient.AppId = PhotonNetwork.PhotonServerSettings.AppSettings.AppIdRealtime;
    PhotonNetwork.NetworkingClient.NameServerHost = "ns.exitgames.com";
    PhotonNetwork.NetworkingClient.ConnectToNameServer();
}

public void ConnectChinaServer()
{
    PhotonNetwork.PhotonServerSettings.AppSettings.AppIdRealtime = "4f3da426-b335-47c1-ab69-7dd9e6578c10"; // TODO: replace with your own AppId
    PhotonNetwork.NetworkingClient.AppId = PhotonNetwork.PhotonServerSettings.AppSettings.AppIdRealtime;
    PhotonNetwork.NetworkingClient.NameServerHost = "ns.photonengine.cn";
    PhotonNetwork.NetworkingClient.ConnectToNameServer();
}
```
## 連線後設定
在連上名稱伺服器的同時會在`LoadBalancingClient`內部調用`OpGetRegions`方法取得地區列表，這個列表儲存在`RegionHandler`裡面並透過回傳方法`OnRegionListReceived`取得。
```C#
void OnRegionListReceived (RegionHandler regionHandler);
```
以下是`RegionHandler`與`Region`類的常用變數與方法：
```C#
class RegionHandler
{
    //這份列表記錄了該名稱伺服器底下的可用地區
    List<Region> EnabledRegions
    
    // 回傳ping值最低的地區
    Region BestRegion

    // 總結BestRegion與EnabledRegions的結果
    string SummaryToCache

    // 測試並找出ping值最低的地區
    bool PingMinimumOfRegions
}

class Region
{
    // 地區名稱，例如：asia,au,cae,eu,in,jp,kr,ru,rue,sa,us,usw,za
    string Code

    // 地區ping值
    int Ping 
}
```
### 測試各地區的ping值
1. 首先透過覆寫`OnRegionListReceived`取得`RegionHandler`。
2. 再調用`RegionHandler`裡面的`PingMinimumOfRegions`方法。
3. 新增一個方法`OnRegionPingCompleted`來接收回傳的`RegionHandler`，回傳方法可按需求自由命名。
```C#
public override void OnRegionListReceived(RegionHandler regionHandler)
{
    regionHandler.PingMinimumOfRegions(this.OnRegionPingCompleted, null);
}

// callback function
private void OnRegionPingCompleted(RegionHandler regionHandler){}
```
### 讀取各地區的ping值
接續上一步，從回傳的方法得到的`RegionHandler`已記錄了各地區的ping值，此時就可以讀取並顯示各地區的ping值讓玩家決定連線的地區伺服器。
```C#
private void OnRegionPingCompleted (RegionHandler regionHandler)
{
    int countRegion = regionHandler.EnabledRegions.Count;
    for (int i = 0; i < countRegion; i++)
    {
            Debug.Log (regionHandler.EnabledRegions[i].Code + ": " + 
                       regionHandler.EnabledRegions[i].Ping);
    }
    Debug.Log ("BestRegion: " + regionHandler.BestRegion);
    Debug.Log ("RegionPingSummary: " + regionHandler.SummaryToCache);
}
```
輸出結果：
```
eu: 300
us: 217
usw: 166
cae: 274
asia: 70
jp: 50
au: 177
sa: 334
in: 113
ru: 307
rue: 231
kr: 107
za: 389
BestRegion: jp[5.8.70.143:5055]: 50ms 
RegionPingSummary: jp;50;asia,au,cae,eu,in,jp,kr,ru,rue,sa,us,usw,za
```
### 選擇地區伺服器
現在玩家知道了所有地區的ping值大小，最後一步就是連上地區伺服器，此時只要在玩家選擇地區的方法中傳入地區參數`region`並調用`ConnectToRegionMaster`即可。
```C#
PhotonNetwork.NetworkingClient.ConnectToRegionMaster(region);
```
當然，如果想讓玩家直接選一個最快的伺服器可以直接在`OnRegionPingCompleted`調用`ConnectToRegionMaster`：
```C#
private void OnRegionPingCompleted (RegionHandler regionHandler)
{
    PhotonNetwork.NetworkingClient.ConnectToRegionMaster(regionHandler.BestRegion.Code);
}
```
#### 注意事項
根據經驗，使用`BestRegion`連接地區伺服器，在台灣有時候會連到`jp`或`asia`甚至`rue`三個不同的地區伺服器，而不同地區伺服器的玩家是無法共同進行遊戲的！
透過`PhotonServerSettings`設定`Fixed Region`並透過`ConnectUsingSettings`連線，可確保連線至固定的地區伺服器。