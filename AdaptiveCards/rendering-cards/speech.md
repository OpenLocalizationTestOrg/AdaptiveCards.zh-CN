---
title: 处理语音
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: ea46a1c2c14a4cd2aded9672d7493561bbebbd16
ms.sourcegitcommit: 6889c7e1a38029d965c8f91dc9108819dbdea552
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/31/2019
ms.locfileid: "68732614"
---
# <a name="handling-speech"></a><span data-ttu-id="b15a1-102">处理语音</span><span class="sxs-lookup"><span data-stu-id="b15a1-102">Handling speech</span></span>

<span data-ttu-id="b15a1-103">支持语音自适应卡`speak`包含属性, 该属性包含有关如何向用户高声朗读卡的信息。</span><span class="sxs-lookup"><span data-stu-id="b15a1-103">To support speech adaptive Cards has the `speak` property which contains information on how a card should be read aloud to a user.</span></span>

<span data-ttu-id="b15a1-104">可以使用[SSML 标记](https://msdn.microsoft.com/en-us/library/office/hh361578(v=office.14).aspx)批注语音标记。</span><span class="sxs-lookup"><span data-stu-id="b15a1-104">The speech tag can be annotated using  [SSML markup](https://msdn.microsoft.com/en-us/library/office/hh361578(v=office.14).aspx).</span></span> <span data-ttu-id="b15a1-105">SSML 使你能够控制语音的速度、音调、转折点。</span><span class="sxs-lookup"><span data-stu-id="b15a1-105">SSML gives you the ability control the speed, tone, inflection of the speech.</span></span>  <span data-ttu-id="b15a1-106">它甚至允许你流式传输音频或从你自己的服务呈现 TTS 音频流, 为你提供了大量自定义。</span><span class="sxs-lookup"><span data-stu-id="b15a1-106">It even allows you to stream audio or a render a TTS audio stream from your own service, giving you a great deal of customization.</span></span>

<span data-ttu-id="b15a1-107">主机应用程序可以使用两种模式来说话属性:</span><span class="sxs-lookup"><span data-stu-id="b15a1-107">There are 2 patterns for speak property usage by a host application:</span></span>
* <span data-ttu-id="b15a1-108">**送达**时-当送出卡时, 客户端可以选择读取卡的 "朗读" 属性, 以将卡作为一个整体来描述。</span><span class="sxs-lookup"><span data-stu-id="b15a1-108">**on delivery** - When a card is delivered a client may opt to read the Speak property for the card to describe the card as a whole.</span></span>
* <span data-ttu-id="b15a1-109">**根据需要**, 架构支持每个元素有一个口述标记。</span><span class="sxs-lookup"><span data-stu-id="b15a1-109">**on demand** - In order to support a richer accessibility model the schema supports a speak tag per element.</span></span>  
<span data-ttu-id="b15a1-110">这允许客户端将每个元素读入具有辅助功能要求的收件人。</span><span class="sxs-lookup"><span data-stu-id="b15a1-110">This allows for clients to read each element to recipients with accessibility requirements.</span></span>

