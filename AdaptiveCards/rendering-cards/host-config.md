---
title: 自适应卡的 HostConfig
author: paulcam206
ms.author: paulcam
ms.date: 09/18/2018
ms.topic: reference
ms.openlocfilehash: 848ce3dd2ccca1f975dfd330c1c88292c753641d
ms.sourcegitcommit: 6889c7e1a38029d965c8f91dc9108819dbdea552
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/31/2019
ms.locfileid: "68733094"
---
# <a name="what-is-hostconfig"></a>什么是 HostConfig？
`HostConfig`是一个**跨平台配置对象**, 该对象指定自适应卡呈现器生成 UI 的方式。

这允许在不同平台和设备上的呈现器之间共享平台不可知的属性。 它还允许创建工具, 这为你提供了卡对给定环境的外观和感觉。

请参阅示例[HostConfig](https://github.com/Microsoft/AdaptiveCards/blob/master/samples/HostConfig/sample.json) , 了解其内容。

---

   * [`AdaptiveCardConfig`](#schema-adaptivecardconfig)-Toplevel 选项`AdaptiveCards`
   * [`ActionsConfig`](#schema-actionsconfig)-用于的`Action`选项
   * [`ContainerStylesConfig`](#schema-containerstylesconfig)-控件默认和强调容器的样式
   * [`FactSetConfig`](#schema-factsetconfig)-控制的`FactSet`显示
   * [`FontSizesConfig`](#schema-fontsizesconfig)-控制不同文本样式的字号指标
   * [`FontWeightsConfig`](#schema-fontweightsconfig)-控制字体权重度量值
   * [`ForegroundColorsConfig`](#schema-foregroundcolorsconfig)-控制各种字体颜色
   * [`ImageSetConfig`](#schema-imagesetconfig)-控制显示`ImageSet`方式
   * [`ImageSizesConfig`](#schema-imagesizesconfig)-控件`Image`大小
   * [`MediaConfig`](#schema-mediaconfig)-控制`Media`元素的显示和行为
   * [`SeparatorConfig`](#schema-separatorconfig)-控制分隔符的显示方式
   * [`ShowCardConfig`](#schema-showcardconfig)-控制的行为和样式`Action.ShowCard`
   * [`SpacingsConfig`](#schema-spacingsconfig)-控制元素的布局方式
   * [`TextBlockConfig`](#schema-textblockconfig)-控制文本显示的参数

# <a name="card-configuration"></a>卡配置

<a name="schema-adaptivecardconfig"></a>
## <a name="adaptivecardconfig"></a>AdaptiveCardConfig

Toplevel 选项`AdaptiveCards`

|Property|类型|必需|描述|Version|
|--------|----|--------|-----------|-------|
|**allowCustomStyle**|`boolean`| 否, 默认值:`true`|控制是否允许自定义样式设置|1.0
|**supportsInteractivity**|`boolean`| 否, 默认值:`true`|控制是否允许`Action`调用交互的|1.0
|**imageBaseUrl**|`string`| No|加载资源时要使用的基 URL|1.0
|**fontFamily**|`string`| 否, 默认值:`"Calibri"`|呈现文本时使用的字体|1.0
|**actions**|`object`| No|用于的`Action`选项|1.0
|**adaptiveCard**|`object`| No|Toplevel 选项`AdaptiveCards`|1.0
|**containerStyles**|`object`| No|控件默认和强调容器的样式设置|1.0
|**imageSizes**|`object`| No|控件`Image`大小|1.0
|**imageSet**|`object`| No|控制显示`ImageSet`方式|1.0
|**factSet**|`object`| No|控制的`FactSet`显示|1.0
|**fontSizes**|`object`| No|控制不同文本样式的字体大小指标|1.0
|**fontWeights**|`object`| No|控制字体粗细指标|1.0
|**spacing**|`object`| No|控制元素的布局方式|1.0
|**separator**|`object`| No|控制分隔符的显示方式|1.0
|**media**|`object`| No|控制`Media`元素的显示和行为|1.1


<a name="schema-actionsconfig"></a>
## <a name="actionsconfig"></a>ActionsConfig

用于的`Action`选项

|属性|类型|必填|描述|Version|
|--------|----|--------|-----------|-------|
|**actionsOrientation**|`string`| 否, 默认值:`"horizontal"`|控制按钮的布局方式|1.0
|**actionAlignment**|`string`| 否, 默认值:`"stretch"`|按钮的控件布局|1.0
|**buttonSpacing**|`integer`| 否, 默认值:`10`|控制按钮间使用的间距|1.0
|**maxActions**|`integer`| 否, 默认值:`5`|控制总共允许多少操作|1.0
|**spacing**|`string`| 否, 默认值:`"default"`|控制 action 元素的总体间距|1.0
|**showCard**|`object`| No|控制的行为和样式`Action.ShowCard`|1.0
|**iconPlacement**|`string`| 否, 默认值:`"aboveTitle"`|控制在何处放置操作图标|1.0
|**iconSize**|`integer`| 否, 默认值:`30`|控制操作图标的大小|1.0


<a name="schema-containerstylesconfig"></a>
## <a name="containerstylesconfig"></a>ContainerStylesConfig

控件默认和强调容器的样式设置

|属性|类型|必填|描述|Version|
|--------|----|--------|-----------|-------|
|**default**|`object`| No|默认容器样式|1.0
|**emphasis**|`object`| No|要用于强调的容器样式|1.0


<a name="schema-factsetconfig"></a>
## <a name="factsetconfig"></a>FactSetConfig

控制的`FactSet`显示

|属性|类型|必需|描述|Version|
|--------|----|--------|-----------|-------|
|**title**|`object`| 否, 默认值:`{"weight":"bolder","size":"default","color":"default","isSubtle":false,"wrap":true,"maxWidth":150}`|控制文本显示的参数|1.0
|**值**|`object`| 否, 默认值:`{"weight":"default","size":"default","color":"default","isSubtle":false,"wrap":true,"maxWidth":0}`|控制文本显示的参数|1.0
|**spacing**|`integer`| 否, 默认值:`10`|&nbsp;|1.0


<a name="schema-fontsizesconfig"></a>
## <a name="fontsizesconfig"></a>FontSizesConfig

控制不同文本样式的字体大小指标

|Property|类型|必需|描述|Version|
|--------|----|--------|-----------|-------|
|**small**|`integer`| 否, 默认值:`10`|小字号|1.0
|**default**|`integer`| 否, 默认值:`12`|默认字号|1.0
|**medium**|`integer`| 否, 默认值:`14`|中等字体大小|1.0
|**large**|`integer`| 否, 默认值:`17`|大字号|1.0
|**extraLarge**|`integer`| 否, 默认值:`20`|超大字号|1.0


<a name="schema-fontweightsconfig"></a>
## <a name="fontweightsconfig"></a>FontWeightsConfig

控制字体粗细指标

|Property|类型|必需|描述|Version|
|--------|----|--------|-----------|-------|
|**lighter**|`integer`| 否, 默认值:`200`|&nbsp;|1.0
|**default**|`integer`| 否, 默认值:`400`|&nbsp;|1.0
|**bolder**|`integer`| 否, 默认值:`800`|&nbsp;|1.0


<a name="schema-foregroundcolorsconfig"></a>
## <a name="foregroundcolorsconfig"></a>ForegroundColorsConfig

控制各种字体颜色

|Property|类型|必填|描述|Version|
|--------|----|--------|-----------|-------|
|**default**|`object`| 否, 默认值:`{"default":"#FF000000","subtle":"#B2000000"}`|&nbsp;|1.0
|**accent**|`object`| 否, 默认值:`{"default":"#FF0000FF","subtle":"#B20000FF"}`|&nbsp;|1.0
|**dark**|`object`| 否, 默认值:`{"default":"#FF101010","subtle":"#B2101010"}`|&nbsp;|1.0
|**light**|`object`| 否, 默认值:`{"default":"#FFFFFFFF","subtle":"#B2FFFFFF"}`|&nbsp;|1.0
|**good**|`object`| 否, 默认值:`{"default":"#FF008000","subtle":"#B2008000"}`|&nbsp;|1.0
|**warning**|`object`| 否, 默认值:`{"default":"#FFFFD700","subtle":"#B2FFD700"}`|&nbsp;|1.0
|**attention**|`object`| 否, 默认值:`{"default":"#FF8B0000","subtle":"#B28B0000"}`|&nbsp;|1.0


<a name="schema-imagesetconfig"></a>
## <a name="imagesetconfig"></a>ImageSetConfig

控制显示`ImageSet`方式

|属性|类型|必填|描述|Version|
|--------|----|--------|-----------|-------|
|**imageSize**|`string`| 否, 默认值:`"auto"`|控制单个图像大小调整|1.0
|**maxImageHeight**|`integer`| 否, 默认值:`100`|将图像高度限制为此值|1.0


<a name="schema-imagesizesconfig"></a>
## <a name="imagesizesconfig"></a>ImageSizesConfig

控件`Image`大小

|属性|类型|必需|描述|Version|
|--------|----|--------|-----------|-------|
|**small**|`integer`| 否, 默认值:`80`|小型图像大小值|1.0
|**medium**|`integer`| 否, 默认值:`120`|中等图像大小值|1.0
|**large**|`integer`| 否, 默认值:`180`|大图像大小值|1.0


<a name="schema-mediaconfig"></a>
## <a name="mediaconfig"></a>MediaConfig

控制`Media`元素的显示和行为

#### <a name="introduced-in-version-11"></a>版本1.1 中引入

|属性|类型|必填|描述|Version|
|--------|----|--------|-----------|-------|
|**defaultPoster**|`string`| No|未调用播放按钮时要显示的图像的 URI|1.1
|**playButton**|`string`| No|要显示为播放按钮的图像|1.1
|**allowInlinePlayback**|`boolean`| 否, 默认值:`true`|是显示内联媒体还是外部调用|1.1


<a name="schema-separatorconfig"></a>
## <a name="separatorconfig"></a>SeparatorConfig

控制分隔符的显示方式

|属性|类型|必填|描述|Version|
|--------|----|--------|-----------|-------|
|**lineThickness**|`integer`| 否, 默认值:`1`|分隔线的粗细|1.0
|**lineColor**|`string,null`| 否, 默认值:`#B2000000`|绘制分隔线时使用的颜色|1.0


<a name="schema-showcardconfig"></a>
## <a name="showcardconfig"></a>ShowCardConfig

控制的行为和样式`Action.ShowCard`

|Property|类型|必需|描述|Version|
|--------|----|--------|-----------|-------|
|**actionMode**|`string`| 否, 默认值:`"inline"`|控制卡的显示方式|1.0
|**style**|`object`| 否, 默认值:`emphasis`|控制容器的样式|1.0
|**inlineTopMargin**|`integer`| 否, 默认值:`16`|显示卡片时使用的边距量|1.0


<a name="schema-spacingsconfig"></a>
## <a name="spacingsconfig"></a>SpacingsConfig

控制元素的布局方式

|Property|类型|必填|描述|Version|
|--------|----|--------|-----------|-------|
|**small**|`integer`| 否, 默认值:`3`|小间距值|1.0
|**default**|`integer`| 否, 默认值:`8`|默认间距值|1.0
|**medium**|`integer`| 否, 默认值:`20`|中间距值|1.0
|**large**|`integer`| 否, 默认值:`30`|大间距值|1.0
|**extraLarge**|`integer`| 否, 默认值:`40`|特大间距值|1.0
|**padding**|`integer`| 否, 默认值:`20`|填充值|1.0


<a name="schema-textblockconfig"></a>
## <a name="textblockconfig"></a>TextBlockConfig

控制文本显示的参数

|Property|类型|必需|描述|Version|
|--------|----|--------|-----------|-------|
|**size**|`string`| 否, 默认值:`"default"`|在卡片未指定时使用的字体大小|1.0
|**weight**|`string`| 否, 默认值:`"normal"`|卡片未指定时要使用的字体粗细|1.0
|**color**|`string`| 否, 默认值:`"default"`|卡片未指定时使用的字体颜色|1.0
|**isSubtle**|`boolean`| 否, 默认值:`false`|如果卡片未指定, 应为文本为微妙|1.0
|**wrap**|`boolean`| 否, 默认值:`true`|如果卡未指定, 应换行文本|1.0
|**maxWidth**|`integer`| 否, 默认值:`0`|卡片未指定时使用的最大宽度|1.0
