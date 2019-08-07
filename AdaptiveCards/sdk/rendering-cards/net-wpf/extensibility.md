---
title: 扩展性-.NET WPF SDK
author: matthidinger
ms.author: mahiding
ms.date: 10/19/2017
ms.topic: article
ms.openlocfilehash: 3e5bb9239d4b4200262648350d67d6494eed9724
ms.sourcegitcommit: 6889c7e1a38029d965c8f91dc9108819dbdea552
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/31/2019
ms.locfileid: "68732474"
---
# <a name="extensibility---net-wpf"></a><span data-ttu-id="5e1ee-102">扩展性-.NET WPF</span><span class="sxs-lookup"><span data-stu-id="5e1ee-102">Extensibility - .NET WPF</span></span>

## <a name="custom-element-rendering"></a><span data-ttu-id="5e1ee-103">自定义元素呈现</span><span class="sxs-lookup"><span data-stu-id="5e1ee-103">Custom Element Rendering</span></span>

<span data-ttu-id="5e1ee-104">若要完全控制呈现器, 可以`ElementRenderers`使用属性**添加**、**删除**或**重写**默认呈现器。</span><span class="sxs-lookup"><span data-stu-id="5e1ee-104">For full control of the renderer you can use the `ElementRenderers` property to **add**, **remove**, or **override** default renderers.</span></span>

<span data-ttu-id="5e1ee-105">下面的示例演示如何定义自定义`"type": "Rating"`元素并对其进行呈现。</span><span class="sxs-lookup"><span data-stu-id="5e1ee-105">The following example shows how you could define a custom `"type": "Rating"` element and render it.</span></span>

```csharp
// Register the new type with the JSON parser
AdaptiveTypedElementConverter.RegisterTypedElement<MyCustomRating>();

// Add the new type to the element renderer registry
renderer.ElementRenderers.Set<MyCustomRating>(MyCustomRating.Render);

// Define a custom Rating element type
public class MyCustomRating : AdaptiveElement
{
    public MyCustomRating() { Type = "Rating"; }

    public override string Type { get; set; }

    public AdaptiveTextSize Size { get; set; }

    public AdaptiveTextColor Color { get; set; }

    public static FrameworkElement Render(MyCustomRating rating, AdaptiveRenderContext context)
    {
        var textBlock = new AdaptiveTextBlock
        {
            Size = rating.Size,
            Color = rating.Color
        };
        for (int i = 0; i < rating.Rating; i++)
        {
            textBlock.Text += "\u2605";
        }
        textBlock.Text += $" ({rating.Rating})";
        return context.Render(textBlock);
    }
}
```
