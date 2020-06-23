---
ms.openlocfilehash: 15418d1ac3ade6a0fa35ca61a02134e20af1baea
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602745"
---

<span data-ttu-id="9aefd-101">Al instalar el paquete de .NET Core, puede ver un error similar a `Failed to fetch ... File has unexpected size ... Mirror sync in progress?`.</span><span class="sxs-lookup"><span data-stu-id="9aefd-101">While installing the .NET Core package, you may see an error similar to `Failed to fetch ... File has unexpected size ... Mirror sync in progress?`.</span></span> <span data-ttu-id="9aefd-102">Este error significa que la fuente de paquetes de .NET Core se está actualizando con versiones de paquetes más recientes y que debe volver a intentarlo más tarde.</span><span class="sxs-lookup"><span data-stu-id="9aefd-102">This error could mean that the package feed for .NET Core is being upgraded with newer package versions, and that you should try again later.</span></span> <span data-ttu-id="9aefd-103">Durante una actualización, la falta de disponibilidad de la fuente de paquetes no debe ser superior a 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="9aefd-103">During an upgrade, the package feed shouldn't be unavailable for more than 30 minutes.</span></span> <span data-ttu-id="9aefd-104">Si recibe este error continuamente durante más de 30 minutos, abra una incidencia en <https://github.com/dotnet/core/issues>.</span><span class="sxs-lookup"><span data-stu-id="9aefd-104">If you continually receive this error for more than 30 minutes, please file an issue at <https://github.com/dotnet/core/issues>.</span></span>
