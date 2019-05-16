---
title: Cuándo se deben implementar contenedores de Windows en Azure Container Service (es decir, Kubernetes)
description: Modernizar aplicaciones .NET existentes con contenedores de Windows y la nube de Azure | Cuándo se deben implementar contenedores de Windows en Azure Container Service (es decir, Kubernetes)
ms.date: 04/30/2018
ms.openlocfilehash: 921767b52f2b0d80f2d31d972b65ac7551d2f7c5
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65643570"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-service-that-is-kubernetes"></a><span data-ttu-id="b0d3f-103">Cuándo se deben implementar contenedores de Windows en Azure Container Service (es decir, Kubernetes)</span><span class="sxs-lookup"><span data-stu-id="b0d3f-103">When to deploy Windows Containers to Azure Container Service (that is, Kubernetes)</span></span>

<span data-ttu-id="b0d3f-104">Azure Container Service optimiza la configuración de tecnologías y herramientas populares de código abierto específicamente para Azure.</span><span class="sxs-lookup"><span data-stu-id="b0d3f-104">Azure Container Service optimizes the configuration of popular open-source tools and technologies specifically for Azure.</span></span> <span data-ttu-id="b0d3f-105">Obtenga una solución abierta que ofrece la portabilidad para sus contenedores tanto para la configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b0d3f-105">You get an open solution that offers portability both for your containers and for your application configuration.</span></span> <span data-ttu-id="b0d3f-106">Seleccione el tamaño, el número de hosts y las herramientas de orchestrator.</span><span class="sxs-lookup"><span data-stu-id="b0d3f-106">You select the size, the number of hosts, and the orchestrator tools.</span></span> <span data-ttu-id="b0d3f-107">Azure Container Service controla la infraestructura para usted.</span><span class="sxs-lookup"><span data-stu-id="b0d3f-107">Azure Container Service handles the infrastructure for you.</span></span>

<span data-ttu-id="b0d3f-108">Si ya está trabajando con orquestadores de código abierto como Kubernetes, Docker Swarm o DC/OS, no es necesario cambiar sus prácticas de administración existente para mover las cargas de trabajo de contenedor a la nube.</span><span class="sxs-lookup"><span data-stu-id="b0d3f-108">If you are already working with open-source orchestrators like Kubernetes, Docker Swarm, or DC/OS, you don't need to change your existing management practices to move container workloads to the cloud.</span></span> <span data-ttu-id="b0d3f-109">Usar las herramientas de administración de la aplicación que ya está familiarizado y conéctese a través de los puntos de conexión de API estándares para el orquestador de su elección.</span><span class="sxs-lookup"><span data-stu-id="b0d3f-109">Use the application management tools that you're already familiar with and connect via the standard API endpoints for the orchestrator of your choice.</span></span>

<span data-ttu-id="b0d3f-110">Todos estos orquestadores son entornos maduros si usa contenedores de Linux Docker, pero sólo puede estar en estado de vista previa para los contenedores de Windows.</span><span class="sxs-lookup"><span data-stu-id="b0d3f-110">All these orchestrators are mature environments if you are using Linux Docker containers, but might only be in Preview state for Windows Containers.</span></span>

<span data-ttu-id="b0d3f-111">Por ejemplo, en Kubernetes, compatibilidad para contenedores es nativo (ciudadano de primera clase), mediante contenedores de Windows en Kubernetes también es efectivo (en versión preliminar de ACS a partir de principios de 2018).</span><span class="sxs-lookup"><span data-stu-id="b0d3f-111">For example, in Kubernetes, support for containers is native (first-class citizen), so using Windows Containers on Kubernetes is also effective (in preview in ACS as of early 2018).</span></span>

<span data-ttu-id="b0d3f-112">Nota importante: El evolucionadas y "PaaS más" versión de ACS (Azure Container Service) para Kubernetes es AKS (Azure Kubernetes Service), sin embargo, los contenedores de Windows aún no se admiten a partir del 2 º trimestre de 2018, pero se admitirá pronto.</span><span class="sxs-lookup"><span data-stu-id="b0d3f-112">Important note: The evolved and “more PaaS” version of ACS (Azure Container Service) for Kubernetes is AKS (Azure Kubernetes Service), however, Windows Containers are still not supported as of Q2 2018, but it will be supported soon.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="b0d3f-113">[Anterior](when-to-deploy-windows-containers-to-service-fabric.md)
>[Siguiente](choosing-azure-compute-options-for-container-based-applications.md)</span><span class="sxs-lookup"><span data-stu-id="b0d3f-113">[Previous](when-to-deploy-windows-containers-to-service-fabric.md)
[Next](choosing-azure-compute-options-for-container-based-applications.md)</span></span>
