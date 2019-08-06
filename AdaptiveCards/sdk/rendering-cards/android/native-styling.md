---
title: 本机样式设置-Android SDK
author: bekao
ms.author: bekao
ms.date: 09/27/2017
ms.topic: article
ms.openlocfilehash: c3190fbb31480f92c774d233476436ee2cfc52b3
ms.sourcegitcommit: 6889c7e1a38029d965c8f91dc9108819dbdea552
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/31/2019
ms.locfileid: "68733019"
---
# <a name="native-styling---android"></a><span data-ttu-id="22075-102">本机样式设置-Android</span><span class="sxs-lookup"><span data-stu-id="22075-102">Native styling - Android</span></span>

<span data-ttu-id="22075-103">Android 呈现器不支持本机样式, 而在版本1.2 中引入了对某些属性的样式支持:</span><span class="sxs-lookup"><span data-stu-id="22075-103">Native styling is not supported on the android renderer, v1.2 introduces the support for styling some properties:</span></span>

## <a name="action-sentiment"></a><span data-ttu-id="22075-104">操作情绪</span><span class="sxs-lookup"><span data-stu-id="22075-104">Action Sentiment</span></span>

<span data-ttu-id="22075-105">操作情绪包含在版本**1.2**中, 而不支持与其他版本一样多的样式, 可以通过实现有效的样式并将以下行添加到项目的样式</span><span class="sxs-lookup"><span data-stu-id="22075-105">Action sentiment is included in **v1.2** and while not supporting as many styles as other versions, actions with *destructive* or *positive* sentiment can be styled by implementing a valid style and adding the following line into the styles.xml for your project</span></span>

```styles.xml
 <item name="adaptiveActionDestructive">@style/adaptiveActionDestructive</item>
 <item name="adaptiveActionPositive">@style/adaptiveActionPositive</item>
```

## <a name="inline-action"></a><span data-ttu-id="22075-106">内联操作</span><span class="sxs-lookup"><span data-stu-id="22075-106">Inline Action</span></span>

<span data-ttu-id="22075-107">带有内联操作的文本输入允许为所呈现的操作设置样式。</span><span class="sxs-lookup"><span data-stu-id="22075-107">Text inputs with an inline action allows styling for the action being rendered.</span></span> <span data-ttu-id="22075-108">这允许将操作的样式设置为按钮 (adaptiveInlineAction) 或图像 (adaptiveInlineActionImage)</span><span class="sxs-lookup"><span data-stu-id="22075-108">This allows styling the action as a button (adaptiveInlineAction) or as an image (adaptiveInlineActionImage)</span></span>

```styles.xml
 <item name="adaptiveInlineAction">@style/adaptiveInlineAction</item>
 <item name="adaptiveInlineActionImage">@style/adaptiveInlineActionImage</item>
```

> [!IMPORTANT]
> <span data-ttu-id="22075-109">如果呈现器查找确切的名称, 则必须将所有项名称保持原样, 如下所示</span><span class="sxs-lookup"><span data-stu-id="22075-109">All item names must be kept as shown here as the renderer looks for those exact names</span></span>
