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
# <a name="actions"></a><span data-ttu-id="6e956-102">操作</span><span class="sxs-lookup"><span data-stu-id="6e956-102">Actions</span></span>

<span data-ttu-id="6e956-103">默认情况下, 这些操作将作为按钮显示在卡片上, 但会由应用程序以使其按预期方式运行。</span><span class="sxs-lookup"><span data-stu-id="6e956-103">By default, the actions will render as buttons on the card, but it's up to your app to make them behave as you expect.</span></span> <span data-ttu-id="6e956-104">每个 SDK 都具有您必须`OnAction`处理的事件的等效项。</span><span class="sxs-lookup"><span data-stu-id="6e956-104">Each SDK has the equivalent of an `OnAction` event that you must handle.</span></span>

* <span data-ttu-id="6e956-105">**OpenUrl** -打开指定`url`的。</span><span class="sxs-lookup"><span data-stu-id="6e956-105">**Action.OpenUrl** - open the specified `url`.</span></span>  
* <span data-ttu-id="6e956-106">**操作. 提交**-获取提交结果, 并将其发送到源。</span><span class="sxs-lookup"><span data-stu-id="6e956-106">**Action.Submit** - take the result of the submit and send it to the source.</span></span> <span data-ttu-id="6e956-107">将其发送到卡的源的方式完全取决于你。</span><span class="sxs-lookup"><span data-stu-id="6e956-107">How you send it to the source of the card is entirely up to you.</span></span>
* <span data-ttu-id="6e956-108">**ShowCard** -调用对话框, 并将子卡呈现到该对话框中。</span><span class="sxs-lookup"><span data-stu-id="6e956-108">**Action.ShowCard** - invokes a dialog and renders the sub-card into that dialog.</span></span> <span data-ttu-id="6e956-109">请注意, 只有在设置为`ShowCardActionMode` `popup`时, 才需要处理此情况。</span><span class="sxs-lookup"><span data-stu-id="6e956-109">Note that you only need to handle this if `ShowCardActionMode` is set to `popup`.</span></span>