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
# <a name="adaptive-cards-for-bot-developers"></a>适用于机器人开发人员的自适应卡

自适应卡非常适合机器人。 它们允许你创作卡片一次, 并使其在多个应用 (如 Microsoft 团队、你自己的网站等) 中呈现完美。

> [!NOTE]
> 当前预览不支持 Skype。 查看最新的 "[合作伙伴状态](../resources/partners.md)" 页。

## <a name="try-it-out"></a>试用

单击下面的链接, 并[与我们的 Scuba 机器人联系](http://contososcubademo.azurewebsites.net/)。 说`I'm looking for scuba`到, 它将帮助您预订梦想的 scuba 行程。  

所有机器人的响应都是通过自适应卡创建的。

[![Scuba 聊天屏幕快照](media/bots/scuba-chat.png)](http://contososcubademo.azurewebsites.net/)

**获取代码**: GitHub 上](https://github.com/matthidinger/ContosoScubaBot
)可以[找到完整的 Contoso Scuba 机器人源代码。


## <a name="bot-framework-integration"></a>机器人框架集成

使用[Bot 框架](https://dev.botframework.com/), 你可以编写能够跨多个 "渠道" (如 Skype、Microsoft 团队、Facebook Messenger 等) 与用户聊天的单个机器人。

## <a name="walkthrough"></a>演练

将自适应卡添加到机器人非常直接。

### <a name="step-0-start-with-a-basic-message"></a>步骤 0：开始使用基本消息

下面是可传递到任何`message`通道并向用户显示文本的标准机器人框架有效负载。

```json
{
   "type": "message",
   "text": "Plain text is ok, but sometimes I long for more..."
}
```

### <a name="step-1-add-an-adaptive-card-attachment"></a>步骤 1：添加自适应卡`attachment`

为了增加一些比文本更丰富的内容, 机器人框架具有的`attachments`概念。 

接下来, 附加显示自定义文本的自适应卡。

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

### <a name="step-2-build-even-richer-cards"></a>步骤 2：构建更丰富的卡 

自适应卡提供的不仅仅是可自定义的文本。 

你可以： 

* 添加`Images`到卡
* 通过和组织你`Containers`的内容`Columns`
* 添加多个类型的`Actions`
* 从`Input`用户收集
* 有一个卡`show another card`
* [查看完整的架构资源管理器](http://adaptivecards.io/explorer/)! 

## <a name="platform-sdks"></a>平台 Sdk

如果你的机器人是使用 .NET 或 NodeJS 开发的, 我们有了一些库来构建自适应卡。

平台|安装|了解详细信息
--------|-------|----------
.NET | `Install-Package AdaptiveCards -IncludePrerelease` | [Bot Framework .NET 文档](https://docs.microsoft.com/en-us/bot-framework/dotnet/bot-builder-dotnet-add-rich-card-attachments)
NodeJS | `npm install adaptivecards` | [机器人 Framework NodeJS 文档](https://docs.microsoft.com/en-us/bot-framework/nodejs/bot-builder-nodejs-send-rich-cards)


## <a name="channel-status"></a>通道状态

机器人框架允许将机器人发布到多个通道。 我们正在使用各种渠道为自适应卡提供完全支持。 查看最新的 "[合作伙伴状态](../resources/partners.md)" 页。


## <a name="dive-in"></a>深入了解!

我们只是在本教程中对表面进行了简要介绍, 因此, 请查看以下链接, 以了解自适应卡如何增强机器人的更多方法。

* 浏览用于灵感的[示例卡](http://adaptivecards.io/samples/)
* 使用 "[架构资源管理器](http://adaptivecards.io/explorer)" 了解可用元素
* 使用[交互式可视化工具](http://adaptivecards.io/visualizer/index.html?hostApp=Skype)构建卡片
* [联系](http://adaptivecards.io/connect)你的任何反馈
