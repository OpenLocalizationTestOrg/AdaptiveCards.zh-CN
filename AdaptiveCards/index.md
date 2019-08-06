---
title: 自适应卡概述
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: d62bae9259a45dd828028e4f866d18fc75924b0c
ms.sourcegitcommit: 6889c7e1a38029d965c8f91dc9108819dbdea552
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/31/2019
ms.locfileid: "68733109"
---
# <a name="adaptive-cards-overview"></a><span data-ttu-id="8bbeb-102">自适应卡概述</span><span class="sxs-lookup"><span data-stu-id="8bbeb-102">Adaptive Cards Overview</span></span> 

<span data-ttu-id="8bbeb-103">自适应卡是一种开放的卡交换格式, 使开发人员能够以一种通用且一致的方式交换 UI 内容。</span><span class="sxs-lookup"><span data-stu-id="8bbeb-103">Adaptive Cards are an open card exchange format enabling developers to exchange UI content in a common and consistent way.</span></span>

<video controls width="100%" poster="./content/videoposter.png">
    <source src="https://adaptivecardsblob.blob.core.windows.net/assets/AdaptiveCardsOverviewVideo.mp4" type="video/mp4">
</video>

## <a name="how-they-work"></a><span data-ttu-id="8bbeb-104">工作原理</span><span class="sxs-lookup"><span data-stu-id="8bbeb-104">How they work</span></span>

<span data-ttu-id="8bbeb-105">[**卡片作者**](authoring-cards/getting-started.md)将其内容描述为一个简单的 JSON 对象。</span><span class="sxs-lookup"><span data-stu-id="8bbeb-105">[**Card Authors**](authoring-cards/getting-started.md) describe their content as a simple JSON object.</span></span> <span data-ttu-id="8bbeb-106">然后, 该内容可以在[**主机应用程序**](rendering-cards/getting-started.md)中以本机方式呈现, 从而自动适应主机的外观。</span><span class="sxs-lookup"><span data-stu-id="8bbeb-106">That content can then be rendered natively inside a [**Host Application**](rendering-cards/getting-started.md), automatically adapting to the look and feel of the Host.</span></span>

<span data-ttu-id="8bbeb-107">例如, Contoso 机器人可以通过 Bot 框架创作自适应卡, 并在将其传送到 Skype 后, 其外观类似于 Skype 卡。</span><span class="sxs-lookup"><span data-stu-id="8bbeb-107">For example, Contoso Bot can author an Adaptive Card through the Bot Framework, and when delivered to Skype, it will look and feel like a Skype card.</span></span> <span data-ttu-id="8bbeb-108">当将同一有效负载发送到 Microsoft 团队时, 它将类似于 Microsoft 团队。</span><span class="sxs-lookup"><span data-stu-id="8bbeb-108">When that same payload is sent to Microsoft Teams, it will look and feel like Microsoft Teams.</span></span> <span data-ttu-id="8bbeb-109">随着更多主机应用开始支持自适应卡, 相同的负载会自动在这些应用程序中亮起, 但在应用程序中也完全是本机。</span><span class="sxs-lookup"><span data-stu-id="8bbeb-109">As more host apps start to support Adaptive Cards, that same payload will automatically light up inside these applications, yet still feel entirely native to the app.</span></span>

<span data-ttu-id="8bbeb-110">用户获胜, 因为一切都非常熟悉。</span><span class="sxs-lookup"><span data-stu-id="8bbeb-110">Users win because everything feels familiar.</span></span> <span data-ttu-id="8bbeb-111">主机应用获胜, 因为它们控制用户体验。</span><span class="sxs-lookup"><span data-stu-id="8bbeb-111">Host apps win because they control the user experience.</span></span> <span data-ttu-id="8bbeb-112">和卡片作者入选, 因为他们的内容可以更广泛地传播, 无需任何其他工作。</span><span class="sxs-lookup"><span data-stu-id="8bbeb-112">And Card Authors win because their content gets broader reach without any additional work.</span></span>

## <a name="goals"></a><span data-ttu-id="8bbeb-113">目标</span><span class="sxs-lookup"><span data-stu-id="8bbeb-113">Goals</span></span> 

<span data-ttu-id="8bbeb-114">自适应卡的目标是:</span><span class="sxs-lookup"><span data-stu-id="8bbeb-114">The goals for Adaptive Cards are:</span></span>

* <span data-ttu-id="8bbeb-115">**可移植**-到任何应用、设备和 UI 框架</span><span class="sxs-lookup"><span data-stu-id="8bbeb-115">**Portable** - To any app, device, and UI framework</span></span>
* <span data-ttu-id="8bbeb-116">**开放**库和架构是开放源代码并共享</span><span class="sxs-lookup"><span data-stu-id="8bbeb-116">**Open** - Libraries and schema are open source and shared</span></span>
* <span data-ttu-id="8bbeb-117">**成本较低**-易于定义、易于使用</span><span class="sxs-lookup"><span data-stu-id="8bbeb-117">**Low cost** - Easy to define, easy to consume</span></span>
* <span data-ttu-id="8bbeb-118">可**表达**性-面向开发人员想要生成的内容的长末尾</span><span class="sxs-lookup"><span data-stu-id="8bbeb-118">**Expressive** - Targeted at the long tail of content that developers want to produce</span></span>
* <span data-ttu-id="8bbeb-119">**纯粹声明**-不需要或不允许代码</span><span class="sxs-lookup"><span data-stu-id="8bbeb-119">**Purely declarative** - No code is needed or allowed</span></span>
* <span data-ttu-id="8bbeb-120">**自动样式**-到主机应用程序 UX 和品牌准则</span><span class="sxs-lookup"><span data-stu-id="8bbeb-120">**Automatically styled** - To the Host application UX and brand guidelines</span></span>

## <a name="for-card-authors"></a><span data-ttu-id="8bbeb-121">对于卡片作者</span><span class="sxs-lookup"><span data-stu-id="8bbeb-121">For Card Authors</span></span>
<span data-ttu-id="8bbeb-122">自适应卡非常适合于卡片作者:</span><span class="sxs-lookup"><span data-stu-id="8bbeb-122">Adaptive Cards are great for card authors:</span></span>

* <span data-ttu-id="8bbeb-123">**一个架构**-您将获得一种格式, 最大限度地减少创建卡的成本, 并最大限度地提高可使用的位数。</span><span class="sxs-lookup"><span data-stu-id="8bbeb-123">**One schema** - You get a single format, minimizing the cost of creating a card and maximizing the number of places it can be used.</span></span>
* <span data-ttu-id="8bbeb-124">**更丰富的表达式**-你的内容可以更紧密地与你想要的内容对齐, 因为你有更丰富的调色板来进行绘制。</span><span class="sxs-lookup"><span data-stu-id="8bbeb-124">**Richer expression** - Your content can more closely align with want you want to say because you have a richer palette to paint with.</span></span>
* <span data-ttu-id="8bbeb-125">**广泛的覆盖**-内容可跨一组更广泛的应用程序使用, 无需了解新的架构。</span><span class="sxs-lookup"><span data-stu-id="8bbeb-125">**Broad reach** - Your content will work across a broader set of applications without you having to learn new schemas.</span></span>
* <span data-ttu-id="8bbeb-126">**输入控制**-您的卡可以包含用于从查看卡的用户那里收集信息的输入控件。</span><span class="sxs-lookup"><span data-stu-id="8bbeb-126">**Input controls** - Your card can include input controls for gathering information from the user that is viewing the card.</span></span>
* <span data-ttu-id="8bbeb-127">**更好的工具**-一种开放式卡生态系统是指由每个人共享的更好的工具。</span><span class="sxs-lookup"><span data-stu-id="8bbeb-127">**Better tooling** - An open card ecosystem means better tooling that is shared by everyone.</span></span>

## <a name="for-experience-owners"></a><span data-ttu-id="8bbeb-128">对于体验所有者</span><span class="sxs-lookup"><span data-stu-id="8bbeb-128">For Experience Owners</span></span>
<span data-ttu-id="8bbeb-129">如果你是一名需要利用第三方内容生态系统的应用开发人员, 你将喜欢自适应卡, 因为:</span><span class="sxs-lookup"><span data-stu-id="8bbeb-129">If you are an app developer who wants to tap into an ecosystem of third-party content you will love Adaptive Cards because:</span></span>

* <span data-ttu-id="8bbeb-130">**一致的用户体验**-确保为用户提供一致的体验, 因为你拥有呈现的卡片的样式。</span><span class="sxs-lookup"><span data-stu-id="8bbeb-130">**Consistent user experience** - You guarantee a consistent experience for your users, because you own the style of the rendered card.</span></span>
* <span data-ttu-id="8bbeb-131">**本机性能**-你可以获得本机性能, 因为它会直接面向你的 UI 框架。</span><span class="sxs-lookup"><span data-stu-id="8bbeb-131">**Native performance** - You get native performance as it targets your UI framework directly.</span></span>
* <span data-ttu-id="8bbeb-132">**安全**的有效负载中提供了安全内容, 因此你无需打开 UI 框架来提供原始标记和脚本。</span><span class="sxs-lookup"><span data-stu-id="8bbeb-132">**Safe** - Content is delivered in safe payloads so you don't have to open up your UI framework to raw markup and scripting.</span></span>
* <span data-ttu-id="8bbeb-133">**易于实现**-可从库中轻松地将其集成到支持的任何平台上</span><span class="sxs-lookup"><span data-stu-id="8bbeb-133">**Easy to implement** - You get off the shelf libraries to easily integrate on any platform you support</span></span> 
* <span data-ttu-id="8bbeb-134">**免费文档**-您可以节省时间, 因为您无需库存、实施和记录专用架构。</span><span class="sxs-lookup"><span data-stu-id="8bbeb-134">**Free documentation** - You save time because you don't have to invent, implement, and document a proprietary schema.</span></span>
* <span data-ttu-id="8bbeb-135">**共享工具**-您可以节省时间, 因为您无需创建自定义工具。</span><span class="sxs-lookup"><span data-stu-id="8bbeb-135">**Shared tooling** - You save time because you don't have to create custom tooling.</span></span>

## <a name="core-design-principles"></a><span data-ttu-id="8bbeb-136">核心设计原则</span><span class="sxs-lookup"><span data-stu-id="8bbeb-136">Core Design Principles</span></span> 

<span data-ttu-id="8bbeb-137">自适应卡由一组指导原则驱动, 这些[指导原则](resources/principles.md)对保持设计的跟踪十分有用。</span><span class="sxs-lookup"><span data-stu-id="8bbeb-137">Adaptive Cards are driven by a set of [guiding principles](resources/principles.md) that have been useful for keeping the design on track.</span></span> 

### <a name="semantic-instead-of-pixel-perfect"></a><span data-ttu-id="8bbeb-138">语义而不是像素-完美</span><span class="sxs-lookup"><span data-stu-id="8bbeb-138">Semantic instead of pixel-perfect</span></span>
<span data-ttu-id="8bbeb-139">与纯像素完美布局相比, 我们尽可能 striven 语义值和概念。</span><span class="sxs-lookup"><span data-stu-id="8bbeb-139">We have striven as much as possible for semantic values and concepts as opposed to pure pixel-perfect layout.</span></span> <span data-ttu-id="8bbeb-140">语义表达式的示例显示在颜色、大小和元素 (例如 FactSet 和 ImageSet) 中。</span><span class="sxs-lookup"><span data-stu-id="8bbeb-140">Examples of semantic expression show up in colors, sizes, and in elements like FactSet and ImageSet.</span></span> <span data-ttu-id="8bbeb-141">这一切都允许主机应用程序对实际的外观作出更好的决策。</span><span class="sxs-lookup"><span data-stu-id="8bbeb-141">These all allow the host application to make better decisions about the actual look and feel.</span></span>

### <a name="card-authors-own-the-content-host-app-owns-the-look-and-feel"></a><span data-ttu-id="8bbeb-142">卡作者拥有内容, 主机应用拥有外观</span><span class="sxs-lookup"><span data-stu-id="8bbeb-142">Card Authors own the content, Host App owns the look and feel</span></span>
<span data-ttu-id="8bbeb-143">卡片作者拥有他们想要表达的内容, 但显示它的应用程序在其应用程序的上下文中具有卡的外观。</span><span class="sxs-lookup"><span data-stu-id="8bbeb-143">The card authors own what they want to say, but the application displaying it owns the look and feel of the card in the context of their application.</span></span>

### <a name="keep-it-simple-but-expressive"></a><span data-ttu-id="8bbeb-144">使其保持简单, 但有意义</span><span class="sxs-lookup"><span data-stu-id="8bbeb-144">Keep it simple, but expressive</span></span>
<span data-ttu-id="8bbeb-145">我们希望自适应卡有表现力和常规用途, 但我们不想构建 UI 框架。</span><span class="sxs-lookup"><span data-stu-id="8bbeb-145">We want Adaptive Cards to be expressive and general purpose, but we don't want to build a UI framework.</span></span>  <span data-ttu-id="8bbeb-146">目标是创建一个 "有意义" 的中间层, 这与 Markdown 为文档提供足够的意义。</span><span class="sxs-lookup"><span data-stu-id="8bbeb-146">The goal is to create an intermediate layer which is "expressive enough" in the same way Markdown is expressive enough for documents.</span></span>

<span data-ttu-id="8bbeb-147">Markdown 着重于使其简单明了, 并为文档内容创建了一个简单一致的说明。</span><span class="sxs-lookup"><span data-stu-id="8bbeb-147">By focusing on keeping it simple and expressive, Markdown created an easy and consistent description of document content.</span></span>  <span data-ttu-id="8bbeb-148">同样地, 我们相信自适应卡可以创建一个简单、有意义的方式来描述卡片内容。</span><span class="sxs-lookup"><span data-stu-id="8bbeb-148">In the same way, we believe that Adaptive Cards can create a simple, expressive means of describing card content.</span></span>

### <a name="when-in-doubt-keep-it-out"></a><span data-ttu-id="8bbeb-149">如果有疑问, 请将它</span><span class="sxs-lookup"><span data-stu-id="8bbeb-149">When in doubt, keep it out</span></span>
<span data-ttu-id="8bbeb-150">稍后添加会更容易, 但会出现错误。</span><span class="sxs-lookup"><span data-stu-id="8bbeb-150">It is easier to add later then it is to live with a mistake.</span></span> <span data-ttu-id="8bbeb-151">如果我们找到了自己的讨论, 无论是否应添加内容, 我们都选择将其关闭。使用我们不需要支持的旧版本, 通常可以更轻松地添加属性。</span><span class="sxs-lookup"><span data-stu-id="8bbeb-151">If we found ourselves debating whether we should add something or not, we opted to leave it out.  It is always easier to add a property than to live with a legacy we wish we didn't have to support.</span></span>


## <a name="build-2018-session"></a><span data-ttu-id="8bbeb-152">生成2018会话</span><span class="sxs-lookup"><span data-stu-id="8bbeb-152">Build 2018 Session</span></span>

<span data-ttu-id="8bbeb-153">以下在版本2018中的会话展示了机器人、Cortana、Outlook 和 Windows 中的自适应卡。</span><span class="sxs-lookup"><span data-stu-id="8bbeb-153">The following session at Build 2018 showcases Adaptive Cards in Bots, Cortana, Outlook, and Windows.</span></span> 

<iframe src="https://medius.studios.ms/Embed/Video/BRK2401?SFYT=true" width="960" height="540" allowFullScreen frameBorder="0"></iframe>
