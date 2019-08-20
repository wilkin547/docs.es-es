---
title: Modernización del ciclo de vida de la aplicación con canalizaciones de CI/CD y herramientas de DevOps en la nube
description: Modernización de las aplicaciones .NET existentes con la nube de Azure y los contenedores de Windows | Modernización del ciclo de vida de la aplicación con canalizaciones de CI/CD y herramientas de DevOps en la nube
ms.date: 04/30/2018
ms.openlocfilehash: fb4bfab4a891e9c8a73867f18cb8249775f9b7b9
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "69578168"
---
# <a name="modernize-your-apps-lifecycle-with-cicd-pipelines-and-devops-tools-in-the-cloud"></a><span data-ttu-id="7a3a9-103">Modernización del ciclo de vida de la aplicación con canalizaciones de CI/CD y herramientas de DevOps en la nube</span><span class="sxs-lookup"><span data-stu-id="7a3a9-103">Modernize your app's lifecycle with CI/CD pipelines and DevOps tools in the cloud</span></span>

<span data-ttu-id="7a3a9-104">Las empresas de hoy en día deben innovar a un ritmo rápido para ser competitivos en Marketplace.</span><span class="sxs-lookup"><span data-stu-id="7a3a9-104">Today’s businesses need to innovate at a rapid pace to be competitive in the marketplace.</span></span> <span data-ttu-id="7a3a9-105">La entrega de aplicaciones modernas de alta calidad requiere herramientas y procesos de DevOps que son fundamentales para implementar este ciclo constante de innovación.</span><span class="sxs-lookup"><span data-stu-id="7a3a9-105">Delivering high-quality, modern applications requires DevOps tools and processes that are critical to implement this constant cycle of innovation.</span></span> <span data-ttu-id="7a3a9-106">Con las herramientas de DevOps adecuadas, los desarrolladores pueden simplificar la implementación continua y obtener aplicaciones innovadoras a las manos de los usuarios con más rapidez.</span><span class="sxs-lookup"><span data-stu-id="7a3a9-106">With the right DevOps tools, developers can streamline continuous deployment and get innovative applications into the hands of users more quickly.</span></span>

<span data-ttu-id="7a3a9-107">Aunque las prácticas de integración e implementación continuas están bien establecidas, la introducción de contenedores presenta nuevas consideraciones, sobre todo cuando se trabaja con aplicaciones de varios contenedores.</span><span class="sxs-lookup"><span data-stu-id="7a3a9-107">Although continuous integration and deployment practices are well established, the introduction of containers introduces new considerations, particularly when you are working with multi-container applications.</span></span>

<span data-ttu-id="7a3a9-108">Azure DevOps Services admite la integración y la implementación continuas de aplicaciones de varios contenedores en una gran variedad de entornos a través de las tareas de implementación de Azure DevOps Services oficiales:</span><span class="sxs-lookup"><span data-stu-id="7a3a9-108">Azure DevOps Services supports continuous integration and deployment of multi-container applications to a variety of environments through the official Azure DevOps Services deployment tasks:</span></span>

- [<span data-ttu-id="7a3a9-109">Implementación en una Web App for Containers de Azure</span><span class="sxs-lookup"><span data-stu-id="7a3a9-109">Deploy to an Azure Web App for Containers</span></span>](https://docs.microsoft.com/azure/devops/pipelines/apps/cd/deploy-docker-webapp?view=azure-devops)

- [<span data-ttu-id="7a3a9-110">Implementar en Azure Container Service: Kubernetes</span><span class="sxs-lookup"><span data-stu-id="7a3a9-110">Deploy to Azure Container Service – Kubernetes</span></span>](https://docs.microsoft.com/azure/devops/build-release/apps/cd/azure/deploy-container-kubernetes)

<span data-ttu-id="7a3a9-111">Pero también puede implementar en [Docker Swarm](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/) o DC/os mediante el uso de Azure DevOps Services tareas basadas en scripts.</span><span class="sxs-lookup"><span data-stu-id="7a3a9-111">But you also can deploy to [Docker Swarm](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/) or DC/OS by using Azure DevOps Services script-based tasks.</span></span>

<span data-ttu-id="7a3a9-112">Para seguir facilitando la agilidad de la implementación, estas herramientas proporcionan excelentes experiencias de implementación de desarrollo a prueba en producción para cargas de trabajo de contenedor, con una elección de soluciones de desarrollo y de CI/CD.</span><span class="sxs-lookup"><span data-stu-id="7a3a9-112">To continue facilitating deployment agility, these tools provide excellent dev-to-test-to-production deployment experiences for container workloads, with a choice of development and CI/CD solutions.</span></span>

<span data-ttu-id="7a3a9-113">En la figura 4-12 se muestra una canalización de implementación continua que se implementa en un clúster de Kubernetes en Azure Container Service.</span><span class="sxs-lookup"><span data-stu-id="7a3a9-113">Figure 4-12 shows a continuous deployment pipeline that deploys to a Kubernetes cluster in Azure Container Service.</span></span>

![Azure DevOps Services canalización de implementación continua, implementar en un clúster de Kubernetes](./media/image12.png)

> <span data-ttu-id="7a3a9-115">**Figura 4-12.**</span><span class="sxs-lookup"><span data-stu-id="7a3a9-115">**Figure 4-12.**</span></span> <span data-ttu-id="7a3a9-116">Azure DevOps Services canalización de implementación continua, implementar en un clúster de Kubernetes</span><span class="sxs-lookup"><span data-stu-id="7a3a9-116">Azure DevOps Services continuous deployment pipeline, deploying to a Kubernetes cluster</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="7a3a9-117">[Anterior](modernize-your-apps-with-monitoring-and-telemetry.md)
>[Siguiente](migrate-to-hybrid-cloud-scenarios.md)</span><span class="sxs-lookup"><span data-stu-id="7a3a9-117">[Previous](modernize-your-apps-with-monitoring-and-telemetry.md)
[Next](migrate-to-hybrid-cloud-scenarios.md)</span></span>
