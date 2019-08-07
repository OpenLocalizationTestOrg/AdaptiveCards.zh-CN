---
title: Android SDK
author: bekao
ms.author: bekao
ms.date: 09/27/2017
ms.topic: article
ms.openlocfilehash: 4723175bf94685c22d99fb15f3d1887ac37b8c57
ms.sourcegitcommit: 6889c7e1a38029d965c8f91dc9108819dbdea552
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/31/2019
ms.locfileid: "68733004"
---
# <a name="getting-started---android"></a>入门-Android

这是面向 Android 本机控件的呈现器。

## <a name="install-maven-package"></a>安装 Maven 包

[![Maven 中部](https://img.shields.io/maven-central/v/io.adaptivecards/adaptivecards-android.svg)](https://search.maven.org/#search%7Cga%7C1%7Ca%3A%22adaptivecards-android%22)

你可以找到已发布的包 ![此处](https://search.maven.org/search?q=g:io.adaptivecards)

若要将库包括到项目中, 你必须在项目 gradle 中包括此行。在 "依赖关系" 部分下生成

```build.gradle
 implementation 'io.adaptivecards:adaptivecards-android:1.1.0'
```
需要根据要包含在项目中的版本更改版本号

## <a name="add-import"></a>添加导入

若要包括对象模型, 请添加此导入

```
 import io.adaptivecards.objectmodel.*;
```

若要包括呈现器, 请添加此导入

```
 import io.adaptivecards.renderer.*;
```

## <a name="next-steps"></a>后续步骤

有关后续步骤, 请参阅[渲染卡](render-a-card.md)!
