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
# <a name="adaptive-cards-overview"></a>自适应卡概述 

自适应卡是一种开放的卡交换格式, 使开发人员能够以一种通用且一致的方式交换 UI 内容。

<video controls width="100%" poster="./content/videoposter.png">
    <source src="https://adaptivecardsblob.blob.core.windows.net/assets/AdaptiveCardsOverviewVideo.mp4" type="video/mp4">
</video>

## <a name="how-they-work"></a>工作原理

[**卡片作者**](authoring-cards/getting-started.md)将其内容描述为一个简单的 JSON 对象。 然后, 该内容可以在[**主机应用程序**](rendering-cards/getting-started.md)中以本机方式呈现, 从而自动适应主机的外观。

例如, Contoso 机器人可以通过 Bot 框架创作自适应卡, 并在将其传送到 Skype 后, 其外观类似于 Skype 卡。 当将同一有效负载发送到 Microsoft 团队时, 它将类似于 Microsoft 团队。 随着更多主机应用开始支持自适应卡, 相同的负载会自动在这些应用程序中亮起, 但在应用程序中也完全是本机。

用户获胜, 因为一切都非常熟悉。 主机应用获胜, 因为它们控制用户体验。 和卡片作者入选, 因为他们的内容可以更广泛地传播, 无需任何其他工作。

## <a name="goals"></a>目标 

自适应卡的目标是:

* **可移植**-到任何应用、设备和 UI 框架
* **开放**库和架构是开放源代码并共享
* **成本较低**-易于定义、易于使用
* 可**表达**性-面向开发人员想要生成的内容的长末尾
* **纯粹声明**-不需要或不允许代码
* **自动样式**-到主机应用程序 UX 和品牌准则

## <a name="for-card-authors"></a>对于卡片作者
自适应卡非常适合于卡片作者:

* **一个架构**-您将获得一种格式, 最大限度地减少创建卡的成本, 并最大限度地提高可使用的位数。
* **更丰富的表达式**-你的内容可以更紧密地与你想要的内容对齐, 因为你有更丰富的调色板来进行绘制。
* **广泛的覆盖**-内容可跨一组更广泛的应用程序使用, 无需了解新的架构。
* **输入控制**-您的卡可以包含用于从查看卡的用户那里收集信息的输入控件。
* **更好的工具**-一种开放式卡生态系统是指由每个人共享的更好的工具。

## <a name="for-experience-owners"></a>对于体验所有者
如果你是一名需要利用第三方内容生态系统的应用开发人员, 你将喜欢自适应卡, 因为:

* **一致的用户体验**-确保为用户提供一致的体验, 因为你拥有呈现的卡片的样式。
* **本机性能**-你可以获得本机性能, 因为它会直接面向你的 UI 框架。
* **安全**的有效负载中提供了安全内容, 因此你无需打开 UI 框架来提供原始标记和脚本。
* **易于实现**-可从库中轻松地将其集成到支持的任何平台上 
* **免费文档**-您可以节省时间, 因为您无需库存、实施和记录专用架构。
* **共享工具**-您可以节省时间, 因为您无需创建自定义工具。

## <a name="core-design-principles"></a>核心设计原则 

自适应卡由一组指导原则驱动, 这些[指导原则](resources/principles.md)对保持设计的跟踪十分有用。 

### <a name="semantic-instead-of-pixel-perfect"></a>语义而不是像素-完美
与纯像素完美布局相比, 我们尽可能 striven 语义值和概念。 语义表达式的示例显示在颜色、大小和元素 (例如 FactSet 和 ImageSet) 中。 这一切都允许主机应用程序对实际的外观作出更好的决策。

### <a name="card-authors-own-the-content-host-app-owns-the-look-and-feel"></a>卡作者拥有内容, 主机应用拥有外观
卡片作者拥有他们想要表达的内容, 但显示它的应用程序在其应用程序的上下文中具有卡的外观。

### <a name="keep-it-simple-but-expressive"></a>使其保持简单, 但有意义
我们希望自适应卡有表现力和常规用途, 但我们不想构建 UI 框架。  目标是创建一个 "有意义" 的中间层, 这与 Markdown 为文档提供足够的意义。

Markdown 着重于使其简单明了, 并为文档内容创建了一个简单一致的说明。  同样地, 我们相信自适应卡可以创建一个简单、有意义的方式来描述卡片内容。

### <a name="when-in-doubt-keep-it-out"></a>如果有疑问, 请将它
稍后添加会更容易, 但会出现错误。 如果我们找到了自己的讨论, 无论是否应添加内容, 我们都选择将其关闭。使用我们不需要支持的旧版本, 通常可以更轻松地添加属性。


## <a name="build-2018-session"></a>生成2018会话

以下在版本2018中的会话展示了机器人、Cortana、Outlook 和 Windows 中的自适应卡。 

<iframe src="https://medius.studios.ms/Embed/Video/BRK2401?SFYT=true" width="960" height="540" allowFullScreen frameBorder="0"></iframe>
