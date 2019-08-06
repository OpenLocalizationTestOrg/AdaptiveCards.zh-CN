---
title: 动机和原则
author: matthidinger
ms.author: mahiding
ms.date: 5/14/2018
ms.topic: article
ms.openlocfilehash: 243ad63fc585c5afc3fa396b86ff6261e8a7ee93
ms.sourcegitcommit: 6889c7e1a38029d965c8f91dc9108819dbdea552
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/31/2019
ms.locfileid: "68732559"
---
# <a name="motivations-and-principles"></a><span data-ttu-id="3ba90-102">动机和原则</span><span class="sxs-lookup"><span data-stu-id="3ba90-102">Motivations and Principles</span></span>

<span data-ttu-id="3ba90-103">下面是一个动机和原则, govering 自适应卡格式的演变。</span><span class="sxs-lookup"><span data-stu-id="3ba90-103">Below are the motivations and principles govering the evolution of the Adaptive Card format.</span></span>

## <a name="motivations-behind-the-format"></a><span data-ttu-id="3ba90-104">格式后面的动机</span><span class="sxs-lookup"><span data-stu-id="3ba90-104">Motivations behind the format</span></span>

<span data-ttu-id="3ba90-105">在早期的2016中, Microsoft (包括 Outlook、Windows 和机器人框架) 的几个团队都需要实现非常类似 ("卡"), 并且每个团队单独设计自己的解决方案:</span><span class="sxs-lookup"><span data-stu-id="3ba90-105">In early 2016, several teams at Microsoft (including Outlook, Windows and the Bot Framework) came to the realization that they all wanted something extremely similar ("cards") and that each of them were designing their own solutions independently:</span></span>

- <span data-ttu-id="3ba90-106">Windows 具有其自己的动态磁贴和通知格式</span><span class="sxs-lookup"><span data-stu-id="3ba90-106">Windows had its own Live Tiles and Notifications format</span></span>
-  <span data-ttu-id="3ba90-107">机器人框架使用一组预定义的卡模板, 开发人员可以在发送机器人消息时进行选择</span><span class="sxs-lookup"><span data-stu-id="3ba90-107">The Bot framework was using a set of predefined card templates developers could choose from when sending Bot messages</span></span>
- <span data-ttu-id="3ba90-108">Outlook 使用自己的 MessageCard 格式来提供其可操作消息功能</span><span class="sxs-lookup"><span data-stu-id="3ba90-108">Outlook was using its own MessageCard format for its Actionable Messages feature</span></span>

<span data-ttu-id="3ba90-109">同时, 其他平台 (如 LINE、FaceBook Messenger、时差等) 定义了其自己的专有 "卡" 格式。</span><span class="sxs-lookup"><span data-stu-id="3ba90-109">At the same time, other platforms such as LINE, FaceBook Messenger, Slack and more were defining their own, proprietary "card" format.</span></span> <span data-ttu-id="3ba90-110">因此, 一些 Microsoft 员工会收集并开始努力定义一种单一的开放式卡片格式和一组 Sdk, 其中包含:</span><span class="sxs-lookup"><span data-stu-id="3ba90-110">So a few Microsoft employees gathered up and started an effort to define a single, open card format and a set of SDKs that:</span></span>

- <span data-ttu-id="3ba90-111">有助于交换主机之间的卡</span><span class="sxs-lookup"><span data-stu-id="3ba90-111">Would facilitate the interchange of cards between hosts</span></span>
- <span data-ttu-id="3ba90-112">允许每个主机控制卡的样式, 以确保视觉对象的一致性</span><span class="sxs-lookup"><span data-stu-id="3ba90-112">Would allow each host to keep control over the styling of cards to ensure visual consistency</span></span>
- <span data-ttu-id="3ba90-113">利用可随时使用的 Sdk, 主机应用程序可以轻松地通过最少工作量显示卡</span><span class="sxs-lookup"><span data-stu-id="3ba90-113">Would make it easy for a host application to display cards with minimum effort via ready-to-use SDKs</span></span>
- <span data-ttu-id="3ba90-114">这也会向第三方提供价值, 并最终被业界广泛采用</span><span class="sxs-lookup"><span data-stu-id="3ba90-114">And that would also provide value to third parties and eventually get adopted widely by the industry</span></span>

## <a name="principles-governing-adaptive-cards"></a><span data-ttu-id="3ba90-115">管理自适应卡的原则</span><span class="sxs-lookup"><span data-stu-id="3ba90-115">Principles governing Adaptive Cards</span></span>

1.  <span data-ttu-id="3ba90-116">**自适应卡是一种_简单_的_声明_卡格式**</span><span class="sxs-lookup"><span data-stu-id="3ba90-116">**Adaptive Card is a _simple_ and _declarative_ card format**</span></span>

    1.  <span data-ttu-id="3ba90-117">它不表示为 HTML 或 XAML 替换/替代</span><span class="sxs-lookup"><span data-stu-id="3ba90-117">It is not meant as an HTML or XAML replacement/alternative</span></span>
    2.  <span data-ttu-id="3ba90-118">自适应卡**没有 "代码隐藏"**</span><span class="sxs-lookup"><span data-stu-id="3ba90-118">There is **no "code behind"** with Adaptive Cards</span></span>
        1. <span data-ttu-id="3ba90-119">卡作者无法在其有效负载中嵌入自定义/任意代码, 因此, 自适应卡主机永远不需要运行第三方代码</span><span class="sxs-lookup"><span data-stu-id="3ba90-119">Card authors cannot embed custom/arbitrary code with their payloads, and as a result an Adaptive Card host never needs to run third party code</span></span>
        2. <span data-ttu-id="3ba90-120">动态性和交互性只通过声明性标记实现</span><span class="sxs-lookup"><span data-stu-id="3ba90-120">Dynamism and interactivity are achieved solely via declarative markup</span></span>
    3.  <span data-ttu-id="3ba90-121">这可确保为新平台构建自适应卡 SDK 所需的工作量保持合理</span><span class="sxs-lookup"><span data-stu-id="3ba90-121">This ensures that the effort necessary to build an Adaptive Card SDK for a new platform remains reasonable</span></span>

2.  <span data-ttu-id="3ba90-122">**自适应卡格式不能对任何特定底层技术施加使用**</span><span class="sxs-lookup"><span data-stu-id="3ba90-122">**The Adaptive Card format can't impose the use of any particular underlying technology**</span></span>

    1.  <span data-ttu-id="3ba90-123">自适应卡格式不依赖于 JavaScript、 C#、Python 或任何其他语言</span><span class="sxs-lookup"><span data-stu-id="3ba90-123">The Adaptive Card format does not rely on JavaScript, C#, Python or any other language</span></span>
    2.  <span data-ttu-id="3ba90-124">同样, 它不依赖于 HTML 或 XAML 或任何其他图形/UI 框架</span><span class="sxs-lookup"><span data-stu-id="3ba90-124">Similarly it doesn't rely on HTML or XAML or any other graphic/UI framework</span></span>
    3.  <span data-ttu-id="3ba90-125">这样一来, 只要存在呈现器, 就可以在任何平台上以本机方式呈现自适应卡</span><span class="sxs-lookup"><span data-stu-id="3ba90-125">This way, Adaptive Cards can be rendered natively on any platform for as long as a renderer exists</span></span>

3.  <span data-ttu-id="3ba90-126">**自适应卡格式是_共享属性_**</span><span class="sxs-lookup"><span data-stu-id="3ba90-126">**The Adaptive Card format is a _shared property_**</span></span>

    1.  <span data-ttu-id="3ba90-127">除了其 Sdk, 格式是开放源代码及其发展社区</span><span class="sxs-lookup"><span data-stu-id="3ba90-127">Along with its SDKs, the format is to be open source and its evolution community driven</span></span>
    2.  <span data-ttu-id="3ba90-128">因此, 格式不属于任何一个团队或不由任何团队驱动</span><span class="sxs-lookup"><span data-stu-id="3ba90-128">The format is therefore not owned nor driven by any one team</span></span>

4.  <span data-ttu-id="3ba90-129">**自适应卡格式并未设计为 "仅供 Microsoft 使用"**</span><span class="sxs-lookup"><span data-stu-id="3ba90-129">**The Adaptive Card format is not designed "just for Microsoft's use"**</span></span>

    1.  <span data-ttu-id="3ba90-130">而是设计为满足各种应用程序和用例的需求</span><span class="sxs-lookup"><span data-stu-id="3ba90-130">Instead it is designed to suit the needs of a wide variety of applications and use cases</span></span>

5.  <span data-ttu-id="3ba90-131">**_自适应卡工作组_控制格式的演变**</span><span class="sxs-lookup"><span data-stu-id="3ba90-131">**The _Adaptive Card Working Group_ governs the evolution of the format**</span></span>

    1.  <span data-ttu-id="3ba90-132">此工作组由一组 Microsoft 员工组成, 这些员工都非常深入地涉及格式的成功</span><span class="sxs-lookup"><span data-stu-id="3ba90-132">This working group is comprised of a set of Microsoft employees that are all deeply involved in the success of the format</span></span>
    2.  <span data-ttu-id="3ba90-133">工作小组在查看功能提议的过程中执行每周会议 (当前在星期一), 讨论并会审了开放式问题, 并跟踪 vNext 工作项的总体进度</span><span class="sxs-lookup"><span data-stu-id="3ba90-133">The Working Group conducts weekly meetings (currently on Monday) during which feature proposals are reviewed, open issues are discussed and triaged and overall progress on vNext work items is tracked</span></span>
    3.  <span data-ttu-id="3ba90-134">工作小组使用来自大型社区的反馈 (包括内部 Microsoft 团队) 来决定如何演变格式</span><span class="sxs-lookup"><span data-stu-id="3ba90-134">The Working Group uses feedback from the community at large, including internal Microsoft teams, to decide how the format evolves</span></span>
        1. <span data-ttu-id="3ba90-135">任何人都可以通过打开 GitHub 中的问题加入工作组 (请参阅下文)</span><span class="sxs-lookup"><span data-stu-id="3ba90-135">Anyone can participate in the working group through opening issues in GitHub (see below)</span></span>
        2. <span data-ttu-id="3ba90-136">在自适应卡框架的实际使用中以实际方式使用的问题/功能请求 (作为主机或卡片作者) 对该格式的未来的影响最大。</span><span class="sxs-lookup"><span data-stu-id="3ba90-136">Issues/feature requests rooted in actual usage of the Adaptive Cards framework (either as a host or as a card author) have the most impact on the future of the format</span></span>
    4.  <span data-ttu-id="3ba90-137">若要通过工作组获得批准, 建议的新功能:</span><span class="sxs-lookup"><span data-stu-id="3ba90-137">To be approved by the Working Group, proposed new features:</span></span>
        1. <span data-ttu-id="3ba90-138">必须由真实用例进行调整</span><span class="sxs-lookup"><span data-stu-id="3ba90-138">Must be justified by real life use cases</span></span>
        2. <span data-ttu-id="3ba90-139">必须具有功能规范</span><span class="sxs-lookup"><span data-stu-id="3ba90-139">Must have a functional specification</span></span>
    5.  <span data-ttu-id="3ba90-140">已批准的新功能已添加到积压工作 (backlog) 并被视为 vNext</span><span class="sxs-lookup"><span data-stu-id="3ba90-140">Approved new feature are added to the backlog and considered for vNext</span></span>
        1. <span data-ttu-id="3ba90-141">用于设置新功能优先级的条件包括功能实现的各种方案, 其复杂性/可维护性和更多</span><span class="sxs-lookup"><span data-stu-id="3ba90-141">The criteria used to prioritize new features include the breadth of scenarios the feature enables, its complexity/maintainability and more</span></span>
        2. <span data-ttu-id="3ba90-142">如果有疑问, 请随时了解!</span><span class="sxs-lookup"><span data-stu-id="3ba90-142">When in doubt, keep it out!</span></span> <span data-ttu-id="3ba90-143">更容易引入一个设计良好的功能, 而不是经常使用错误。</span><span class="sxs-lookup"><span data-stu-id="3ba90-143">It's a lot easier to introduce a well designed feature later than to live with a mistake forever.</span></span>
    6.  <span data-ttu-id="3ba90-144">所有新功能都在所有支持的 Sdk 中实现</span><span class="sxs-lookup"><span data-stu-id="3ba90-144">All new features are implemented in all supported SDKs</span></span>
    7.  <span data-ttu-id="3ba90-145">所有新功能都已记录并与 samples 文件夹中发布的测试卡相关联</span><span class="sxs-lookup"><span data-stu-id="3ba90-145">All new features are documented and associated with a test card published in the samples folder</span></span>
    8.  <span data-ttu-id="3ba90-146">新版本的格式和 Sdk 经过 beta 阶段</span><span class="sxs-lookup"><span data-stu-id="3ba90-146">New versions of the format and SDKs go through a beta phase</span></span>
    9.  <span data-ttu-id="3ba90-147">自适应卡架构和 SDK 版本的发布计划由质量驱动, 而不是按日期</span><span class="sxs-lookup"><span data-stu-id="3ba90-147">The release schedule for Adaptive Card schema and SDK versions is driven by quality, not date</span></span>

6.  <span data-ttu-id="3ba90-148">**互操作性**</span><span class="sxs-lookup"><span data-stu-id="3ba90-148">**Interoperability**</span></span>
    1.  <span data-ttu-id="3ba90-149">根据记录格式 (例如, 不使用任何主机特定的扩展) 编写的卡将在任何支持自助功能的主机中正确呈现</span><span class="sxs-lookup"><span data-stu-id="3ba90-149">Cards authored in accordance with the documented format (e.g. not using any host-specific extensions) will render properly in any Adaptive Card-capable host</span></span>
    2.  <span data-ttu-id="3ba90-150">此原则的唯一例外是:</span><span class="sxs-lookup"><span data-stu-id="3ba90-150">The only exceptions to this principles are:</span></span>
        1.  <span data-ttu-id="3ba90-151">某些主机可能不允许交互操作, 因此不会呈现输入和操作</span><span class="sxs-lookup"><span data-stu-id="3ba90-151">Some hosts might not allow interactivity, and will therefore not render inputs nor actions</span></span>
        2.  <span data-ttu-id="3ba90-152">执行操作。提交操作由主机决定, 并非所有主机都必须正确处理所有操作。提交有效负载。</span><span class="sxs-lookup"><span data-stu-id="3ba90-152">Execution of Action.Submit actions is at the discretion of the host, and not all hosts will necessarily properly handle all Action.Submit payloads.</span></span> <span data-ttu-id="3ba90-153">此外, 某些主机可能不支持操作。全部提交</span><span class="sxs-lookup"><span data-stu-id="3ba90-153">Furthermore, some hosts might not support Action.Submit at all</span></span>

7.  <span data-ttu-id="3ba90-154">**格式必须是可扩展的**</span><span class="sxs-lookup"><span data-stu-id="3ba90-154">**The format needs to be extensible**</span></span>

    1.  <span data-ttu-id="3ba90-155">主机应可以自由地添加对自定义元素的支持或自定义操作, 这些支持超出了该格式的支持</span><span class="sxs-lookup"><span data-stu-id="3ba90-155">Hosts should have the freedom of adding support for custom elements or custom actions that go beyond what the format is capable of</span></span>
    2.  <span data-ttu-id="3ba90-156">这对于操作尤其重要, 因为不同的主机不一定支持同一组操作</span><span class="sxs-lookup"><span data-stu-id="3ba90-156">This is particularly important for actions, as various hosts don't necessarily support the same set of actions</span></span>
    3.  <span data-ttu-id="3ba90-157">这些添加是主机的判断</span><span class="sxs-lookup"><span data-stu-id="3ba90-157">These additions are at the discretion of the host</span></span>
        1. <span data-ttu-id="3ba90-158">它们不是自适应卡规范的*事实上*补充</span><span class="sxs-lookup"><span data-stu-id="3ba90-158">They are not a *de facto* addition to the Adaptive Card specification</span></span>
        2. <span data-ttu-id="3ba90-159">因此, 它们会使使用不兼容主流自适应卡格式的有效负载</span><span class="sxs-lookup"><span data-stu-id="3ba90-159">As such, they make a payload that uses them incompatible with the mainstream Adaptive Card format</span></span>
        3. <span data-ttu-id="3ba90-160">不过, 可以将其提供给工作组, 并建议将其作为新版本格式的新功能, 如点 #5</span><span class="sxs-lookup"><span data-stu-id="3ba90-160">They can however be presented to the Working Group and proposed as new features for a future version of the format, as described in point #5</span></span>

8.  <span data-ttu-id="3ba90-161">**卡作者拥有内容, 主机应用拥有外观**</span><span class="sxs-lookup"><span data-stu-id="3ba90-161">**Card authors own the content, host apps own the look and feel**</span></span>

    1.  <span data-ttu-id="3ba90-162">主机应用对其样式进行了设置, 因此卡的外观和感觉就像是应用体验的本机扩展</span><span class="sxs-lookup"><span data-stu-id="3ba90-162">Host apps impose their styling so cards look and feel like they are native extensions of the app's experience</span></span>
    2.  <span data-ttu-id="3ba90-163">卡片作者仍可以指定样式, 但只能通过颜色、大小等语义表达式来指定。</span><span class="sxs-lookup"><span data-stu-id="3ba90-163">Card authors can still specify styling, but only via semantic expressions of colors, sizes, etc.</span></span>

9.  <span data-ttu-id="3ba90-164">**将为最流行的开发人员平台提供 Sdk**</span><span class="sxs-lookup"><span data-stu-id="3ba90-164">**SDKs will be provided for the most popular developer platforms**</span></span>

    1.  <span data-ttu-id="3ba90-165">Sdk 使你能够轻松地在任何主机中呈现自适应卡负载</span><span class="sxs-lookup"><span data-stu-id="3ba90-165">SDKs make it easy to render Adaptive Card payloads in any host</span></span>
    2.  <span data-ttu-id="3ba90-166">这可确保进入的障碍尽可能低, 因为这同时适用于第三方开发人员和 Microsoft 团队</span><span class="sxs-lookup"><span data-stu-id="3ba90-166">This ensures the barrier to entry is as low as can be both for third party developers and Microsoft teams</span></span>
