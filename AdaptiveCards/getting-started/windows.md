---
title: 适用于 Windows 开发人员的自适应卡
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: c9ea788cfbc8e365cdece1cd8f42c3718b7bc3e7
ms.sourcegitcommit: 6889c7e1a38029d965c8f91dc9108819dbdea552
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/31/2019
ms.locfileid: "68733114"
---
# <a name="adaptive-cards-for-windows-developers"></a>适用于 Windows 开发人员的自适应卡



## <a name="timeline"></a>时间线

支持自适应卡的第一项 Windows 体验是时间线, 一种全新的体验是在 Windows 10 1803 中首次引入的。 

![时间线](media/windows/timeline.png)

### <a name="useractivity-api"></a>UserActivity API

[`Windows.ApplicationModel.UserActivities.UserActivity`](https://docs.microsoft.com/en-us/uwp/api/windows.applicationmodel.useractivities.useractivity) API 将活动填充到时间线。

将通过`Content`的`VisualElement`属性提供自适应卡, 如下所示:

```csharp
UserActivity userActivity = await channel.GetOrCreateUserActivityAsync(activityId, new HostName("contoso.com"));
userActivity.ActivationUri = new Uri("rss-reader:article?" + article.Link);
userActivity.DisplayText = article.Title; //used for details tile text
userActivity.VisualElements.Content = AdaptiveCardBuilder.CreateAdaptiveCardFromJson(jsonString);
await userActivity.SaveAsync();
```

### <a name="learn-more"></a>了解详细信息

版本2017中的此会话介绍了 detial 中的用户活动。

<iframe src="https://channel9.msdn.com/Events/Build/2017/B8108/player" width="960" height="540" allowFullScreen frameBorder="0"></iframe>

## <a name="other-windows-surfaces"></a>其他窗口图面
我们还没有任何内容可以共享, 但我们正在努力将自适应卡整合到更多 Windows 体验中。

## <a name="dive-in"></a>深入了解!

在本教程中, 我们只是简要介绍了这一情况, 因此请稍后查看并浏览以下链接, 以了解有关自适应卡的详细信息。

* 浏览用于灵感的[示例卡](http://adaptivecards.io/samples/)
* 使用 "[架构资源管理器](http://adaptivecards.io/explorer)" 了解可用元素
* 使用[交互式可视化工具](http://adaptivecards.io/visualizer/index.html?hostApp=Skype)构建卡片
* [联系](http://adaptivecards.io/connect)你的任何反馈
