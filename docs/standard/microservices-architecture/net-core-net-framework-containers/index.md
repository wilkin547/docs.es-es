---
title: Selección entre .NET Core y .NET Framework para contenedores de Docker
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Selección entre .NET Core y .NET Framework para contenedores de Docker
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 60d21de06262a14f9be6a1a5ce80edf15ddf1b59
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="choosing-between-net-core-and-net-framework-for-docker-containers"></a><span data-ttu-id="cb756-104">Selección entre .NET Core y .NET Framework para contenedores de Docker</span><span class="sxs-lookup"><span data-stu-id="cb756-104">Choosing Between .NET Core and .NET Framework for Docker Containers</span></span>

<span data-ttu-id="cb756-105">Se admiten dos implementaciones para compilar aplicaciones de Docker en contenedor del lado del servidor con .NET: [.NET Framework](https://www.microsoft.com/net/download/framework) y [.NET Core](https://www.microsoft.com/net/download/core).</span><span class="sxs-lookup"><span data-stu-id="cb756-105">There are two supported implementations for building server-side containerized Docker applications with .NET: [.NET Framework](https://www.microsoft.com/net/download/framework) and [.NET Core](https://www.microsoft.com/net/download/core).</span></span> <span data-ttu-id="cb756-106">Ambas comparten muchos de los componentes de .NET Standard y es posible compartir código entre ellas.</span><span class="sxs-lookup"><span data-stu-id="cb756-106">They share many .NET Standard components, and you can share code across the two.</span></span> <span data-ttu-id="cb756-107">Aun así, presentan diferencias fundamentales, y la elección de la implementación dependerá de lo que quiera realizar.</span><span class="sxs-lookup"><span data-stu-id="cb756-107">However, there are fundamental differences between them, and which implementation you use will depend on what you want to accomplish.</span></span> <span data-ttu-id="cb756-108">En esta sección se proporciona orientación sobre cuándo se debe elegir cada implementación.</span><span class="sxs-lookup"><span data-stu-id="cb756-108">This section provides guidance on when to choose each implementation.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="cb756-109">[Anterior] (../container-docker-introduction/docker-containers-images-registries.md) [Siguiente] (general-guidance.md)</span><span class="sxs-lookup"><span data-stu-id="cb756-109">[Previous] (../container-docker-introduction/docker-containers-images-registries.md) [Next] (general-guidance.md)</span></span>
