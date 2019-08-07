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
# <a name="getting-started---android"></a><span data-ttu-id="55bc1-102">入门-Android</span><span class="sxs-lookup"><span data-stu-id="55bc1-102">Getting started - Android</span></span>

<span data-ttu-id="55bc1-103">这是面向 Android 本机控件的呈现器。</span><span class="sxs-lookup"><span data-stu-id="55bc1-103">This is a renderer which targets Android native controls.</span></span>

## <a name="install-maven-package"></a><span data-ttu-id="55bc1-104">安装 Maven 包</span><span class="sxs-lookup"><span data-stu-id="55bc1-104">Install Maven package</span></span>

<span data-ttu-id="55bc1-105">[![Maven 中部](https://img.shields.io/maven-central/v/io.adaptivecards/adaptivecards-android.svg)](https://search.maven.org/#search%7Cga%7C1%7Ca%3A%22adaptivecards-android%22)</span><span class="sxs-lookup"><span data-stu-id="55bc1-105">[![Maven Central](https://img.shields.io/maven-central/v/io.adaptivecards/adaptivecards-android.svg)](https://search.maven.org/#search%7Cga%7C1%7Ca%3A%22adaptivecards-android%22)</span></span>

<span data-ttu-id="55bc1-106">你可以找到已发布的包</span><span class="sxs-lookup"><span data-stu-id="55bc1-106">You can find the published packages</span></span> ![此处](https://search.maven.org/search?q=g:io.adaptivecards)

<span data-ttu-id="55bc1-108">若要将库包括到项目中, 你必须在项目 gradle 中包括此行。在 "依赖关系" 部分下生成</span><span class="sxs-lookup"><span data-stu-id="55bc1-108">To include library to your project you must include this line into your project gradle.build under the dependencies section</span></span>

```build.gradle
 implementation 'io.adaptivecards:adaptivecards-android:1.1.0'
```
<span data-ttu-id="55bc1-109">需要根据要包含在项目中的版本更改版本号</span><span class="sxs-lookup"><span data-stu-id="55bc1-109">You need to change the version number depending on the version you want to include into your project</span></span>

## <a name="add-import"></a><span data-ttu-id="55bc1-110">添加导入</span><span class="sxs-lookup"><span data-stu-id="55bc1-110">Add import</span></span>

<span data-ttu-id="55bc1-111">若要包括对象模型, 请添加此导入</span><span class="sxs-lookup"><span data-stu-id="55bc1-111">To include the object model, add this import</span></span>

```
 import io.adaptivecards.objectmodel.*;
```

<span data-ttu-id="55bc1-112">若要包括呈现器, 请添加此导入</span><span class="sxs-lookup"><span data-stu-id="55bc1-112">To include the renderer, add this import</span></span>

```
 import io.adaptivecards.renderer.*;
```

## <a name="next-steps"></a><span data-ttu-id="55bc1-113">后续步骤</span><span class="sxs-lookup"><span data-stu-id="55bc1-113">Next steps</span></span>

<span data-ttu-id="55bc1-114">有关后续步骤, 请参阅[渲染卡](render-a-card.md)!</span><span class="sxs-lookup"><span data-stu-id="55bc1-114">See [Render a card](render-a-card.md) for the next steps!</span></span>
