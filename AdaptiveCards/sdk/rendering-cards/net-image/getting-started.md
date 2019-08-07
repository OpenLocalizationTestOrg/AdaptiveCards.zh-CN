---
title: .NET 图像呈现 SDK
author: matthidinger
ms.author: mahiding
ms.date: 10/19/2017
ms.topic: article
ms.openlocfilehash: bf97d851b954b861b01b1f7ff8ce79dc9ec6413b
ms.sourcegitcommit: 6889c7e1a38029d965c8f91dc9108819dbdea552
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/31/2019
ms.locfileid: "68732799"
---
# <a name="getting-started---net-image"></a><span data-ttu-id="d89e7-102">入门-.NET 映像</span><span class="sxs-lookup"><span data-stu-id="d89e7-102">Getting started - .NET Image</span></span>

<span data-ttu-id="d89e7-103">正如我们在[入门](../../../authoring-cards/getting-started.md)"页中所述, 自适应卡是 JSON 序列化的卡对象模型。</span><span class="sxs-lookup"><span data-stu-id="d89e7-103">As we described in [Getting Started](../../../authoring-cards/getting-started.md) page, an Adaptive Card is a JSON-serialized card object model.</span></span> <span data-ttu-id="d89e7-104">利用此库, 可以轻松地将 JSON 转换成 PNG 图像。</span><span class="sxs-lookup"><span data-stu-id="d89e7-104">This library makes it easy to render that JSON into into a PNG image.</span></span>

<span data-ttu-id="d89e7-105">此包甚至可以在服务器上用于生成映像, 并为您实现所有 "幻 STA 线程" goo。</span><span class="sxs-lookup"><span data-stu-id="d89e7-105">This package can even be used on a server to generate images, and implements all the "magic STA thread" goo for you.</span></span> 

## <a name="nuget-install"></a><span data-ttu-id="d89e7-106">NuGet 安装</span><span class="sxs-lookup"><span data-stu-id="d89e7-106">NuGet install</span></span>

<span data-ttu-id="d89e7-107">[![Nuget 安装](https://img.shields.io/nuget/vpre/AdaptiveCards.Rendering.Wpf.svg)](https://www.nuget.org/packages/AdaptiveCards.Rendering.Wpf)</span><span class="sxs-lookup"><span data-stu-id="d89e7-107">[![Nuget install](https://img.shields.io/nuget/vpre/AdaptiveCards.Rendering.Wpf.svg)](https://www.nuget.org/packages/AdaptiveCards.Rendering.Wpf)</span></span>

```console
Install-Package AdaptiveCards.Rendering.Wpf -IncludePrerelease
```

## <a name="next-steps"></a><span data-ttu-id="d89e7-108">后续步骤</span><span class="sxs-lookup"><span data-stu-id="d89e7-108">Next steps</span></span>

<span data-ttu-id="d89e7-109">有关后续步骤, 请参阅[渲染卡](render-a-card.md)!</span><span class="sxs-lookup"><span data-stu-id="d89e7-109">See [Render a card](render-a-card.md) for the next steps!</span></span>