---
title: 主机配置-iOS SDK
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: 34d28ef0f0cd7200965fb6967bb2f252f6a47456
ms.sourcegitcommit: 6889c7e1a38029d965c8f91dc9108819dbdea552
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/31/2019
ms.locfileid: "68732929"
---
# <a name="host-config---ios"></a>主机配置-iOS

可以通过 JSON 字符串生成的 HostConfig 配置主机

```objective-c
ACOParseResult *hostconfigParseResult = [ACOHostConfig FromJson:self.hostconfig];
```

可以实例化默认 HostConfig

```objective-c
ACOHostConfig *defaultConfig = [[ACHostConfig alloc] init];
```

## <a name="render-a-card-using-host-config"></a>使用主机配置呈现卡

Rederer 采用自适应卡和主机配置。HostConfig 可以为 nil, 如果为 nil, 则使用默认值。

```objective-c
ACRRenderResult *renderResult;
renderResult = [ACRRenderer render:cardParseResult.card
                            config:hostconfigParseResult.config
                   widthConstraint:300.0];
```