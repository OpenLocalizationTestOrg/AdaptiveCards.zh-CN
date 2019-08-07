---
title: JavaScript SDK
author: matthidinger
ms.author: mahiding
ms.date: 11/28/2017
ms.topic: article
ms.openlocfilehash: 55360658d74ca384b0e6090631a7f5db463e968a
ms.sourcegitcommit: 6889c7e1a38029d965c8f91dc9108819dbdea552
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/31/2019
ms.locfileid: "68732904"
---
# <a name="getting-started---javascript"></a><span data-ttu-id="423be-102">入门-JavaScript</span><span class="sxs-lookup"><span data-stu-id="423be-102">Getting started - JavaScript</span></span>

<span data-ttu-id="423be-103">正如我们在[入门](../../../authoring-cards/getting-started.md)"页中所述, 自适应卡是 JSON 序列化的卡对象模型。</span><span class="sxs-lookup"><span data-stu-id="423be-103">As we described in [Getting Started](../../../authoring-cards/getting-started.md) page, an Adaptive Card is a JSON-serialized card object model.</span></span> <span data-ttu-id="423be-104">这是用于在浏览器中生成客户端 HTML 的 JavaScript SDK。</span><span class="sxs-lookup"><span data-stu-id="423be-104">This is a JavaScript SDK for generating client-side HTML in the browser.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="423be-105">**V 0.5 中的重大更改**</span><span class="sxs-lookup"><span data-stu-id="423be-105">**Breaking changes from v0.5**</span></span>
> 
> 1. <span data-ttu-id="423be-106">包已从`microsoft-adaptivecards`重命名为`adaptivecards`</span><span class="sxs-lookup"><span data-stu-id="423be-106">Package renamed from `microsoft-adaptivecards` to `adaptivecards`</span></span>
> 1. <span data-ttu-id="423be-107">静态`AdaptiveCards.setHostConfig()`已移动到的实例`AdaptiveCard`成员。</span><span class="sxs-lookup"><span data-stu-id="423be-107">The static `AdaptiveCards.setHostConfig()` has been moved to an instance member of `AdaptiveCard`.</span></span> <span data-ttu-id="423be-108">例如,`myCard.hostConfig = {}`</span><span class="sxs-lookup"><span data-stu-id="423be-108">E.g., `myCard.hostConfig = {}`</span></span> 
> 1. <span data-ttu-id="423be-109">`HostConfig`已离开各种重命名和移动。</span><span class="sxs-lookup"><span data-stu-id="423be-109">`HostConfig` has gone though various renames and moves.</span></span> <span data-ttu-id="423be-110">请参阅当前结构的[示例 json](https://github.com/Microsoft/AdaptiveCards/blob/master/samples/HostConfig/sample.json)主机配置</span><span class="sxs-lookup"><span data-stu-id="423be-110">See the [sample.json](https://github.com/Microsoft/AdaptiveCards/blob/master/samples/HostConfig/sample.json) Host Config for current structure</span></span>
> 1. <span data-ttu-id="423be-111">前面的0.5 个预览中也有一些架构更改,[这里概述](https://github.com/Microsoft/AdaptiveCards/pull/633)了这些更改</span><span class="sxs-lookup"><span data-stu-id="423be-111">There have also been some schema changes from the v0.5 preview, which are [outlined here](https://github.com/Microsoft/AdaptiveCards/pull/633)</span></span>
> 1. <span data-ttu-id="423be-112">已删除`renderCard()`静态函数, 因为它与类方法冗余。</span><span class="sxs-lookup"><span data-stu-id="423be-112">The static `renderCard()` function was removed as it was redundant with the class methods.</span></span> <span data-ttu-id="423be-113">如下`adaptiveCard.render()`所述使用。</span><span class="sxs-lookup"><span data-stu-id="423be-113">Use `adaptiveCard.render()` as described below.</span></span> 


## <a name="install"></a><span data-ttu-id="423be-114">安装</span><span class="sxs-lookup"><span data-stu-id="423be-114">Install</span></span>

### <a name="node"></a><span data-ttu-id="423be-115">节点</span><span class="sxs-lookup"><span data-stu-id="423be-115">Node</span></span>

<span data-ttu-id="423be-116">[![npm 安装](https://img.shields.io/npm/v/adaptivecards.svg)](https://www.npmjs.com/package/adaptivecards)</span><span class="sxs-lookup"><span data-stu-id="423be-116">[![npm install](https://img.shields.io/npm/v/adaptivecards.svg)](https://www.npmjs.com/package/adaptivecards)</span></span>

```console
npm install adaptivecards --save
```

### <a name="cdn"></a><span data-ttu-id="423be-117">CDN</span><span class="sxs-lookup"><span data-stu-id="423be-117">CDN</span></span>

```html
<script src="https://unpkg.com/adaptivecards/dist/adaptivecards.js"></script>
```

## <a name="usage"></a><span data-ttu-id="423be-118">用法</span><span class="sxs-lookup"><span data-stu-id="423be-118">Usage</span></span>

### <a name="import-the-module"></a><span data-ttu-id="423be-119">导入模块</span><span class="sxs-lookup"><span data-stu-id="423be-119">Import the module</span></span>

```js
// import the module
import * as AdaptiveCards from "adaptivecards";

// or require it
var AdaptiveCards = require("adaptivecards");

// or use the global variable if loaded from CDN
AdaptiveCards.renderCard(...);
```

## <a name="next-steps"></a><span data-ttu-id="423be-120">后续步骤</span><span class="sxs-lookup"><span data-stu-id="423be-120">Next steps</span></span>

<span data-ttu-id="423be-121">有关后续步骤, 请参阅[渲染卡](render-a-card.md)!</span><span class="sxs-lookup"><span data-stu-id="423be-121">See [Render a card](render-a-card.md) for the next steps!</span></span>
