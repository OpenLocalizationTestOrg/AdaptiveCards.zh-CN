---
title: 呈现器状态
author: matthidinger
ms.author: mahiding
ms.date: 10/12/2018
ms.topic: article
ms.openlocfilehash: 63426b2250407cc40af8c46975c10f57d1028a40
ms.sourcegitcommit: 6889c7e1a38029d965c8f91dc9108819dbdea552
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/31/2019
ms.locfileid: "68733084"
---
# <a name="renderer-status"></a>呈现器状态
下表显示了每个呈现器的当前状态 (基于其公开发布的版本)。

### <a name="parsing"></a>分析

|功能 | HTML | .NET | UWP | iOS | Android |
|--- | --- | --- | --- | --- | --- | --- |
|返回验证失败 | ✅ | ✅ | ✅ | ✅ | ✅ |
|分析未知属性 | ✅ | ✅ | ✅ | ✅ | ✅ |

### <a name="card-rendering"></a>卡片呈现

|功能 | HTML | .NET | UWP | iOS | Android |
|--- | --- | --- | --- | --- | --- | --- |
|检查支持的版本 | ✅ | ✅ | ✅ | ✅ | ✅  |
|呈现完整架构 | ✅ | ✅ | ✅ | ✅ | ✅ |
|呈现操作栏 | ✅ | ✅ | ✅ | ✅ | ✅ |
|忽略未知元素 | ✅ | ✅ | ✅ | ✅ | ✅ |
|主机配置支持 | ✅ | ✅ | ✅ | ✅ | ✅ |
|本机平台样式 | ✅ | ✅ | ✅ | ✅ | ✅ |

### <a name="element-rendering"></a>元素呈现

|功能 | HTML | .NET | UWP | iOS | Android |
|--- | --- | --- | --- | --- | --- | --- |
|间距和分隔符 | ✅ | ✅ | ✅ | ✅ | ✅ |
|[TextBlock 日期/时间格式](../authoring-cards/text-features.md#datetime-formatting-and-localization) | ✅ | ✅ | ✅ | ✅ | ✅ |
|[TextBlock Markdown 支持](../authoring-cards/text-features.md#markdown) | ✅* | ✅ | ✅ | ✅ | ✅ |
|完整输入支持 | ✅ | ✅ | ✅ | ✅ | ✅ |

\*HTML 呈现器不包含内置的 Markdown 支持, 以便最大限度地减少库大小, 并让应用程序使用其首选的 Markdown 处理器。 但 HTML 呈现器将自动使用 Markdown-如果已加载它, 则为。

### <a name="extensibility"></a>扩展性

|功能 | HTML | .NET | UWP | iOS | Android |
|--- | --- | --- | --- | --- | --- | --- |
|重写元素呈现器 | ✅ | ✅ | ✅ | ✅ | ✅ |
|添加新元素呈现器 | ✅ | ✅ | ✅ | ✅ | ✅ |
|删除元素呈现器 | ✅ | ✅ | ✅ | ✅ | ✅ |
|[重写/添加/删除操作呈现器](https://github.com/Microsoft/AdaptiveCards/issues/1671) | ✅ | ✅ | ❌ | ✅ | ✅ |

### <a name="actions"></a>操作

| 功能 | HTML | .NET | UWP | iOS | Android |
|--- | --- | --- | --- | --- | --- | --- |
| OpenUrl 支持 | ✅ | ✅ | ✅ | ✅ | ✅  |
| ShowCard 支持  | ✅ | ✅ | ✅ | ✅ | ✅ |
| 操作。提交支持  | ✅ | ✅ | ✅ | ✅ | ✅  |
| selectAction 支持 | ✅ | ✅ | ✅ | ✅ | ✅ |

### <a name="events"></a>事件

|       功能        | HTML | .NET | UWP | iOS | Android | 
|----------------------------|------|------|-----|-----|---------|
| 元素可见性已更改 |  ✅   |  ❌   |  ❌  |  ❌  | ❌ |

