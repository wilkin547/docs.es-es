---
title: Modernización del ciclo de vida de la aplicación con canalizaciones de CI/CD y herramientas de DevOps en la nube
description: Modernizar aplicaciones .NET existentes con contenedores de Windows y la nube de Azure | Modernice el ciclo de vida de la aplicación con canalizaciones de CI/CD y herramientas de DevOps en la nube
ms.date: 04/30/2018
ms.openlocfilehash: fb4bfab4a891e9c8a73867f18cb8249775f9b7b9
ms.sourcegitcommit: 34593b4d0be779699d38a9949d6aec11561657ec
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2019
ms.locfileid: "66833953"
---
# <a name="modernize-your-apps-lifecycle-with-cicd-pipelines-and-devops-tools-in-the-cloud"></a><span data-ttu-id="5e207-103">Modernización del ciclo de vida de la aplicación con canalizaciones de CI/CD y herramientas de DevOps en la nube</span><span class="sxs-lookup"><span data-stu-id="5e207-103">Modernize your app's lifecycle with CI/CD pipelines and DevOps tools in the cloud</span></span>

<span data-ttu-id="5e207-104">Las empresas de hoy en día necesitan innovar con rapidez para ser competitivos en marketplace.</span><span class="sxs-lookup"><span data-stu-id="5e207-104">Today’s businesses need to innovate at a rapid pace to be competitive in the marketplace.</span></span> <span data-ttu-id="5e207-105">Entrega de alta calidad, las aplicaciones modernas requiere herramientas de DevOps y procesos que son fundamentales para implementar este ciclo constante de innovación.</span><span class="sxs-lookup"><span data-stu-id="5e207-105">Delivering high-quality, modern applications requires DevOps tools and processes that are critical to implement this constant cycle of innovation.</span></span> <span data-ttu-id="5e207-106">Con las herramientas adecuadas de DevOps, los desarrolladores pueden simplificar la implementación continua y obtener aplicaciones innovadoras en manos de usuarios más rápidamente.</span><span class="sxs-lookup"><span data-stu-id="5e207-106">With the right DevOps tools, developers can streamline continuous deployment and get innovative applications into the hands of users more quickly.</span></span>

<span data-ttu-id="5e207-107">Aunque las prácticas de integración e implementación continua están bien consolidadas, la introducción de los contenedores de introduce nuevas consideraciones, especialmente cuando se trabaja con aplicaciones de varios contenedores.</span><span class="sxs-lookup"><span data-stu-id="5e207-107">Although continuous integration and deployment practices are well established, the introduction of containers introduces new considerations, particularly when you are working with multi-container applications.</span></span>

<span data-ttu-id="5e207-108">Servicios de Azure DevOps es compatible con la integración continua e implementación de aplicaciones de varios contenedores a una variedad de entornos a través de las tareas de implementación de servicios de Azure DevOps oficiales:</span><span class="sxs-lookup"><span data-stu-id="5e207-108">Azure DevOps Services supports continuous integration and deployment of multi-container applications to a variety of environments through the official Azure DevOps Services deployment tasks:</span></span>

- [<span data-ttu-id="5e207-109">Implementar en una aplicación Web de Azure para contenedores</span><span class="sxs-lookup"><span data-stu-id="5e207-109">Deploy to an Azure Web App for Containers</span></span>](https://docs.microsoft.com/azure/devops/pipelines/apps/cd/deploy-docker-webapp?view=azure-devops)

- [<span data-ttu-id="5e207-110">Implementar en Azure Container Service: Kubernetes</span><span class="sxs-lookup"><span data-stu-id="5e207-110">Deploy to Azure Container Service – Kubernetes</span></span>](https://docs.microsoft.com/azure/devops/build-release/apps/cd/azure/deploy-container-kubernetes)

<span data-ttu-id="5e207-111">Pero también puede implementar en [Docker Swarm](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/) o DC/OS mediante el uso de las tareas basadas en scripts de servicios de Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="5e207-111">But you also can deploy to [Docker Swarm](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/) or DC/OS by using Azure DevOps Services script-based tasks.</span></span>

<span data-ttu-id="5e207-112">Para continuar facilita la agilidad de implementación, estas herramientas ofrecen experiencias de implementación de desarrollo a prueba a producción excelente para cargas de trabajo de contenedor, con las opciones de desarrollo y las soluciones de CI/CD.</span><span class="sxs-lookup"><span data-stu-id="5e207-112">To continue facilitating deployment agility, these tools provide excellent dev-to-test-to-production deployment experiences for container workloads, with a choice of development and CI/CD solutions.</span></span>

<span data-ttu-id="5e207-113">Figura 4-12 se muestra una canalización de implementación continua que se implementa en un clúster de Kubernetes en Azure Container Service.</span><span class="sxs-lookup"><span data-stu-id="5e207-113">Figure 4-12 shows a continuous deployment pipeline that deploys to a Kubernetes cluster in Azure Container Service.</span></span>

![Canalización de implementación continua de Azure DevOps servicios, la implementación en un clúster de Kubernetes](./media/image12.png)

> <span data-ttu-id="5e207-115">**Figura 4-12.**</span><span class="sxs-lookup"><span data-stu-id="5e207-115">**Figure 4-12.**</span></span> <span data-ttu-id="5e207-116">Canalización de implementación continua de Azure DevOps servicios, la implementación en un clúster de Kubernetes</span><span class="sxs-lookup"><span data-stu-id="5e207-116">Azure DevOps Services continuous deployment pipeline, deploying to a Kubernetes cluster</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="5e207-117">[Anterior](modernize-your-apps-with-monitoring-and-telemetry.md)
>[Siguiente](migrate-to-hybrid-cloud-scenarios.md)</span><span class="sxs-lookup"><span data-stu-id="5e207-117">[Previous](modernize-your-apps-with-monitoring-and-telemetry.md)
[Next](migrate-to-hybrid-cloud-scenarios.md)</span></span>
