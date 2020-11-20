---
title: 'NETSDK1022: Se han incluido elementos duplicados.'
description: Procedimiento para resolver el mensaje de elementos duplicados en función de inclusiones predeterminadas.
author: marcpopMSFT
ms.topic: error-reference
ms.date: 10/9/2020
f1_keywords:
- NETSDK1022
ms.openlocfilehash: bc803f5316bf09c12c563f1a63b8385d1be4e9ce
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506641"
---
# <a name="netsdk1022-duplicate-items-were-included"></a><span data-ttu-id="02748-103">NETSDK1022: Se han incluido elementos duplicados.</span><span class="sxs-lookup"><span data-stu-id="02748-103">NETSDK1022: Duplicate items were included.</span></span>

<span data-ttu-id="02748-104">**Este artículo se aplica a:** ✔️ SDK de .NET 2.1.100 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="02748-104">**This article applies to:** ✔️ .NET 2.1.100 SDK and later versions</span></span>

<span data-ttu-id="02748-105">A partir de Visual Studio 2017 y MSBuild, versión 15.3, el SDK de .NET incluye automáticamente los elementos del directorio del proyecto de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="02748-105">Starting in Visual Studio 2017 / MSBuild version 15.3, the .NET SDK automatically includes items from the project directory by default.</span></span>  <span data-ttu-id="02748-106">Esto incluye los destinos `Compile` y `Content`.</span><span class="sxs-lookup"><span data-stu-id="02748-106">This includes `Compile` and `Content` targets.</span></span>  <span data-ttu-id="02748-107">Esto debería limpiar en gran medida el archivo del proyecto y reducir su complejidad.</span><span class="sxs-lookup"><span data-stu-id="02748-107">This should greatly clean up your project file and reduce the complexity you have there.</span></span>

<span data-ttu-id="02748-108">Puede revertir al comportamiento anterior si establece la propiedad correcta en "false".</span><span class="sxs-lookup"><span data-stu-id="02748-108">You can revert to the earlier behavior by setting the correct property to false.</span></span>

<span data-ttu-id="02748-109">Ejemplo para elementos `Compile`:</span><span class="sxs-lookup"><span data-stu-id="02748-109">Example for `Compile` items:</span></span>

```xml
<PropertyGroup>
    <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```
