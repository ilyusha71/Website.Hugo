---
title: "在Windows使用Hugo在Github架設網站"
date: 2020-03-30T00:08:15+08:00
description: "速成架站與經驗整理"
draft: false
hideToc: false
enableToc: true
enableTocContent: true
author: 伊琉沙 AKA 哇咔咔
authorEmoji: 👩🏿‍🚀
tags: 
- hugo
series:
categories:
image: images/feature/github.svg
---
注意！以下內容均在Win 10環境下操作，其他作業系統的操作方式並不相同。
## 安裝Chocolatey
Chocolatey是Windows下的軟件管理器，很多軟件都能直接安裝。
在Win 10安裝Chocolatey有兩種方式：
### 使用Powershell安裝
在Win 10左下角的搜尋輸入`powershell`就能找到Windows PowerShell。
記得以<mark>系統管理員身份</mark>執行。
```powershell
Set-ExecutionPolicy Bypass -Scope Process -Force; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
```
### 使用命令提示字元 / 命令提示符
在Win 10左下角的搜尋輸入`cmd`打開命令提示字元。
記得以<mark>系統管理員身份</mark>執行。
```bat
@"%SystemRoot%\System32\WindowsPowerShell\v1.0\powershell.exe" -NoProfile -InputFormat None -ExecutionPolicy Bypass -Command "iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))" && SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin"
```
## 安裝Git與Hugo
安裝完Chocolatey之後，接下來的安裝就很方便，直接重新開啟PowerShell，輸入：
```powershell
choco install git.install
```
```powershell
choco install hugo
```
有些較為複雜的Hugo主題會使用`Sass/SCSS`，此時必須要再安裝Hugo的擴展。
```powershell
choco install hugo-extended
```
## Hugo建立網站
通過`cd`指令到你要建站的目錄，然後輸入：
```powershell
hugo new site <你的網站名稱>
```
### 安裝主題
進到網站根目錄，在[Hugo Theme](https://themes.gohugo.io/)挑選喜歡的主題，不同主題安裝方法略有差異。
基本設置如下：
```powershell
git init
git submodule add <主題網址.git> themes/<主題名稱>
```
## 主題設置與測試
關於設置主題的部分，每個主題都有自己的一套配置方法，詳見各主題的網站與github。以下為大多數主題的基本設置：
+ 進入`theme/主題資料夾/exampleSite`（不是所有主題都有`exampleSite`這個資料夾）
+ 在`exampleSite`找到`config.toml`複製一份至根目錄。
+ 為方便測試，可以把`content`資料夾也複製到根目錄。
### 進階設置
部分主題需要到`theme/主題資料夾`複製`Static`與`Layout`的內容或整個資料夾至根目錄才能正常顯示。
### 測試
透過下面的指令會啟動本地端的網站，在網址列輸入`localhost:1313/`即可預覽。
```powershell
hugo server
// 若之後的修改要完全刷新預覽可以改成
hugo server --disableFastRender
```
## 網站發佈到Github
### 網站發佈
透過指令下面的指令會生成一個`public`的資料夾，這個資料夾就是要發佈到Github的內容。
```powershell
hugo
```
網站發佈前要先把`config.toml`的`baseURL`與`manifest.json`的`start_url`換成Github使用的網址，確保網站的各項參數能關聯到正確的地址。
## Push到Github
先移動到`public`資料夾，輸入指令：
```powershell
git init
git add .
git commit -m "init"
git push origin master
```