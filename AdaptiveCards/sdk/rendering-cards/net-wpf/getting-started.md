---
title: .NET WPF SDK
author: matthidinger
ms.author: mahiding
ms.date: 10/19/2017
ms.topic: article
ms.openlocfilehash: 999f8ac3cd6a18fbbfc8b8bbdcf47465d8bb314f
ms.sourcegitcommit: 6889c7e1a38029d965c8f91dc9108819dbdea552
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/31/2019
ms.locfileid: "68732729"
---
# <a name="getting-started---net-wpf"></a>入门-.NET WPF

正如我们在[入门](../../../authoring-cards/getting-started.md)"页中所述, 自适应卡是 JSON 序列化的卡对象模型。 利用此库, 可以轻松地将 JSON 呈现到可在应用中使用的 WPF UI 中。

## <a name="nuget-install"></a>NuGet 安装

[![Nuget 安装](https://img.shields.io/nuget/vpre/AdaptiveCards.Rendering.Wpf.svg)](https://www.nuget.org/packages/AdaptiveCards.Rendering.Wpf)

```console
Install-Package AdaptiveCards.Rendering.Wpf
```

### <a name="xceed-enhanced-input-package"></a>Xceed 增强型输入包

此可选包可增强自适应卡输入控件, 而 WPF 不提供该功能。 它依赖于`Extended.Wpf.Toolkit`

[![Nuget 安装](https://img.shields.io/nuget/vpre/AdaptiveCards.Rendering.Wpf.Xceed.svg)](https://www.nuget.org/packages/AdaptiveCards.Rendering.Wpf.Xceed)

```console
Install-Package AdaptiveCards.Rendering.Wpf.Xceed
```

## <a name="wpf-visualizer-sample"></a>WPF 可视化工具示例

![可视化工具屏幕截图](../../../resources/media/tools/wpfvisualizer.png)

[Wpf 可视化工具示例](https://github.com/Microsoft/AdaptiveCards/tree/master/source/dotnet/Samples/WPFVisualizer)使你可以使用 wpf 可视化卡片。  中`Host Config`内置了编辑器, 用于编辑和查看主机配置设置。 将这些设置保存为 JSON, 以便在应用程序中进行呈现。

## <a name="next-steps"></a>后续步骤

有关后续步骤, 请参阅[渲染卡](render-a-card.md)!
