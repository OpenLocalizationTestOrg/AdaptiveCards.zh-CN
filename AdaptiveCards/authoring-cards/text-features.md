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
# <a name="text-features"></a><span data-ttu-id="24559-102">文本功能</span><span class="sxs-lookup"><span data-stu-id="24559-102">Text features</span></span>

<span data-ttu-id="24559-103">`TextBlock`提供一些用于设置文本格式和本地化的高级功能。</span><span class="sxs-lookup"><span data-stu-id="24559-103">`TextBlock` offers some advanced features for formatting and localizing the text.</span></span>

## <a name="markdown"></a><span data-ttu-id="24559-104">Markdown</span><span class="sxs-lookup"><span data-stu-id="24559-104">Markdown</span></span>
<span data-ttu-id="24559-105">若要支持内联标记, 自适应卡支持 Markdown 语法的**子集**。</span><span class="sxs-lookup"><span data-stu-id="24559-105">To support inline markup, Adaptive Cards support a **subset** of Markdown syntax.</span></span>

<span data-ttu-id="24559-106">_支持_</span><span class="sxs-lookup"><span data-stu-id="24559-106">_Supported_</span></span>

| <span data-ttu-id="24559-107">文本样式</span><span class="sxs-lookup"><span data-stu-id="24559-107">Text Style</span></span>      | <span data-ttu-id="24559-108">Markdown</span><span class="sxs-lookup"><span data-stu-id="24559-108">Markdown</span></span> |
|-----------------|-----|
| <span data-ttu-id="24559-109">**加粗**</span><span class="sxs-lookup"><span data-stu-id="24559-109">**Bold**</span></span>        | ```**Bold**``` |
| <span data-ttu-id="24559-110">_斜体_</span><span class="sxs-lookup"><span data-stu-id="24559-110">_Italic_</span></span>        | ```_Italic_``` |
| <span data-ttu-id="24559-111">项目符号列表</span><span class="sxs-lookup"><span data-stu-id="24559-111">Bullet list</span></span>     | ```- Item 1\r- Item 2\r- Item 3``` | 
| <span data-ttu-id="24559-112">编号列表</span><span class="sxs-lookup"><span data-stu-id="24559-112">Numbered list</span></span>   | ```1. Green\r2. Orange\r3. Blue``` |
| <span data-ttu-id="24559-113">中超</span><span class="sxs-lookup"><span data-stu-id="24559-113">Hyperlinks</span></span>      | ```[Title](url)``` |

<span data-ttu-id="24559-114">_不支持_</span><span class="sxs-lookup"><span data-stu-id="24559-114">_Not supported_</span></span>

* <span data-ttu-id="24559-115">标头</span><span class="sxs-lookup"><span data-stu-id="24559-115">Headers</span></span>
* <span data-ttu-id="24559-116">表</span><span class="sxs-lookup"><span data-stu-id="24559-116">Tables</span></span>
* <span data-ttu-id="24559-117">映像</span><span class="sxs-lookup"><span data-stu-id="24559-117">Images</span></span>
* <span data-ttu-id="24559-118">不在上表中的任何内容</span><span class="sxs-lookup"><span data-stu-id="24559-118">Anything not in the table above</span></span>

### <a name="markdown-example"></a><span data-ttu-id="24559-119">Markdown 示例</span><span class="sxs-lookup"><span data-stu-id="24559-119">Markdown Example</span></span>

<span data-ttu-id="24559-120">以下有效负载如下所示:</span><span class="sxs-lookup"><span data-stu-id="24559-120">The below payload would render something like this:</span></span>

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

## <a name="datetime-formatting-and-localization"></a><span data-ttu-id="24559-122">日期/时间格式设置和本地化</span><span class="sxs-lookup"><span data-stu-id="24559-122">Date/Time formatting and localization</span></span>

<span data-ttu-id="24559-123">有时你不知道接收卡的用户的时区, 因此, 自适应卡提供`DATE()`和`TIME()`格式化功能以自动本地化目标设备上的时间。</span><span class="sxs-lookup"><span data-stu-id="24559-123">Sometimes you won't know the timezone of the user receiving the card, so Adaptive Cards offers `DATE()` and `TIME()` formatting functions to automatically localize the time on the target device.</span></span>

### <a name="datetime-example"></a><span data-ttu-id="24559-124">日期/时间示例</span><span class="sxs-lookup"><span data-stu-id="24559-124">Date/Time Example</span></span>

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

<span data-ttu-id="24559-125">上面的卡片将显示:</span><span class="sxs-lookup"><span data-stu-id="24559-125">The above card will display:</span></span> 

> <span data-ttu-id="24559-126">**你的包将于2017年2月14日星期二上午6:00**</span><span class="sxs-lookup"><span data-stu-id="24559-126">**Your package will arrive on Tue, Feb 14th, 2017 at 6:00 AM**</span></span>

### <a name="datetime-function-rules"></a><span data-ttu-id="24559-127">日期/时间函数规则</span><span class="sxs-lookup"><span data-stu-id="24559-127">Date/Time function rules</span></span>

<span data-ttu-id="24559-128">有一些规则可以在每个平台上正确解释日期/时间函数。</span><span class="sxs-lookup"><span data-stu-id="24559-128">There are some rules to properly interpret the the date/time functions on every platform.</span></span> <span data-ttu-id="24559-129">如果不满足规则, 则会向用户显示原始字符串, 而不需要任何人。</span><span class="sxs-lookup"><span data-stu-id="24559-129">If the rules aren't met then the raw string will be displayed to the user, and no one wants that.</span></span>

1. <span data-ttu-id="24559-130">**区分大小写**(必须全部大写)</span><span class="sxs-lookup"><span data-stu-id="24559-130">**CASE SENSITIVE** (must be all caps)</span></span>
1. <span data-ttu-id="24559-131">`{{`  、`}}`或括号之间没有空格</span><span class="sxs-lookup"><span data-stu-id="24559-131">**NO SPACES** between the `{{`, `}}`, or parentheses</span></span>
1. <span data-ttu-id="24559-132">**严格[RFC 3389](https://tools.ietf.org/html/rfc3339)格式**(请参阅以下示例)</span><span class="sxs-lookup"><span data-stu-id="24559-132">**STRICT [RFC 3389](https://tools.ietf.org/html/rfc3339) FORMATTING** (See examples below)</span></span>
1. <span data-ttu-id="24559-133">**必须为**有效的日期和时间</span><span class="sxs-lookup"><span data-stu-id="24559-133">**MUST BE** a valid date and time</span></span>

### <a name="valid-formats"></a><span data-ttu-id="24559-134">有效的格式</span><span class="sxs-lookup"><span data-stu-id="24559-134">Valid formats</span></span>

* `2017-02-14T06:08:00Z`
* `2017-02-14T06:08:00-07:00`
* `2017-02-14T06:08:00+07:00`

### <a name="date-formatting-param"></a><span data-ttu-id="24559-135">日期格式参数</span><span class="sxs-lookup"><span data-stu-id="24559-135">Date formatting param</span></span>

<span data-ttu-id="24559-136">对于日期, 可以指定一个可选的参数来设置输出的格式。</span><span class="sxs-lookup"><span data-stu-id="24559-136">For dates, an optional param may be specified to format the output.</span></span>


|       <span data-ttu-id="24559-137">格式</span><span class="sxs-lookup"><span data-stu-id="24559-137">Format</span></span>        |            <span data-ttu-id="24559-138">示例</span><span class="sxs-lookup"><span data-stu-id="24559-138">Example</span></span>            |
|---------------------|-------------------------------|
| <span data-ttu-id="24559-139">`COMPACT`缺省值</span><span class="sxs-lookup"><span data-stu-id="24559-139">`COMPACT` (Default)</span></span> |          <span data-ttu-id="24559-140">"2/13/2017"</span><span class="sxs-lookup"><span data-stu-id="24559-140">"2/13/2017"</span></span>          |
|       `SHORT`       |     <span data-ttu-id="24559-141">"周一至年2月13日, 2017"</span><span class="sxs-lookup"><span data-stu-id="24559-141">"Mon, Feb 13th, 2017"</span></span>     |
|       `LONG`        | <span data-ttu-id="24559-142">"星期一, 2017 年2月13日</span><span class="sxs-lookup"><span data-stu-id="24559-142">"Monday, February 13th, 2017"</span></span> |

