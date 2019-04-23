---
title: Selección entre .NET Core y .NET Framework para contenedores de Docker
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Selección entre .NET Core y .NET Framework para contenedores de Docker
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/11/2018
ms.openlocfilehash: e71739b06275d4ee786d246004930d7b66fbc72b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62019612"
---
# <a name="choosing-between-net-core-and-net-framework-for-docker-containers"></a><span data-ttu-id="3b24a-103">Selección entre .NET Core y .NET Framework para contenedores de Docker</span><span class="sxs-lookup"><span data-stu-id="3b24a-103">Choosing Between .NET Core and .NET Framework for Docker Containers</span></span>

<span data-ttu-id="3b24a-104">Se admiten dos marcos para compilar aplicaciones de Docker en contenedor del lado servidor con .NET: [.NET Framework y .NET Core](https://www.microsoft.com/net/download).</span><span class="sxs-lookup"><span data-stu-id="3b24a-104">There are two supported frameworks for building server-side containerized Docker applications with .NET: [.NET Framework and .NET Core](https://www.microsoft.com/net/download).</span></span> <span data-ttu-id="3b24a-105">Ambos comparten muchos de los componentes de la plataforma .NET y es posible compartir código entre ellos.</span><span class="sxs-lookup"><span data-stu-id="3b24a-105">They share many .NET platform components, and you can share code across the two.</span></span> <span data-ttu-id="3b24a-106">Aun así, presentan diferencias fundamentales, y la elección del marco dependerá de lo que quiera realizar.</span><span class="sxs-lookup"><span data-stu-id="3b24a-106">However, there are fundamental differences between them, and which framework you use will depend on what you want to accomplish.</span></span> <span data-ttu-id="3b24a-107">En esta sección se proporciona orientación sobre cuándo se debe elegir cada marco.</span><span class="sxs-lookup"><span data-stu-id="3b24a-107">This section provides guidance on when to choose each framework.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="3b24a-108">[Anterior](../container-docker-introduction/docker-containers-images-registries.md)
>[Siguiente](general-guidance.md)</span><span class="sxs-lookup"><span data-stu-id="3b24a-108">[Previous](../container-docker-introduction/docker-containers-images-registries.md)
[Next](general-guidance.md)</span></span>