---
title: Pasos del flujo de trabajo de DevOps de bucle externo para una aplicación de Docker
description: Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft
ms.date: 02/15/2019
ms.openlocfilehash: 9fdc5acfd375e4f2266859f061ef1c854286b914
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65644982"
---
# <a name="creating-cicd-pipelines-in-azure-devops-services-for-a-net-core-20-application-on-containers-and-deploying-to-a-kubernetes-cluster"></a><span data-ttu-id="d3616-103">Creación de canalizaciones de CI/CD en Azure DevOps Services para una aplicación .NET Core 2.0 en contenedores e implementación en un clúster de Kubernetes</span><span class="sxs-lookup"><span data-stu-id="d3616-103">Creating CI/CD pipelines in Azure DevOps Services for a .NET Core 2.0 application on Containers and deploying to a Kubernetes cluster</span></span>

<span data-ttu-id="d3616-104">En la figura 5-12 puede ver el escenario de DevOps-to-end, que abarcan la administración de código, compilación de código, compilación de imágenes de Docker, inserción de imágenes de Docker en un registro de Docker y, finalmente, la implementación en un clúster de Kubernetes en Azure.</span><span class="sxs-lookup"><span data-stu-id="d3616-104">In Figure 5-12 you can see the end-to-end DevOps scenario covering the code management, code compilation, Docker images build, Docker images push to a Docker registry and finally the deployment to a Kubernetes cluster in Azure.</span></span>

![Flujo de trabajo: Se inicia en el equipo de desarrollo.](media/docker-workflow-ci-cd-aks.png)

<span data-ttu-id="d3616-107">**Figura 5-12**.</span><span class="sxs-lookup"><span data-stu-id="d3616-107">**Figure 5-12**.</span></span> <span data-ttu-id="d3616-108">Escenario de CI/CD, crear imágenes de Docker e implementar en un clúster de Kubernetes en Azure</span><span class="sxs-lookup"><span data-stu-id="d3616-108">CI/CD scenario creating Docker images and deploying to a Kubernetes cluster in Azure</span></span>

<span data-ttu-id="d3616-109">Es importante destacar que los dos canalizaciones y compilación, CI/CD de la versión, están conectados a través del registro de Docker (como Docker Hub o Azure Container Registry).</span><span class="sxs-lookup"><span data-stu-id="d3616-109">It is important to highlight that the two pipelines, build/CI, and release/CD, are connected through the Docker Registry (such as Docker Hub or Azure Container Registry).</span></span> <span data-ttu-id="d3616-110">El registro de Docker es una de las principales diferencias en comparación con un proceso de CI/CD tradicionales sin Docker.</span><span class="sxs-lookup"><span data-stu-id="d3616-110">The Docker registry is one of the main differences compared to a traditional CI/CD process without Docker.</span></span>

<span data-ttu-id="d3616-111">Como se muestra en la figura 5-13, la primera fase es la canalización de compilación o CI.</span><span class="sxs-lookup"><span data-stu-id="d3616-111">As shown in Figure 5-13, the first phase is the build/CI pipeline.</span></span> <span data-ttu-id="d3616-112">En los servicios de DevOps de Azure puede crear canalizaciones de compilación, CI que compile el código, crear las imágenes de Docker y transmitirlos a un registro de Docker como Docker Hub o Azure Container Registry.</span><span class="sxs-lookup"><span data-stu-id="d3616-112">In Azure DevOps Services you can create build/CI pipelines that will compile the code, create the Docker images, and push them to a Docker Registry like Docker Hub or Azure Container Registry.</span></span>

![Vista del explorador de Azure DevOps, definición de tarea de proceso de compilación.](media/build-ci-pipeline-azure-devops-push-to-docker-registry.png)

<span data-ttu-id="d3616-114">**Figura 5-13**.</span><span class="sxs-lookup"><span data-stu-id="d3616-114">**Figure 5-13**.</span></span> <span data-ttu-id="d3616-115">Canalización de compilación/integración continua en Azure DevOps compilar imágenes de Docker e inserción de imágenes en un registro de Docker</span><span class="sxs-lookup"><span data-stu-id="d3616-115">Build/CI pipeline in Azure DevOps building Docker images and pushing images to a Docker registry</span></span>

<span data-ttu-id="d3616-116">La segunda fase consiste en crear una canalización de implementación y lanzamiento.</span><span class="sxs-lookup"><span data-stu-id="d3616-116">The second phase is to create a deployment/release pipeline.</span></span> <span data-ttu-id="d3616-117">En los servicios de Azure DevOps, puede crear fácilmente una canalización de implementación destinadas a un clúster de Kubernetes mediante el uso de las tareas de Kubernetes para los servicios de Azure DevOps, como se muestra en la figura 5-14.</span><span class="sxs-lookup"><span data-stu-id="d3616-117">In Azure DevOps Services, you can easily create a deployment pipeline targeting a Kubernetes cluster by using the Kubernetes tasks for Azure DevOps Services, as shown in Figure 5-14.</span></span>

![Vista del explorador de Azure DevOps, implemente en la definición de tarea de Kubernetes.](media/release-cd-pipeline-azure-devops-deploy-to-kubernetes.png)

<span data-ttu-id="d3616-119">**Figura 5-14**.</span><span class="sxs-lookup"><span data-stu-id="d3616-119">**Figure 5-14**.</span></span> <span data-ttu-id="d3616-120">Canalización de versión/CD en la implementación de servicios de Azure DevOps a un clúster de Kubernetes</span><span class="sxs-lookup"><span data-stu-id="d3616-120">Release/CD pipeline in Azure DevOps Services deploying to a Kubernetes cluster</span></span>

> [! Tutorial]<span data-ttu-id="d3616-121"> implementación eShopModernized en Kubernetes:</span><span class="sxs-lookup"><span data-stu-id="d3616-121"> Deploying eShopModernized to Kubernetes:</span></span>
>
> <span data-ttu-id="d3616-122">Para obtener un tutorial detallado de las canalizaciones de Azure DevOps CI/CD de implementación en Kubernetes, consulte esta publicación: \\</span><span class="sxs-lookup"><span data-stu-id="d3616-122">For a detailed walkthrough of Azure DevOps CI/CD pipelines deploying to Kubernetes, see this post: \\</span></span>
><https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)>

>[!div class="step-by-step"]
><span data-ttu-id="d3616-123">[Anterior](docker-application-outer-loop-devops-workflow.md)
>[Siguiente](../run-manage-monitor-docker-environments/index.md)</span><span class="sxs-lookup"><span data-stu-id="d3616-123">[Previous](docker-application-outer-loop-devops-workflow.md)
[Next](../run-manage-monitor-docker-environments/index.md)</span></span>
