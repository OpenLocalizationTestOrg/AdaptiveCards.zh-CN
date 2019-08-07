---
title: JavaScript SDK
author: matthidinger
ms.author: mahiding
ms.date: 11/28/2017
ms.topic: article
ms.openlocfilehash: 55360658d74ca384b0e6090631a7f5db463e968a
ms.sourcegitcommit: 6889c7e1a38029d965c8f91dc9108819dbdea552
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/31/2019
ms.locfileid: "68732904"
---
# <a name="getting-started---javascript"></a>入门-JavaScript

正如我们在[入门](../../../authoring-cards/getting-started.md)"页中所述, 自适应卡是 JSON 序列化的卡对象模型。 这是用于在浏览器中生成客户端 HTML 的 JavaScript SDK。

> [!IMPORTANT]
> **V 0.5 中的重大更改**
> 
> 1. 包已从`microsoft-adaptivecards`重命名为`adaptivecards`
> 1. 静态`AdaptiveCards.setHostConfig()`已移动到的实例`AdaptiveCard`成员。 例如,`myCard.hostConfig = {}` 
> 1. `HostConfig`已离开各种重命名和移动。 请参阅当前结构的[示例 json](https://github.com/Microsoft/AdaptiveCards/blob/master/samples/HostConfig/sample.json)主机配置
> 1. 前面的0.5 个预览中也有一些架构更改,[这里概述](https://github.com/Microsoft/AdaptiveCards/pull/633)了这些更改
> 1. 已删除`renderCard()`静态函数, 因为它与类方法冗余。 如下`adaptiveCard.render()`所述使用。 


## <a name="install"></a>安装

### <a name="node"></a>节点

[![npm 安装](https://img.shields.io/npm/v/adaptivecards.svg)](https://www.npmjs.com/package/adaptivecards)

```console
npm install adaptivecards --save
```

### <a name="cdn"></a>CDN

```html
<script src="https://unpkg.com/adaptivecards/dist/adaptivecards.js"></script>
```

## <a name="usage"></a>用法

### <a name="import-the-module"></a>导入模块

```js
// import the module
import * as AdaptiveCards from "adaptivecards";

// or require it
var AdaptiveCards = require("adaptivecards");

// or use the global variable if loaded from CDN
AdaptiveCards.renderCard(...);
```

## <a name="next-steps"></a>后续步骤

有关后续步骤, 请参阅[渲染卡](render-a-card.md)!
