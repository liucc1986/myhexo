title: "ios系统中html5游戏声音切换问题 audio"
date: 2014-09-15 00:10:37
tags: [html5游戏,audio,ios]
categories: javascript
description: 在iphone手机中使用audio播放声音如何在无人为事件的情况下自动切换声音
toc: true

---
我现在又这样一个需求，游戏中需要播放背景音乐，游戏结束需要，停止背景音乐并播放“你死了”的声音，事实是游戏结束时背景音乐停止了，但是“你死了”声音没有播放。
###需求：在iphone手机中使用audio播放声音如何在无人为事件的情况下自动切换声音
据扯：**iOS Safari 中的 HTML5 媒体元素都是单例的，所以一次只能播放一个 HTML5 音频（和 HTML5 视频）流（估计是为了减少数据费用）。**

**探索：**
事实是：创建另一个audio，让丫播放，以为他会覆盖掉当前的audio，事实是没有，没有声音，很安静。
好吧，换一个思路，既然是一个单例audio，咱就只用一个单例，换声音的时候，`audio.src='other.mp3`'；`audio.play()`;仍然不灵。于是我想到了，是不是还没来得及load？一定是。

    audio.src='other.mp3'；audio.load()；audio.play();
咿~响了。

**办法：**

于是每次咱切换声音的时候就`audio.src='some.mp3'；audio.load()；audio.play()`;（如果需要循环，就加loop）
那么问题来了：挖掘机。。sorry。如果在游戏中想播放点击音效咋办？h5游戏声音的问题这才是一小丢丢欲知如何，下回分解。
