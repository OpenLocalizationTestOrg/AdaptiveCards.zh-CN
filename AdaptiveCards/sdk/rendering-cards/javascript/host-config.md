---
title: 主机配置-JavaScript SDK
author: matthidinger
ms.author: mahiding
ms.date: 11/28/2017
ms.topic: article
ms.openlocfilehash: a011ffc43c2990cd8eb568b9f1c449cf541f9a70
ms.sourcegitcommit: 6889c7e1a38029d965c8f91dc9108819dbdea552
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/31/2019
ms.locfileid: "68732894"
---
# <a name="host-config---javascript"></a>主机配置-JavaScript

```js
// Create an AdaptiveCard instance
var adaptiveCard = new AdaptiveCards.AdaptiveCard();

// Set its hostConfig property unless you want to use the default Host Config
// Host Config defines the style and behavior of a card
adaptiveCard.hostConfig = new AdaptiveCards.HostConfig({
    fontFamily: "Segoe UI, Helvetica Neue, sans-serif"
    // More host config options
});

// Render the card to an HTML element:
var renderedCard = adaptiveCard.render();
```

## <a name="customization"></a>自定义

有三种方法可自定义自适应卡呈现: 
1. 主机配置
2. CSS 样式
3. 自定义元素呈现

### <a name="hostconfig"></a>HostConfig 

[主机配置](../../../rendering-cards/host-config.md)是所有呈现器都理解的共享配置对象。 这允许您定义将由每个平台呈现器自动解释的通用样式 (例如, 字体系列、字体大小、默认间距) 和行为 (例如, 最大操作数)。 

目标是每个平台呈现器生成的本机 UI 看起来非常相似, 只是在您的部分中工作。

```javascript
var renderOptions = {
    ...
    hostConfig: {
        // Define your host config object here
        // See the HostConfig docs for details
    }
};
```