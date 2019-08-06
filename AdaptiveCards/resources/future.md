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
# <a name="future-work"></a><span data-ttu-id="1a5a0-102">未来工作</span><span class="sxs-lookup"><span data-stu-id="1a5a0-102">Future work</span></span>

<span data-ttu-id="1a5a0-103">虽然我们已经完成了定义自适应卡的出色进度, 但仍有许多工作要做。</span><span class="sxs-lookup"><span data-stu-id="1a5a0-103">While we have made excellent progress defining adaptive cards, there is still lots of work to do.</span></span> <span data-ttu-id="1a5a0-104">我们希望通过 botness 等积极的开发人员社区和极佳的合作伙伴 (如松弛和 Kik), 我们可以创建一个极大的跨平台的生态系统。</span><span class="sxs-lookup"><span data-stu-id="1a5a0-104">Our hope is that through active developer communities like botness, and great partners like Slack and Kik, we can create a great ecosystem of cross-platform cards.</span></span>

## <a name="roadmap"></a><span data-ttu-id="1a5a0-105">路线图</span><span class="sxs-lookup"><span data-stu-id="1a5a0-105">Roadmap</span></span>

<span data-ttu-id="1a5a0-106">此处可以看到我们[当前的 (非最终) 路线图](https://portal.productboard.com/adaptivecards/1-adaptive-cards-portal/tabs/1-backlog)。</span><span class="sxs-lookup"><span data-stu-id="1a5a0-106">You can see our [current (non-final) roadmap here](https://portal.productboard.com/adaptivecards/1-adaptive-cards-portal/tabs/1-backlog).</span></span> <span data-ttu-id="1a5a0-107">请注意, 此处的任何内容可能会发生更改, 并且不能保证发运。</span><span class="sxs-lookup"><span data-stu-id="1a5a0-107">Note that anything on here is subject to change, and is not a guarantee of shipping.</span></span>

## <a name="future-ideas"></a><span data-ttu-id="1a5a0-108">未来创意</span><span class="sxs-lookup"><span data-stu-id="1a5a0-108">Future ideas</span></span>

<span data-ttu-id="1a5a0-109">下面是我们所拥有的一些未来创意, 它们只是在集体讨论阶段。</span><span class="sxs-lookup"><span data-stu-id="1a5a0-109">The following are some future ideas we have, which are simply in the brainstorm stage.</span></span> <span data-ttu-id="1a5a0-110">如果对其中的任何一项感兴趣, 请在评论中告诉我们。</span><span class="sxs-lookup"><span data-stu-id="1a5a0-110">If you're interested in any of these, let us know in a comment.</span></span>

### <a name="great-looking-cards-from-data"></a><span data-ttu-id="1a5a0-111">从数据了解更好的卡片</span><span class="sxs-lookup"><span data-stu-id="1a5a0-111">Great looking Cards from Data</span></span>

<span data-ttu-id="1a5a0-112">我们知道许多卡片作者已经在其卡后面有了明确定义的数据。</span><span class="sxs-lookup"><span data-stu-id="1a5a0-112">We know many card authors already have well-defined data behind their cards.</span></span> <span data-ttu-id="1a5a0-113">我们的计划是探索一个模板化模型, 该模型允许基于数据和定义完善且可自定义的模板的存储库生成 (服务器端或客户端) 的卡。</span><span class="sxs-lookup"><span data-stu-id="1a5a0-113">Our plan is to explore a templating model that would allow cards to be generated (server side or client side) based on the data and a repository of well-defined and customizable templates.</span></span>

### <a name="make-cards-responsive"></a><span data-ttu-id="1a5a0-114">使卡响应</span><span class="sxs-lookup"><span data-stu-id="1a5a0-114">Make cards responsive</span></span>

<span data-ttu-id="1a5a0-115">卡片布局应对可用空间有反应。</span><span class="sxs-lookup"><span data-stu-id="1a5a0-115">Card layouts should be reactive to available space.</span></span> <span data-ttu-id="1a5a0-116">自适应卡可适应不同的设备、ux 样式和 ui 框架, 但并不是被动的。</span><span class="sxs-lookup"><span data-stu-id="1a5a0-116">Adaptive cards are adaptable to different devices, ux styles and and ui frameworks, but they are not reactive yet.</span></span> <span data-ttu-id="1a5a0-117">必须在元素上定义其他属性, 这些元素允许卡发生器为呈现库提供必要的提示, 使其能够以维持卡意图的方式智能地更改布局。</span><span class="sxs-lookup"><span data-stu-id="1a5a0-117">Additional properties must be defined on elements which allow card producers to provide the necessary hints to the rendering libraries so that they can intelligently change the layout in a way which maintains the intent of the card.</span></span>

### <a name="responsive-exploration"></a><span data-ttu-id="1a5a0-118">响应式浏览</span><span class="sxs-lookup"><span data-stu-id="1a5a0-118">Responsive exploration</span></span>

* <span data-ttu-id="1a5a0-119">添加**重要性**属性, 批注内容的重要性。</span><span class="sxs-lookup"><span data-stu-id="1a5a0-119">Add an **importance** property which annotates importance of content.</span></span> <span data-ttu-id="1a5a0-120">可以删除不太重要的内容来容纳可用空间</span><span class="sxs-lookup"><span data-stu-id="1a5a0-120">Less important content can be dropped to fit available space</span></span>
* <span data-ttu-id="1a5a0-121">添加**约束**和**策略**属性, 描述在无法满足约束时如何做出反应。</span><span class="sxs-lookup"><span data-stu-id="1a5a0-121">Add **constraints** and **policy** properties describing how to react when constraints can't be met.</span></span> 
  * <span data-ttu-id="1a5a0-122">隐藏内容或将内容折叠到较小的大小。</span><span class="sxs-lookup"><span data-stu-id="1a5a0-122">Hide content or collapse content to smaller size.</span></span>
  * <span data-ttu-id="1a5a0-123">添加一个阈值, 超过此阈值时, `columnSet`将更改列的轮播。</span><span class="sxs-lookup"><span data-stu-id="1a5a0-123">Add a threshold that, when exceeded, changes `columnSet` to carousel of columns.</span></span>

### <a name="new-element-types"></a><span data-ttu-id="1a5a0-124">新元素类型</span><span class="sxs-lookup"><span data-stu-id="1a5a0-124">New element types</span></span>

* <span data-ttu-id="1a5a0-125">地图?</span><span class="sxs-lookup"><span data-stu-id="1a5a0-125">Maps?</span></span> <span data-ttu-id="1a5a0-126">-将地图嵌入到带有交互性或回退到位图的卡片</span><span class="sxs-lookup"><span data-stu-id="1a5a0-126">- embed a map into a card with interactivity or fallback to bitmap</span></span>
* <span data-ttu-id="1a5a0-127">需要*哪些元素*？</span><span class="sxs-lookup"><span data-stu-id="1a5a0-127">*What elements do you want or need*?</span></span>

### <a name="new-rendering-libraries"></a><span data-ttu-id="1a5a0-128">新的呈现库</span><span class="sxs-lookup"><span data-stu-id="1a5a0-128">New rendering libraries</span></span>

* <span data-ttu-id="1a5a0-129">回应?</span><span class="sxs-lookup"><span data-stu-id="1a5a0-129">React?</span></span>
* <span data-ttu-id="1a5a0-130">Xamarin?</span><span class="sxs-lookup"><span data-stu-id="1a5a0-130">Xamarin?</span></span>
* <span data-ttu-id="1a5a0-131">*需要什么框架？*</span><span class="sxs-lookup"><span data-stu-id="1a5a0-131">*What frameworks do you want?*</span></span>
