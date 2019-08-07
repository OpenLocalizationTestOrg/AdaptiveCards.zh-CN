---
title: 入门
author: matthidinger
ms.author: mahiding
ms.date: 11/9/2017
ms.topic: article
ms.openlocfilehash: c9a0ad07ba5fefbcdc35239591c02fe0720b5b66
ms.sourcegitcommit: 6889c7e1a38029d965c8f91dc9108819dbdea552
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/31/2019
ms.locfileid: "68732649"
---
# <a name="getting-started"></a>入门 

自适应卡是 JSON 序列化的卡对象模型。

## <a name="adaptive-card-structure"></a>自适应卡结构

卡片的基本结构如下所示:

* `AdaptiveCard`-根对象描述 AdaptiveCard 本身, 其中包括其元素构成、其操作、应如何口述以及呈现它所需的架构版本。
* `body`-卡片的主体由称为`elements`的构建基块组成。 可以通过几乎无限的方式撰写元素, 以创建多种类型的卡。 
* `actions`-许多卡都具有一组用户可能会执行的操作。 此属性描述通常呈现在底部的 "操作栏" 中的操作。

### <a name="example-card"></a>示例卡

此示例卡包含一行文本, 后跟一个图像。

```json
{
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": [
        {
            "type": "TextBlock",
            "text": "Here is a ninja cat"
        },
        {
            "type": "Image",
            "url": "http://adaptivecards.io/content/cats/1.png"
        }
    ]
}
```

## <a name="type-property"></a>`Type` 属性

每个元素都`type`有一个属性, 用于标识对象的类型。 查看上面的卡片, 可以看到我们有两个元素: `TextBlock` `Image`和。

所有自适应卡元素都**垂直堆叠**, 并**向其父**对象 ( `display: block`以 HTML 格式) 展开。 但是, 可以使用`ColumnSet`来创建容器的并行列。

## <a name="adaptive-elements"></a>自适应元素

最基本的元素包括:

* **TextBlock** -添加一个文本块, 其中包含用于控制文本外观的属性
* **图像**-添加一个图像, 其中包含用于控制图像外观的属性

## <a name="container-elements"></a>容器元素

卡还可以具有容器, 它们排列子元素的集合。

* **容器**-定义元素集合
* **列集/column** -定义列的集合, 每个列都是一个容器
* **FactSet** -事实的容器
* **ImageSet** -图像的容器, 以便 UI 可以显示图像集合的适当照片库体验。

## <a name="input-elements"></a>输入元素

输入元素可让你请求本机 UI 来构建简单窗体:

* **输入文本**-从用户获取文本内容
* **输入。日期**-从用户获取日期
* **输入。时间**-从用户获取时间
* **输入数字**-从用户获取一个数字
* **输入. ChoiceSet** -为用户指定一组选择, 并选择
* **输入。切换**-为用户设置两个项之间的单个选择, 并选择它们

## <a name="actions"></a>操作

操作将按钮添加到卡片。 这些操作可以执行各种操作, 如打开 URL 或提交一些数据。

* **OpenUrl** -该按钮将打开一个外部 URL 以便查看
* **ShowCard** -请求向用户显示子卡。
* **操作: 提交**-要求将所有输入元素向上收集到对象, 然后通过主机应用程序定义的方法将其发送给您。

> **示例操作。提交**:使用 Skype 时, 操作。提交操作会将 Bot Framework 机器人活动发送回机器人, 其中包含**值**属性, 其中包含具有所有输入数据的对象。

## <a name="learn-more"></a>了解更多信息

* 浏览用于灵感的[示例卡](http://adaptivecards.io/samples/)
* 使用[架构资源管理器](http://adaptivecards.io/explorer)浏览可用元素
* 使用[交互式可视化工具](http://adaptivecards.io/visualizer/)构建卡片
* [联系](http://adaptivecards.io/connect)你的任何反馈
