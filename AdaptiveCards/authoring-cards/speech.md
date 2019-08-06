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
# <a name="speech-and-advanced-customization"></a>语音和高级自定义
我们通过 Cortana 等服务在语音交互时代生活。  自适应卡从第一天开始设计, 以支持语音, 实现超酷全新的动手体验方案。

`speak`标记使自适应卡能够传递到视觉对象显示不是主要体验的环境中, 例如, 在推动的情况下为汽车面板。 

## <a name="speak-property"></a>讲述属性
为了支持语音, 我们有`speak`一个属性, 其中包含向用户显示的文本。 文本可以使用语音合成标记语言 ([SSML](https://msdn.microsoft.com/en-us/library/office/hh361578)) 进行批注。 SSML 控制语音的速度、色调和转折点。  它甚至允许您从自己的服务流式传输音频或呈现 TTS 音频流, 为自定义提供了很大的灵活性。

主机应用程序可以通过两种模式来说明属性的用法:

* **送达**时-在交付卡时, 客户端可以选择读取卡的 "朗读" 属性, 以将卡作为一个整体来描述。
* 为支持更丰富的可访问性模型, 架构支持每个元素都有一个口述标记。 客户端可以读取卡中每个元素的 "朗读" 属性。

### <a name="examples"></a>示例

```json
    "speak":"hello world!"

    "speak":"<s>This is sentence 1.</s><s>This is sentence two</s>"

    "speak":"<speak><audio src='https://www.soundjay.com/misc/bell-ringing-04.mp3'/><s>Time to wake up!</s></speak>"
```

## <a name="speech-content-design"></a>语音内容设计

为语音设计的内容不同于为视觉对象显示而设计的内容。 设计卡片时, 您正在设计整个视觉体验, 以便以乐趣的方式向用户显示信息。 设计语音时, 应考虑如何口头方式传达以乐趣用户的方式描述内容。  
