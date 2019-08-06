---
title: 操作-.NET HTML SDK
author: matthidinger
ms.author: mahiding
ms.date: 10/19/2017
ms.topic: article
ms.openlocfilehash: f577c0bab73e2bd1f75bb22dd7a41a7dbfd63307
ms.sourcegitcommit: 6889c7e1a38029d965c8f91dc9108819dbdea552
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/31/2019
ms.locfileid: "68732849"
---
# <a name="actions---net-html"></a><span data-ttu-id="e1157-102">操作-.NET HTML</span><span class="sxs-lookup"><span data-stu-id="e1157-102">Actions - .NET HTML</span></span>

<span data-ttu-id="e1157-103">顶级卡片`actions`将呈现为 HTML `<button>`。</span><span class="sxs-lookup"><span data-stu-id="e1157-103">Top-level card `actions` will render as an HTML `<button>`.</span></span> <span data-ttu-id="e1157-104">由于这是一个服务器端库, 因此在按下按钮时, 将由您来连接客户端事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e1157-104">Since this is a server-side library it's up to you to wire up client-side event handlers when buttons are pressed.</span></span> <span data-ttu-id="e1157-105">HTML `<button>`中的每个都具有可用于连接正确行为的特性。</span><span class="sxs-lookup"><span data-stu-id="e1157-105">Each `<button>` in the HTML will have attributes that you can use to wire up the proper behavior.</span></span>

<span data-ttu-id="e1157-106">某些元素具有`selectAction`属性 (容器、列、图像), 使其可调用。</span><span class="sxs-lookup"><span data-stu-id="e1157-106">Some elements have a `selectAction` property (Container, Columns, Image) which makes them invokable.</span></span> <span data-ttu-id="e1157-107">如果元素具有`selectAction` `ac-selectable`, 则呈现器将添加的 CSS 类以及以下属性。</span><span class="sxs-lookup"><span data-stu-id="e1157-107">If an element has a `selectAction` the renderer will add a CSS class of `ac-selectable`, along with the below attributes.</span></span>

<span data-ttu-id="e1157-108">操作类型</span><span class="sxs-lookup"><span data-stu-id="e1157-108">Action Type</span></span> | <span data-ttu-id="e1157-109">CSS 类</span><span class="sxs-lookup"><span data-stu-id="e1157-109">CSS class</span></span> | <span data-ttu-id="e1157-110">其他属性</span><span class="sxs-lookup"><span data-stu-id="e1157-110">Additional attributes</span></span>
---|---|---
`Action.OpenUrl` | `ac-action-openUrl` | <span data-ttu-id="e1157-111">`data-ac-url`(卡片`url`中的属性)</span><span class="sxs-lookup"><span data-stu-id="e1157-111">`data-ac-url` (the `url` property from the card)</span></span>
`Action.Submit` | `ac-action-submit` | <span data-ttu-id="e1157-112">`data-ac-data`(卡片`data`中的属性)</span><span class="sxs-lookup"><span data-stu-id="e1157-112">`data-ac-data` (the `data` property from the card)</span></span>
`Action.ShowCard` | `ac-action-showCard` | <span data-ttu-id="e1157-113">`data-ac-showcardid``id` (`<div>`包含内部卡的)</span><span class="sxs-lookup"><span data-stu-id="e1157-113">`data-ac-showcardid` (the `id` of the `<div>` containing the inner card)</span></span>