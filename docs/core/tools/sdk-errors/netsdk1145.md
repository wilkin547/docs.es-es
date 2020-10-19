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
# <a name="netsdk1145-targeting-or-apphost-pack-missing"></a><span data-ttu-id="99bb9-103">NETSDK1145: Falta el paquete de destino o de apphost</span><span class="sxs-lookup"><span data-stu-id="99bb9-103">NETSDK1145: Targeting or apphost pack missing</span></span>

<span data-ttu-id="99bb9-104">**Este artículo se aplica a:** ✔️ SDK de .NET 5.0.100 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="99bb9-104">**This article applies to:** ✔️ .NET 5.0.100 SDK and later versions</span></span>

<span data-ttu-id="99bb9-105">Cuando el SDK de .NET emite el error NETSDK1145, no se instalan el paquete de destino o apphost, y no se admite la restauración de paquetes NuGet.</span><span class="sxs-lookup"><span data-stu-id="99bb9-105">When the .NET SDK issues error NETSDK1145, the targeting or apphost pack is not installed and NuGet package restore is not supported.</span></span> <span data-ttu-id="99bb9-106">Normalmente esto se debe a la presencia de un SDK más reciente que el que se incluye en los proyectos de Visual Studio para C++/CLI.</span><span class="sxs-lookup"><span data-stu-id="99bb9-106">This is typically caused by having a newer SDK than the one included in Visual Studio for C++/CLI projects.</span></span> <span data-ttu-id="99bb9-107">Actualice Visual Studio, quite _global.json_ si especifica una versión concreta del SDK y desinstale el SDK más reciente.</span><span class="sxs-lookup"><span data-stu-id="99bb9-107">Upgrade Visual Studio, remove _global.json_ if it specifies a certain SDK version, and uninstall the newer SDK.</span></span> <span data-ttu-id="99bb9-108">También puede invalidar la versión de destino o de apphost.</span><span class="sxs-lookup"><span data-stu-id="99bb9-108">Alternatively, you could override the targeting or apphost version.</span></span> <span data-ttu-id="99bb9-109">Busque la versión que existe en el directorio pack del mensaje de error y que coincida con la plataforma de destino del proyecto.</span><span class="sxs-lookup"><span data-stu-id="99bb9-109">Find the version that exists under the pack directory from the error message and matches the target framework of the project.</span></span> <span data-ttu-id="99bb9-110">Agregue lo siguiente al proyecto:</span><span class="sxs-lookup"><span data-stu-id="99bb9-110">Add the following to the project:</span></span>

<span data-ttu-id="99bb9-111">Para el paquete de apphost</span><span class="sxs-lookup"><span data-stu-id="99bb9-111">For apphost pack</span></span>

```xml
<ItemGroup>
  <KnownAppHostPack Update="@(KnownAppHostPack)">
    <AppHostPackVersion Condition="'%(TargetFramework)' == 'TARGETFRAMEWORK'">EXISTINGVERSION</AppHostPackVersion>
  </KnownAppHostPack>
</ItemGroup>
```

<span data-ttu-id="99bb9-112">Para el paquete de destino</span><span class="sxs-lookup"><span data-stu-id="99bb9-112">For targeting pack</span></span>

```xml
<ItemGroup>
  <KnownAppHostPack Update="@(KnownAppHostPack)">
    <AppHostPackVersion Condition="'%(TargetFramework)' == 'TARGETFRAMEWORK'">EXISTINGVERSION</AppHostPackVersion>
  </KnownAppHostPack>
</ItemGroup>
```
