---
title: 地面MOD
date: 2020-05-01T17:25:02+08:00
description: 地面MOD
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

# 地面MOD
## 地面介面
+ 地面介面：`IGround @020001DD`
+ 繼承類：
    + 耕作地面介面：`CultivatedGround @020001C6`
        + 剷平命令：<br>`GroundFlattenCommand.GroundFlattenCommand(GroundModel, Action, Action<GroundModel, int, Type>) : void @0600152F`
        + 剷平命令：<br>
        + 剷平命令：<br>
        + 剷平命令：<br>
        + 剷平命令：<br>
        + 剷平命令：<br>
        + 剷平命令：<br>
        + 剷平命令：<br>
    + 礦床地面介面：`DepositGround @020001C7`
        + 挖掘命令類：`GroundMineCommand @020001D6`
        + 下樓命令類：`GroundGoDownstairsCommand @020001D2`
        + 上樓命令類：`GroundGoUpstairsCommand @020001D3`
    + 拔草命令類：
    + 平坦地面介面：`FlatGround @020001C8`
    + 拔草命令類：
    + 障礙地面介面：`ObstacleGround @020001DE`
    + 拔草命令類：
    + 雜草地面介面：`WeedyGround @020001DF`
        + 拔草命令：<br>`GroundGetWeedCommand.GroundGetWeedCommand(GroundModel, Action) : void @06001539`
        + 割草命令：<br>`GroundMowWeedCommand.GroundMowWeedCommand(GroundModel, Action, Action<GroundModel, int, Type>) : void @06001577`

## 礦床地面介面
+ 礦床地面介面：`DepositGround @020001C7`

### 砍伐命令類
+ 砍斷樹枝命令

### 挖掘命令類
+ 挖掘命令類：`GroundMineCommand @020001D6`
    + 蓄力挖掘方法：`GroundMineCommand.ExecuteAtCharging(int, bool, out ResponseModel) : bool @06001561`

#### 

#### 蓄力挖掘方法
```C#
protected override bool ExecuteAtCharging(int charge_num, bool is_executing_at_once, out ResponseModel response)
{
    response = null;
    this.mAdditionalActions = null;
    if (!this.IsValid())
    {
        return false;
    }
    SingletonMonoBehaviour<UserManager>.Instance.User.ConsumeStaminaInUsingTool(charge_num);
    if (!this.CanBreak())
    {
        response = new ResponseModel(SingletonMonoBehaviour<MasterManager>.Instance.TextMaster.GetText(Text.Command.ID_5007_0001));
        return false;
    }
    int num = (SingletonMonoBehaviour<UserManager>.Instance.User.Inventory.GetItemInHand().Tool.Power < Mine.MAX_POWER) ? (charge_num * 2) : Mine.MAX_DAMAGE;
    if (SingletonMonoBehaviour<UserManager>.Instance.User.GetUsingGadget(1104040) != null)
    {
        int usingGradeupLiquidItemID = Item.GetUsingGradeupLiquidItemID(SingletonMonoBehaviour<UserManager>.Instance.User.Inventory.GetItemInHand().Id);
        if (usingGradeupLiquidItemID != -1)
        {
            num = ((new ItemModel(usingGradeupLiquidItemID).Tool.Power < Mine.MAX_POWER) ? (charge_num * 2) : Mine.MAX_DAMAGE);
        }
    }
    if (num == 0)
    {
        num = 1;
    }
    if (!this.mGround.TryMine(num))
    {
        return true;
    }
    UsingGadgetModel usingGadget = SingletonMonoBehaviour<UserManager>.Instance.User.GetUsingGadget(1104050);
    if (this.mGround.Id != SingletonMonoBehaviour<UserManager>.Instance.User.CurrentMap.HoleIndex && usingGadget != null)
    {
        MineFloorMasterModel mineFloor = SingletonMonoBehaviour<MasterManager>.Instance.MineMaster.GetMineFloor(Mine.GOOD_LUCK_MOON_MINE_FLOOR);
        this.mGround.ReLotteryOreItem(mineFloor);
    }
    this.PlayEffect(Effect.Id.DepositBroken);
    if (this.mGround.Id == SingletonMonoBehaviour<UserManager>.Instance.User.CurrentMap.HoleIndex)
    {
        this.mGround.MakeHole();
    }
    else if (this.mGround.OreItemId != -1)
    {
        this.mAdditionalActions = new ActionModel[]
        {
            new ActionModel(Define.Action.Id.BagIn, this.mGround.OreItemId, true, UnitNodeHolder.TypeEnum.Bag_Item_loc)
        };
        SingletonMonoBehaviour<UserManager>.Instance.User.Inventory.TryAddItem(this.mGround.OreItemId, 1, 1, -1);
        ItemMasterModel item = SingletonMonoBehaviour<MasterManager>.Instance.ItemMaster.GetItem(this.mGround.OreItemId);
        if (item != null)
        {
            response = new ResponseModel(string.Format(SingletonMonoBehaviour<MasterManager>.Instance.TextMaster.GetText(Text.Command.ID_5030_0001), SingletonMonoBehaviour<MasterManager>.Instance.TextMaster.GetText(item.NameId)));
            response.SetItemId(this.mGround.OreItemId);
        }
    }
    if (this.mUpdatedCallback != null)
    {
        this.mUpdatedCallback();
    }
    return true;
}
```



### 下樓命令類
+ 下樓命令類：`GroundGoDownstairsCommand @020001D2`

### 上樓命令類
+ 上樓命令類：`GroundGoUpstairsCommand @020001D3`

## 整地命令類
+ 整地命令類：`GroundFlattenCommand @020001D0`

## 耕地命令類
+ 耕地命令類：`GroundCultivateCommand @020001CE`

## 播種命令類
+ 播種命令類：`GroundSowSeedCommand @020001DA`

## 施肥命令類
+ 施肥命令類：`GroundFertilizeCommand @020001CF`

## 澆水命令類
+ 澆水命令類： `GroundWetCommand @020001DC`

## 成長命令類
+ 成長命令類：`GroundGrowCommand @020001D4`

## 割草命令類
+ 割草命令類：`GroundMowCropCommand @020001D7`

## 收割命令類
+ 收割命令類：`GroundReapCropCommand @020001D9`

## 收成命令類
+ 收成命令類：`GroundHarvestCropCommand @020001D5`

# 定義
## 土地類
+ 土地類：`Ground @0200045E`
    + [取得礦床HP方法](../doraemon-story-mod-ground/#取得礦床HP方法)
    + [取得礦床硬度方法](../doraemon-story-mod-ground/#取得礦床硬度方法)
    + [取得蓄力範圍方法](../doraemon-story-mod-ground/#取得蓄力範圍方法)
    + [類型轉換介面類型方法](../doraemon-story-mod-ground/#類型轉換介面類型方法)
    + [礦床HP表](../doraemon-story-mod-ground/#礦床HP表)
    + [礦床硬度表](../doraemon-story-mod-ground/#礦床硬度表)
    + [一段蓄力範圍](../doraemon-story-mod-ground/#一段蓄力範圍)
    + [二段蓄力範圍](../doraemon-story-mod-ground/#二段蓄力範圍)
    + [三段蓄力範圍](../doraemon-story-mod-ground/#三段蓄力範圍)
    + [類型枚舉](../doraemon-story-mod-ground/#類型枚舉)
    + [介面類型枚舉](../doraemon-story-mod-ground/#介面類型枚舉)

### 取得礦床HP方法
+ `Define.Ground.GetDepositHP(Ground.TypeEnum) : int @060028FE`

```C#
public static int GetDepositHP(Ground.TypeEnum type)
{
    return Ground.DepositHPTable.GetValue((int)type, 0);
}
```
### 取得礦床硬度方法
+ `Define.Ground.GetDepositPowerLimit(Ground.TypeEnum) : int @060028FF`

```C#
public static int GetDepositPowerLimit(Ground.TypeEnum type)
{
    return Ground.DepositPowerLimitTable.GetValue((int)type, 0);
}
```
### 取得蓄力範圍方法
+ `Define.Ground.GetRange(int) : Vector3[] @06002900`

```C#
public static Vector3[] GetRange(int charge_num)
{
    if (charge_num == 1)
    {
        return Ground.CHARGE_RANGE_1;
    }
    if (charge_num == 2)
    {
        return Ground.CHARGE_RANGE_2;
    }
    if (charge_num != 3)
    {
        return null;
    }
    return Ground.CHARGE_RANGE_3;
}
```
### 類型轉換介面類型方法
+ `Define.Ground.TypeToInterfaceType(Ground.TypeEnum) : Ground.InterfaceTypeEnum @06002902`

```C#
public static Ground.InterfaceTypeEnum TypeToInterfaceType(Ground.TypeEnum type)
{
    switch (type)
    {
    case Ground.TypeEnum.Flat:
        return Ground.InterfaceTypeEnum.Flat;
    case Ground.TypeEnum.Cultivated:
    case Ground.TypeEnum.Wet:
        return Ground.InterfaceTypeEnum.Cultivated;
    case Ground.TypeEnum.Weedy:
        return Ground.InterfaceTypeEnum.Weedy;
    case Ground.TypeEnum.Obstacle:
        return Ground.InterfaceTypeEnum.Obstacle;
    case Ground.TypeEnum.SoftDeposit:
    case Ground.TypeEnum.HardDeposit:
    case Ground.TypeEnum.BlackDeposit:
    case Ground.TypeEnum.MinedDeposit:
    case Ground.TypeEnum.Hole:
    case Ground.TypeEnum.Rope:
        return Ground.InterfaceTypeEnum.Deposit;
    }
    return Ground.InterfaceTypeEnum.None;
}
```
### 礦床HP表
+ `Define.Ground.DepositHPTable : Dictionary<int, int> @04001DCC`

```C#
private static readonly Dictionary<int, int> DepositHPTable = new Dictionary<int, int>
{
    {
        5,
        1
    },
    {
        6,
        2
    },
    {
        7,
        4
    }
};
```
### 礦床硬度表
+ `Define.Ground.DepositPowerLimitTable : Dictionary<int, int> @04001DCD`

```C#
private static readonly Dictionary<int, int> DepositPowerLimitTable = new Dictionary<int, int>
{
    {
        5,
        1
    },
    {
        6,
        2
    },
    {
        7,
        3
    }
};
```
### 一段蓄力範圍
+ `Define.Ground.CHARGE_RANGE_1 : Vector3[] @04001DCE`

```C#
private static readonly Vector3[] CHARGE_RANGE_1 = new Vector3[]
{
    new Vector3(0f, 0f, 1f)
};
```
### 二段蓄力範圍
+ `Define.Ground.CHARGE_RANGE_2 : Vector3[] @04001DCF`

```C#
private static readonly Vector3[] CHARGE_RANGE_2 = new Vector3[]
{
    new Vector3(0f, 0f, 1f),
    new Vector3(0f, 0f, 2f)
};
```
### 三段蓄力範圍
+ `Define.Ground.CHARGE_RANGE_3 : Vector3[] @04001DD0`

```C#
private static readonly Vector3[] CHARGE_RANGE_3 = new Vector3[]
{
    new Vector3(0f, 0f, 1f),
    new Vector3(0f, 0f, 2f),
    new Vector3(-1f, 0f, 0f),
    new Vector3(-1f, 0f, 1f),
    new Vector3(-1f, 0f, 2f),
    new Vector3(1f, 0f, 0f),
    new Vector3(1f, 0f, 1f),
    new Vector3(1f, 0f, 2f)
};
```
### 類型枚舉
+ `TypeEnum @0200045F`

```C#
public enum TypeEnum
{
    // Token: 0x04001DD2 RID: 7634
    Flat,
    // Token: 0x04001DD3 RID: 7635
    Cultivated,
    // Token: 0x04001DD4 RID: 7636
    Wet,
    // Token: 0x04001DD5 RID: 7637
    Weedy,
    // Token: 0x04001DD6 RID: 7638
    Obstacle,
    // Token: 0x04001DD7 RID: 7639
    SoftDeposit,
    // Token: 0x04001DD8 RID: 7640
    HardDeposit,
    // Token: 0x04001DD9 RID: 7641
    BlackDeposit,
    // Token: 0x04001DDA RID: 7642
    MinedDeposit,
    // Token: 0x04001DDB RID: 7643
    Hole,
    // Token: 0x04001DDC RID: 7644
    Rope,
    // Token: 0x04001DDD RID: 7645
    Filled,
    // Token: 0x04001DDE RID: 7646
    MiniGameHole,
    // Token: 0x04001DDF RID: 7647
    Length,
    // Token: 0x04001DE0 RID: 7648
    None = -1
}
```
### 介面類型枚舉
+ `InterfaceTypeEnum @02000460`

```C#
public enum InterfaceTypeEnum
{
    // Token: 0x04001DE2 RID: 7650
    Flat,
    // Token: 0x04001DE3 RID: 7651
    Cultivated,
    // Token: 0x04001DE4 RID: 7652
    Weedy,
    // Token: 0x04001DE5 RID: 7653
    Obstacle,
    // Token: 0x04001DE6 RID: 7654
    Deposit,
    // Token: 0x04001DE7 RID: 7655
    Length,
    // Token: 0x04001DE8 RID: 7656
    None = -1
}
```
# 未分類相關
## 使用者模板類
+ 使用者模板類：`UserModel @020005C2`
    + [使用工具體力消耗方法](../doraemon-story-mod-ground/#使用工具體力消耗方法)：`UserModel.ConsumeStaminaInUsingTool(int) : void @06003345`

### 使用工具體力消耗方法
```C#
public void ConsumeStaminaInUsingTool(int charge_num = 0)
{
    ItemModel itemInHand = this.Inventory.GetItemInHand();
    if (itemInHand == null || itemInHand.Tool == null)
    {
        return;
    }
    this.Player.Stamina.Consume(itemInHand.Tool.StaminaConsumption + charge_num);
}
```