---
title: "【哆啦A夢牧場物語】MOD安裝方法"
date: 2020-04-02T22:33:33+08:00
description: "手把手教你安裝MOD"
draft: false
hideToc: false
enableToc: false
enableTocContent: true
author: 伊琉沙 AKA 哇咔咔
authorEmoji: 👩🏿‍🚀
tags: 
series:
- 哆啦A夢牧場物語
categories:
- 哆啦A夢
image: https://mod.3dmgame.com/static/upload/game/210s.png
---
## MOD
本篇參考MOD製作者 <u>***a_nderw***</u> 的解說：[如何让大雄加载mod](https://bbs.3dmgame.com/thread-5971864-1-1.html)
以下MOD均來自[3DM](https://www.3dmgame.com/)。
哆啦A夢牧場物語的MOD主要有三種類型，安裝方法並不相同也不能直接替換dll檔。
### 遊戲安裝目錄
Steam版的哆啦A夢牧場物語安裝目錄應該會是在Steam安裝目錄下的這個位置：
`Steam\steamapps\common\DORAEMON STORY OF SEASONS`
### 第一類MOD：整合的Assembly-CSharp.dll
使用Unity開發的遊戲都會有`Assembly-CSharp.dll`這個檔案，通常是放在遊戲目錄下的這個位置：
`DORaEMON STORY OF SEASONS_Data\Managed`
若MOD是`Assembly-CSharp.dll`，表示MOD本身的功能已經重新編譯在裡面，直接替換掉遊戲安裝目錄下的檔案即可。

需要使用這個方法的MOD有：
+ [《哆啦A梦：大雄的牧场物语》作物品质上升速度提高MOD](https://dl.3dmgame.com/patch/146727.html) by <u>***nethunter***</u>

### 第二類MOD：單獨的.dll檔
使用這類的MOD需先下載 <u>***zealot180***</u> 開發的MOD支持補丁[《哆啦A梦：大雄的牧场物语》游戏MOD支持补丁](https://dl.3dmgame.com/patch/147023.html)，複製補丁裡面的`Assembly-CSharp.dll`與`0Harmony.dll`，再到遊戲目錄的`DORaEMON STORY OF SEASONS_Data\Managed`覆蓋掉原來的`Assembly-CSharp.dll`，以及`0Harmony.dll`，建議操作前進行備份。

需要使用這個方法的MOD有：
+ [《哆啦A梦：大雄的牧场物语》快速钓鱼MOD](https://dl.3dmgame.com/patch/146725.html) by <u>***zealot180***</u>
+ [《哆啦A梦：大雄的牧场物语》矿场下层洞口固定点刷新MOD](https://dl.3dmgame.com/patch/146726.html) by <u>***weitianhan***</u>
+ [《哆啦A梦：大雄的牧场物语》镰刀收割作物MOD](https://dl.3dmgame.com/patch/146736.html) by <u>***weitianhan***</u>
+ [《哆啦A梦：大雄的牧场物语》大型十页存货箱MOD](https://dl.3dmgame.com/patch/146738.html) by <u>***zealot180***</u>
    + StorageTableCount，不再為了爆倉爆冰箱而煩惱。。。
+ [《哆啦A梦：大雄的牧场物语》在家看帐本MOD](https://dl.3dmgame.com/patch/146740.html) by <u>***zealot180***</u>
+ [《哆啦A梦：大雄的牧场物语》NPC无限送礼物MOD](https://dl.3dmgame.com/patch/146744.html) by <u>***zealot180***</u>
    + InfiniteReceivePresent，測試與實驗遊戲數據方便。
+ [《哆啦A梦：大雄的牧场物语》动物可以无限喂零食MOD](https://dl.3dmgame.com/patch/146745.html) by <u>***zealot180***</u>
    + InfiniteSnack，測試方便。
+ [《哆啦A梦：大雄的牧场物语》作物5星收获MOD](https://dl.3dmgame.com/patch/146746.html) by <u>***zealot180***</u>
+ [《哆啦A梦：大雄的牧场物语》体力消耗减半MOD](https://dl.3dmgame.com/patch/146750.html) by <u>***a_nderw***</u>
+ [《哆啦A梦：大雄的牧场物语》移动速度加快MOD](https://dl.3dmgame.com/patch/146752.html) by <u>***a_nderw***</u>
+ [《哆啦A梦：大雄的牧场物语》半夜睡觉无体力惩罚MOD](https://dl.3dmgame.com/patch/146754.html) by <u>***a_nderw***</u>
+ [《哆啦A梦：大雄的牧场物语》超级午睡MOD](https://dl.3dmgame.com/patch/146755.html) by <u>***a_nderw***</u>
+ [《哆啦A梦：大雄的牧场物语》时间变慢MOD](https://dl.3dmgame.com/patch/146757.html) by <u>***a_nderw***</u>
+ [《哆啦A梦：大雄的牧场物语》建筑一日完工MOD](https://dl.3dmgame.com/patch/147021.html) by <u>***ialger***</u>
+ [《哆啦A梦：大雄的牧场物语》铁匠商铺出售宝石MOD](https://dl.3dmgame.com/patch/147022.html) by <u>***zealot180***</u>
    + AddMineralShopItem，遊戲中後期推薦使用，這樣遊戲前期可以把不需要的高級礦石直接賣錢。
+ [《哆啦A梦：大雄的牧场物语》安静的大雄MOD](https://dl.3dmgame.com/patch/147026.html) by <u>***a_nderw***</u>
+ [《哆啦A梦：大雄的牧场物语》晚上放牧不会降好感MOD](https://dl.3dmgame.com/patch/147126.html) by  <u>***a_nderw***</u>
+ [《哆啦A梦：大雄的牧场物语》无损种植收获MOD](https://dl.3dmgame.com/patch/147127.html) by <u>***a_nderw***</u>
+ [《哆啦A梦：大雄的牧场物语》5倍破坏力MOD](https://dl.3dmgame.com/patch/147130.html) by <u>***a_nderw***</u>
+ [《哆啦A梦：大雄的牧场物语》床上三件套MOD](https://dl.3dmgame.com/patch/147133.html) by <u>***a_nderw***</u>
    + supperBedAccount，在家查賬，測試的時候很方便。
    + supperBedAffiche，等同於在家上網看電子公佈欄。
    + supperBedPictureBook，快速查看圖鑒。
+ [《哆啦A梦：大雄的牧场物语》物品堆叠上限提高MOD](https://dl.3dmgame.com/patch/147135.html) by <u>***a_nderw***</u>
    + stackEX.dll，必裝MOD，囤積材料破百不煩惱
    + 第三類MOD也有同功能MOD
+ [《哆啦A梦：大雄的牧场物语》作物不会枯萎MOD](https://dl.3dmgame.com/patch/147137.html) by <u>***a_nderw***</u>
+ [《哆啦A梦：大雄的牧场物语》家具摆放MOD](https://dl.3dmgame.com/patch/147524.html) by <u>***a_nderw***</u>
+ [《哆啦A梦：大雄的牧场物语》A梦帮忙做农活MOD](https://dl.3dmgame.com/patch/147525.html) by <u>***zealot180***</u>
    + DoCropWork，後期大面積栽種這個會很有幫助。
+ [《哆啦A梦：大雄的牧场物语》消除屏幕白边MOD](https://dl.3dmgame.com/patch/147527.html) by <u>***a_nderw***</u>
+ [《哆啦A梦：大雄的牧场物语》快速下矿MOD](https://dl.3dmgame.com/patch/147530.html) by <u>***没有翅膀的白鸽***</u>
+ [《哆啦A梦：大雄的牧场物语》动物对话显示压力MOD](https://dl.3dmgame.com/patch/148185.html) by  <u>***a_nderw***</u>
    + talkMessageShowStress，測試與實驗使用，正常玩遊戲沒差太多。
+ [《哆啦A梦：大雄的牧场物语》放牧强化MOD](https://dl.3dmgame.com/patch/148186.html) by <u>***a_nderw***</u>

### 第三類MOD：壓縮檔帶有dll檔與json文件
這類MOD需下載[Unity Mod 管理工具(Unity Mod Manager) 0.21.2汉化版](https://mod.3dmgame.com/mod/44550)，打開`UnityModManager.exe`（注意不要去更新），選擇`哆啦A梦：大雄的牧场物语`然後選擇遊戲的安裝目錄，按下`Install`，會在遊戲目錄的根目錄新增一個`Mods`的資料夾，把所有要裝的Mod的資料夾放進去即可，又或是直接把解壓縮檔拉進Unity Mode 管理器的Mod也行，注意！由於Mod的資料夾是簡體字，使用繁體電腦透過管理器生成的Mod資料夾會變成亂碼哦！

需要使用這個方法的補丁有：

+ [游戏时间流逝的更慢](https://mod.3dmgame.com/mod/146126) by <u>***a_nderw***</u>
+ [提高物品的堆叠上限](https://mod.3dmgame.com/mod/146127) by <u>***a_nderw***</u>
+ [隐藏屏幕四周的白边](https://mod.3dmgame.com/mod/146130) by <u>***a_nderw***</u>
+ [界面直接显示出体力](https://mod.3dmgame.com/mod/146195) by <u>***a_nderw***</u>
    + 與第二類MOD同時使用會產生衝突，進入遊戲後會花屏。
+ [让桌子有特殊的功能](https://mod.3dmgame.com/mod/146196) by <u>***a_nderw***</u>
    + 與第二類MOD同時使用會產生衝突，無法激活。
+ [可以保存自定义键位](https://mod.3dmgame.com/mod/146197) by <u>***a_nderw***</u>
    + 解決官方始終不修復的Bug
+ [减少钓鱼的等待时间](https://mod.3dmgame.com/mod/146203) by <u>***a_nderw***</u>
+ [用双击快速存取物品](https://mod.3dmgame.com/mod/146222) by <u>***a_nderw***</u>
+ [午睡回复更多的体力](https://mod.3dmgame.com/mod/146238) by <u>***a_nderw***</u>