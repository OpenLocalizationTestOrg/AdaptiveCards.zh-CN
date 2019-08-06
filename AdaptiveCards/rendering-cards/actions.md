---
title: 操作
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: 34283b52f0c4902c71ea33634676832c7dfec5c9
ms.sourcegitcommit: 6889c7e1a38029d965c8f91dc9108819dbdea552
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/31/2019
ms.locfileid: "68733104"
---
# <a name="actions"></a>操作

默认情况下, 这些操作将作为按钮显示在卡片上, 但会由应用程序以使其按预期方式运行。 每个 SDK 都具有您必须`OnAction`处理的事件的等效项。

* **OpenUrl** -打开指定`url`的。  
* **操作. 提交**-获取提交结果, 并将其发送到源。 将其发送到卡的源的方式完全取决于你。
* **ShowCard** -调用对话框, 并将子卡呈现到该对话框中。 请注意, 只有在设置为`ShowCardActionMode` `popup`时, 才需要处理此情况。