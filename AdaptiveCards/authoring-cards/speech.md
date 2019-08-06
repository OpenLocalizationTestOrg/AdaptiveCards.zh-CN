---
title: 语音和高级自定义
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: 468d090dff0511f40cb7e5eedc4f4a18fa12aa3c
ms.sourcegitcommit: 6889c7e1a38029d965c8f91dc9108819dbdea552
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/31/2019
ms.locfileid: "68732664"
---
# <a name="speech-and-advanced-customization"></a><span data-ttu-id="f5c10-102">语音和高级自定义</span><span class="sxs-lookup"><span data-stu-id="f5c10-102">Speech and advanced customization</span></span>
<span data-ttu-id="f5c10-103">我们通过 Cortana 等服务在语音交互时代生活。</span><span class="sxs-lookup"><span data-stu-id="f5c10-103">We live in an era of speech interaction via services like Cortana.</span></span>  <span data-ttu-id="f5c10-104">自适应卡从第一天开始设计, 以支持语音, 实现超酷全新的动手体验方案。</span><span class="sxs-lookup"><span data-stu-id="f5c10-104">Adaptive cards are designed from day one to support speech, enabling cool new hands-full scenarios.</span></span>

<span data-ttu-id="f5c10-105">`speak`标记使自适应卡能够传递到视觉对象显示不是主要体验的环境中, 例如, 在推动的情况下为汽车面板。</span><span class="sxs-lookup"><span data-stu-id="f5c10-105">The `speak` tag enables the adaptive card to be delivered to an environment where a visual display is not primary experience, such as to a car dashboard while driving.</span></span> 

## <a name="speak-property"></a><span data-ttu-id="f5c10-106">讲述属性</span><span class="sxs-lookup"><span data-stu-id="f5c10-106">Speak property</span></span>
<span data-ttu-id="f5c10-107">为了支持语音, 我们有`speak`一个属性, 其中包含向用户显示的文本。</span><span class="sxs-lookup"><span data-stu-id="f5c10-107">To support speech we have a `speak` property which contains text to say to the user.</span></span> <span data-ttu-id="f5c10-108">文本可以使用语音合成标记语言 ([SSML](https://msdn.microsoft.com/en-us/library/office/hh361578)) 进行批注。</span><span class="sxs-lookup"><span data-stu-id="f5c10-108">The text can be annotated using speech synthesis markup language ([SSML](https://msdn.microsoft.com/en-us/library/office/hh361578)).</span></span> <span data-ttu-id="f5c10-109">SSML 控制语音的速度、色调和转折点。</span><span class="sxs-lookup"><span data-stu-id="f5c10-109">SSML controls the speed, tone, and inflection of the speech.</span></span>  <span data-ttu-id="f5c10-110">它甚至允许您从自己的服务流式传输音频或呈现 TTS 音频流, 为自定义提供了很大的灵活性。</span><span class="sxs-lookup"><span data-stu-id="f5c10-110">It even allows you to stream audio or a render a TTS audio stream from your own service, giving you a great deal of flexibility for customization.</span></span>

<span data-ttu-id="f5c10-111">主机应用程序可以通过两种模式来说明属性的用法:</span><span class="sxs-lookup"><span data-stu-id="f5c10-111">There are two patterns for speak property usage by a host application:</span></span>

* <span data-ttu-id="f5c10-112">**送达**时-在交付卡时, 客户端可以选择读取卡的 "朗读" 属性, 以将卡作为一个整体来描述。</span><span class="sxs-lookup"><span data-stu-id="f5c10-112">**On delivery** - When a card is delivered, the client may opt to read the Speak property for the card to describe the card as a whole.</span></span>
* <span data-ttu-id="f5c10-113">为支持更丰富的可访问性模型, 架构支持每个元素都有一个口述标记。</span><span class="sxs-lookup"><span data-stu-id="f5c10-113">**On demand** - In order to support a richer accessibility model, the schema supports a speak tag for each element.</span></span> <span data-ttu-id="f5c10-114">客户端可以读取卡中每个元素的 "朗读" 属性。</span><span class="sxs-lookup"><span data-stu-id="f5c10-114">The client may read a Speak property  for each element in the card.</span></span>

### <a name="examples"></a><span data-ttu-id="f5c10-115">示例</span><span class="sxs-lookup"><span data-stu-id="f5c10-115">Examples</span></span>

```json
    "speak":"hello world!"

    "speak":"<s>This is sentence 1.</s><s>This is sentence two</s>"

    "speak":"<speak><audio src='https://www.soundjay.com/misc/bell-ringing-04.mp3'/><s>Time to wake up!</s></speak>"
```

## <a name="speech-content-design"></a><span data-ttu-id="f5c10-116">语音内容设计</span><span class="sxs-lookup"><span data-stu-id="f5c10-116">Speech content design</span></span>

<span data-ttu-id="f5c10-117">为语音设计的内容不同于为视觉对象显示而设计的内容。</span><span class="sxs-lookup"><span data-stu-id="f5c10-117">Content designed for speech is different from content designed for visual display.</span></span> <span data-ttu-id="f5c10-118">设计卡片时, 您正在设计整个视觉体验, 以便以乐趣的方式向用户显示信息。</span><span class="sxs-lookup"><span data-stu-id="f5c10-118">When you design a card, you are designing an entire visual experience to present information to a user in a way that delights them.</span></span> <span data-ttu-id="f5c10-119">设计语音时, 应考虑如何口头方式传达以乐趣用户的方式描述内容。</span><span class="sxs-lookup"><span data-stu-id="f5c10-119">When designing for speech, you should think about how to verbally describe the content in a way that delights the user.</span></span>  
