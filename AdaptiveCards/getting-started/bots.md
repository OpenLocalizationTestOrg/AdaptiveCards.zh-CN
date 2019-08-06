---
title: 适用于机器人开发人员的自适应卡
author: matthidinger
ms.author: mahiding
ms.date: 05/30/2018
ms.topic: article
ms.openlocfilehash: a50f2e6f145ae2c4571d6b20b61b9ad182ca7ba5
ms.sourcegitcommit: 6889c7e1a38029d965c8f91dc9108819dbdea552
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/31/2019
ms.locfileid: "68733164"
---
# <a name="adaptive-cards-for-bot-developers"></a><span data-ttu-id="5b1aa-102">适用于机器人开发人员的自适应卡</span><span class="sxs-lookup"><span data-stu-id="5b1aa-102">Adaptive Cards for Bot Developers</span></span>

<span data-ttu-id="5b1aa-103">自适应卡非常适合机器人。</span><span class="sxs-lookup"><span data-stu-id="5b1aa-103">Adaptive Cards are a great fit for Bots.</span></span> <span data-ttu-id="5b1aa-104">它们允许你创作卡片一次, 并使其在多个应用 (如 Microsoft 团队、你自己的网站等) 中呈现完美。</span><span class="sxs-lookup"><span data-stu-id="5b1aa-104">They let you author a card once and have it render beautifully inside multiple apps, like  Microsoft Teams, your own website, and more.</span></span>

> [!NOTE]
> <span data-ttu-id="5b1aa-105">当前预览不支持 Skype。</span><span class="sxs-lookup"><span data-stu-id="5b1aa-105">Skype is not supported in the current preview.</span></span> <span data-ttu-id="5b1aa-106">查看最新的 "[合作伙伴状态](../resources/partners.md)" 页。</span><span class="sxs-lookup"><span data-stu-id="5b1aa-106">See the [Partner Status](../resources/partners.md) page for the latest.</span></span>

## <a name="try-it-out"></a><span data-ttu-id="5b1aa-107">试用</span><span class="sxs-lookup"><span data-stu-id="5b1aa-107">Try it out</span></span>

<span data-ttu-id="5b1aa-108">单击下面的链接, 并[与我们的 Scuba 机器人联系](http://contososcubademo.azurewebsites.net/)。</span><span class="sxs-lookup"><span data-stu-id="5b1aa-108">Click the following link and [talk to our Scuba Bot](http://contososcubademo.azurewebsites.net/).</span></span> <span data-ttu-id="5b1aa-109">说`I'm looking for scuba`到, 它将帮助您预订梦想的 scuba 行程。</span><span class="sxs-lookup"><span data-stu-id="5b1aa-109">Say `I'm looking for scuba` and it'll help you book the scuba trip of your dreams.</span></span>  

<span data-ttu-id="5b1aa-110">所有机器人的响应都是通过自适应卡创建的。</span><span class="sxs-lookup"><span data-stu-id="5b1aa-110">All of the bot's responses are created with Adaptive Cards.</span></span>

<span data-ttu-id="5b1aa-111">[![Scuba 聊天屏幕快照](media/bots/scuba-chat.png)](http://contososcubademo.azurewebsites.net/)</span><span class="sxs-lookup"><span data-stu-id="5b1aa-111">[![Scuba chat screenshot](media/bots/scuba-chat.png)](http://contososcubademo.azurewebsites.net/)</span></span>

<span data-ttu-id="5b1aa-112">**获取代码**: GitHub 上](https://github.com/matthidinger/ContosoScubaBot
)可以[找到完整的 Contoso Scuba 机器人源代码。</span><span class="sxs-lookup"><span data-stu-id="5b1aa-112">**Get the code**: the full [Contoso Scuba Bot source code](https://github.com/matthidinger/ContosoScubaBot
) can be found on GitHub.</span></span>


## <a name="bot-framework-integration"></a><span data-ttu-id="5b1aa-113">机器人框架集成</span><span class="sxs-lookup"><span data-stu-id="5b1aa-113">Bot Framework Integration</span></span>

<span data-ttu-id="5b1aa-114">使用[Bot 框架](https://dev.botframework.com/), 你可以编写能够跨多个 "渠道" (如 Skype、Microsoft 团队、Facebook Messenger 等) 与用户聊天的单个机器人。</span><span class="sxs-lookup"><span data-stu-id="5b1aa-114">With the [Bot Framework](https://dev.botframework.com/) you can write a single bot that is able to chat with users across multiple "channels", like Skype, Microsoft Teams, Facebook Messenger, etc.</span></span>

## <a name="walkthrough"></a><span data-ttu-id="5b1aa-115">演练</span><span class="sxs-lookup"><span data-stu-id="5b1aa-115">Walkthrough</span></span>

<span data-ttu-id="5b1aa-116">将自适应卡添加到机器人非常直接。</span><span class="sxs-lookup"><span data-stu-id="5b1aa-116">It's pretty straight forward to add an Adaptive Card to your bot.</span></span>

### <a name="step-0-start-with-a-basic-message"></a><span data-ttu-id="5b1aa-117">步骤 0：开始使用基本消息</span><span class="sxs-lookup"><span data-stu-id="5b1aa-117">Step 0: Start with a basic message</span></span>

<span data-ttu-id="5b1aa-118">下面是可传递到任何`message`通道并向用户显示文本的标准机器人框架有效负载。</span><span class="sxs-lookup"><span data-stu-id="5b1aa-118">Here's a standard Bot Framework `message` payload that can be delivered to any channel and display text to the user.</span></span>

```json
{
   "type": "message",
   "text": "Plain text is ok, but sometimes I long for more..."
}
```

### <a name="step-1-add-an-adaptive-card-attachment"></a><span data-ttu-id="5b1aa-119">步骤 1：添加自适应卡`attachment`</span><span class="sxs-lookup"><span data-stu-id="5b1aa-119">Step 1: Add an Adaptive Card `attachment`</span></span>

<span data-ttu-id="5b1aa-120">为了增加一些比文本更丰富的内容, 机器人框架具有的`attachments`概念。</span><span class="sxs-lookup"><span data-stu-id="5b1aa-120">To add some richness beyond just text, the Bot Framework has a concept of `attachments`.</span></span> 

<span data-ttu-id="5b1aa-121">接下来, 附加显示自定义文本的自适应卡。</span><span class="sxs-lookup"><span data-stu-id="5b1aa-121">Let's attach an Adaptive Card that displays custom text.</span></span>

![基本自适应卡](media/bots/hello-adaptivecards.png)

```json
{
  "type": "message",
  "text": "Plain text is ok, but sometimes I long for more...",
  "attachments": [
    {
      "contentType": "application/vnd.microsoft.card.adaptive",
      "content": {
        "type": "AdaptiveCard",
        "version": "1.0",
        "body": [
          {
            "type": "TextBlock",
            "text": "Hello World!",
            "size": "large"
          },
          {
            "type": "TextBlock",
            "text": "*Sincerely yours,*"
          },
          {
            "type": "TextBlock",
            "text": "Adaptive Cards",
            "separation": "none"
          }
        ],
        "actions": [
          {
            "type": "Action.OpenUrl",
            "url": "http://adaptivecards.io",
            "title": "Learn More"
          }
        ]
      }
    }
  ]
}
```

### <a name="step-2-build-even-richer-cards"></a><span data-ttu-id="5b1aa-123">步骤 2：构建更丰富的卡</span><span class="sxs-lookup"><span data-stu-id="5b1aa-123">Step 2: Build even richer cards</span></span> 

<span data-ttu-id="5b1aa-124">自适应卡提供的不仅仅是可自定义的文本。</span><span class="sxs-lookup"><span data-stu-id="5b1aa-124">Adaptive Cards offer much more than just customizable text.</span></span> 

<span data-ttu-id="5b1aa-125">你可以：</span><span class="sxs-lookup"><span data-stu-id="5b1aa-125">You can:</span></span> 

* <span data-ttu-id="5b1aa-126">添加`Images`到卡</span><span class="sxs-lookup"><span data-stu-id="5b1aa-126">Add `Images` to your card</span></span>
* <span data-ttu-id="5b1aa-127">通过和组织你`Containers`的内容`Columns`</span><span class="sxs-lookup"><span data-stu-id="5b1aa-127">Organize your content with `Containers` and `Columns`</span></span>
* <span data-ttu-id="5b1aa-128">添加多个类型的`Actions`</span><span class="sxs-lookup"><span data-stu-id="5b1aa-128">Add multiple types of `Actions`</span></span>
* <span data-ttu-id="5b1aa-129">从`Input`用户收集</span><span class="sxs-lookup"><span data-stu-id="5b1aa-129">Collect `Input` from your users</span></span>
* <span data-ttu-id="5b1aa-130">有一个卡`show another card`</span><span class="sxs-lookup"><span data-stu-id="5b1aa-130">Have one card `show another card`</span></span>
* <span data-ttu-id="5b1aa-131">[查看完整的架构资源管理器](http://adaptivecards.io/explorer/)!</span><span class="sxs-lookup"><span data-stu-id="5b1aa-131">[Check out the full schema explorer](http://adaptivecards.io/explorer/)!</span></span> 

## <a name="platform-sdks"></a><span data-ttu-id="5b1aa-132">平台 Sdk</span><span class="sxs-lookup"><span data-stu-id="5b1aa-132">Platform SDKs</span></span>

<span data-ttu-id="5b1aa-133">如果你的机器人是使用 .NET 或 NodeJS 开发的, 我们有了一些库来构建自适应卡。</span><span class="sxs-lookup"><span data-stu-id="5b1aa-133">If your bot is developed using .NET or NodeJS we have libraries to make building Adaptive Cards even easier.</span></span>

<span data-ttu-id="5b1aa-134">平台</span><span class="sxs-lookup"><span data-stu-id="5b1aa-134">Platform</span></span>|<span data-ttu-id="5b1aa-135">安装</span><span class="sxs-lookup"><span data-stu-id="5b1aa-135">Install</span></span>|<span data-ttu-id="5b1aa-136">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="5b1aa-136">Learn more</span></span>
--------|-------|----------
<span data-ttu-id="5b1aa-137">.NET</span><span class="sxs-lookup"><span data-stu-id="5b1aa-137">.NET</span></span> | `Install-Package AdaptiveCards -IncludePrerelease` | [<span data-ttu-id="5b1aa-138">Bot Framework .NET 文档</span><span class="sxs-lookup"><span data-stu-id="5b1aa-138">Bot Framework .NET Docs</span></span>](https://docs.microsoft.com/en-us/bot-framework/dotnet/bot-builder-dotnet-add-rich-card-attachments)
<span data-ttu-id="5b1aa-139">NodeJS</span><span class="sxs-lookup"><span data-stu-id="5b1aa-139">NodeJS</span></span> | `npm install adaptivecards` | [<span data-ttu-id="5b1aa-140">机器人 Framework NodeJS 文档</span><span class="sxs-lookup"><span data-stu-id="5b1aa-140">Bot Framework NodeJS Docs</span></span>](https://docs.microsoft.com/en-us/bot-framework/nodejs/bot-builder-nodejs-send-rich-cards)


## <a name="channel-status"></a><span data-ttu-id="5b1aa-141">通道状态</span><span class="sxs-lookup"><span data-stu-id="5b1aa-141">Channel status</span></span>

<span data-ttu-id="5b1aa-142">机器人框架允许将机器人发布到多个通道。</span><span class="sxs-lookup"><span data-stu-id="5b1aa-142">The Bot Framework lets you publish your bot to multiple channels.</span></span> <span data-ttu-id="5b1aa-143">我们正在使用各种渠道为自适应卡提供完全支持。</span><span class="sxs-lookup"><span data-stu-id="5b1aa-143">We're working with various channels to provide full support for Adaptive Cards.</span></span> <span data-ttu-id="5b1aa-144">查看最新的 "[合作伙伴状态](../resources/partners.md)" 页。</span><span class="sxs-lookup"><span data-stu-id="5b1aa-144">See the [Partner Status](../resources/partners.md) page for the latest.</span></span>


## <a name="dive-in"></a><span data-ttu-id="5b1aa-145">深入了解!</span><span class="sxs-lookup"><span data-stu-id="5b1aa-145">Dive in!</span></span>

<span data-ttu-id="5b1aa-146">我们只是在本教程中对表面进行了简要介绍, 因此, 请查看以下链接, 以了解自适应卡如何增强机器人的更多方法。</span><span class="sxs-lookup"><span data-stu-id="5b1aa-146">We've just scratched the surface in this tutorial, so please take a look at the links below to explore more ways that Adaptive Cards can enhance your bot.</span></span>

* <span data-ttu-id="5b1aa-147">浏览用于灵感的[示例卡](http://adaptivecards.io/samples/)</span><span class="sxs-lookup"><span data-stu-id="5b1aa-147">[Browse Sample cards](http://adaptivecards.io/samples/) for inspiration</span></span>
* <span data-ttu-id="5b1aa-148">使用 "[架构资源管理器](http://adaptivecards.io/explorer)" 了解可用元素</span><span class="sxs-lookup"><span data-stu-id="5b1aa-148">Use the [Schema Explorer](http://adaptivecards.io/explorer) to learn the available elements</span></span>
* <span data-ttu-id="5b1aa-149">使用[交互式可视化工具](http://adaptivecards.io/visualizer/index.html?hostApp=Skype)构建卡片</span><span class="sxs-lookup"><span data-stu-id="5b1aa-149">Build a card using the [Interactive Visualizer](http://adaptivecards.io/visualizer/index.html?hostApp=Skype)</span></span>
* <span data-ttu-id="5b1aa-150">[联系](http://adaptivecards.io/connect)你的任何反馈</span><span class="sxs-lookup"><span data-stu-id="5b1aa-150">[Get in touch](http://adaptivecards.io/connect) with any feedback you have</span></span>
