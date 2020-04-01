---
title: "讓Unity的Timeline支援TextMeshPro進行文本變化"
date: 2020-04-01T15:56:54+08:00
description: "手把手改寫Playable讓Timeline支援TextMeshPro進行文本變化"
draft: false
hideToc: true
enableToc: true
enableTocContent: true
author: 伊琉沙 AKA 哇咔咔
authorEmoji: 👩🏿‍🚀
tags: 
- Playable
- Timeline
- TextMeshPro
series:
- 遊戲開發
categories:
- Unity
image: https://blog.photonengine.com/wp-content/uploads/2013/10/x_unitynetworking.jpg
---
17年在台灣參加Unity工作坊的一個項目——<mark>Hover Race</mark>，曾使用preview版本的`TMP`，記得當時可以直接把TMP Text拖到Timeline就能建立TMP的Track與Clip，並直接建立文本變換。最近有個項目需要使用這個功能，多年沒碰Timeline（DoTween使用慣了就懶）發現這個功能消失了，看到知乎的這篇[Timeline中让你事半功倍的工具链](https://zhuanlan.zhihu.com/p/98630673)才知道有些功能被整合自獨立的Asset了，於是重新研究了一下，並再次實現這個功能。
如果你的專題也有Timeline變換TMP文本的需求就看下去，同時也能一同學習客製化`Playable`。
![TMP Text Switcher Track](/images/post/HoverRace_TMP.png)

### 開發環境
+ Unity 2018.4.20f1
+ TextMesh Pro 1.4.1

## 下載Default Playables
先到Asset Store下載最新版的[`Default Playables`](https://assetstore.unity.com/packages/essentials/default-playables-95266)，這是Unity官方自行整合的Playable功能包。
![Text Switcher Track](/images/post/TextSwitcherTrack.png)
導入後刷新Timeline窗口，可以發現增加了一堆功能，而我們要使用的文本轉換也有，可惜地是只支援UGUI Text，不過可以在Asset中的DefaultPlayables中找到`Text Switcher Track`功能的源代碼，看起來只要將裡面的UGUI Text全部換成TMP Text就能實作TMP Text Switcher Track。

## 實作TMP Text Switcher Track
![Text Switcher Track Folder](/images/post/TextSwitcherTrack_Folder.png)
在DefaultPlayables的TextSwitcher目錄中包含五個腳本，以下直接複製一份TextSwitcher到根目錄改名為<mark>TMPTextSwitcher</mark>。
接下來就要改裡面的代碼。

### TMPTextSwitcherBehaviour
在`TMPTextSwitcherBehaviour.cs`中只要改類名稱即可。
這部分是實作TMP Text能被修改的變量，有需求可自行增加。
```C#
[Serializable]
public class TMPTextSwitcherBehaviour : PlayableBehaviour
{
    public Color color = Color.white;
    public int fontSize = 14;
    public string text;
}
```
### TMPSwitcherDrawer
在Editor資料夾下的`TMPSwitcherDrawer.cs`主要是描繪Inspector的顯示界面，內容對應`TMPTextSwitcherBehaviour`中需要修改的變量，需要修改的地方有兩處：
+ CustomPropertyDrawer標籤的指定型別
```C#
[CustomPropertyDrawer(typeof(TMPTextSwitcherBehaviour))]
```
+ 類名稱
```C#
public class TMPSwitcherDrawer : PropertyDrawer
{
    ...
}
```
### TMPTextSwitcherClip
`TMPTextSwitcherClip.cs`的修改有三處：
+ 類名稱
```C#
[Serializable]
public class TMPTextSwitcherClip : PlayableAsset, ITimelineClipAsset
{
    ...
}
```
+ template的宣告與初始
```C#
public class TMPTextSwitcherClip : PlayableAsset, ITimelineClipAsset
{
    public TMPTextSwitcherBehaviour template = new TMPTextSwitcherBehaviour ();
    ...
}
```
+ playable的建立方法
```C#
public class TMPTextSwitcherClip : PlayableAsset, ITimelineClipAsset
{
    ...
    public override Playable CreatePlayable (PlayableGraph graph, GameObject owner)
    {
        var playable = ScriptPlayable<TMPTextSwitcherBehaviour>.Create (graph, template);
        return playable;
    }
}
```
### TMPTextSwitcherMixerBehaviour
+ 類名稱
```C#
public class TMPTextSwitcherMixerBehaviour : PlayableBehaviour
{
    ...
}
```
+ inputPlayable的宣告與初始化
+ input的宣告
```C#
    public override void ProcessFrame(Playable playable, FrameData info, object playerData)
    {
        ...
        for (int i = 0; i < inputCount; i++)
        {
            ...
            ScriptPlayable<TMPTextSwitcherBehaviour> inputPlayable = (ScriptPlayable<TMPTextSwitcherBehaviour>)playable.GetInput(i);
            TMPTextSwitcherBehaviour input = inputPlayable.GetBehaviour ();
            ...
        }
        ...
    }
```
+ 引入`TMPro`
+ m_DefaultFontSize的型別改為`float`
+ m_TrackBinding的型別改為`TextMeshProUGUI`
```C#
// using UnityEngine.UI;
using TMPro;

public class TMPTextSwitcherMixerBehaviour : PlayableBehaviour
{
    ...
    float m_DefaultFontSize;
    ...
    TextMeshProUGUI m_TrackBinding;
    ...

    public override void ProcessFrame(Playable playable, FrameData info, object playerData)
    {
        m_TrackBinding = playerData as TextMeshProUGUI;
        ...
    }
}
```
### TextSwitcherTrack
`TextSwitcherTrack.cs`
+ 引入TMPro
+ TrackClipType標籤的指定型別為`TMPTextSwitcherClip`
+ TrackBindingType標籤的指定型別為`TextMeshProUGUI`
+ 類名稱
```C#
// using UnityEngine.UI;
using TMPro;

[TrackClipType(typeof(TMPTextSwitcherClip))]
[TrackBindingType(typeof(TextMeshProUGUI))]
public class TMPTextSwitcherTrack : TrackAsset
{
    ...
}
```
+ CreateTrackMixerde的建立方法
```C#
public class TMPTextSwitcherTrack : TrackAsset
{
    public override Playable CreateTrackMixer(PlayableGraph graph, GameObject go, int inputCount)
    {
        return ScriptPlayable<TMPTextSwitcherMixerBehaviour>.Create (graph, inputCount);
    }
    ...
}
```
+ trackBinding的型別修改為`TextMeshProUGUI`
+ driver.AddFromName方法的型別
```C#
public class TMPTextSwitcherTrack : TrackAsset
{
    ...
    public override void GatherProperties (PlayableDirector director, IPropertyCollector driver)
    {
#if UNITY_EDITOR
        TextMeshProUGUI trackBinding = director.GetGenericBinding(this) as TextMeshProUGUI;
        ...
        while (iterator.NextVisible(true))
        {
            ...
            driver.AddFromName<TextMeshProUGUI>(trackBinding.gameObject, iterator.propertyPath);
        }
#endif
        ...
    }
}
```