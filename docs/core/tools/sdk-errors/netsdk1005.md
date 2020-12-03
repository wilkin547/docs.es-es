---
title: 'NETSDK1005 y NETSDK1047: Falta el destino del archivo de recursos'
description: Procedimiento para resolver el problema de la falta de un destino en un archivo de recursos.
author: sfoslund
ms.topic: error-reference
ms.date: 10/09/2020
f1_keywords:
- NETSDK1005
- NETSDK1047
ms.openlocfilehash: 207c8b0274c13e7af594e05cfac2a95907f85b81
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717908"
---
# <a name="netsdk1005-and-netsdk1047-asset-file-is-missing-target"></a><span data-ttu-id="aa491-103">NETSDK1005 y NETSDK1047: Falta el destino del archivo de recursos</span><span class="sxs-lookup"><span data-stu-id="aa491-103">NETSDK1005 and NETSDK1047: Asset file is missing target</span></span>

<span data-ttu-id="aa491-104">**Este artículo se aplica a: ✔️** SDK de .NET Core 2.1.100 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="aa491-104">**This article applies to:** ✔️ .NET Core 2.1.100 SDK and later versions</span></span>

<span data-ttu-id="aa491-105">Cuando el SDK de .NET emite el error NETSDK1005 o NETSDK1047, falta información sobre una de las plataformas de destino en el archivo de recursos del proyecto.</span><span class="sxs-lookup"><span data-stu-id="aa491-105">When the .NET SDK issues error NETSDK1005 or NETSDK1047, the project's assets file is missing information on one of your target frameworks.</span></span> <span data-ttu-id="aa491-106">Normalmente, para corregir esto debe asegurarse de que se ejecute la restauración y de que el valor de destino que falta está incluido en la propiedad `TargetFrameworks` del proyecto.</span><span class="sxs-lookup"><span data-stu-id="aa491-106">This can usually be fixed by ensuring that restore is run and that the missing target value is included in the `TargetFrameworks` property of your project.</span></span>

> [!NOTE]
> <span data-ttu-id="aa491-107">Ha habido un problema conocido con las primeras compilaciones de .NET 5 Preview 8 cuando se usaba con versiones de vista previa de Visual Studio 16.8 en las que se producía este error.</span><span class="sxs-lookup"><span data-stu-id="aa491-107">There was a known issue with early builds of .NET 5 preview 8 when used with versions of Visual Studio 16.8 previews which resulted in this error.</span></span> <span data-ttu-id="aa491-108">En concreto, si el destino que falta es `net5.0-windows7.0` o `net5.0`, asegúrese de que ha actualizado a las versiones más recientes de Visual Studio y el SDK de .NET 5.</span><span class="sxs-lookup"><span data-stu-id="aa491-108">Specifically, if the missing target is `net5.0-windows7.0` or `net5.0`, ensure that you have updated to the latest versions of Visual Studio and the .NET 5 SDK.</span></span>
