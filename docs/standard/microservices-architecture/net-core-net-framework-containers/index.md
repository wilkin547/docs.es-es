---
title: Selección entre .NET Core y .NET Framework para contenedores de Docker
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Selección entre .NET Core y .NET Framework para contenedores de Docker
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: b483214e7bd039a71ae642aa26e69d63222af8ab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="choosing-between-net-core-and-net-framework-for-docker-containers"></a><span data-ttu-id="828bf-103">Selección entre .NET Core y .NET Framework para contenedores de Docker</span><span class="sxs-lookup"><span data-stu-id="828bf-103">Choosing Between .NET Core and .NET Framework for Docker Containers</span></span>

<span data-ttu-id="828bf-104">Se admiten dos implementaciones para compilar aplicaciones de Docker en contenedor del lado del servidor con .NET: [.NET Framework](https://www.microsoft.com/net/download/framework) y [.NET Core](https://www.microsoft.com/net/download/core).</span><span class="sxs-lookup"><span data-stu-id="828bf-104">There are two supported implementations for building server-side containerized Docker applications with .NET: [.NET Framework](https://www.microsoft.com/net/download/framework) and [.NET Core](https://www.microsoft.com/net/download/core).</span></span> <span data-ttu-id="828bf-105">Ambas comparten muchos de los componentes de .NET Standard y es posible compartir código entre ellas.</span><span class="sxs-lookup"><span data-stu-id="828bf-105">They share many .NET Standard components, and you can share code across the two.</span></span> <span data-ttu-id="828bf-106">Aun así, presentan diferencias fundamentales, y la elección de la implementación dependerá de lo que quiera realizar.</span><span class="sxs-lookup"><span data-stu-id="828bf-106">However, there are fundamental differences between them, and which implementation you use will depend on what you want to accomplish.</span></span> <span data-ttu-id="828bf-107">En esta sección se proporciona orientación sobre cuándo se debe elegir cada implementación.</span><span class="sxs-lookup"><span data-stu-id="828bf-107">This section provides guidance on when to choose each implementation.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="828bf-108">[Anterior] (../container-docker-introduction/docker-containers-images-registries.md) [Siguiente] (general-guidance.md)</span><span class="sxs-lookup"><span data-stu-id="828bf-108">[Previous] (../container-docker-introduction/docker-containers-images-registries.md) [Next] (general-guidance.md)</span></span>
