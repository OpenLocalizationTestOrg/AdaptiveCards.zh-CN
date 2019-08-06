---
title: 实现呈现器
author: matthidinger
ms.author: mahiding
ms.date: 09/15/2017
ms.topic: article
ms.openlocfilehash: 607ce40e70e0e54e61a572853a521d2dd70a5c23
ms.sourcegitcommit: 6889c7e1a38029d965c8f91dc9108819dbdea552
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/31/2019
ms.locfileid: "68732609"
---
# <a name="adaptive-card-renderer-specification"></a><span data-ttu-id="ff7ff-102">自适应卡呈现器规范</span><span class="sxs-lookup"><span data-stu-id="ff7ff-102">Adaptive Card Renderer Specification</span></span>

<span data-ttu-id="ff7ff-103">以下规范介绍了如何在任何 UI 平台上实现自适应卡呈现器。</span><span class="sxs-lookup"><span data-stu-id="ff7ff-103">The following specification describes how implement an Adaptive Card renderer on any UI platform.</span></span>

> [!IMPORTANT]
> 
> <span data-ttu-id="ff7ff-104">尚未完成此内容。</span><span class="sxs-lookup"><span data-stu-id="ff7ff-104">This content is not finished yet.</span></span> <span data-ttu-id="ff7ff-105">请稍后再回来查看。</span><span class="sxs-lookup"><span data-stu-id="ff7ff-105">Check back shortly.</span></span>

## <a name="sdk-versioning"></a><span data-ttu-id="ff7ff-106">SDK 版本控制</span><span class="sxs-lookup"><span data-stu-id="ff7ff-106">SDK Versioning</span></span>

1. <span data-ttu-id="ff7ff-107">SDK 的主要版本和次要版本**应**与`schema`版本相匹配。</span><span class="sxs-lookup"><span data-stu-id="ff7ff-107">The SDK major and minor version **SHOULD** match the `schema` version.</span></span> 
1. <span data-ttu-id="ff7ff-108">修补程序/生成**应**用于未进行架构更改的呈现器更新。</span><span class="sxs-lookup"><span data-stu-id="ff7ff-108">Patch/build **SHOULD** be used for renderer updates that don't have schema changes.</span></span>

## <a name="parsing-json"></a><span data-ttu-id="ff7ff-109">分析 JSON</span><span class="sxs-lookup"><span data-stu-id="ff7ff-109">Parsing JSON</span></span>

### <a name="error-conditions"></a><span data-ttu-id="ff7ff-110">错误条件</span><span class="sxs-lookup"><span data-stu-id="ff7ff-110">Error conditions</span></span>
1. <span data-ttu-id="ff7ff-111">分析器**必须**检查它是否为有效的 JSON 内容</span><span class="sxs-lookup"><span data-stu-id="ff7ff-111">A parser **MUST** check that it's valid JSON content</span></span>
1. <span data-ttu-id="ff7ff-112">分析器**必须**对架构进行验证 (必需属性, 等等)</span><span class="sxs-lookup"><span data-stu-id="ff7ff-112">A parser **MUST** validate against the schema (required properties, etc)</span></span>
1. <span data-ttu-id="ff7ff-113">**必须**将上述错误报告给主机应用 (异常或等效)</span><span class="sxs-lookup"><span data-stu-id="ff7ff-113">The above errors **MUST** be reported to the host app (exception or equivalent)</span></span>

### <a name="unknown-types"></a><span data-ttu-id="ff7ff-114">未知类型</span><span class="sxs-lookup"><span data-stu-id="ff7ff-114">Unknown types</span></span>
1. <span data-ttu-id="ff7ff-115">如果遇到未知的 "类型", 则必须从结果中**删除**它们</span><span class="sxs-lookup"><span data-stu-id="ff7ff-115">If unknown "types" are encountered they **MUST BE DROPPED** from the result</span></span>
1. <span data-ttu-id="ff7ff-116">**应**将有效负载的任何变更 (如上文所述) 报告为主机应用的警告</span><span class="sxs-lookup"><span data-stu-id="ff7ff-116">Any alterations of the payload (like above) **SHOULD** be reported as warnings to the host app</span></span>

### <a name="unknown-properties"></a><span data-ttu-id="ff7ff-117">未知属性</span><span class="sxs-lookup"><span data-stu-id="ff7ff-117">Unknown properties</span></span>
1. <span data-ttu-id="ff7ff-118">分析器**必须**在元素上包含**其他**属性</span><span class="sxs-lookup"><span data-stu-id="ff7ff-118">A parser **MUST** include **additional** properties on elements</span></span>

### <a name="additional-considerations"></a><span data-ttu-id="ff7ff-119">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="ff7ff-119">Additional considerations</span></span>
1. <span data-ttu-id="ff7ff-120">属性可能包含 SSML 标记, 并且必须返回到指定的主机应用中 `speak`</span><span class="sxs-lookup"><span data-stu-id="ff7ff-120">The `speak` property may contain SSML markup and **MUST** be returned to the host app as-specified</span></span>

## <a name="parsing-host-config"></a><span data-ttu-id="ff7ff-121">正在分析主机配置</span><span class="sxs-lookup"><span data-stu-id="ff7ff-121">Parsing Host Config</span></span>
1. <span data-ttu-id="ff7ff-122">TODO</span><span class="sxs-lookup"><span data-stu-id="ff7ff-122">TODO</span></span>

## <a name="versioning"></a><span data-ttu-id="ff7ff-123">版本管理</span><span class="sxs-lookup"><span data-stu-id="ff7ff-123">Versioning</span></span>

1. <span data-ttu-id="ff7ff-124">呈现器**必须**实现架构的特定版本。</span><span class="sxs-lookup"><span data-stu-id="ff7ff-124">A renderer **MUST** implement a particular version of the schema.</span></span> 
1. <span data-ttu-id="ff7ff-125">构造函数**必须**根据当前架构版本为属性指定默认值`version` `AdaptiveCard`</span><span class="sxs-lookup"><span data-stu-id="ff7ff-125">The `AdaptiveCard` constructor **MUST** give the `version` property a default value based on the current schema version</span></span> 
1. <span data-ttu-id="ff7ff-126">如果呈现`version`器在`AdaptiveCard`中遇到大于受支持版本的属性`fallbackText` , 则**必须**改为返回。</span><span class="sxs-lookup"><span data-stu-id="ff7ff-126">If a renderer encounters a `version` property in the `AdaptiveCard` that is higher than the supported version, it **MUST** return the `fallbackText` instead.</span></span>

## <a name="rendering"></a><span data-ttu-id="ff7ff-127">“呈现”</span><span class="sxs-lookup"><span data-stu-id="ff7ff-127">Rendering</span></span>

<span data-ttu-id="ff7ff-128">`AdaptiveCard`由`body`和组成`actions`。</span><span class="sxs-lookup"><span data-stu-id="ff7ff-128">An `AdaptiveCard` consists of a `body` and `actions`.</span></span> <span data-ttu-id="ff7ff-129">是呈现器将按`CardElement`顺序枚举并呈现的的集合。 `body`</span><span class="sxs-lookup"><span data-stu-id="ff7ff-129">The `body` is a collection of `CardElement`s that a renderer will enumerate and render in order.</span></span> 

1. <span data-ttu-id="ff7ff-130">每个元素**都必须**延伸到其父级的宽度 ( `display: block`以 HTML 格式考虑)。</span><span class="sxs-lookup"><span data-stu-id="ff7ff-130">Each Element **MUST** stretch to the width of its parent (think `display: block` in HTML).</span></span>
1. <span data-ttu-id="ff7ff-131">呈现器**必须**忽略未知元素类型, 并继续呈现其他有效负载。</span><span class="sxs-lookup"><span data-stu-id="ff7ff-131">A renderer **MUST** ignore unknown element types, and continue rendering the rest of the payload.</span></span>

### <a name="spacing-and-separators"></a><span data-ttu-id="ff7ff-132">间距和分隔符</span><span class="sxs-lookup"><span data-stu-id="ff7ff-132">Spacing and Separators</span></span>

1. <span data-ttu-id="ff7ff-133">每`spacing`个元素的属性会影响**当前**元素与**前**一个元素之间的空间量。</span><span class="sxs-lookup"><span data-stu-id="ff7ff-133">The `spacing` property on every element influences the amount of space between the **CURRENT** element and the one **BEFORE** it.</span></span>
1. <span data-ttu-id="ff7ff-134">间距**必须仅**适用于实际有元素的情况。</span><span class="sxs-lookup"><span data-stu-id="ff7ff-134">Spacing **MUST ONLY** apply when there actually is an element preceding it.</span></span> <span data-ttu-id="ff7ff-135">(例如, 不会应用到数组中的第一项)</span><span class="sxs-lookup"><span data-stu-id="ff7ff-135">(E.g., won't apply to the first item in an array)</span></span>
1. <span data-ttu-id="ff7ff-136">呈现器**必须**查找应用于当前元素的枚举值的`hostConfig`间距所使用的空间量。</span><span class="sxs-lookup"><span data-stu-id="ff7ff-136">A renderer **MUST** look up the amount of space to use from the `hostConfig` spacing for the enum value applied to the current element.</span></span>
1. <span data-ttu-id="ff7ff-137">如果元素`separator`的值为`true`, 则**必须**在当前元素与前一个元素之间绘制一个可见的行。</span><span class="sxs-lookup"><span data-stu-id="ff7ff-137">If the element has a `separator` value of `true`, then a visible line **MUST** be drawn between the current element and the one before it.</span></span>
1. <span data-ttu-id="ff7ff-138">**必须**使用`container.style.default.foregroundColor`绘制分隔线。</span><span class="sxs-lookup"><span data-stu-id="ff7ff-138">The separator line **MUST** be drawn using the `container.style.default.foregroundColor`.</span></span>
1. <span data-ttu-id="ff7ff-139">**只有**当项**不是**数组中的第一个时, 才能绘制分隔符。</span><span class="sxs-lookup"><span data-stu-id="ff7ff-139">A separator **MUST ONLY** be drawn if the item **IS NOT** the first in the array.</span></span>

### <a name="columns"></a><span data-ttu-id="ff7ff-140">列</span><span class="sxs-lookup"><span data-stu-id="ff7ff-140">Columns</span></span>

1. <span data-ttu-id="ff7ff-141">`Column`必须通过 "自动"、"拉伸" 或加权比率来进行解释。 `width`</span><span class="sxs-lookup"><span data-stu-id="ff7ff-141">`Column` `width` **MUST** be interpreted by "auto", "stretch" or a weighted ratio.</span></span>

### <a name="textblock"></a><span data-ttu-id="ff7ff-142">TextBlock</span><span class="sxs-lookup"><span data-stu-id="ff7ff-142">TextBlock</span></span>

1. <span data-ttu-id="ff7ff-143">除非`wrap`属性 为`true`, 否则 TextBlock 必须占用一行。</span><span class="sxs-lookup"><span data-stu-id="ff7ff-143">A TextBlock **MUST** take up a single line unless the `wrap` property is `true`.</span></span> 
1. <span data-ttu-id="ff7ff-144">文本块**应**使用省略号 (...) 来修整多余的文本</span><span class="sxs-lookup"><span data-stu-id="ff7ff-144">The text block **SHOULD** trim any excess text with an ellipsis (...)</span></span>

#### <a name="markdown"></a><span data-ttu-id="ff7ff-145">Markdown</span><span class="sxs-lookup"><span data-stu-id="ff7ff-145">Markdown</span></span>

1. <span data-ttu-id="ff7ff-146">自适应卡允许 Markdown 的子集, 并且**应**在中`TextBlock`受支持。</span><span class="sxs-lookup"><span data-stu-id="ff7ff-146">Adaptive Cards allow for a subset of Markdown and **SHOULD** be supported in `TextBlock`.</span></span> 
1. <span data-ttu-id="ff7ff-147">查看完整的[markdown 要求](../authoring-cards/text-features.md)</span><span class="sxs-lookup"><span data-stu-id="ff7ff-147">See full [markdown requirements](../authoring-cards/text-features.md)</span></span>

#### <a name="formatting-functions"></a><span data-ttu-id="ff7ff-148">格式设置函数</span><span class="sxs-lookup"><span data-stu-id="ff7ff-148">Formatting functions</span></span>

1. <span data-ttu-id="ff7ff-149">`TextBlock`允许对每个呈现器都**必须**支持的[日期/时间格式设置函数](../authoring-cards/text-features.md)。</span><span class="sxs-lookup"><span data-stu-id="ff7ff-149">`TextBlock` allows [DATE/TIME formatting functions](../authoring-cards/text-features.md) that **MUST** be supported on every renderer.</span></span>
1. <span data-ttu-id="ff7ff-150">**所有失败都必须**显示卡中的原始字符串。</span><span class="sxs-lookup"><span data-stu-id="ff7ff-150">**ALL FAILURES MUST** display the raw string in the card.</span></span> <span data-ttu-id="ff7ff-151">未尝试友好消息。</span><span class="sxs-lookup"><span data-stu-id="ff7ff-151">No friendly message attempted.</span></span> <span data-ttu-id="ff7ff-152">(要使开发人员立即意识到的目标是一个问题)</span><span class="sxs-lookup"><span data-stu-id="ff7ff-152">(The goal being to make the developer immediately aware there is a problem)</span></span>

1. <span data-ttu-id="ff7ff-153">TODO：包括 regex</span><span class="sxs-lookup"><span data-stu-id="ff7ff-153">TODO: Include regex</span></span>

### <a name="images"></a><span data-ttu-id="ff7ff-154">映像</span><span class="sxs-lookup"><span data-stu-id="ff7ff-154">Images</span></span>

1. <span data-ttu-id="ff7ff-155">呈现器**应该**允许主机应用知道何时下载了所有 HTTP 映像, 并且卡已 "完全呈现"</span><span class="sxs-lookup"><span data-stu-id="ff7ff-155">A renderer **SHOULD** allow host apps to know when all HTTP images have been downloaded and the card is "fully rendered"</span></span>
1. <span data-ttu-id="ff7ff-156">下载 HTTP映像时, 呈现器`maxImageSize`必须检查主机配置参数</span><span class="sxs-lookup"><span data-stu-id="ff7ff-156">A renderer **MUST** inspect the Host Config `maxImageSize` param when downloading HTTP images</span></span>
1. <span data-ttu-id="ff7ff-157">呈现器**必须**支持`.png`和`.jpeg`</span><span class="sxs-lookup"><span data-stu-id="ff7ff-157">A renderer **MUST** support `.png` and `.jpeg`</span></span>
1. <span data-ttu-id="ff7ff-158">呈现器**应**支持`.gif`图像</span><span class="sxs-lookup"><span data-stu-id="ff7ff-158">A renderer **SHOULD** support `.gif` images</span></span>

### <a name="host-config"></a><span data-ttu-id="ff7ff-159">主机配置</span><span class="sxs-lookup"><span data-stu-id="ff7ff-159">Host Config</span></span>

* <span data-ttu-id="ff7ff-160">TODO：默认值应该是什么？</span><span class="sxs-lookup"><span data-stu-id="ff7ff-160">TODO: What should the defaults be?</span></span> <span data-ttu-id="ff7ff-161">它们是否都共享？</span><span class="sxs-lookup"><span data-stu-id="ff7ff-161">Should they all share it?</span></span> <span data-ttu-id="ff7ff-162">是否应在二进制文件中嵌入公用 hostConfig 文件？</span><span class="sxs-lookup"><span data-stu-id="ff7ff-162">Should we embed a common hostConfig.json file in the binaries?</span></span>
* <span data-ttu-id="ff7ff-163">TODO：我想还需要对 HostConfig 进行版本控制, 以便进行分析？</span><span class="sxs-lookup"><span data-stu-id="ff7ff-163">TODO: I think HostConfig needs to be versioned as well for parsing?</span></span>

<span data-ttu-id="ff7ff-164">[`HostConfig`](host-config.md)是一个共享配置对象, 该对象指定自适应卡呈现器生成 UI 的方式。</span><span class="sxs-lookup"><span data-stu-id="ff7ff-164">[`HostConfig`](host-config.md) is a shared configuration object that specifies how an Adaptive Card Renderer generates UI.</span></span>  

<span data-ttu-id="ff7ff-165">这允许在不同平台和设备上的呈现器之间共享平台不可知的属性。</span><span class="sxs-lookup"><span data-stu-id="ff7ff-165">This allows properties which are platform agnostic to be shared among renderers on different platforms and devices.</span></span> <span data-ttu-id="ff7ff-166">它还允许创建工具, 这为你提供了卡对给定环境的外观和感觉。</span><span class="sxs-lookup"><span data-stu-id="ff7ff-166">It also allows tooling to be created which gives you an idea of the look and feel that card would have for a given environment.</span></span>

1. <span data-ttu-id="ff7ff-167">呈现器**必须**向宿主应用公开**主机配置**参数</span><span class="sxs-lookup"><span data-stu-id="ff7ff-167">Renderers **MUST** expose a **Host Config** parameter to host apps</span></span>
1. <span data-ttu-id="ff7ff-168">所有元素都**必须**按照各自的主机配置设置样式</span><span class="sxs-lookup"><span data-stu-id="ff7ff-168">All elements **MUST** be styled according to their respective Host Config settings</span></span>

### <a name="native-platform-styling"></a><span data-ttu-id="ff7ff-169">本机平台样式</span><span class="sxs-lookup"><span data-stu-id="ff7ff-169">Native platform styling</span></span>

1. <span data-ttu-id="ff7ff-170">每个元素类型**应**将本机平台样式附加到生成的 UI 元素。</span><span class="sxs-lookup"><span data-stu-id="ff7ff-170">Each element type **SHOULD** attach a native platform style with the generated UI element.</span></span> <span data-ttu-id="ff7ff-171">例如, 在 HTML 中, 我们已将一个 CSS 类添加到元素类型, 而在 XAML 中我们将分配特定样式。</span><span class="sxs-lookup"><span data-stu-id="ff7ff-171">E.g., in HTML we added a CSS class to the element types, and in XAML we assign a specific Style.</span></span>

## <a name="extensibility"></a><span data-ttu-id="ff7ff-172">扩展性</span><span class="sxs-lookup"><span data-stu-id="ff7ff-172">Extensibility</span></span> 

1. <span data-ttu-id="ff7ff-173">呈现器**必须**允许主机应用重写默认元素呈现器。</span><span class="sxs-lookup"><span data-stu-id="ff7ff-173">A renderer **MUST** allow host apps to override default element renderers.</span></span> <span data-ttu-id="ff7ff-174">例如, 将呈现`TextBlock`替换为自己的逻辑。</span><span class="sxs-lookup"><span data-stu-id="ff7ff-174">E.g., replace `TextBlock` rendering with their own logic.</span></span>
1. <span data-ttu-id="ff7ff-175">呈现器**必须**允许主机应用注册自定义元素类型。</span><span class="sxs-lookup"><span data-stu-id="ff7ff-175">A renderer **MUST** allow host apps to register custom element types.</span></span> <span data-ttu-id="ff7ff-176">例如, 添加对自定义`Rating`元素的支持</span><span class="sxs-lookup"><span data-stu-id="ff7ff-176">E.g., add support for a custom `Rating` element</span></span>
1. <span data-ttu-id="ff7ff-177">呈现器**必须**允许主机应用删除对默认元素的支持。</span><span class="sxs-lookup"><span data-stu-id="ff7ff-177">A renderer **MUST** allow host apps to remove support for a default element.</span></span> <span data-ttu-id="ff7ff-178">例如, 如果不`Action.Submit`想支持, 请将其删除。</span><span class="sxs-lookup"><span data-stu-id="ff7ff-178">E.g., remove `Action.Submit` if they don't want it supported.</span></span>

## <a name="actions"></a><span data-ttu-id="ff7ff-179">操作</span><span class="sxs-lookup"><span data-stu-id="ff7ff-179">Actions</span></span>

1. <span data-ttu-id="ff7ff-180">如果 HostConfig `supportsInteractivity`为`false`, 则呈现器**不**能呈现任何操作。</span><span class="sxs-lookup"><span data-stu-id="ff7ff-180">If HostConfig `supportsInteractivity` is `false`, a renderer **MUST NOT** render any actions.</span></span>
1. <span data-ttu-id="ff7ff-181">该`actions`属性**必须**呈现为某种操作栏中的按钮, 通常位于卡的底部。</span><span class="sxs-lookup"><span data-stu-id="ff7ff-181">The `actions` property **MUST** be rendered as buttons in some kind of action bar, usually at the bottom of the card.</span></span> 
1. <span data-ttu-id="ff7ff-182">点击按钮时, 它**必须**允许主机应用处理事件。</span><span class="sxs-lookup"><span data-stu-id="ff7ff-182">When a button is tapped it **MUST** allow the host app to handle the event.</span></span> 
1. <span data-ttu-id="ff7ff-183">事件**必须**通过所有关联的属性和操作</span><span class="sxs-lookup"><span data-stu-id="ff7ff-183">The event **MUST** pass along all associated properties with the action</span></span>
1. <span data-ttu-id="ff7ff-184">事件**必须**通过执行的`AdaptiveCard`操作</span><span class="sxs-lookup"><span data-stu-id="ff7ff-184">The event **MUST** pass along the `AdaptiveCard` which was executed</span></span>

<span data-ttu-id="ff7ff-185">操作</span><span class="sxs-lookup"><span data-stu-id="ff7ff-185">Action</span></span> | <span data-ttu-id="ff7ff-186">行为</span><span class="sxs-lookup"><span data-stu-id="ff7ff-186">Behavior</span></span>
--- | ---
<span data-ttu-id="ff7ff-187">**Action.OpenUrl**</span><span class="sxs-lookup"><span data-stu-id="ff7ff-187">**Action.OpenUrl**</span></span> | <span data-ttu-id="ff7ff-188">打开外部 URL 以便查看</span><span class="sxs-lookup"><span data-stu-id="ff7ff-188">Open an external URL for viewing</span></span>
<span data-ttu-id="ff7ff-189">**Action.ShowCard**</span><span class="sxs-lookup"><span data-stu-id="ff7ff-189">**Action.ShowCard**</span></span> | <span data-ttu-id="ff7ff-190">请求向用户显示子卡。</span><span class="sxs-lookup"><span data-stu-id="ff7ff-190">Requests a sub-card to be shown to the user.</span></span>
<span data-ttu-id="ff7ff-191">**Action.Submit**</span><span class="sxs-lookup"><span data-stu-id="ff7ff-191">**Action.Submit**</span></span> | <span data-ttu-id="ff7ff-192">要求将所有输入元素向上收集到一个对象中, 该对象随后会通过主机应用程序定义的某些方法发送给您。</span><span class="sxs-lookup"><span data-stu-id="ff7ff-192">Ask for all of the input elements to be gathered up into an object which is then sent to you through some method defined by the host application.</span></span>

### <a name="actionopenurl"></a><span data-ttu-id="ff7ff-193">Action.OpenUrl</span><span class="sxs-lookup"><span data-stu-id="ff7ff-193">Action.OpenUrl</span></span>
1. <span data-ttu-id="ff7ff-194">`Action.OpenUrl`**应**使用本机平台机制打开 URL</span><span class="sxs-lookup"><span data-stu-id="ff7ff-194">`Action.OpenUrl` **SHOULD** open a URL using the native platform mechanism</span></span>
1. <span data-ttu-id="ff7ff-195">如果这是不可能的, 则**必须**向宿主应用程序引发事件以处理打开 URL。</span><span class="sxs-lookup"><span data-stu-id="ff7ff-195">If this is not possible it **MUST** raise an event to the host app to handle opening the URL.</span></span> <span data-ttu-id="ff7ff-196">此事件**必须**允许宿主应用重写默认行为。</span><span class="sxs-lookup"><span data-stu-id="ff7ff-196">This event **MUST** allow the host app to override the default behavior.</span></span> <span data-ttu-id="ff7ff-197">例如, 让他们在自己的应用程序中打开 URL。</span><span class="sxs-lookup"><span data-stu-id="ff7ff-197">E.g., let them open the URL within their own app.</span></span>

### <a name="actionshowcard"></a><span data-ttu-id="ff7ff-198">Action.ShowCard</span><span class="sxs-lookup"><span data-stu-id="ff7ff-198">Action.ShowCard</span></span>

1. <span data-ttu-id="ff7ff-199">`Action.ShowCard`**必须**以某种方式受支持, 具体取决于 hostConfig 设置。</span><span class="sxs-lookup"><span data-stu-id="ff7ff-199">`Action.ShowCard` **MUST** be supported in some way, based on the hostConfig setting.</span></span> <span data-ttu-id="ff7ff-200">有两种模式: 内联和 popup。</span><span class="sxs-lookup"><span data-stu-id="ff7ff-200">There are two modes: inline, and popup.</span></span> <span data-ttu-id="ff7ff-201">内嵌卡**应**自动切换卡片可见性。</span><span class="sxs-lookup"><span data-stu-id="ff7ff-201">Inline cards **SHOULD** toggle the card visibility automatically.</span></span> <span data-ttu-id="ff7ff-202">在 popup 模式下,**应**将事件激发到主机应用程序以某种方式显示卡。</span><span class="sxs-lookup"><span data-stu-id="ff7ff-202">In popup mode, an event **SHOULD** be fired to the host app to show the card in some way.</span></span>

### <a name="actionsubmit"></a><span data-ttu-id="ff7ff-203">Action.Submit</span><span class="sxs-lookup"><span data-stu-id="ff7ff-203">Action.Submit</span></span>

<span data-ttu-id="ff7ff-204">提交操作的行为类似于 HTML 窗体提交, 不同之处在于, HTML 通常会触发 HTTP post, 而自适应卡会将其放在每个主机应用上, 以确定 "提交" 对它们的含义。</span><span class="sxs-lookup"><span data-stu-id="ff7ff-204">The Submit Action behaves like an HTML form submit, except that where HTML typically triggers an HTTP post, Adaptive Cards leaves it up to each host app to determine what "submit" means to them.</span></span> 

1. <span data-ttu-id="ff7ff-205">当此操作**必须**引发事件时, 用户点击调用的操作。</span><span class="sxs-lookup"><span data-stu-id="ff7ff-205">When this **MUST** raise an event the user taps the action invoked.</span></span>  
1. <span data-ttu-id="ff7ff-206">属性必须包括在回调负载中。 `data`</span><span class="sxs-lookup"><span data-stu-id="ff7ff-206">The `data` property **MUST** be included in the callback payload.</span></span>
1. <span data-ttu-id="ff7ff-207">对于`Action.Submit`, 呈现器**必须**收集卡片上的所有输入并检索其值。</span><span class="sxs-lookup"><span data-stu-id="ff7ff-207">For `Action.Submit`, a renderer **MUST** gather all inputs on the card and retrieve their values.</span></span> 

### <a name="selectaction"></a><span data-ttu-id="ff7ff-208">selectAction</span><span class="sxs-lookup"><span data-stu-id="ff7ff-208">selectAction</span></span>

1. <span data-ttu-id="ff7ff-209">如果主机配置`supportedInteractivity`为`false` , 则`selectAction` **不能**呈现为触控目标。</span><span class="sxs-lookup"><span data-stu-id="ff7ff-209">If Host Config `supportedInteractivity` is `false` then a `selectAction` **MUST NOT** render as a touch target.</span></span>
1. <span data-ttu-id="ff7ff-210">`Image`、 `ColumnSet`和`Column`提供一个`selectAction`属性, 该属性**应**在用户调用它时执行 (例如, 通过点击元素来执行)。</span><span class="sxs-lookup"><span data-stu-id="ff7ff-210">`Image`, `ColumnSet`, and `Column` offer a `selectAction` property, which **SHOULD** be executed when the user invokes it, e.g., by tapping the element.</span></span>

## <a name="inputs"></a><span data-ttu-id="ff7ff-211">输入</span><span class="sxs-lookup"><span data-stu-id="ff7ff-211">Inputs</span></span>

1. <span data-ttu-id="ff7ff-212">如果 HostConfig `supportsInteractivity`是`false`呈现器, 则**不**能呈现任何输入。</span><span class="sxs-lookup"><span data-stu-id="ff7ff-212">If HostConfig `supportsInteractivity` is `false` a renderer **MUST NOT** render any inputs.</span></span>
2. <span data-ttu-id="ff7ff-213">输入**应**以尽可能高保真的方式呈现。</span><span class="sxs-lookup"><span data-stu-id="ff7ff-213">Inputs **SHOULD** render with the highest fidelity possible.</span></span> <span data-ttu-id="ff7ff-214">例如, `Input.Date`理想情况下, 会向用户提供日期选取器, 但如果无法在 UI 堆栈上进行此选择, 则呈现器**必须**回退以呈现标准文本框。</span><span class="sxs-lookup"><span data-stu-id="ff7ff-214">For example, an `Input.Date` would ideally offer a date picker to a user, but if this isn't possible on your UI stack, then the renderer **MUST** fall back to rendering a standard text box.</span></span>
3. <span data-ttu-id="ff7ff-215">呈现器**应**显示`placeholderText` (如果可能)</span><span class="sxs-lookup"><span data-stu-id="ff7ff-215">A renderer **SHOULD** display the `placeholderText` if possible</span></span>
4. <span data-ttu-id="ff7ff-216">呈现器不必实现对输入的验证。</span><span class="sxs-lookup"><span data-stu-id="ff7ff-216">A renderer **DOES NOT** have to implement validation of the input.</span></span> <span data-ttu-id="ff7ff-217">自适应卡的用户必须计划在其端验证接收到的任何数据。</span><span class="sxs-lookup"><span data-stu-id="ff7ff-217">Users of Adaptive Cards must plan to validate any received data on their end.</span></span>
5. <span data-ttu-id="ff7ff-218">**必须**正确转义输入值绑定</span><span class="sxs-lookup"><span data-stu-id="ff7ff-218">Input value binding **MUST** be properly escaped</span></span>

6. <span data-ttu-id="ff7ff-219">对象**必须**返回到主机应用程序, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="ff7ff-219">The object **MUST** be returned to the host app as follows:</span></span>

   <span data-ttu-id="ff7ff-220">在自适应卡中, 我们不会对输入验证做出任何承诺, 因此, 接收方可以正确分析响应。</span><span class="sxs-lookup"><span data-stu-id="ff7ff-220">We do not make any promises of input validation in adaptive cards, so it's up to the receiving party to properly parse the response.</span></span> <span data-ttu-id="ff7ff-221">例如, 输入的数字可能返回 "hello", 需要为该数字做好准备。</span><span class="sxs-lookup"><span data-stu-id="ff7ff-221">E.g., a Input.Number could return "hello" and they need to be prepared for that.</span></span>


## <a name="events"></a><span data-ttu-id="ff7ff-222">事件</span><span class="sxs-lookup"><span data-stu-id="ff7ff-222">Events</span></span>

1. <span data-ttu-id="ff7ff-223">当元素的可见性发生更改时, 呈现器**应**激发事件, 从而允许主机应用将卡滚动到位置。</span><span class="sxs-lookup"><span data-stu-id="ff7ff-223">A renderer **SHOULD** fire an event when an element's visibility has changed, allowing the host app to scroll the card into position.</span></span>
