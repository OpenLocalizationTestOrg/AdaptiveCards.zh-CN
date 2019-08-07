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
# <a name="tools-and-samples"></a><span data-ttu-id="d5188-102">工具和示例</span><span class="sxs-lookup"><span data-stu-id="d5188-102">Tools and Samples</span></span>

## <a name="card-designer"></a><span data-ttu-id="d5188-103">卡设计器</span><span class="sxs-lookup"><span data-stu-id="d5188-103">Card Designer</span></span> 

<span data-ttu-id="d5188-104">需要使用工具来设计卡？</span><span class="sxs-lookup"><span data-stu-id="d5188-104">Need for a tool to design your cards?</span></span> <span data-ttu-id="d5188-105">请不要再查看基于浏览器的自适应卡设计器[https://adaptivecards.io/designer](https://adaptivecards.io/designer)</span><span class="sxs-lookup"><span data-stu-id="d5188-105">Look no further than the browser-based adaptive card designer at [https://adaptivecards.io/designer](https://adaptivecards.io/designer)</span></span>

<span data-ttu-id="d5188-106">[![设计器屏幕快照](media/tools/designer.jpg)](https://adaptivecards.io/designer)</span><span class="sxs-lookup"><span data-stu-id="d5188-106">[![designer screenshot](media/tools/designer.jpg)](https://adaptivecards.io/designer)</span></span>

### <a name="embed-the-designer-into-your-app"></a><span data-ttu-id="d5188-107">将设计器嵌入应用</span><span class="sxs-lookup"><span data-stu-id="d5188-107">Embed the designer into your app</span></span>

<span data-ttu-id="d5188-108">但是, 当你可以使用我们的 JavaScript 库将**卡设计器直接嵌入到 web 应用中**时, 为什么向用户发送。</span><span class="sxs-lookup"><span data-stu-id="d5188-108">But why send your users there when you can **embed the card designer directly into your web** app using our JavaScript library.</span></span> 

<span data-ttu-id="d5188-109">若要开始, 请查看[adaptivecards](https://npmjs.com/adaptivecards-designer)包。</span><span class="sxs-lookup"><span data-stu-id="d5188-109">Check out the [adaptivecards-designer](https://npmjs.com/adaptivecards-designer) package to get started.</span></span>

## <a name="schema-validation"></a><span data-ttu-id="d5188-110">架构验证</span><span class="sxs-lookup"><span data-stu-id="d5188-110">Schema validation</span></span>

<span data-ttu-id="d5188-111">架构验证是一种功能强大的方法, 可简化创作和启用工具。</span><span class="sxs-lookup"><span data-stu-id="d5188-111">Schema validation is a powerful way of making authoring easier and enabling tooling.</span></span>

<span data-ttu-id="d5188-112">我们提供了一个完整的[Json 架构文件](http://adaptivecards.io/schemas/1.2.0/adaptive-card.json), 用于在 JSON 中编辑和验证自适应卡。</span><span class="sxs-lookup"><span data-stu-id="d5188-112">We have provided a complete [JSON Schema file](http://adaptivecards.io/schemas/1.2.0/adaptive-card.json) for editing and validating adaptive cards in json.</span></span> <span data-ttu-id="d5188-113">请注意, 架构 URL 是版本控制的, 较新版本的自适应卡将具有相应的 URL。</span><span class="sxs-lookup"><span data-stu-id="d5188-113">Note that the schema URL is versioned, newer versions of Adaptive Cards will have a corresponding URL.</span></span>

<span data-ttu-id="d5188-114">在 Visual Studio 和 Visual Studio Code 中, 可以通过包括`$schema`引用来获取自动 Intellisense。</span><span class="sxs-lookup"><span data-stu-id="d5188-114">In Visual Studio and Visual Studio Code you can get automatic Intellisense by including a `$schema` reference.</span></span>

![bad](media/tools/invalidjson1.png)

![自动完成](media/tools/autocomplete.png)

## <a name="example"></a><span data-ttu-id="d5188-117">示例</span><span class="sxs-lookup"><span data-stu-id="d5188-117">Example</span></span>

```json
{
    "$schema": "http://adaptivecards.io/schemas/1.2.0/adaptive-card.json",
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": []
}
```

## <a name="visual-studio-code-extension"></a><span data-ttu-id="d5188-118">Visual Studio Code 扩展</span><span class="sxs-lookup"><span data-stu-id="d5188-118">Visual Studio Code Extension</span></span>

<span data-ttu-id="d5188-119">我们创建了一个 Visual Studio code 扩展, 使你能够在编辑器自身内实时查看正在编辑的卡片。</span><span class="sxs-lookup"><span data-stu-id="d5188-119">We have created a Visual Studio code extension which allows you to visualize the card you are editing in real time inside the editor itself.</span></span> 

![扩展](media/tools/vscode-extension.png)

<span data-ttu-id="d5188-121">若要安装, 请打开 Extensions Marketplace 并搜索**自适应卡查看器**。</span><span class="sxs-lookup"><span data-stu-id="d5188-121">To install, open Extensions Marketplace and search for **Adaptive Card Viewer**.</span></span>

![定位](media/tools/vscode-extension-marketplace.png)

### <a name="usage"></a><span data-ttu-id="d5188-123">用法</span><span class="sxs-lookup"><span data-stu-id="d5188-123">Usage</span></span>

<span data-ttu-id="d5188-124">使用自适应卡`$schema`属性编辑 json 文件时, 可以使用`Ctrl+Shift+V A`查看。</span><span class="sxs-lookup"><span data-stu-id="d5188-124">When you are editing a .json file with an Adaptive Card `$schema` property you can view by using `Ctrl+Shift+V A`.</span></span>
```json
{
    "$schema": "http://adaptivecards.io/schemas/1.2.0/adaptive-card.json",
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": []
}
```

### <a name="options"></a><span data-ttu-id="d5188-125">选项</span><span class="sxs-lookup"><span data-stu-id="d5188-125">Options</span></span>

<span data-ttu-id="d5188-126">以下 Visual Studio Code 设置适用于 AdaptiveCards 查看器。</span><span class="sxs-lookup"><span data-stu-id="d5188-126">The following Visual Studio Code setting is available for the AdaptiveCards Viewer.</span></span> <span data-ttu-id="d5188-127">可以在 "用户设置" 或 "工作区设置" 中设置此项。</span><span class="sxs-lookup"><span data-stu-id="d5188-127">This can be set in User Settings or Workspace Settings.</span></span>

```js
{
    // Open or not open the preview screen automatically
    "adaptivecardsviewer.enableautopreview": true,
}
```

## <a name="wpf-visualizer-sample"></a><span data-ttu-id="d5188-128">WPF 可视化工具示例</span><span class="sxs-lookup"><span data-stu-id="d5188-128">WPF Visualizer Sample</span></span>

<span data-ttu-id="d5188-129">使用[wpf 可视化工具示例项目](https://github.com/Microsoft/AdaptiveCards/tree/master/source/dotnet/Samples/WPFVisualizer), 可以在 Windows 计算机上使用 WPF/Xaml 直观显示卡。</span><span class="sxs-lookup"><span data-stu-id="d5188-129">The [WPF visualizer sample project](https://github.com/Microsoft/AdaptiveCards/tree/master/source/dotnet/Samples/WPFVisualizer) lets you visualize cards using WPF/Xaml on a Windows machine.</span></span>  <span data-ttu-id="d5188-130">中`hostconfig`内置了编辑器, 用于编辑和查看主机配置设置。</span><span class="sxs-lookup"><span data-stu-id="d5188-130">A `hostconfig` editor is built in for editing and viewing host config settings.</span></span> <span data-ttu-id="d5188-131">将这些设置保存为 JSON, 以便在应用程序中进行呈现。</span><span class="sxs-lookup"><span data-stu-id="d5188-131">Save these settings as a JSON to use them in rendering in your application.</span></span>

![wpf 可视化工具](media/tools/wpfvisualizer.png)

## <a name="wpf-imagerender-sample"></a><span data-ttu-id="d5188-133">WPF ImageRender 示例</span><span class="sxs-lookup"><span data-stu-id="d5188-133">WPF ImageRender Sample</span></span>

<span data-ttu-id="d5188-134">[ImageRender 示例项目](https://github.com/Microsoft/AdaptiveCards/tree/master/source/dotnet/Samples/AdaptiveCards.Sample.ImageRender)使用 WPF 从命令行将任何卡片转换为 PNG。</span><span class="sxs-lookup"><span data-stu-id="d5188-134">The [ImageRender sample project](https://github.com/Microsoft/AdaptiveCards/tree/master/source/dotnet/Samples/AdaptiveCards.Sample.ImageRender) turns any card into a PNG from the command line using WPF.</span></span> 
