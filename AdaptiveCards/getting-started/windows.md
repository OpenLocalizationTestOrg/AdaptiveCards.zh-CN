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
# <a name="adaptive-cards-for-windows-developers"></a><span data-ttu-id="897d5-102">适用于 Windows 开发人员的自适应卡</span><span class="sxs-lookup"><span data-stu-id="897d5-102">Adaptive Cards for Windows Developers</span></span>



## <a name="timeline"></a><span data-ttu-id="897d5-103">时间线</span><span class="sxs-lookup"><span data-stu-id="897d5-103">Timeline</span></span>

<span data-ttu-id="897d5-104">支持自适应卡的第一项 Windows 体验是时间线, 一种全新的体验是在 Windows 10 1803 中首次引入的。</span><span class="sxs-lookup"><span data-stu-id="897d5-104">The first Windows experience to supports Adaptive Cards is Timeline, a brand new experience first introduced in Windows 10 1803.</span></span> 

![时间线](media/windows/timeline.png)

### <a name="useractivity-api"></a><span data-ttu-id="897d5-106">UserActivity API</span><span class="sxs-lookup"><span data-stu-id="897d5-106">UserActivity API</span></span>

<span data-ttu-id="897d5-107">[`Windows.ApplicationModel.UserActivities.UserActivity`](https://docs.microsoft.com/en-us/uwp/api/windows.applicationmodel.useractivities.useractivity) API 将活动填充到时间线。</span><span class="sxs-lookup"><span data-stu-id="897d5-107">The [`Windows.ApplicationModel.UserActivities.UserActivity`](https://docs.microsoft.com/en-us/uwp/api/windows.applicationmodel.useractivities.useractivity) API is what populates an Activity into Timeline.</span></span>

<span data-ttu-id="897d5-108">将通过`Content`的`VisualElement`属性提供自适应卡, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="897d5-108">The Adaptive Card will be supplied via the `Content` property of `VisualElement`, as seen below:</span></span>

```csharp
UserActivity userActivity = await channel.GetOrCreateUserActivityAsync(activityId, new HostName("contoso.com"));
userActivity.ActivationUri = new Uri("rss-reader:article?" + article.Link);
userActivity.DisplayText = article.Title; //used for details tile text
userActivity.VisualElements.Content = AdaptiveCardBuilder.CreateAdaptiveCardFromJson(jsonString);
await userActivity.SaveAsync();
```

### <a name="learn-more"></a><span data-ttu-id="897d5-109">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="897d5-109">Learn more</span></span>

<span data-ttu-id="897d5-110">版本2017中的此会话介绍了 detial 中的用户活动。</span><span class="sxs-lookup"><span data-stu-id="897d5-110">This session at Build 2017 covers User Activities in detial.</span></span>

<iframe src="https://channel9.msdn.com/Events/Build/2017/B8108/player" width="960" height="540" allowFullScreen frameBorder="0"></iframe>

## <a name="other-windows-surfaces"></a><span data-ttu-id="897d5-111">其他窗口图面</span><span class="sxs-lookup"><span data-stu-id="897d5-111">Other Windows Surfaces</span></span>
<span data-ttu-id="897d5-112">我们还没有任何内容可以共享, 但我们正在努力将自适应卡整合到更多 Windows 体验中。</span><span class="sxs-lookup"><span data-stu-id="897d5-112">We don't have anything to share just yet, but we're working on incorporating Adaptive Cards into more Windows experiences.</span></span>

## <a name="dive-in"></a><span data-ttu-id="897d5-113">深入了解!</span><span class="sxs-lookup"><span data-stu-id="897d5-113">Dive in!</span></span>

<span data-ttu-id="897d5-114">在本教程中, 我们只是简要介绍了这一情况, 因此请稍后查看并浏览以下链接, 以了解有关自适应卡的详细信息。</span><span class="sxs-lookup"><span data-stu-id="897d5-114">We've barely scratched the surface in this tutorial, so check back soon and browse the links below to explore more about Adaptive Cards.</span></span>

* <span data-ttu-id="897d5-115">浏览用于灵感的[示例卡](http://adaptivecards.io/samples/)</span><span class="sxs-lookup"><span data-stu-id="897d5-115">[Browse Sample cards](http://adaptivecards.io/samples/) for inspiration</span></span>
* <span data-ttu-id="897d5-116">使用 "[架构资源管理器](http://adaptivecards.io/explorer)" 了解可用元素</span><span class="sxs-lookup"><span data-stu-id="897d5-116">Use the [Schema Explorer](http://adaptivecards.io/explorer) to learn the available elements</span></span>
* <span data-ttu-id="897d5-117">使用[交互式可视化工具](http://adaptivecards.io/visualizer/index.html?hostApp=Skype)构建卡片</span><span class="sxs-lookup"><span data-stu-id="897d5-117">Build a card using the [Interactive Visualizer](http://adaptivecards.io/visualizer/index.html?hostApp=Skype)</span></span>
* <span data-ttu-id="897d5-118">[联系](http://adaptivecards.io/connect)你的任何反馈</span><span class="sxs-lookup"><span data-stu-id="897d5-118">[Get in touch](http://adaptivecards.io/connect) with any feedback you have</span></span>
