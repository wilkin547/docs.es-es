---
title: Cuándo se deben implementar contenedores Windows en Azure Container Service (es decir, Kubernetes)
description: Modernización de las aplicaciones .NET existentes con Azure Clour y contenedores Windows | Cuándo se deben implementar contenedores Windows en Azure Container Service (es decir, Kubernetes)
ms.date: 04/30/2018
ms.openlocfilehash: 3ff51a70d4e158b831155ab4992ec32f5d98cedb
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2020
ms.locfileid: "80987769"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-service-that-is-kubernetes"></a><span data-ttu-id="22ec3-103">Cuándo se deben implementar contenedores Windows en Azure Container Service (es decir, Kubernetes)</span><span class="sxs-lookup"><span data-stu-id="22ec3-103">When to deploy Windows Containers to Azure Container Service (that is, Kubernetes)</span></span>

<span data-ttu-id="22ec3-104">Azure Container Service optimiza la configuración de las conocidas herramientas y tecnologías de código abierto específicamente para Azure.</span><span class="sxs-lookup"><span data-stu-id="22ec3-104">Azure Container Service optimizes the configuration of popular open-source tools and technologies specifically for Azure.</span></span> <span data-ttu-id="22ec3-105">Se trata de una solución abierta que ofrece portabilidad tanto para los contenedores como para la configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="22ec3-105">You get an open solution that offers portability both for your containers and for your application configuration.</span></span> <span data-ttu-id="22ec3-106">Seleccione el tamaño, el número de hosts y las herramientas de orquestador.</span><span class="sxs-lookup"><span data-stu-id="22ec3-106">You select the size, the number of hosts, and the orchestrator tools.</span></span> <span data-ttu-id="22ec3-107">Azure Container Service controla la infraestructura.</span><span class="sxs-lookup"><span data-stu-id="22ec3-107">Azure Container Service handles the infrastructure for you.</span></span>

<span data-ttu-id="22ec3-108">Si ya está trabajando con orquestadores de código abierto, como Kubernetes, Docker Swarm o DC/OS, no es necesario cambiar los procedimientos de administración existentes para trasladar las cargas de trabajo de los contenedores a la nube.</span><span class="sxs-lookup"><span data-stu-id="22ec3-108">If you are already working with open-source orchestrators like Kubernetes, Docker Swarm, or DC/OS, you don't need to change your existing management practices to move container workloads to the cloud.</span></span> <span data-ttu-id="22ec3-109">Use las herramientas de administración de aplicaciones con las que ya está familiarizado y conéctelas a través de los puntos de conexión de API estándar para el orquestador de su elección.</span><span class="sxs-lookup"><span data-stu-id="22ec3-109">Use the application management tools that you're already familiar with and connect via the standard API endpoints for the orchestrator of your choice.</span></span>

<span data-ttu-id="22ec3-110">Todos estos orquestadores son entornos maduros si usa contenedores Linux de Docker, pero podrían estar solo en versión preliminar para los contenedores Windows.</span><span class="sxs-lookup"><span data-stu-id="22ec3-110">All these orchestrators are mature environments if you are using Linux Docker containers, but might only be in Preview state for Windows Containers.</span></span>

<span data-ttu-id="22ec3-111">Por ejemplo, en Kubernetes, la compatibilidad con contenedores es nativa (ciudadano de primera clase), por lo que el uso de contenedores Windows en Kubernetes también es eficaz (en versión preliminar en ACS desde principios de 2018).</span><span class="sxs-lookup"><span data-stu-id="22ec3-111">For example, in Kubernetes, support for containers is native (first-class citizen), so using Windows Containers on Kubernetes is also effective (in preview in ACS as of early 2018).</span></span>

<span data-ttu-id="22ec3-112">Nota importante: La versión evolucionada y "más PaaS" de ACS (Azure Container Service) para Kubernetes es AKS (Azure Kubernetes Service). Sin embargo, en el 2T de 2018 aún no se admiten los contenedores Windows, que pronto se admitirán.</span><span class="sxs-lookup"><span data-stu-id="22ec3-112">Important note: The evolved and "more PaaS" version of ACS (Azure Container Service) for Kubernetes is AKS (Azure Kubernetes Service), however, Windows Containers are still not supported as of Q2 2018, but it will be supported soon.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="22ec3-113">[Anterior](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)
>[Siguiente](choosing-azure-compute-options-for-container-based-applications.md)</span><span class="sxs-lookup"><span data-stu-id="22ec3-113">[Previous](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)
[Next](choosing-azure-compute-options-for-container-based-applications.md)</span></span>
