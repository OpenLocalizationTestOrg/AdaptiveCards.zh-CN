---
title: 呈现卡-Android SDK
author: bekao
ms.author: bekao
ms.date: 09/27/2017
ms.topic: article
ms.openlocfilehash: 5ced7a2217ef6ef475aa344d92ad2f5e567266f8
ms.sourcegitcommit: 6889c7e1a38029d965c8f91dc9108819dbdea552
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/31/2019
ms.locfileid: "68732999"
---
# <a name="render-a-card---android"></a><span data-ttu-id="84c17-102">呈现卡-Android</span><span class="sxs-lookup"><span data-stu-id="84c17-102">Render a card - Android</span></span>

<span data-ttu-id="84c17-103">下面介绍如何使用 Android SDK 呈现卡片。</span><span class="sxs-lookup"><span data-stu-id="84c17-103">Here's how to render a card using the Android SDK.</span></span>

## <a name="create-adaptive-card-object-instance-from-json-text"></a><span data-ttu-id="84c17-104">从 JSON 文本创建自适应卡对象实例</span><span class="sxs-lookup"><span data-stu-id="84c17-104">Create Adaptive Card Object Instance from JSON Text</span></span>

```java
ParseResult parseResult = AdaptiveCard.DeserializeFromString(jsonText, AdaptiveCardRenderer.VERSION, elementParserRegistration);
AdaptiveCard adaptiveCard = parseResult.GetAdaptiveCard();
```
> [!IMPORTANT]
> <span data-ttu-id="84c17-105">**针对1.2 版的重大更改**</span><span class="sxs-lookup"><span data-stu-id="84c17-105">**Breaking changes for v1.2**</span></span>
> 

1. <span data-ttu-id="84c17-106">ElementParserRegistration 参数已更改为 ParseContext, 其中包含 ElementParserRegistration 和 ActionParserRegistration 对象</span><span class="sxs-lookup"><span data-stu-id="84c17-106">ElementParserRegistration parameter changed to ParseContext which includes an ElementParserRegistration and an ActionParserRegistration object</span></span>

```java
ParseContext context = new ParseContext(); // Empty parseContext so only known elements up to v1.2 will be parsed
ParseResult parseResult = AdaptiveCard.DeserializeFromString(jsonText, AdaptiveCardRenderer.VERSION, context);
```

<span data-ttu-id="84c17-107">或</span><span class="sxs-lookup"><span data-stu-id="84c17-107">or</span></span>

```java
ParseContext context = new ParseContext(elementParserRegistration, actionParserRegistration);
ParseResult parseResult = AdaptiveCard.DeserializeFromString(jsonText, AdaptiveCardRenderer.VERSION, context);
```

## <a name="render-a-card"></a><span data-ttu-id="84c17-108">渲染卡片</span><span class="sxs-lookup"><span data-stu-id="84c17-108">Render a card</span></span>

```java
RenderedAdaptiveCard renderedCard = AdaptiveCardRenderer.getInstance().render(context, fragmentManager, adaptiveCard, cardActionHandler, hostConfig);
View v = renderedCard.getView();
```
