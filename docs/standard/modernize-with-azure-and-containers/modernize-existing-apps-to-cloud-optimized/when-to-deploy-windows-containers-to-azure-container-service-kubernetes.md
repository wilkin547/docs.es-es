---
title: Cuándo se debe implementar contenedores de Windows en el servicio de contenedor de Azure (es decir, Kubernetes)
description: Modernizar las aplicaciones .NET existentes con contenedores de Windows y de nube de Azure | Cuándo se debe implementar contenedores de Windows en el servicio de contenedor de Azure (es decir, Kubernetes)
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/30/2018
ms.openlocfilehash: b7f106e2b79a2c6bb24733debf7f4828505d66a6
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2018
ms.locfileid: "33958175"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-service-that-is-kubernetes"></a><span data-ttu-id="d6cb6-103">Cuándo se debe implementar contenedores de Windows en el servicio de contenedor de Azure (es decir, Kubernetes)</span><span class="sxs-lookup"><span data-stu-id="d6cb6-103">When to deploy Windows Containers to Azure Container Service (that is, Kubernetes)</span></span>

<span data-ttu-id="d6cb6-104">Servicio de contenedor de Azure optimiza la configuración de tecnologías y herramientas de código abierto populares específicamente para Azure.</span><span class="sxs-lookup"><span data-stu-id="d6cb6-104">Azure Container Service optimizes the configuration of popular open-source tools and technologies specifically for Azure.</span></span> <span data-ttu-id="d6cb6-105">Obtener una solución abierta que ofrece la portabilidad de los contenedores y para la configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d6cb6-105">You get an open solution that offers portability both for your containers and for your application configuration.</span></span> <span data-ttu-id="d6cb6-106">Seleccione el tamaño, el número de hosts y las herramientas de orchestrator.</span><span class="sxs-lookup"><span data-stu-id="d6cb6-106">You select the size, the number of hosts, and the orchestrator tools.</span></span> <span data-ttu-id="d6cb6-107">Servicio de contenedor de Azure controla la infraestructura de.</span><span class="sxs-lookup"><span data-stu-id="d6cb6-107">Azure Container Service handles the infrastructure for you.</span></span>

<span data-ttu-id="d6cb6-108">Si ya está trabajando con orchestrators de código abierto como Kubernetes, Docker Swarm o DC/OS, no es necesario cambiar sus prácticas de administración existente para mover cargas de trabajo de contenedor en la nube.</span><span class="sxs-lookup"><span data-stu-id="d6cb6-108">If you are already working with open-source orchestrators like Kubernetes, Docker Swarm, or DC/OS, you don't need to change your existing management practices to move container workloads to the cloud.</span></span> <span data-ttu-id="d6cb6-109">Usar las herramientas de administración de aplicación que ya está familiarizado con y se conecte a través de los extremos de API estándar por el orquestador de su elección.</span><span class="sxs-lookup"><span data-stu-id="d6cb6-109">Use the application management tools that you're already familiar with and connect via the standard API endpoints for the orchestrator of your choice.</span></span>

<span data-ttu-id="d6cb6-110">Todas estas orchestrators son entornos consolidados si utiliza contenedores de Linux Docker, pero sólo puede estar en estado de vista previa para los contenedores de Windows.</span><span class="sxs-lookup"><span data-stu-id="d6cb6-110">All these orchestrators are mature environments if you are using Linux Docker containers, but might only be in Preview state for Windows Containers.</span></span>

<span data-ttu-id="d6cb6-111">Por ejemplo, en Kubernetes, la compatibilidad con contenedores es nativo (ciudadano de primera clase), por lo que usar contenedores de Windows en Kubernetes también es efectivo (en versión preliminar en ACS a partir de 2018 anticipado).</span><span class="sxs-lookup"><span data-stu-id="d6cb6-111">For example, in Kubernetes, support for containers is native (first-class citizen), so using Windows Containers on Kubernetes is also effective (in preview in ACS as of early 2018).</span></span>

<span data-ttu-id="d6cb6-112">Nota importante: la evolved y "PaaS más" versión de ACS (servicio de contenedor de Azure) para Kubernetes es AKS (servicio de Kubernetes de Azure), sin embargo, los contenedores de Windows aún no se admiten a partir de Q2 2018, pero se admitirá pronto.</span><span class="sxs-lookup"><span data-stu-id="d6cb6-112">Important note: The evolved and “more PaaS” version of ACS (Azure Container Service) for Kubernetes is AKS (Azure Kubernetes Service), however, Windows Containers are still not supported as of Q2 2018, but it will be supported soon.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="d6cb6-113">[Anterior](when-to-deploy-windows-containers-to-service-fabric.md)
[Siguiente](choosing-azure-compute-options-for-container-based-applications.md)</span><span class="sxs-lookup"><span data-stu-id="d6cb6-113">[Previous](when-to-deploy-windows-containers-to-service-fabric.md)
[Next](choosing-azure-compute-options-for-container-based-applications.md)</span></span>
