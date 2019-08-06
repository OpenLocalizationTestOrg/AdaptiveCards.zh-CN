---
title: 主机配置-Android SDK
author: bekao
ms.author: bekao
ms.date: 09/27/2017
ms.topic: article
ms.openlocfilehash: 2828a379d8fda151b1cfca51e5898135186333ae
ms.sourcegitcommit: 6889c7e1a38029d965c8f91dc9108819dbdea552
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/31/2019
ms.locfileid: "68733009"
---
# <a name="host-config---android"></a>主机配置-Android

若要自定义呈现器, 请提供 HostConfig 对象的实例。 (有关完整的说明, 请参阅[主机配置架构](../../../rendering-cards/host-config.md)。)

若要通过字符串创建 HostConfig 对象, 请使用 DeserializeFromString 方法

```java
HostConfig hostConfig = HostConfig.DeserializeFromString(hostConfigText);
```