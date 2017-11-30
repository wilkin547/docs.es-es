---
title: "Selección entre .NET Core y .NET Framework para contenedores de Docker"
description: "Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Selección entre .NET Core y .NET Framework para contenedores de Docker"
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: f7a5fee26f4d138ae22f3551a25a674b22a2f6d1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="choosing-between-net-core-and-net-framework-for-docker-containers"></a><span data-ttu-id="9d034-104">Selección entre .NET Core y .NET Framework para contenedores de Docker</span><span class="sxs-lookup"><span data-stu-id="9d034-104">Choosing Between .NET Core and .NET Framework for Docker Containers</span></span>

<span data-ttu-id="9d034-105">Se admiten dos implementaciones para compilar aplicaciones de Docker en contenedor del lado del servidor con .NET: [.NET Framework](https://www.microsoft.com/net/download/framework) y [.NET Core](https://www.microsoft.com/net/download/core).</span><span class="sxs-lookup"><span data-stu-id="9d034-105">There are two supported implementations for building server-side containerized Docker applications with .NET: [.NET Framework](https://www.microsoft.com/net/download/framework) and [.NET Core](https://www.microsoft.com/net/download/core).</span></span> <span data-ttu-id="9d034-106">Ambas comparten muchos de los componentes de .NET Standard y es posible compartir código entre ellas.</span><span class="sxs-lookup"><span data-stu-id="9d034-106">They share many .NET Standard components, and you can share code across the two.</span></span> <span data-ttu-id="9d034-107">Aun así, presentan diferencias fundamentales, y la elección de la implementación dependerá de lo que quiera realizar.</span><span class="sxs-lookup"><span data-stu-id="9d034-107">However, there are fundamental differences between them, and which implementation you use will depend on what you want to accomplish.</span></span> <span data-ttu-id="9d034-108">En esta sección se proporciona orientación sobre cuándo se debe elegir cada implementación.</span><span class="sxs-lookup"><span data-stu-id="9d034-108">This section provides guidance on when to choose each implementation.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="9d034-109">[Anterior] (../container-docker-introduction/docker-containers-images-registries.md) [Siguiente] (general-guidance.md)</span><span class="sxs-lookup"><span data-stu-id="9d034-109">[Previous] (../container-docker-introduction/docker-containers-images-registries.md) [Next] (general-guidance.md)</span></span>
