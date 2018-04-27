---
title: Cuándo se debe implementar contenedores de Windows en el servicio de contenedor de Azure (es decir, Kubernetes)
description: Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Cuándo se debe implementar contenedores de Windows en el servicio de contenedor de Azure (es decir, Kubernetes)
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.prod: .net
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: cccf78ef5b7683a2eefa3efab50a7bbe1bffda18
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2018
---
# <a name="when-to-deploy-windows-containers-to-azure-container-service-that-is-kubernetes"></a><span data-ttu-id="5358d-103">Cuándo se debe implementar contenedores de Windows en el servicio de contenedor de Azure (es decir, Kubernetes)</span><span class="sxs-lookup"><span data-stu-id="5358d-103">When to deploy Windows Containers to Azure Container Service (that is, Kubernetes)</span></span>

<span data-ttu-id="5358d-104">Servicio de contenedor de Azure optimiza la configuración de tecnologías y herramientas de código abierto populares específicamente para Azure.</span><span class="sxs-lookup"><span data-stu-id="5358d-104">Azure Container Service optimizes the configuration of popular open-source tools and technologies specifically for Azure.</span></span> <span data-ttu-id="5358d-105">Obtener una solución abierta que ofrece la portabilidad de los contenedores y para la configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5358d-105">You get an open solution that offers portability both for your containers and for your application configuration.</span></span> <span data-ttu-id="5358d-106">Seleccione el tamaño, el número de hosts y las herramientas de orchestrator.</span><span class="sxs-lookup"><span data-stu-id="5358d-106">You select the size, the number of hosts, and the orchestrator tools.</span></span> <span data-ttu-id="5358d-107">Servicio de contenedor de Azure controla la infraestructura de.</span><span class="sxs-lookup"><span data-stu-id="5358d-107">Azure Container Service handles the infrastructure for you.</span></span>

<span data-ttu-id="5358d-108">Si ya está trabajando con orchestrators de código abierto como Kubernetes, Docker Swarm o DC/OS, no es necesario cambiar sus prácticas de administración existente para mover cargas de trabajo de contenedor en la nube.</span><span class="sxs-lookup"><span data-stu-id="5358d-108">If you are already working with open-source orchestrators like Kubernetes, Docker Swarm, or DC/OS, you don't need to change your existing management practices to move container workloads to the cloud.</span></span> <span data-ttu-id="5358d-109">Use las herramientas de administración de la aplicación que ya está familiarizado con y conectarse a través de los extremos de API estándar para el orquestador de su elección.</span><span class="sxs-lookup"><span data-stu-id="5358d-109">Use the application management tools that you're already familiar with, and connect via the standard API endpoints for the orchestrator of your choice.</span></span>

<span data-ttu-id="5358d-110">Todas estas orchestrators son entornos consolidados si utilizas contenedores de Linux Docker, pero también compatibilidad con contenedores de Windows como de 2017 (algunos anteriormente, algunos más recientemente, según el orchestrator).</span><span class="sxs-lookup"><span data-stu-id="5358d-110">All these orchestrators are mature environments if you are using Linux Docker containers, but they also support Windows Containers as of 2017 (some earlier, some more recently, depending on the orchestrator).</span></span>

<span data-ttu-id="5358d-111">Por ejemplo, en Kubernetes, la compatibilidad con contenedores es nativo (ciudadano de primera clase), por lo que usar contenedores de Windows en Kubernetes también es muy eficaz y confiable (en vista previa hasta una fase temprana quedan 2017).</span><span class="sxs-lookup"><span data-stu-id="5358d-111">For example, in Kubernetes, support for containers is native (first-class citizen), so using Windows Containers on Kubernetes is also very effective and reliable (in preview until early fall 2017).</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="5358d-112">[Anterior](when-to-deploy-windows-containers-to-service-fabric.md)
[Siguiente](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="5358d-112">[Previous](when-to-deploy-windows-containers-to-service-fabric.md)
[Next](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span></span>
