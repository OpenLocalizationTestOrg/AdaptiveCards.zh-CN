---
title: 本机样式设置-Android SDK
author: bekao
ms.author: bekao
ms.date: 09/27/2017
ms.topic: article
ms.openlocfilehash: c3190fbb31480f92c774d233476436ee2cfc52b3
ms.sourcegitcommit: 6889c7e1a38029d965c8f91dc9108819dbdea552
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/31/2019
ms.locfileid: "68733019"
---
# <a name="native-styling---android"></a>本机样式设置-Android

Android 呈现器不支持本机样式, 而在版本1.2 中引入了对某些属性的样式支持:

## <a name="action-sentiment"></a>操作情绪

操作情绪包含在版本**1.2**中, 而不支持与其他版本一样多的样式, 可以通过实现有效的样式并将以下行添加到项目的样式

```styles.xml
 <item name="adaptiveActionDestructive">@style/adaptiveActionDestructive</item>
 <item name="adaptiveActionPositive">@style/adaptiveActionPositive</item>
```

## <a name="inline-action"></a>内联操作

带有内联操作的文本输入允许为所呈现的操作设置样式。 这允许将操作的样式设置为按钮 (adaptiveInlineAction) 或图像 (adaptiveInlineActionImage)

```styles.xml
 <item name="adaptiveInlineAction">@style/adaptiveInlineAction</item>
 <item name="adaptiveInlineActionImage">@style/adaptiveInlineActionImage</item>
```

> [!IMPORTANT]
> 如果呈现器查找确切的名称, 则必须将所有项名称保持原样, 如下所示
