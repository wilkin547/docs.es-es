---
title: "Modernizar del ciclo de vida de la aplicación con las canalizaciones de CI/CD y las herramientas de DevOps en la nube"
description: "Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Modernizar del ciclo de vida de la aplicación con las canalizaciones de CI/CD y las herramientas de DevOps en la nube"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c0b87d01c1305695dacaf3ba112b387de2ee0cc1
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="modernize-your-apps-lifecycle-with-cicd-pipelines-and-devops-tools-in-the-cloud"></a><span data-ttu-id="6ce16-103">Modernizar del ciclo de vida de la aplicación con las canalizaciones de CI/CD y las herramientas de DevOps en la nube</span><span class="sxs-lookup"><span data-stu-id="6ce16-103">Modernize your app's lifecycle with CI/CD pipelines and DevOps tools in the cloud</span></span>

<span data-ttu-id="6ce16-104">Las empresas de hoy en día necesitan innovar a un ritmo rápido para ser competitivos en el mercado.</span><span class="sxs-lookup"><span data-stu-id="6ce16-104">Today’s businesses need to innovate at a rapid pace to be competitive in the marketplace.</span></span> <span data-ttu-id="6ce16-105">Entrega de alta calidad, las aplicaciones modernas requiere las herramientas de DevOps y procesos que son fundamentales para implementar este ciclo constante de innovación.</span><span class="sxs-lookup"><span data-stu-id="6ce16-105">Delivering high-quality, modern applications requires DevOps tools and processes that are critical to implement this constant cycle of innovation.</span></span> <span data-ttu-id="6ce16-106">Con las herramientas adecuadas de DevOps, los desarrolladores pueden simplificar la implementación continua y obtención más rápida de aplicaciones innovadoras en manos de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="6ce16-106">With the right DevOps tools, developers can streamline continuous deployment and get innovative applications into the hands of users more quickly.</span></span>

<span data-ttu-id="6ce16-107">Aunque los procedimientos de integración e implementación continuados están bien consolidados, la introducción de contenedores presenta nuevas consideraciones, especialmente cuando se trabaja con aplicaciones de contenedor de varios.</span><span class="sxs-lookup"><span data-stu-id="6ce16-107">Although continuous integration and deployment practices are well established, the introduction of containers introduces new considerations, particularly when you are working with multi-container applications.</span></span>

<span data-ttu-id="6ce16-108">Visual Studio Team Services admite la integración continua y la implementación de aplicaciones de contenedor de varios a una variedad de entornos a través de las tareas de implementación de Team Services oficiales:</span><span class="sxs-lookup"><span data-stu-id="6ce16-108">Visual Studio Team Services supports continuous integration and deployment of multi-container applications to a variety of environments through the official Team Services deployment tasks:</span></span>

-   <span data-ttu-id="6ce16-109">[Implementar en la máquina virtual del Host de Docker independiente](https://docs.microsoft.com/vsts/build-release/apps/cd/deploy-docker-windowsvm) (Linux o Windows Server 2016 o posterior)</span><span class="sxs-lookup"><span data-stu-id="6ce16-109">[Deploy to standalone Docker Host VM](https://docs.microsoft.com/vsts/build-release/apps/cd/deploy-docker-windowsvm) (Linux or Windows Server 2016 or later)</span></span>

-   [<span data-ttu-id="6ce16-110">Implementar en Service Fabric.</span><span class="sxs-lookup"><span data-stu-id="6ce16-110">Deploy to Service Fabric</span></span>](https://docs.microsoft.com/azure/service-fabric/service-fabric-tutorial-deploy-app-with-cicd-vsts)

-   [<span data-ttu-id="6ce16-111">Implementar en el servicio de contenedor de Azure: Kubernetes</span><span class="sxs-lookup"><span data-stu-id="6ce16-111">Deploy to Azure Container Service – Kubernetes</span></span>](https://docs.microsoft.com/vsts/build-release/apps/cd/azure/deploy-container-kubernetes)

<span data-ttu-id="6ce16-112">Pero también puede implementar en [Docker Swarm](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/) o DC/OS mediante el uso de las tareas basadas en secuencias de comandos de Team Services.</span><span class="sxs-lookup"><span data-stu-id="6ce16-112">But you also can deploy to [Docker Swarm](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/) or DC/OS by using Team Services script-based tasks.</span></span>

<span data-ttu-id="6ce16-113">Para continuar facilitar la agilidad de la implementación, estas herramientas proporcionan experiencias de implementación excelente de desarrollo a prueba a producción para cargas de trabajo de contenedor, con una opción de desarrollo y las soluciones de integración continua/CD.</span><span class="sxs-lookup"><span data-stu-id="6ce16-113">To continue facilitating deployment agility, these tools provide excellent dev-to-test-to-production deployment experiences for container workloads, with a choice of development and CI/CD solutions.</span></span>

<span data-ttu-id="6ce16-114">Figura 4-12 se muestra una canalización de implementación continua que se implementa en un clúster de Kubernetes en el servicio de contenedor de Azure.</span><span class="sxs-lookup"><span data-stu-id="6ce16-114">Figure 4-12 shows a continuous deployment pipeline that deploys to a Kubernetes cluster in Azure Container Service.</span></span>

![Canalización de implementación continua de Visual Studio Team Services, implementar en un clúster de Kubernetes](./media/image12.png)

> <span data-ttu-id="6ce16-116">**Figura 4-12.**</span><span class="sxs-lookup"><span data-stu-id="6ce16-116">**Figure 4-12.**</span></span> <span data-ttu-id="6ce16-117">Canalización de implementación continua de Visual Studio Team Services, implementar en un clúster de Kubernetes</span><span class="sxs-lookup"><span data-stu-id="6ce16-117">Visual Studio Team Services continuous deployment pipeline, deploying to a Kubernetes cluster</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="6ce16-118">[Anterior](modernize-your-apps-with-monitoring-and-telemetry.md)
[Siguiente](migrate-to-hybrid-cloud-scenarios.md)</span><span class="sxs-lookup"><span data-stu-id="6ce16-118">[Previous](modernize-your-apps-with-monitoring-and-telemetry.md)
[Next](migrate-to-hybrid-cloud-scenarios.md)</span></span>
