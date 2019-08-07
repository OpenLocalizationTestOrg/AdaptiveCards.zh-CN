---
title: 自适应卡工具
author: matthidinger
ms.author: mahiding
ms.date: 03/14/2019
ms.topic: article
ms.openlocfilehash: f0c5a61d3406e1defffefc575ee0a6ec78fba93d
ms.sourcegitcommit: 6889c7e1a38029d965c8f91dc9108819dbdea552
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/31/2019
ms.locfileid: "68733024"
---
# <a name="tools-and-samples"></a>工具和示例

## <a name="card-designer"></a>卡设计器 

需要使用工具来设计卡？ 请不要再查看基于浏览器的自适应卡设计器[https://adaptivecards.io/designer](https://adaptivecards.io/designer)

[![设计器屏幕快照](media/tools/designer.jpg)](https://adaptivecards.io/designer)

### <a name="embed-the-designer-into-your-app"></a>将设计器嵌入应用

但是, 当你可以使用我们的 JavaScript 库将**卡设计器直接嵌入到 web 应用中**时, 为什么向用户发送。 

若要开始, 请查看[adaptivecards](https://npmjs.com/adaptivecards-designer)包。

## <a name="schema-validation"></a>架构验证

架构验证是一种功能强大的方法, 可简化创作和启用工具。

我们提供了一个完整的[Json 架构文件](http://adaptivecards.io/schemas/1.2.0/adaptive-card.json), 用于在 JSON 中编辑和验证自适应卡。 请注意, 架构 URL 是版本控制的, 较新版本的自适应卡将具有相应的 URL。

在 Visual Studio 和 Visual Studio Code 中, 可以通过包括`$schema`引用来获取自动 Intellisense。

![bad](media/tools/invalidjson1.png)

![自动完成](media/tools/autocomplete.png)

## <a name="example"></a>示例

```json
{
    "$schema": "http://adaptivecards.io/schemas/1.2.0/adaptive-card.json",
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": []
}
```

## <a name="visual-studio-code-extension"></a>Visual Studio Code 扩展

我们创建了一个 Visual Studio code 扩展, 使你能够在编辑器自身内实时查看正在编辑的卡片。 

![扩展](media/tools/vscode-extension.png)

若要安装, 请打开 Extensions Marketplace 并搜索**自适应卡查看器**。

![定位](media/tools/vscode-extension-marketplace.png)

### <a name="usage"></a>用法

使用自适应卡`$schema`属性编辑 json 文件时, 可以使用`Ctrl+Shift+V A`查看。
```json
{
    "$schema": "http://adaptivecards.io/schemas/1.2.0/adaptive-card.json",
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": []
}
```

### <a name="options"></a>选项

以下 Visual Studio Code 设置适用于 AdaptiveCards 查看器。 可以在 "用户设置" 或 "工作区设置" 中设置此项。

```js
{
    // Open or not open the preview screen automatically
    "adaptivecardsviewer.enableautopreview": true,
}
```

## <a name="wpf-visualizer-sample"></a>WPF 可视化工具示例

使用[wpf 可视化工具示例项目](https://github.com/Microsoft/AdaptiveCards/tree/master/source/dotnet/Samples/WPFVisualizer), 可以在 Windows 计算机上使用 WPF/Xaml 直观显示卡。  中`hostconfig`内置了编辑器, 用于编辑和查看主机配置设置。 将这些设置保存为 JSON, 以便在应用程序中进行呈现。

![wpf 可视化工具](media/tools/wpfvisualizer.png)

## <a name="wpf-imagerender-sample"></a>WPF ImageRender 示例

[ImageRender 示例项目](https://github.com/Microsoft/AdaptiveCards/tree/master/source/dotnet/Samples/AdaptiveCards.Sample.ImageRender)使用 WPF 从命令行将任何卡片转换为 PNG。 
