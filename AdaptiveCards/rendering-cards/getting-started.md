---
title: 在应用程序中呈现卡
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: a562a05a91676dc5e6d8b51690acc4788802fb99
ms.sourcegitcommit: 6889c7e1a38029d965c8f91dc9108819dbdea552
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/31/2019
ms.locfileid: "68732604"
---
# <a name="rendering-cards-inside-your-application"></a>在应用程序中呈现卡

在应用程序中呈现自适应卡非常简单。 我们为所有常见平台提供 Sdk, 并提供创建自己的自适应卡呈现器的[详细规范](implement-a-renderer.md)。

1. 为目标平台**安装呈现器 SDK** 。
2. **创建一个呈现器实例**, 该实例配置为使用应用的样式、规则和操作事件处理程序。
3. 将**卡片呈现为本机 UI** -自动样式化到你的应用程序。

## <a name="adaptive-cards-sdks"></a>自适应卡 Sdk

|平台|安装|Build|Docs|状态|
|---|---|---|---|---|
| JavaScript | [![npm 安装](https://img.shields.io/npm/v/adaptivecards.svg)](https://www.npmjs.com/package/adaptivecards) | [源](https://github.com/Microsoft/AdaptiveCards/tree/master/source/nodejs)| [Docs](../sdk/rendering-cards/javascript/getting-started.md) | ![生成状态](https://img.shields.io/vso/build/Microsoft/56cf629e-8f3a-4412-acbc-bf69366c552c/20564.svg) |
| .NET WPF | [![Nuget 安装](https://img.shields.io/nuget/vpre/AdaptiveCards.Rendering.Wpf.svg)](https://www.nuget.org/packages/AdaptiveCards.Rendering.Wpf) | [源](https://github.com/Microsoft/AdaptiveCards/tree/master/source/dotnet)| [Docs](../sdk/rendering-cards/net-wpf/getting-started.md) | ![生成状态](https://img.shields.io/vso/build/Microsoft/56cf629e-8f3a-4412-acbc-bf69366c552c/20596.svg) |
| .NET HTML | [![Nuget 安装](https://img.shields.io/nuget/vpre/AdaptiveCards.Rendering.Html.svg)](https://www.nuget.org/packages/AdaptiveCards.Rendering.Html) | [源](https://github.com/Microsoft/AdaptiveCards/tree/master/source/dotnet) | [Docs](../sdk/rendering-cards/net-html/getting-started.md) | ![生成状态](https://img.shields.io/vso/build/Microsoft/56cf629e-8f3a-4412-acbc-bf69366c552c/20596.svg) |
| Windows UWP | [![Nuget 安装](https://img.shields.io/nuget/vpre/AdaptiveCards.Rendering.Uwp.svg)](https://www.nuget.org/packages/AdaptiveCards.Rendering.Uwp) | [源](https://github.com/Microsoft/AdaptiveCards/tree/master/source/uwp) | [Docs](../sdk/rendering-cards/uwp/getting-started.md) | ![生成状态](https://img.shields.io/vso/build/Microsoft/56cf629e-8f3a-4412-acbc-bf69366c552c/20583.svg) |
| Android | [![Maven 中部](https://img.shields.io/maven-central/v/io.adaptivecards/adaptivecards-android.svg)](https://search.maven.org/#search%7Cga%7C1%7Ca%3A%22adaptivecards-android%22) | [源](https://github.com/Microsoft/AdaptiveCards/tree/master/source/android) | [Docs](../sdk/rendering-cards/android/getting-started.md) | ![生成状态](https://img.shields.io/vso/build/Microsoft/8d47e068-03c8-4cdc-aa9b-fc6929290322/17651.svg)
| iOS | [![CocoaPods](https://img.shields.io/cocoapods/v/AdaptiveCards.svg)](https://cocoapods.org/pods/AdaptiveCards) | [源](https://github.com/Microsoft/AdaptiveCards/tree/master/source/ios) | [Docs](../sdk/rendering-cards/ios/getting-started.md) |  ![生成状态](https://img.shields.io/vso/build/Microsoft/8d47e068-03c8-4cdc-aa9b-fc6929290322/16990.svg) |

## <a name="create-an-instance-of-the-renderer"></a>创建呈现器的实例

下一步是创建的实例`AdaptiveCardRenderer`。 

### <a name="hook-up-action-events"></a>挂接操作事件

默认情况下, 这些操作将作为按钮显示在卡片上, 但会由应用程序以使其按预期方式运行。 每个 SDK 都具有您必须`OnAction`处理的事件的等效项。

* **OpenUrl** -打开指定`url`的。  
* **操作. 提交**-获取提交结果, 并将其发送到源。 将其发送到卡的源的方式完全取决于你。
* **ShowCard** -调用对话框, 并将子卡呈现到该对话框中。 请注意, 只有在设置为`ShowCardActionMode` `popup`时, 才需要处理此情况。

## <a name="render-a-card"></a>渲染卡片

获取卡有效负载后, 只需调用呈现器并传入卡即可。 你将返回由卡片内容组成的本机 UI 对象。 现在只需将此 UI 放置在应用中的某个位置。

## <a name="customization"></a>自定义

可以通过多种方式自定义呈现的内容。 

### <a name="hostconfig"></a>HostConfig

[HostConfig](host-config.md)是一个共享的跨平台配置对象, 用于控制应用内卡的基本样式和行为。 它定义字体大小、元素间的间距、所支持操作的数量等内容。 

### <a name="native-platform-styling"></a>本机平台样式

大多数 UI 框架使你可以使用本机 UI 框架样式设置呈现的卡片的样式。 例如, 在 HTML 中, 可以为 HTML 指定 CSS 类, 也可以在 XAML 中传递自定义 ResourceDictionary, 以便对输出进行精细控制。

### <a name="customize-per-element-rendering"></a>自定义按元素呈现

每个 SDK 都允许重写任何元素的呈现, 甚至添加对定义的全新元素的支持。  例如, 你可以更改`Input.Date`呈现器以发出你自己的自定义控件, 同时仍然保留呈现器的其余输出。 也可以添加对定义的自定义`Rating`元素的支持。



