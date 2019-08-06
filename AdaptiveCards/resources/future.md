---
title: Adaptive Cards Roadmap
author: matthidinger
ms.author: mahiding
ms.date: 05/16/2018
ms.topic: article
ms.openlocfilehash: b11edbedca83bb26d2990d029a220165f68bc1ca
ms.sourcegitcommit: 6889c7e1a38029d965c8f91dc9108819dbdea552
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/31/2019
ms.locfileid: "68733089"
---
# <a name="future-work"></a>未来工作

虽然我们已经完成了定义自适应卡的出色进度, 但仍有许多工作要做。 我们希望通过 botness 等积极的开发人员社区和极佳的合作伙伴 (如松弛和 Kik), 我们可以创建一个极大的跨平台的生态系统。

## <a name="roadmap"></a>路线图

此处可以看到我们[当前的 (非最终) 路线图](https://portal.productboard.com/adaptivecards/1-adaptive-cards-portal/tabs/1-backlog)。 请注意, 此处的任何内容可能会发生更改, 并且不能保证发运。

## <a name="future-ideas"></a>未来创意

下面是我们所拥有的一些未来创意, 它们只是在集体讨论阶段。 如果对其中的任何一项感兴趣, 请在评论中告诉我们。

### <a name="great-looking-cards-from-data"></a>从数据了解更好的卡片

我们知道许多卡片作者已经在其卡后面有了明确定义的数据。 我们的计划是探索一个模板化模型, 该模型允许基于数据和定义完善且可自定义的模板的存储库生成 (服务器端或客户端) 的卡。

### <a name="make-cards-responsive"></a>使卡响应

卡片布局应对可用空间有反应。 自适应卡可适应不同的设备、ux 样式和 ui 框架, 但并不是被动的。 必须在元素上定义其他属性, 这些元素允许卡发生器为呈现库提供必要的提示, 使其能够以维持卡意图的方式智能地更改布局。

### <a name="responsive-exploration"></a>响应式浏览

* 添加**重要性**属性, 批注内容的重要性。 可以删除不太重要的内容来容纳可用空间
* 添加**约束**和**策略**属性, 描述在无法满足约束时如何做出反应。 
  * 隐藏内容或将内容折叠到较小的大小。
  * 添加一个阈值, 超过此阈值时, `columnSet`将更改列的轮播。

### <a name="new-element-types"></a>新元素类型

* 地图? -将地图嵌入到带有交互性或回退到位图的卡片
* 需要*哪些元素*？

### <a name="new-rendering-libraries"></a>新的呈现库

* 回应?
* Xamarin?
* *需要什么框架？*
