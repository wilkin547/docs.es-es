---
title: 'NETSDK1022: Se han incluido elementos duplicados.'
description: Procedimiento para resolver el mensaje de elementos duplicados en función de inclusiones predeterminadas.
author: marcpopMSFT
ms.topic: error-reference
ms.date: 10/9/2020
f1_keywords:
- NETSDK1022
ms.openlocfilehash: c2bdbbb5503e5e4f6e6826f95f5a2cb08c908ceb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717880"
---
# <a name="netsdk1022-duplicate-items-were-included"></a><span data-ttu-id="50ece-103">NETSDK1022: Se han incluido elementos duplicados.</span><span class="sxs-lookup"><span data-stu-id="50ece-103">NETSDK1022: Duplicate items were included.</span></span>

<span data-ttu-id="50ece-104">**Este artículo se aplica a: ✔️** SDK de .NET Core 2.1.100 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="50ece-104">**This article applies to:** ✔️ .NET Core 2.1.100 SDK and later versions</span></span>

<span data-ttu-id="50ece-105">A partir de Visual Studio 2017 y MSBuild, versión 15.3, el SDK de .NET incluye automáticamente los elementos del directorio del proyecto de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="50ece-105">Starting in Visual Studio 2017 / MSBuild version 15.3, the .NET SDK automatically includes items from the project directory by default.</span></span>  <span data-ttu-id="50ece-106">Esto incluye los destinos `Compile` y `Content`.</span><span class="sxs-lookup"><span data-stu-id="50ece-106">This includes `Compile` and `Content` targets.</span></span>  <span data-ttu-id="50ece-107">Esto debería limpiar en gran medida el archivo del proyecto y reducir su complejidad.</span><span class="sxs-lookup"><span data-stu-id="50ece-107">This should greatly clean up your project file and reduce the complexity you have there.</span></span>

<span data-ttu-id="50ece-108">Puede revertir al comportamiento anterior si establece la propiedad correcta en "false".</span><span class="sxs-lookup"><span data-stu-id="50ece-108">You can revert to the earlier behavior by setting the correct property to false.</span></span>

<span data-ttu-id="50ece-109">Ejemplo para elementos `Compile`:</span><span class="sxs-lookup"><span data-stu-id="50ece-109">Example for `Compile` items:</span></span>

```xml
<PropertyGroup>
    <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```
