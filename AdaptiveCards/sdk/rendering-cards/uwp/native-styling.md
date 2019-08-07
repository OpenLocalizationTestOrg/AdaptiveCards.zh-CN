---
title: 本机样式-UWP SDK
author: matthidinger
ms.author: mahiding
ms.date: 08/15/2018
ms.topic: article
ms.openlocfilehash: 565c61535adc5b316cb8b1f3ad77e511012e7612
ms.sourcegitcommit: 6889c7e1a38029d965c8f91dc9108819dbdea552
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/31/2019
ms.locfileid: "68732539"
---
# <a name="native-styling---uwp"></a><span data-ttu-id="1ee21-102">本机样式-UWP</span><span class="sxs-lookup"><span data-stu-id="1ee21-102">Native styling - UWP</span></span>

<span data-ttu-id="1ee21-103">虽然主机配置在每个平台上都可获得大多数方法, 但你可能需要在每个平台上执行一些本机样式。</span><span class="sxs-lookup"><span data-stu-id="1ee21-103">While Host Config will get you most of the way there on each platform, it's likely that you will have to do some native styling on each platform.</span></span> 

<span data-ttu-id="1ee21-104">UWP 使你可以传递 ResourceDictionary 以实现精细的样式、行为、动画等, 从而使其变得简单。</span><span class="sxs-lookup"><span data-stu-id="1ee21-104">UWP makes this easy by allowing you to pass a ResourceDictionary for fine-grained styling, behavior, animations, etc.</span></span>

| <span data-ttu-id="1ee21-105">元素</span><span class="sxs-lookup"><span data-stu-id="1ee21-105">Element</span></span> | <span data-ttu-id="1ee21-106">样式名称</span><span class="sxs-lookup"><span data-stu-id="1ee21-106">Style names</span></span> |
|---|---|
| <span data-ttu-id="1ee21-107">AdaptiveCard</span><span class="sxs-lookup"><span data-stu-id="1ee21-107">AdaptiveCard</span></span> | <span data-ttu-id="1ee21-108">Adaptive.Card</span><span class="sxs-lookup"><span data-stu-id="1ee21-108">Adaptive.Card</span></span>| 
| <span data-ttu-id="1ee21-109">Action.OpenUrl</span><span class="sxs-lookup"><span data-stu-id="1ee21-109">Action.OpenUrl</span></span>  | <span data-ttu-id="1ee21-110">Adaptive.Action.OpenUrl</span><span class="sxs-lookup"><span data-stu-id="1ee21-110">Adaptive.Action.OpenUrl</span></span>  |
| <span data-ttu-id="1ee21-111">Action.ShowCard</span><span class="sxs-lookup"><span data-stu-id="1ee21-111">Action.ShowCard</span></span> | <span data-ttu-id="1ee21-112">Adaptive.Action.ShowCard</span><span class="sxs-lookup"><span data-stu-id="1ee21-112">Adaptive.Action.ShowCard</span></span> |
| <span data-ttu-id="1ee21-113">Action.Submit</span><span class="sxs-lookup"><span data-stu-id="1ee21-113">Action.Submit</span></span>  | <span data-ttu-id="1ee21-114">Adaptive.Action.Submit</span><span class="sxs-lookup"><span data-stu-id="1ee21-114">Adaptive.Action.Submit</span></span>  |
| <span data-ttu-id="1ee21-115">列</span><span class="sxs-lookup"><span data-stu-id="1ee21-115">Column</span></span> | <span data-ttu-id="1ee21-116">Adaptive.Column, Adaptive.Action.Tap</span><span class="sxs-lookup"><span data-stu-id="1ee21-116">Adaptive.Column, Adaptive.Action.Tap</span></span> |
| <span data-ttu-id="1ee21-117">ColumnSet</span><span class="sxs-lookup"><span data-stu-id="1ee21-117">ColumnSet</span></span> | <span data-ttu-id="1ee21-118">Adaptive.ColumnSet, Adaptive.VerticalSeparator</span><span class="sxs-lookup"><span data-stu-id="1ee21-118">Adaptive.ColumnSet, Adaptive.VerticalSeparator</span></span> |
| <span data-ttu-id="1ee21-119">容器</span><span class="sxs-lookup"><span data-stu-id="1ee21-119">Container</span></span> | <span data-ttu-id="1ee21-120">Adaptive.Container</span><span class="sxs-lookup"><span data-stu-id="1ee21-120">Adaptive.Container</span></span>|
| <span data-ttu-id="1ee21-121">Input.ChoiceSet</span><span class="sxs-lookup"><span data-stu-id="1ee21-121">Input.ChoiceSet</span></span> | <span data-ttu-id="1ee21-122">Adaptive.Input.ChoiceSet,  Adaptive.Input.ChoiceSet.ComboBox, Adaptive.Input.ChoiceSet.CheckBox,  Adaptive.Input.ChoiceSet.Radio,  Adaptive.Input.ChoiceSet.ComboBoxItem</span><span class="sxs-lookup"><span data-stu-id="1ee21-122">Adaptive.Input.ChoiceSet,  Adaptive.Input.ChoiceSet.ComboBox, Adaptive.Input.ChoiceSet.CheckBox,  Adaptive.Input.ChoiceSet.Radio,  Adaptive.Input.ChoiceSet.ComboBoxItem</span></span> |
| <span data-ttu-id="1ee21-123">Input.Date</span><span class="sxs-lookup"><span data-stu-id="1ee21-123">Input.Date</span></span> | <span data-ttu-id="1ee21-124">Adaptive.Input.Text.Date</span><span class="sxs-lookup"><span data-stu-id="1ee21-124">Adaptive.Input.Text.Date</span></span>
| <span data-ttu-id="1ee21-125">Input.Number</span><span class="sxs-lookup"><span data-stu-id="1ee21-125">Input.Number</span></span> | <span data-ttu-id="1ee21-126">Adaptive.Input.Text.Number</span><span class="sxs-lookup"><span data-stu-id="1ee21-126">Adaptive.Input.Text.Number</span></span> |
| <span data-ttu-id="1ee21-127">Input.Text</span><span class="sxs-lookup"><span data-stu-id="1ee21-127">Input.Text</span></span> | <span data-ttu-id="1ee21-128">Adaptive.Input.Text</span><span class="sxs-lookup"><span data-stu-id="1ee21-128">Adaptive.Input.Text</span></span> |
| <span data-ttu-id="1ee21-129">Input.Time</span><span class="sxs-lookup"><span data-stu-id="1ee21-129">Input.Time</span></span> | <span data-ttu-id="1ee21-130">Adaptive.Input.Text.Time</span><span class="sxs-lookup"><span data-stu-id="1ee21-130">Adaptive.Input.Text.Time</span></span> |
| <span data-ttu-id="1ee21-131">Input.Toggle</span><span class="sxs-lookup"><span data-stu-id="1ee21-131">Input.Toggle</span></span>| <span data-ttu-id="1ee21-132">Adaptive.Input.Toggle</span><span class="sxs-lookup"><span data-stu-id="1ee21-132">Adaptive.Input.Toggle</span></span>|
| <span data-ttu-id="1ee21-133">图像</span><span class="sxs-lookup"><span data-stu-id="1ee21-133">Image</span></span>  | <span data-ttu-id="1ee21-134">Adaptive.Image</span><span class="sxs-lookup"><span data-stu-id="1ee21-134">Adaptive.Image</span></span> |
| <span data-ttu-id="1ee21-135">ImageSet</span><span class="sxs-lookup"><span data-stu-id="1ee21-135">ImageSet</span></span>  | <span data-ttu-id="1ee21-136">Adaptive.ImageSet</span><span class="sxs-lookup"><span data-stu-id="1ee21-136">Adaptive.ImageSet</span></span> |
| <span data-ttu-id="1ee21-137">FactSet</span><span class="sxs-lookup"><span data-stu-id="1ee21-137">FactSet</span></span> | <span data-ttu-id="1ee21-138">Adaptive.FactSet, Adaptive.Fact.Title, Adaptive.Fact.Value</span><span class="sxs-lookup"><span data-stu-id="1ee21-138">Adaptive.FactSet, Adaptive.Fact.Title, Adaptive.Fact.Value</span></span> |
| <span data-ttu-id="1ee21-139">TextBlock</span><span class="sxs-lookup"><span data-stu-id="1ee21-139">TextBlock</span></span>  | <span data-ttu-id="1ee21-140">Adaptive.TextBlock</span><span class="sxs-lookup"><span data-stu-id="1ee21-140">Adaptive.TextBlock</span></span> |

<span data-ttu-id="1ee21-141">此示例 XAML 资源字典, 它将所有 Textblock 的背景设置为浅绿色。</span><span class="sxs-lookup"><span data-stu-id="1ee21-141">This sample XAML Resource dictionary that sets the background of all TextBlocks to Aqua.</span></span> <span data-ttu-id="1ee21-142">你可能希望比此更高级的东西😁</span><span class="sxs-lookup"><span data-stu-id="1ee21-142">You will probably want something more advanced than this 😁</span></span>

```xml
<ResourceDictionary
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation" 
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">
    <Style x:Key="Adaptive.TextBlock" TargetType="TextBlock">
        <Setter Property="Background" Value="Aqua"></Setter>
    </Style>
</ResourceDictionary>
```
```csharp
// Use a ResourceDictionary instance
// DON'T use this property if rendering from a server
renderer.Resources = myResourceDictionary;
```
