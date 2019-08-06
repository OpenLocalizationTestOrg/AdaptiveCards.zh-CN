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
# <a name="adaptive-card-renderer-specification"></a>自适应卡呈现器规范

以下规范介绍了如何在任何 UI 平台上实现自适应卡呈现器。

> [!IMPORTANT]
> 
> 尚未完成此内容。 请稍后再回来查看。

## <a name="sdk-versioning"></a>SDK 版本控制

1. SDK 的主要版本和次要版本**应**与`schema`版本相匹配。 
1. 修补程序/生成**应**用于未进行架构更改的呈现器更新。

## <a name="parsing-json"></a>分析 JSON

### <a name="error-conditions"></a>错误条件
1. 分析器**必须**检查它是否为有效的 JSON 内容
1. 分析器**必须**对架构进行验证 (必需属性, 等等)
1. **必须**将上述错误报告给主机应用 (异常或等效)

### <a name="unknown-types"></a>未知类型
1. 如果遇到未知的 "类型", 则必须从结果中**删除**它们
1. **应**将有效负载的任何变更 (如上文所述) 报告为主机应用的警告

### <a name="unknown-properties"></a>未知属性
1. 分析器**必须**在元素上包含**其他**属性

### <a name="additional-considerations"></a>其他注意事项
1. 属性可能包含 SSML 标记, 并且必须返回到指定的主机应用中 `speak`

## <a name="parsing-host-config"></a>正在分析主机配置
1. TODO

## <a name="versioning"></a>版本管理

1. 呈现器**必须**实现架构的特定版本。 
1. 构造函数**必须**根据当前架构版本为属性指定默认值`version` `AdaptiveCard` 
1. 如果呈现`version`器在`AdaptiveCard`中遇到大于受支持版本的属性`fallbackText` , 则**必须**改为返回。

## <a name="rendering"></a>“呈现”

`AdaptiveCard`由`body`和组成`actions`。 是呈现器将按`CardElement`顺序枚举并呈现的的集合。 `body` 

1. 每个元素**都必须**延伸到其父级的宽度 ( `display: block`以 HTML 格式考虑)。
1. 呈现器**必须**忽略未知元素类型, 并继续呈现其他有效负载。

### <a name="spacing-and-separators"></a>间距和分隔符

1. 每`spacing`个元素的属性会影响**当前**元素与**前**一个元素之间的空间量。
1. 间距**必须仅**适用于实际有元素的情况。 (例如, 不会应用到数组中的第一项)
1. 呈现器**必须**查找应用于当前元素的枚举值的`hostConfig`间距所使用的空间量。
1. 如果元素`separator`的值为`true`, 则**必须**在当前元素与前一个元素之间绘制一个可见的行。
1. **必须**使用`container.style.default.foregroundColor`绘制分隔线。
1. **只有**当项**不是**数组中的第一个时, 才能绘制分隔符。

### <a name="columns"></a>列

1. `Column`必须通过 "自动"、"拉伸" 或加权比率来进行解释。 `width`

### <a name="textblock"></a>TextBlock

1. 除非`wrap`属性 为`true`, 否则 TextBlock 必须占用一行。 
1. 文本块**应**使用省略号 (...) 来修整多余的文本

#### <a name="markdown"></a>Markdown

1. 自适应卡允许 Markdown 的子集, 并且**应**在中`TextBlock`受支持。 
1. 查看完整的[markdown 要求](../authoring-cards/text-features.md)

#### <a name="formatting-functions"></a>格式设置函数

1. `TextBlock`允许对每个呈现器都**必须**支持的[日期/时间格式设置函数](../authoring-cards/text-features.md)。
1. **所有失败都必须**显示卡中的原始字符串。 未尝试友好消息。 (要使开发人员立即意识到的目标是一个问题)

1. TODO：包括 regex

### <a name="images"></a>映像

1. 呈现器**应该**允许主机应用知道何时下载了所有 HTTP 映像, 并且卡已 "完全呈现"
1. 下载 HTTP映像时, 呈现器`maxImageSize`必须检查主机配置参数
1. 呈现器**必须**支持`.png`和`.jpeg`
1. 呈现器**应**支持`.gif`图像

### <a name="host-config"></a>主机配置

* TODO：默认值应该是什么？ 它们是否都共享？ 是否应在二进制文件中嵌入公用 hostConfig 文件？
* TODO：我想还需要对 HostConfig 进行版本控制, 以便进行分析？

[`HostConfig`](host-config.md)是一个共享配置对象, 该对象指定自适应卡呈现器生成 UI 的方式。  

这允许在不同平台和设备上的呈现器之间共享平台不可知的属性。 它还允许创建工具, 这为你提供了卡对给定环境的外观和感觉。

1. 呈现器**必须**向宿主应用公开**主机配置**参数
1. 所有元素都**必须**按照各自的主机配置设置样式

### <a name="native-platform-styling"></a>本机平台样式

1. 每个元素类型**应**将本机平台样式附加到生成的 UI 元素。 例如, 在 HTML 中, 我们已将一个 CSS 类添加到元素类型, 而在 XAML 中我们将分配特定样式。

## <a name="extensibility"></a>扩展性 

1. 呈现器**必须**允许主机应用重写默认元素呈现器。 例如, 将呈现`TextBlock`替换为自己的逻辑。
1. 呈现器**必须**允许主机应用注册自定义元素类型。 例如, 添加对自定义`Rating`元素的支持
1. 呈现器**必须**允许主机应用删除对默认元素的支持。 例如, 如果不`Action.Submit`想支持, 请将其删除。

## <a name="actions"></a>操作

1. 如果 HostConfig `supportsInteractivity`为`false`, 则呈现器**不**能呈现任何操作。
1. 该`actions`属性**必须**呈现为某种操作栏中的按钮, 通常位于卡的底部。 
1. 点击按钮时, 它**必须**允许主机应用处理事件。 
1. 事件**必须**通过所有关联的属性和操作
1. 事件**必须**通过执行的`AdaptiveCard`操作

操作 | 行为
--- | ---
**Action.OpenUrl** | 打开外部 URL 以便查看
**Action.ShowCard** | 请求向用户显示子卡。
**Action.Submit** | 要求将所有输入元素向上收集到一个对象中, 该对象随后会通过主机应用程序定义的某些方法发送给您。

### <a name="actionopenurl"></a>Action.OpenUrl
1. `Action.OpenUrl`**应**使用本机平台机制打开 URL
1. 如果这是不可能的, 则**必须**向宿主应用程序引发事件以处理打开 URL。 此事件**必须**允许宿主应用重写默认行为。 例如, 让他们在自己的应用程序中打开 URL。

### <a name="actionshowcard"></a>Action.ShowCard

1. `Action.ShowCard`**必须**以某种方式受支持, 具体取决于 hostConfig 设置。 有两种模式: 内联和 popup。 内嵌卡**应**自动切换卡片可见性。 在 popup 模式下,**应**将事件激发到主机应用程序以某种方式显示卡。

### <a name="actionsubmit"></a>Action.Submit

提交操作的行为类似于 HTML 窗体提交, 不同之处在于, HTML 通常会触发 HTTP post, 而自适应卡会将其放在每个主机应用上, 以确定 "提交" 对它们的含义。 

1. 当此操作**必须**引发事件时, 用户点击调用的操作。  
1. 属性必须包括在回调负载中。 `data`
1. 对于`Action.Submit`, 呈现器**必须**收集卡片上的所有输入并检索其值。 

### <a name="selectaction"></a>selectAction

1. 如果主机配置`supportedInteractivity`为`false` , 则`selectAction` **不能**呈现为触控目标。
1. `Image`、 `ColumnSet`和`Column`提供一个`selectAction`属性, 该属性**应**在用户调用它时执行 (例如, 通过点击元素来执行)。

## <a name="inputs"></a>输入

1. 如果 HostConfig `supportsInteractivity`是`false`呈现器, 则**不**能呈现任何输入。
2. 输入**应**以尽可能高保真的方式呈现。 例如, `Input.Date`理想情况下, 会向用户提供日期选取器, 但如果无法在 UI 堆栈上进行此选择, 则呈现器**必须**回退以呈现标准文本框。
3. 呈现器**应**显示`placeholderText` (如果可能)
4. 呈现器不必实现对输入的验证。 自适应卡的用户必须计划在其端验证接收到的任何数据。
5. **必须**正确转义输入值绑定

6. 对象**必须**返回到主机应用程序, 如下所示:

   在自适应卡中, 我们不会对输入验证做出任何承诺, 因此, 接收方可以正确分析响应。 例如, 输入的数字可能返回 "hello", 需要为该数字做好准备。


## <a name="events"></a>事件

1. 当元素的可见性发生更改时, 呈现器**应**激发事件, 从而允许主机应用将卡滚动到位置。
