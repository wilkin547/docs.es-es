---
title: Modernización del ciclo de vida de la aplicación con canalizaciones de CI/CD y herramientas de DevOps en la nube
description: Modernización de las aplicaciones .NET existentes con Azure Clour y contenedores Windows | Modernización del ciclo de vida de la aplicación con canalizaciones de CI/CD y herramientas de DevOps en la nube
ms.date: 12/21/2018
ms.openlocfilehash: e7ad76edb659fbacfc85cb398ec0c9fe9e3c66c9
ms.sourcegitcommit: 5d9cee27d9ffe8f5670e5f663434511e81b8ac38
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2021
ms.locfileid: "98025256"
---
# <a name="modernize-your-apps-lifecycle-with-cicd-pipelines-and-devops-tools-in-the-cloud"></a><span data-ttu-id="2098c-103">Modernización del ciclo de vida de la aplicación con canalizaciones de CI/CD y herramientas de DevOps en la nube</span><span class="sxs-lookup"><span data-stu-id="2098c-103">Modernize your app's lifecycle with CI/CD pipelines and DevOps tools in the cloud</span></span>

<span data-ttu-id="2098c-104">Las empresas actuales deben innovar a un ritmo rápido para ser competitivas en el mercado.</span><span class="sxs-lookup"><span data-stu-id="2098c-104">Today's businesses need to innovate at a rapid pace to be competitive in the marketplace.</span></span> <span data-ttu-id="2098c-105">La entrega de aplicaciones modernas de alta calidad requiere herramientas y procesos de DevOps que son fundamentales para implementar este ciclo constante de innovación.</span><span class="sxs-lookup"><span data-stu-id="2098c-105">Delivering high-quality, modern applications requires DevOps tools and processes that are critical to implement this constant cycle of innovation.</span></span> <span data-ttu-id="2098c-106">Con las herramientas de DevOps adecuadas, los desarrolladores pueden simplificar la implementación continua y poner aplicaciones innovadoras en manos de los usuarios con más rapidez.</span><span class="sxs-lookup"><span data-stu-id="2098c-106">With the right DevOps tools, developers can streamline continuous deployment and get innovative applications into the hands of users more quickly.</span></span>

<span data-ttu-id="2098c-107">Aunque las prácticas de integración e implementación continuas están bien establecidas, la introducción de contenedores presenta nuevas consideraciones, sobre todo cuando se trabaja con aplicaciones en varios contenedores.</span><span class="sxs-lookup"><span data-stu-id="2098c-107">Although continuous integration and deployment practices are well established, the introduction of containers introduces new considerations, particularly when you are working with multi-container applications.</span></span>

<span data-ttu-id="2098c-108">Azure DevOps Services admite la integración y la implementación continuas de aplicaciones en varios contenedores en diversos entornos mediante las tareas de implementación oficiales de Azure DevOps Services:</span><span class="sxs-lookup"><span data-stu-id="2098c-108">Azure DevOps Services supports continuous integration and deployment of multi-container applications to various environments through the official Azure DevOps Services deployment tasks:</span></span>

- [<span data-ttu-id="2098c-109">Implementación en una aplicación de Azure Web App for Containers</span><span class="sxs-lookup"><span data-stu-id="2098c-109">Deploy to an Azure Web App for Containers</span></span>](/azure/devops/pipelines/apps/cd/deploy-docker-webapp?tabs=dotnet-core)

- [<span data-ttu-id="2098c-110">Implementación en Azure Kubernetes Service</span><span class="sxs-lookup"><span data-stu-id="2098c-110">Deploy to Azure Kubernetes Service</span></span>](/azure/devops/pipelines/apps/cd/deploy-aks?tabs=dotnet-core)

<span data-ttu-id="2098c-111">Pero también puede implementar en [Docker Swarm](https://blog.jcorioland.io/archives/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services.html) o DC/OS mediante tareas de Azure DevOps Services basadas en scripts.</span><span class="sxs-lookup"><span data-stu-id="2098c-111">But you can also deploy to [Docker Swarm](https://blog.jcorioland.io/archives/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services.html) or DC/OS by using Azure DevOps Services script-based tasks.</span></span>

<span data-ttu-id="2098c-112">Para facilitar aún más la agilidad de la implementación, estas herramientas proporcionan excelentes experiencias de implementación en la secuencia desarrollo-pruebas-producción para cargas de trabajo de contenedor, con diversas soluciones de desarrollo y CI/CD.</span><span class="sxs-lookup"><span data-stu-id="2098c-112">To continue facilitating deployment agility, these tools provide excellent dev-to-test-to-production deployment experiences for container workloads, with a choice of development and CI/CD solutions.</span></span>

<span data-ttu-id="2098c-113">En la figura 4-12 se muestra una canalización de implementación continua que se implementa en un clúster de Kubernetes en Azure Container Service.</span><span class="sxs-lookup"><span data-stu-id="2098c-113">Figure 4-12 shows a continuous deployment pipeline that deploys to a Kubernetes cluster in Azure Container Service.</span></span>

![Captura de pantalla de una implementación de Azure DevOps Services en un clúster de Kubernetes.](./media/life-cycle-ci-cd-pipelines-devops-tools/deploy-mvc-app-container-kubernetes.png)

<span data-ttu-id="2098c-115">**Figura 4-12.**</span><span class="sxs-lookup"><span data-stu-id="2098c-115">**Figure 4-12.**</span></span> <span data-ttu-id="2098c-116">Canalización de implementación continua de Azure DevOps Services, implementación en un clúster de Kubernetes</span><span class="sxs-lookup"><span data-stu-id="2098c-116">Azure DevOps Services continuous deployment pipeline, deploying to a Kubernetes cluster</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="2098c-117">[Anterior](modernize-your-apps-with-monitoring-and-telemetry.md)
>[Siguiente](migrate-to-hybrid-cloud-scenarios.md)</span><span class="sxs-lookup"><span data-stu-id="2098c-117">[Previous](modernize-your-apps-with-monitoring-and-telemetry.md)
[Next](migrate-to-hybrid-cloud-scenarios.md)</span></span>
