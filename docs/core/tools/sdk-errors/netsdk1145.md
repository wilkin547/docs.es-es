---
title: 'NETSDK1145: Falta el paquete de destino o de apphost'
description: Procedimiento para resolver el problema de la falta del paquete de destino mientras no se admite la restauración de paquetes NuGet
author: wli3
ms.topic: error-reference
ms.date: 09/14/2020
f1_keywords:
- NETSDK1145
ms.openlocfilehash: c343952582cafb63eae388fd216769e6c67d4741
ms.sourcegitcommit: 636af37170ae75a11c4f7d1ecd770820e7dfe7bd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2020
ms.locfileid: "91805313"
---
# <a name="netsdk1145-targeting-or-apphost-pack-missing"></a>NETSDK1145: Falta el paquete de destino o de apphost

**Este artículo se aplica a:** ✔️ SDK de .NET 5.0.100 y versiones posteriores

Cuando el SDK de .NET emite el error NETSDK1145, no se instalan el paquete de destino o apphost, y no se admite la restauración de paquetes NuGet. Normalmente esto se debe a la presencia de un SDK más reciente que el que se incluye en los proyectos de Visual Studio para C++/CLI. Actualice Visual Studio, quite _global.json_ si especifica una versión concreta del SDK y desinstale el SDK más reciente. También puede invalidar la versión de destino o de apphost. Busque la versión que existe en el directorio pack del mensaje de error y que coincida con la plataforma de destino del proyecto. Agregue lo siguiente al proyecto:

Para el paquete de apphost

```xml
<ItemGroup>
  <KnownAppHostPack Update="@(KnownAppHostPack)">
    <AppHostPackVersion Condition="'%(TargetFramework)' == 'TARGETFRAMEWORK'">EXISTINGVERSION</AppHostPackVersion>
  </KnownAppHostPack>
</ItemGroup>
```

Para el paquete de destino

```xml
<ItemGroup>
  <KnownAppHostPack Update="@(KnownAppHostPack)">
    <AppHostPackVersion Condition="'%(TargetFramework)' == 'TARGETFRAMEWORK'">EXISTINGVERSION</AppHostPackVersion>
  </KnownAppHostPack>
</ItemGroup>
```
