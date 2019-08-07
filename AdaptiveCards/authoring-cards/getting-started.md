---
title: 入门
author: matthidinger
ms.author: mahiding
ms.date: 11/9/2017
ms.topic: article
ms.openlocfilehash: c9a0ad07ba5fefbcdc35239591c02fe0720b5b66
ms.sourcegitcommit: 6889c7e1a38029d965c8f91dc9108819dbdea552
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/31/2019
ms.locfileid: "68732649"
---
# <a name="getting-started"></a><span data-ttu-id="14fa1-102">入门</span><span class="sxs-lookup"><span data-stu-id="14fa1-102">Getting Started</span></span> 

<span data-ttu-id="14fa1-103">自适应卡是 JSON 序列化的卡对象模型。</span><span class="sxs-lookup"><span data-stu-id="14fa1-103">An Adaptive Card is a JSON-serialized card object model.</span></span>

## <a name="adaptive-card-structure"></a><span data-ttu-id="14fa1-104">自适应卡结构</span><span class="sxs-lookup"><span data-stu-id="14fa1-104">Adaptive Card structure</span></span>

<span data-ttu-id="14fa1-105">卡片的基本结构如下所示:</span><span class="sxs-lookup"><span data-stu-id="14fa1-105">The basic structure of a card is as follows:</span></span>

* <span data-ttu-id="14fa1-106">`AdaptiveCard`-根对象描述 AdaptiveCard 本身, 其中包括其元素构成、其操作、应如何口述以及呈现它所需的架构版本。</span><span class="sxs-lookup"><span data-stu-id="14fa1-106">`AdaptiveCard` - The root object describes the AdaptiveCard itself, including its element makeup, its actions, how it should be spoken, and the schema version required to render it.</span></span>
* <span data-ttu-id="14fa1-107">`body`-卡片的主体由称为`elements`的构建基块组成。</span><span class="sxs-lookup"><span data-stu-id="14fa1-107">`body` - The body of the card is made up of building-blocks known as `elements`.</span></span> <span data-ttu-id="14fa1-108">可以通过几乎无限的方式撰写元素, 以创建多种类型的卡。</span><span class="sxs-lookup"><span data-stu-id="14fa1-108">Elements can be composed in nearly infinite arrangements to create many types of cards.</span></span> 
* <span data-ttu-id="14fa1-109">`actions`-许多卡都具有一组用户可能会执行的操作。</span><span class="sxs-lookup"><span data-stu-id="14fa1-109">`actions` - Many cards have a set of actions a user may take on it.</span></span> <span data-ttu-id="14fa1-110">此属性描述通常呈现在底部的 "操作栏" 中的操作。</span><span class="sxs-lookup"><span data-stu-id="14fa1-110">This property describes those actions which typically get rendered in an "action bar" at the bottom.</span></span>

### <a name="example-card"></a><span data-ttu-id="14fa1-111">示例卡</span><span class="sxs-lookup"><span data-stu-id="14fa1-111">Example Card</span></span>

<span data-ttu-id="14fa1-112">此示例卡包含一行文本, 后跟一个图像。</span><span class="sxs-lookup"><span data-stu-id="14fa1-112">This sample card which includes a single line of text followed by an image.</span></span>

```json
{
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": [
        {
            "type": "TextBlock",
            "text": "Here is a ninja cat"
        },
        {
            "type": "Image",
            "url": "http://adaptivecards.io/content/cats/1.png"
        }
    ]
}
```

## <a name="type-property"></a><span data-ttu-id="14fa1-113">`Type` 属性</span><span class="sxs-lookup"><span data-stu-id="14fa1-113">`Type` property</span></span>

<span data-ttu-id="14fa1-114">每个元素都`type`有一个属性, 用于标识对象的类型。</span><span class="sxs-lookup"><span data-stu-id="14fa1-114">Every element has a `type` property which identifies what kind of object it is.</span></span> <span data-ttu-id="14fa1-115">查看上面的卡片, 可以看到我们有两个元素: `TextBlock` `Image`和。</span><span class="sxs-lookup"><span data-stu-id="14fa1-115">Looking at the above card, you can see we have two elements, a `TextBlock` and an `Image`.</span></span>

<span data-ttu-id="14fa1-116">所有自适应卡元素都**垂直堆叠**, 并**向其父**对象 ( `display: block`以 HTML 格式) 展开。</span><span class="sxs-lookup"><span data-stu-id="14fa1-116">All Adaptive Card elements **stack vertically** and **expand to the width of their parent** (think `display: block` in HTML).</span></span> <span data-ttu-id="14fa1-117">但是, 可以使用`ColumnSet`来创建容器的并行列。</span><span class="sxs-lookup"><span data-stu-id="14fa1-117">However, you can use a `ColumnSet` to create side-by-side columns of containers.</span></span>

## <a name="adaptive-elements"></a><span data-ttu-id="14fa1-118">自适应元素</span><span class="sxs-lookup"><span data-stu-id="14fa1-118">Adaptive Elements</span></span>

<span data-ttu-id="14fa1-119">最基本的元素包括:</span><span class="sxs-lookup"><span data-stu-id="14fa1-119">The most fundamental elements are:</span></span>

* <span data-ttu-id="14fa1-120">**TextBlock** -添加一个文本块, 其中包含用于控制文本外观的属性</span><span class="sxs-lookup"><span data-stu-id="14fa1-120">**TextBlock** - adds a block of text with properties to control what the text looks like</span></span>
* <span data-ttu-id="14fa1-121">**图像**-添加一个图像, 其中包含用于控制图像外观的属性</span><span class="sxs-lookup"><span data-stu-id="14fa1-121">**Image** - adds an image with properties to control what the image looks like</span></span>

## <a name="container-elements"></a><span data-ttu-id="14fa1-122">容器元素</span><span class="sxs-lookup"><span data-stu-id="14fa1-122">Container elements</span></span>

<span data-ttu-id="14fa1-123">卡还可以具有容器, 它们排列子元素的集合。</span><span class="sxs-lookup"><span data-stu-id="14fa1-123">Cards can also have containers, which arrange a collection of child elements.</span></span>

* <span data-ttu-id="14fa1-124">**容器**-定义元素集合</span><span class="sxs-lookup"><span data-stu-id="14fa1-124">**Container** - Defines a a collection of elements</span></span>
* <span data-ttu-id="14fa1-125">**列集/column** -定义列的集合, 每个列都是一个容器</span><span class="sxs-lookup"><span data-stu-id="14fa1-125">**ColumnSet/Column** - Defines a collection of columns, each column is a container</span></span>
* <span data-ttu-id="14fa1-126">**FactSet** -事实的容器</span><span class="sxs-lookup"><span data-stu-id="14fa1-126">**FactSet** - Container of Facts</span></span>
* <span data-ttu-id="14fa1-127">**ImageSet** -图像的容器, 以便 UI 可以显示图像集合的适当照片库体验。</span><span class="sxs-lookup"><span data-stu-id="14fa1-127">**ImageSet** - Container of Images so that UI can show appropriate photo gallery experience for a collection of images.</span></span>

## <a name="input-elements"></a><span data-ttu-id="14fa1-128">输入元素</span><span class="sxs-lookup"><span data-stu-id="14fa1-128">Input elements</span></span>

<span data-ttu-id="14fa1-129">输入元素可让你请求本机 UI 来构建简单窗体:</span><span class="sxs-lookup"><span data-stu-id="14fa1-129">Input elements allow you to ask for native UI to build simple forms:</span></span>

* <span data-ttu-id="14fa1-130">**输入文本**-从用户获取文本内容</span><span class="sxs-lookup"><span data-stu-id="14fa1-130">**Input.Text** - get text content from the user</span></span>
* <span data-ttu-id="14fa1-131">**输入。日期**-从用户获取日期</span><span class="sxs-lookup"><span data-stu-id="14fa1-131">**Input.Date** - get a Date from the user</span></span>
* <span data-ttu-id="14fa1-132">**输入。时间**-从用户获取时间</span><span class="sxs-lookup"><span data-stu-id="14fa1-132">**Input.Time** - get a Time from the user</span></span>
* <span data-ttu-id="14fa1-133">**输入数字**-从用户获取一个数字</span><span class="sxs-lookup"><span data-stu-id="14fa1-133">**Input.Number** - get a Number from the user</span></span>
* <span data-ttu-id="14fa1-134">**输入. ChoiceSet** -为用户指定一组选择, 并选择</span><span class="sxs-lookup"><span data-stu-id="14fa1-134">**Input.ChoiceSet** - Give the user a set of choices and have them pick</span></span>
* <span data-ttu-id="14fa1-135">**输入。切换**-为用户设置两个项之间的单个选择, 并选择它们</span><span class="sxs-lookup"><span data-stu-id="14fa1-135">**Input.Toggle** - Give the user a single choice between two items and have them pick</span></span>

## <a name="actions"></a><span data-ttu-id="14fa1-136">操作</span><span class="sxs-lookup"><span data-stu-id="14fa1-136">Actions</span></span>

<span data-ttu-id="14fa1-137">操作将按钮添加到卡片。</span><span class="sxs-lookup"><span data-stu-id="14fa1-137">Actions add buttons to the card.</span></span> <span data-ttu-id="14fa1-138">这些操作可以执行各种操作, 如打开 URL 或提交一些数据。</span><span class="sxs-lookup"><span data-stu-id="14fa1-138">These can perform a variety of actions, like opening a URL or submitting some data.</span></span>

* <span data-ttu-id="14fa1-139">**OpenUrl** -该按钮将打开一个外部 URL 以便查看</span><span class="sxs-lookup"><span data-stu-id="14fa1-139">**Action.OpenUrl** - the button opens an external URL for viewing</span></span>
* <span data-ttu-id="14fa1-140">**ShowCard** -请求向用户显示子卡。</span><span class="sxs-lookup"><span data-stu-id="14fa1-140">**Action.ShowCard** - Requests a sub-card to be shown to the user.</span></span>
* <span data-ttu-id="14fa1-141">**操作: 提交**-要求将所有输入元素向上收集到对象, 然后通过主机应用程序定义的方法将其发送给您。</span><span class="sxs-lookup"><span data-stu-id="14fa1-141">**Action.Submit** - Ask for all of the input elements to be gathered up into an object which is then sent to you through some method defined by the host application.</span></span>

> <span data-ttu-id="14fa1-142">**示例操作。提交**:使用 Skype 时, 操作。提交操作会将 Bot Framework 机器人活动发送回机器人, 其中包含**值**属性, 其中包含具有所有输入数据的对象。</span><span class="sxs-lookup"><span data-stu-id="14fa1-142">**Example Action.Submit**: With Skype, an Action.Submit will send a Bot Framework bot activity back to the bot with the **Value** property containing an object with all of the input data on it.</span></span>

## <a name="learn-more"></a><span data-ttu-id="14fa1-143">了解更多信息</span><span class="sxs-lookup"><span data-stu-id="14fa1-143">Learn More</span></span>

* <span data-ttu-id="14fa1-144">浏览用于灵感的[示例卡](http://adaptivecards.io/samples/)</span><span class="sxs-lookup"><span data-stu-id="14fa1-144">[Browse Sample cards](http://adaptivecards.io/samples/) for inspiration</span></span>
* <span data-ttu-id="14fa1-145">使用[架构资源管理器](http://adaptivecards.io/explorer)浏览可用元素</span><span class="sxs-lookup"><span data-stu-id="14fa1-145">Use the [Schema Explorer](http://adaptivecards.io/explorer) to browse the available elements</span></span>
* <span data-ttu-id="14fa1-146">使用[交互式可视化工具](http://adaptivecards.io/visualizer/)构建卡片</span><span class="sxs-lookup"><span data-stu-id="14fa1-146">Build a card using the [Interactive Visualizer](http://adaptivecards.io/visualizer/)</span></span>
* <span data-ttu-id="14fa1-147">[联系](http://adaptivecards.io/connect)你的任何反馈</span><span class="sxs-lookup"><span data-stu-id="14fa1-147">[Get in touch](http://adaptivecards.io/connect) with any feedback you have</span></span>
