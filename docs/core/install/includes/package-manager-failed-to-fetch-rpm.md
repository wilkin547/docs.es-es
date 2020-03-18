---
ms.openlocfilehash: 96f3ef0160144322f77413995c842b745bb5bb1e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "76920734"
---

<span data-ttu-id="c871e-101">Al instalar el paquete de .NET Core, puede ver un error similar a `signature verification failed for file 'repomd.xml' from repository 'packages-microsoft-com-prod'`.</span><span class="sxs-lookup"><span data-stu-id="c871e-101">While installing the .NET Core package, you may see an error similar to `signature verification failed for file 'repomd.xml' from repository 'packages-microsoft-com-prod'`.</span></span> <span data-ttu-id="c871e-102">En términos generales, este error significa que la fuente de paquetes para .NET Core se está actualizando con versiones de paquetes más recientes y que debe volver a intentarlo más tarde.</span><span class="sxs-lookup"><span data-stu-id="c871e-102">Generally speaking, this error means that the package feed for .NET Core is being upgraded with newer package versions, and that you should try again later.</span></span> <span data-ttu-id="c871e-103">Durante una actualización, la fuente de paquetes no debe estar disponible durante más de 2 horas.</span><span class="sxs-lookup"><span data-stu-id="c871e-103">During an upgrade, the package feed should not be unavailable for more than 2 hours.</span></span> <span data-ttu-id="c871e-104">Si recibe este error continuamente durante más de 2 horas, abra una incidencia en <https://github.com/dotnet/core/issues>.</span><span class="sxs-lookup"><span data-stu-id="c871e-104">If you continually receive this error for more than 2 hours, please file an issue at <https://github.com/dotnet/core/issues>.</span></span>
