---
title: "HC12遠距無線通訊模組開發記錄 Part.1"
date: 2020-03-27T17:58:22+08:00
description: "第一天使用HC12就上手"
draft: false
hideToc: false
enableToc: true
enableTocContent: true
author: iLYuSha
authorEmoji: 👩🏿‍🚀
tags: 
- Arduino
- HC12
- 無線通訊
series:
- 密室開發
categories:
- Arduino
image: images/feature/module.svg
---
## 開發前
本次的項目是在兒童樂園I店建置大型迷宮密室，內部由大量隔間組成，每道門都配有RFID射頻識別門鎖。在遊戲設計初期（2020年1月）考慮納入計時功能來限制玩家在各關卡的挑戰時間，但尚未實際討論過實作的問題。2月中開發清單增加了`DS3231時鐘模組`（之後會補充記錄這部分的開發問題）來處理計時的功能，DS3231使用`I2C`傳輸可以提供多個Arduino在時間記錄上的參考，但隨之而來的問題是I店場域很大，I2C無法提供長距離的穩定通訊，在研究了`RS232`、`RS485`、`CAN`等有線長距離傳輸的姿勢後，在龐大的佈線壓力下（還有就是場域要連網的設備基數太多），還是決定使用無線通訊，早期也曾考慮過使用但是當時公司只有大量的便宜貨`FS1000A`與 `MX-RM-5V`，這個在前年曾經使用過，但傳輸距離頂多2米，超過2米之後傳輸的速率大幅下降，而且組成是一對發射器與接收器，顯然會大量增加連接的裝置。最終決定使用本文的主角HC12遠距無線通訊模組！
## 開發學習
簡單研究了HC12的使用與FS1000A，除了HC12收發一體之外，代碼在讀寫控制上並無太多區別，而相比I2C的通訊需要區分主從設備並在發送與接收的過程需要對答來看，HC12顯然要方便許多。

### HC12的基本設置
#### 靚照
![HC12正面](/images/post/HC12-module0.png)
![HC12背面](/images/post/HC12-module1.png)
#### 配線
配線的基本原則：
* HC12 `VCC` --- `5V`  Arduino
* HC12 `GND` --- `GND` Arduino
* HC12 `RX ` --- `TX ` Arduino
* HC12 `TX ` --- `RX`  Arduino
在本次的開發項目中，大多數的設備第10~13腳已經被RFID的`SPI`介面使用了，第5~7腳則作為蜂鳴器與繼電器的輸出，所以HC12對接的RX（接收）TX（傳送）設定為第2與第3腳，以下是代碼中的設定，使用HC12必須引入`SoftwareSerial`庫。
{{< highlight arduino >}}
#include <SoftwareSerial.h>
SoftwareSerial HC12(2, 3); // HC-12 TX Pin, HC-12 RX Pin
{{< /highlight >}}
![HC12連接圖](https://www.allaboutcircuits.com/uploads/articles/Hughes_HC12_diagram1.jpg)
參考了網上資料，在HC12的電源正負端最好配上22µF至1mF的去耦電容，而在電源正極之前串聯一顆`1N4007`二極體。
#### 安裝
![作為Server的HC12帶有一塊DS3231時鐘模組](/images/post/HC12-module2.png)
#### 測試
基本上兩塊Arduino各自配置HC12後就可以使用下面的代碼進行雙向傳輸
{{< highlight C >}}
void loop() {
  while (HC12.available()) {        // If HC-12 has data
    Serial.write(HC12.read());      // Send the data to Serial monitor
  }
  while (Serial.available()) {      // If Serial monitor has data
    HC12.write(Serial.read());      // Send that data to HC-12
  }
}
{{< /highlight >}}
### 參考來源
[基于Arduino开发板使用HC-12远程无线通信模块](https://www.yiboard.com/thread-998-1-1.html)