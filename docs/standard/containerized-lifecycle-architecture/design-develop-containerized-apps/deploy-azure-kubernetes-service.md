---
title: Orquestación de microservicios y aplicaciones de varios contenedores para una alta escalabilidad y disponibilidad
description: Obtenga información sobre cómo implementar una aplicación con Azure Kubernetes Service.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/23/2018
ms.openlocfilehash: 984a72c9ca8883b338d10fdaa826a6007580372d
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/13/2019
ms.locfileid: "56221523"
---
# <a name="deploy-to-azure-kubernetes-service-aks"></a><span data-ttu-id="4360d-103">Implementar en Azure Kubernetes Service (AKS)</span><span class="sxs-lookup"><span data-stu-id="4360d-103">Deploy to Azure Kubernetes Service (AKS)</span></span>

<span data-ttu-id="4360d-104">Puede interactuar con AKS mediante el sistema operativo de cliente preferida, aquí se muestra cómo hacerlo con Microsoft Windows y una versión incrustada de Ubuntu Linux en Windows, mediante comandos de Bash.</span><span class="sxs-lookup"><span data-stu-id="4360d-104">You can interact with AKS using your preferred client operating system, here we show how to do it with Microsoft Windows and an embedded version of Ubuntu Linux in Windows, using Bash commands.</span></span>

<span data-ttu-id="4360d-105">Requisitos previos para tener antes de usar AKS son:</span><span class="sxs-lookup"><span data-stu-id="4360d-105">Prerequisites to have before using AKS are:</span></span>

- <span data-ttu-id="4360d-106">Equipo de desarrollo de Linux o Mac</span><span class="sxs-lookup"><span data-stu-id="4360d-106">Linux or Mac development machine</span></span>
- <span data-ttu-id="4360d-107">Equipo de desarrollo de Windows</span><span class="sxs-lookup"><span data-stu-id="4360d-107">Windows development machine</span></span>
  - <span data-ttu-id="4360d-108">Modo de programador habilitado en Windows</span><span class="sxs-lookup"><span data-stu-id="4360d-108">Developer Mode enabled on Windows</span></span>
  - <span data-ttu-id="4360d-109">Subsistema de Windows para Linux</span><span class="sxs-lookup"><span data-stu-id="4360d-109">Windows Subsystem for Linux</span></span>
- <span data-ttu-id="4360d-110">CLI de Azure instalada en [Windows, Mac o Linux](https://docs.microsoft.com/cli/azure/install-azure-cli?view=azure-cli-latest)</span><span class="sxs-lookup"><span data-stu-id="4360d-110">Azure-CLI installed on [Windows, Mac or Linux](https://docs.microsoft.com/cli/azure/install-azure-cli?view=azure-cli-latest)</span></span>

> [!NOTE]
> <span data-ttu-id="4360d-111">Para obtener información completa sobre:</span><span class="sxs-lookup"><span data-stu-id="4360d-111">To find complete information about:</span></span>
>
> <span data-ttu-id="4360d-112">CLI de Azure: [https://docs.microsoft.com/cli/azure/index?view=azure-cli-latest](https://docs.microsoft.com/cli/azure/index?view=azure-cli-latest)</span><span class="sxs-lookup"><span data-stu-id="4360d-112">Azure-CLI: [https://docs.microsoft.com/cli/azure/index?view=azure-cli-latest](https://docs.microsoft.com/cli/azure/index?view=azure-cli-latest)</span></span>
>
> <span data-ttu-id="4360d-113">Subsistema de Windows para Linux: [https://docs.microsoft.com/windows/wsl/about](https://docs.microsoft.com/windows/wsl/about)</span><span class="sxs-lookup"><span data-stu-id="4360d-113">Windows Subsystem for Linux: [https://docs.microsoft.com/windows/wsl/about](https://docs.microsoft.com/windows/wsl/about)</span></span>

## <a name="create-the-aks-environment-in-azure"></a><span data-ttu-id="4360d-114">Crear el entorno de AKS en Azure</span><span class="sxs-lookup"><span data-stu-id="4360d-114">Create the AKS environment in Azure</span></span>

<span data-ttu-id="4360d-115">Hay varias maneras de crear el entorno de AKS.</span><span class="sxs-lookup"><span data-stu-id="4360d-115">There are several ways to create the AKS Environment.</span></span> <span data-ttu-id="4360d-116">Puede realizarse mediante comandos de CLI de Azure o mediante el portal de Azure.</span><span class="sxs-lookup"><span data-stu-id="4360d-116">It can be done by using Azure-CLI commands or by using the Azure portal.</span></span>

<span data-ttu-id="4360d-117">Aquí, puede explorar algunos ejemplos de uso de la CLI de Azure para crear el clúster y el portal de Azure para revisar los resultados.</span><span class="sxs-lookup"><span data-stu-id="4360d-117">Here you can explore some examples using the Azure-CLI to create the cluster and the Azure portal to review the results.</span></span> <span data-ttu-id="4360d-118">También deberá tener Kubectl y Docker en el equipo de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="4360d-118">You also need to have Kubectl and Docker in your development machine.</span></span>  

## <a name="create-the-aks-cluster"></a><span data-ttu-id="4360d-119">Crear el clúster de AKS</span><span class="sxs-lookup"><span data-stu-id="4360d-119">Create the AKS cluster</span></span>

<span data-ttu-id="4360d-120">Crear el clúster AKS con este comando:</span><span class="sxs-lookup"><span data-stu-id="4360d-120">Create the AKS cluster using this command:</span></span>

```console
az aks create --resource-group MSSampleResourceGroup --name MSSampleClusterK801 --agent-count 1 --generate-ssh-keys --location westus2
```

<span data-ttu-id="4360d-121">Cuando finalice el trabajo de creación, puede ver el AKS creado en el portal de Azure:</span><span class="sxs-lookup"><span data-stu-id="4360d-121">After the creation job finishes, you can see the AKS created in the Azure portal:</span></span>

<span data-ttu-id="4360d-122">El grupo de recursos:</span><span class="sxs-lookup"><span data-stu-id="4360d-122">The resource group:</span></span>

![Vista de explorador del grupo de recursos de AKS de Azure.](media/aks-resource-group-view.png)

<span data-ttu-id="4360d-124">**Figura 4-17**.</span><span class="sxs-lookup"><span data-stu-id="4360d-124">**Figure 4-17**.</span></span> <span data-ttu-id="4360d-125">Vista de grupo de recursos de AKS desde Azure.</span><span class="sxs-lookup"><span data-stu-id="4360d-125">AKS Resource Group view from Azure.</span></span>

<span data-ttu-id="4360d-126">El clúster de AKS:</span><span class="sxs-lookup"><span data-stu-id="4360d-126">The AKS cluster:</span></span>

![Vista del explorador de un grupo de recursos AKS.](media/aks-cluster-view.png)

<span data-ttu-id="4360d-128">**Figura 4-18**.</span><span class="sxs-lookup"><span data-stu-id="4360d-128">**Figure 4-18**.</span></span> <span data-ttu-id="4360d-129">Vista AKS desde Azure.</span><span class="sxs-lookup"><span data-stu-id="4360d-129">AKS view from Azure.</span></span>

<span data-ttu-id="4360d-130">También puede ver el nodo creado mediante `Azure-CLI` y `Kubectl`.</span><span class="sxs-lookup"><span data-stu-id="4360d-130">You can also view the node created using `Azure-CLI` and `Kubectl`.</span></span>

<span data-ttu-id="4360d-131">En primer lugar, al obtener las credenciales:</span><span class="sxs-lookup"><span data-stu-id="4360d-131">First, getting the credentials:</span></span>

```console
az aks get-credentials --resource-group MSSampleK8ClusterRG --name MSSampleK8Cluster
```

![Salida del comando anterior en la consola: Combinado "MsSampleK8Cluster como el contexto actual en /root/.kube/config.](media/get-credentials-command-result.png)

<span data-ttu-id="4360d-133">**Figura 4-19**.</span><span class="sxs-lookup"><span data-stu-id="4360d-133">**Figure 4-19**.</span></span> <span data-ttu-id="4360d-134">`aks get-credentials` resultado del comando.</span><span class="sxs-lookup"><span data-stu-id="4360d-134">`aks get-credentials` command result.</span></span>

<span data-ttu-id="4360d-135">Y, a continuación, obtener los nodos de Kubectl:</span><span class="sxs-lookup"><span data-stu-id="4360d-135">And then, getting nodes from Kubectl:</span></span>

```console
kubectl get nodes
```

![Salida antes del comando en la consola: Lista de nodos con estado, la antigüedad (tiempo de ejecución) y versión](media/kubectl-get-nodes-command-result.png)

<span data-ttu-id="4360d-137">**Figura 4-20**.</span><span class="sxs-lookup"><span data-stu-id="4360d-137">**Figure 4-20**.</span></span> <span data-ttu-id="4360d-138">`kubectl get nodes` resultado del comando.</span><span class="sxs-lookup"><span data-stu-id="4360d-138">`kubectl get nodes` command result.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="4360d-139">[Anterior](orchestrate-high-scalability-availability.md)
>[Siguiente](docker-apps-development-environment.md)</span><span class="sxs-lookup"><span data-stu-id="4360d-139">[Previous](orchestrate-high-scalability-availability.md)
[Next](docker-apps-development-environment.md)</span></span>
