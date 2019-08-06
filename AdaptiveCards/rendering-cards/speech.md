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
# <a name="handling-speech"></a>处理语音

支持语音自适应卡`speak`包含属性, 该属性包含有关如何向用户高声朗读卡的信息。

可以使用[SSML 标记](https://msdn.microsoft.com/en-us/library/office/hh361578(v=office.14).aspx)批注语音标记。 SSML 使你能够控制语音的速度、音调、转折点。  它甚至允许你流式传输音频或从你自己的服务呈现 TTS 音频流, 为你提供了大量自定义。

主机应用程序可以使用两种模式来说话属性:
* **送达**时-当送出卡时, 客户端可以选择读取卡的 "朗读" 属性, 以将卡作为一个整体来描述。
* **根据需要**, 架构支持每个元素有一个口述标记。  
这允许客户端将每个元素读入具有辅助功能要求的收件人。

