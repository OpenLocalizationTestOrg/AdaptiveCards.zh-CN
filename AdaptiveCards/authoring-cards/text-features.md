---
title: 文本功能
author: matthidinger
ms.author: mahiding
ms.date: 11/09/2017
ms.topic: article
ms.openlocfilehash: f7ea40b80df4d976c0a8a86b15254018fdf2fac6
ms.sourcegitcommit: 6889c7e1a38029d965c8f91dc9108819dbdea552
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/31/2019
ms.locfileid: "68732669"
---
# <a name="text-features"></a>文本功能

`TextBlock`提供一些用于设置文本格式和本地化的高级功能。

## <a name="markdown"></a>Markdown
若要支持内联标记, 自适应卡支持 Markdown 语法的**子集**。

_支持_

| 文本样式      | Markdown |
|-----------------|-----|
| **加粗**        | ```**Bold**``` |
| _斜体_        | ```_Italic_``` |
| 项目符号列表     | ```- Item 1\r- Item 2\r- Item 3``` | 
| 编号列表   | ```1. Green\r2. Orange\r3. Blue``` |
| 中超      | ```[Title](url)``` |

_不支持_

* 标头
* 表
* 映像
* 不在上表中的任何内容

### <a name="markdown-example"></a>Markdown 示例

以下有效负载如下所示:

![markdown 屏幕快照](media/text-features/markdown.png)

```json
{
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": [
        {
            "type": "TextBlock",
            "text": "This is some **bold** text"
        },
        {
            "type": "TextBlock",
            "text": "This is some _italic_ text"
        },
        {
            "type": "TextBlock",
            "text": "- Bullet \r- List \r",
            "wrap": true
        },
        {
            "type": "TextBlock",
            "text": "1. Numbered\r2. List\r",
            "wrap": true
        },
        {
            "type": "TextBlock",
            "text": "Check out [Adaptive Cards](http://adaptivecards.io)"
        }
    ]
}
```

## <a name="datetime-formatting-and-localization"></a>日期/时间格式设置和本地化

有时你不知道接收卡的用户的时区, 因此, 自适应卡提供`DATE()`和`TIME()`格式化功能以自动本地化目标设备上的时间。

### <a name="datetime-example"></a>日期/时间示例

```json
{
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": [
        {
            "type": "TextBlock",
            "text": "Your package will arrive on {{DATE(2017-02-14T06:00:00Z, SHORT)}} at {{TIME(2017-02-14T06:00:00Z)}}",
            "wrap": true
        }
    ]
}
```

上面的卡片将显示: 

> **你的包将于2017年2月14日星期二上午6:00**

### <a name="datetime-function-rules"></a>日期/时间函数规则

有一些规则可以在每个平台上正确解释日期/时间函数。 如果不满足规则, 则会向用户显示原始字符串, 而不需要任何人。

1. **区分大小写**(必须全部大写)
1. `{{`  、`}}`或括号之间没有空格
1. **严格[RFC 3389](https://tools.ietf.org/html/rfc3339)格式**(请参阅以下示例)
1. **必须为**有效的日期和时间

### <a name="valid-formats"></a>有效的格式

* `2017-02-14T06:08:00Z`
* `2017-02-14T06:08:00-07:00`
* `2017-02-14T06:08:00+07:00`

### <a name="date-formatting-param"></a>日期格式参数

对于日期, 可以指定一个可选的参数来设置输出的格式。


|       格式        |            示例            |
|---------------------|-------------------------------|
| `COMPACT`缺省值 |          "2/13/2017"          |
|       `SHORT`       |     "周一至年2月13日, 2017"     |
|       `LONG`        | "星期一, 2017 年2月13日 |

