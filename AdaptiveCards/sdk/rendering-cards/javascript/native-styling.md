---
title: 本机样式设置-JavaScript SDK
author: matthidinger
ms.author: mahiding
ms.date: 11/28/2017
ms.topic: article
ms.openlocfilehash: 687a90dd572ba2df786816fdd9dc313746cca982
ms.sourcegitcommit: 6889c7e1a38029d965c8f91dc9108819dbdea552
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/31/2019
ms.locfileid: "68732619"
---
# <a name="native-styling---javascript"></a><span data-ttu-id="7e316-102">本机样式设置-JavaScript</span><span class="sxs-lookup"><span data-stu-id="7e316-102">Native styling - JavaScript</span></span>

<span data-ttu-id="7e316-103">使用 CSS 对卡片 HTML 进行精细的样式设置。</span><span class="sxs-lookup"><span data-stu-id="7e316-103">Use CSS for fine-grained styling of the card HTML.</span></span>

<span data-ttu-id="7e316-104">以下 CSS 类将添加到各种元素。</span><span class="sxs-lookup"><span data-stu-id="7e316-104">The following CSS classes will be added to various elements.</span></span>

| <span data-ttu-id="7e316-105">CSS 类</span><span class="sxs-lookup"><span data-stu-id="7e316-105">CSS class</span></span> | <span data-ttu-id="7e316-106">用法</span><span class="sxs-lookup"><span data-stu-id="7e316-106">Usage</span></span> |
|---|---|
| <span data-ttu-id="7e316-107">.ac-container</span><span class="sxs-lookup"><span data-stu-id="7e316-107">.ac-container</span></span> | <span data-ttu-id="7e316-108">容器</span><span class="sxs-lookup"><span data-stu-id="7e316-108">containers</span></span> |
| <span data-ttu-id="7e316-109">.ac-selectable</span><span class="sxs-lookup"><span data-stu-id="7e316-109">.ac-selectable</span></span>  | <span data-ttu-id="7e316-110">元素与`selectAction`</span><span class="sxs-lookup"><span data-stu-id="7e316-110">elements with `selectAction`</span></span> |
| <span data-ttu-id="7e316-111">.ac-image</span><span class="sxs-lookup"><span data-stu-id="7e316-111">.ac-image</span></span> | <span data-ttu-id="7e316-112">图像</span><span class="sxs-lookup"><span data-stu-id="7e316-112">image</span></span> |
| <span data-ttu-id="7e316-113">.ac-pushButton</span><span class="sxs-lookup"><span data-stu-id="7e316-113">.ac-pushButton</span></span> | <span data-ttu-id="7e316-114">呈现的操作类似于按钮</span><span class="sxs-lookup"><span data-stu-id="7e316-114">actions rendered like buttons</span></span> |
| <span data-ttu-id="7e316-115">.ac-linkButton</span><span class="sxs-lookup"><span data-stu-id="7e316-115">.ac-linkButton</span></span>  | <span data-ttu-id="7e316-116">呈现的操作, 如链接</span><span class="sxs-lookup"><span data-stu-id="7e316-116">actions rendered like links</span></span> |
| <span data-ttu-id="7e316-117">.ac-input</span><span class="sxs-lookup"><span data-stu-id="7e316-117">.ac-input</span></span> | <span data-ttu-id="7e316-118">输入控件</span><span class="sxs-lookup"><span data-stu-id="7e316-118">input controls</span></span>|
| <span data-ttu-id="7e316-119">.ac-textInput</span><span class="sxs-lookup"><span data-stu-id="7e316-119">.ac-textInput</span></span>| <span data-ttu-id="7e316-120">文本输入</span><span class="sxs-lookup"><span data-stu-id="7e316-120">text input</span></span> |
| <span data-ttu-id="7e316-121">.ac-multiline</span><span class="sxs-lookup"><span data-stu-id="7e316-121">.ac-multiline</span></span> | <span data-ttu-id="7e316-122">多行文本输入</span><span class="sxs-lookup"><span data-stu-id="7e316-122">multiline text input</span></span> |
| <span data-ttu-id="7e316-123">.ac-numberInput</span><span class="sxs-lookup"><span data-stu-id="7e316-123">.ac-numberInput</span></span> | <span data-ttu-id="7e316-124">数字输入</span><span class="sxs-lookup"><span data-stu-id="7e316-124">number input</span></span>|
| <span data-ttu-id="7e316-125">.ac-dateInput</span><span class="sxs-lookup"><span data-stu-id="7e316-125">.ac-dateInput</span></span> | <span data-ttu-id="7e316-126">日期输入</span><span class="sxs-lookup"><span data-stu-id="7e316-126">date input</span></span>|
| <span data-ttu-id="7e316-127">.ac-timeInput</span><span class="sxs-lookup"><span data-stu-id="7e316-127">.ac-timeInput</span></span> | <span data-ttu-id="7e316-128">时间输入</span><span class="sxs-lookup"><span data-stu-id="7e316-128">time input</span></span> |
| <span data-ttu-id="7e316-129">.ac-multichoiceInput</span><span class="sxs-lookup"><span data-stu-id="7e316-129">.ac-multichoiceInput</span></span> | <span data-ttu-id="7e316-130">multichoice 输入</span><span class="sxs-lookup"><span data-stu-id="7e316-130">multichoice input</span></span>|