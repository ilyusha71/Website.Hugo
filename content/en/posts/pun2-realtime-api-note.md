---
title: "PUN2 Realtime API 筆記"
date: 2020-03-31T13:16:55+08:00
description: "如果想自行設計遊戲登入的方法與遊戲大廳就看下去吧！"
draft: false
hideToc: true
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
image: https://blog.photonengine.com/wp-content/uploads/2013/10/x_unitynetworking.jpg
---
### 實作環境
+ Unity2018.3.0f2
+ PUN 2.17
+ Photon lib 4.1.3.0

如果還沒加入PUN2可以參考上一篇，[PUN2 快速上手](../pun2-test)
## API
### Photon.Realtime API
#### Connect()
```C#
public virtual bool Connect()
{
    this.DisconnectedCause = DisconnectCause.None;

    #if UNITY_WEBGL
    SocketWebTcp.SerializationProtocol = Enum.GetName(typeof(SerializationProtocol), this.LoadBalancingPeer.SerializationProtocolType);
    #endif

    if (this.LoadBalancingPeer.Connect(this.MasterServerAddress, this.AppId, this.TokenForInit))
    {
        this.State = ClientState.ConnectingToMasterServer;
        return true;
    }

    #if UNITY_XBOXONE
    if (this.AuthValues == null || this.AuthValues.AuthType != CustomAuthenticationType.Xbox)
    {
        UnityEngine.Debug.LogError("UNITY_XBOXONE builds must set AuthValues.AuthType to \"CustomAuthenticationType.Xbox\". Set this before calling any Connect method. Connect failed!");
        return false;
    }
    #endif

    return false;
}
```
`Connect`可以直接連到主伺服器（MasterServer），調用此方法前必須先設定`AppId`與`MasterServerAddress`，如果使用Photon Cloud則應該使用[`ConnectToRegionMaster`](#connecttoregionmaster)。

```C#
PhotonNetwork.NetworkingClient.Connect();
```
#### ConnectToNameServer()
```C#
public bool ConnectToNameServer()
{
    this.IsUsingNameServer = true;
    this.CloudRegion = null;

    #if UNITY_WEBGL
    SocketWebTcp.SerializationProtocol = Enum.GetName(typeof(SerializationProtocol), this.LoadBalancingPeer.SerializationProtocolType);
    #endif

    if (this.AuthMode == AuthModeOption.AuthOnceWss)
    {
        this.ExpectedProtocol = this.LoadBalancingPeer.TransportProtocol;
        this.LoadBalancingPeer.TransportProtocol = ConnectionProtocol.WebSocketSecure;
    }

    if (!this.LoadBalancingPeer.Connect(this.NameServerAddress, "NameServer", this.TokenForInit))
    {
        return false;
    }

    this.State = ClientState.ConnectingToNameServer;
    return true;
}
```
`ConnectToNameServer`可以直接連到名稱伺服器，調用此方法前必須先設定`AppId`與`NameServerHost`。
##### 實作
```C#
// 自定義連線方法
void ConnectToServer()
{
    PhotonNetwork.NetworkingClient.AppId = PhotonNetwork.PhotonServerSettings.AppSettings.AppIdRealtime;
    PhotonNetwork.NetworkingClient.NameServerHost = "ns.photonengine.cn"; // 如果不指定，預設會是 ns.exitgames.com
    PhotonNetwork.NetworkingClient.ConnectToNameServer();
}
```
執行後，PUN會開始連線（`StatusCode.Connect`）並建立加密（`StatusCode.EncryptionEstablished`）。
```C#
virtual void OnStatusChanged (StatusCode statusCode)
```
從內部狀態方法可發現，在加密完成後，會調用<mark>OpGetRegions</mark>方法取得名稱伺服器下的地區列表，這份列表儲存在`RegionHandler`類裡面。
```C#
private bool OpGetRegions ()
{
    if (!this.CheckIfOpCanBeSent (OperationCode.GetRegions, this.Server, "GetRegions"))
    {
        return false;
    }

    bool sent = this.LoadBalancingPeer.OpGetRegions (this.AppId);
    return sent;
}
```
最後由`OnRegionListReceived`接收回傳的RegionHandler。
```C# OnRegionListReceived (RegionHandler regionHandler)
public void OnRegionListReceived (RegionHandler regionHandler)
{
    this.UpdateCallbackTargets ();

    foreach (IConnectionCallbacks target in this)
    {
        target.OnRegionListReceived (regionHandler);
    }
}
```
#### ConnectToRegionMaster()
```C#
public bool ConnectToRegionMaster(string region)
{
    this.IsUsingNameServer = true;

    if (this.State == ClientState.ConnectedToNameServer)
    {
        this.CloudRegion = region;
        return this.CallAuthenticate();
    }

    this.LoadBalancingPeer.Disconnect();
    this.CloudRegion = region;

    #if UNITY_WEBGL
    SocketWebTcp.SerializationProtocol = Enum.GetName(typeof(SerializationProtocol), this.LoadBalancingPeer.SerializationProtocolType);
    #endif

    if (this.AuthMode == AuthModeOption.AuthOnceWss)
    {
        this.ExpectedProtocol = this.LoadBalancingPeer.TransportProtocol;
        this.LoadBalancingPeer.TransportProtocol = ConnectionProtocol.WebSocketSecure;
    }

    if (!this.LoadBalancingPeer.Connect(this.NameServerAddress, "NameServer", null))
    {
        return false;
    }

    this.State = ClientState.ConnectingToNameServer;
    return true;
}
```
`ConnectToRegionMaster`可透過`region`參數，連到指定地區的伺服器，調用此方法前必須先設定`AppId`與`NameServerHost`。
##### 實作
```C#
// 自定義連線方法
void ConnectToServer()
{
    string region = "asia"; // 指定地區
    PhotonNetwork.NetworkingClient.AppId = PhotonNetwork.PhotonServerSettings.AppSettings.AppIdRealtime;
    PhotonNetwork.NetworkingClient.NameServerHost = "ns.photonengine.cn"; // 如果不指定，預設會是 ns.exitgames.com
    PhotonNetwork.NetworkingClient.ConnectToRegionMaster(region);
}
```