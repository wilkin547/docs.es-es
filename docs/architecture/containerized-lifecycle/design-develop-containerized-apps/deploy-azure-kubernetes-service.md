---
title: Orquestación de microservicios y aplicaciones de varios contenedores para una alta escalabilidad y disponibilidad
description: Obtenga información sobre cómo implementar una aplicación con Azure Kubernetes Service.
ms.date: 08/06/2020
ms.openlocfilehash: ba9887c0a4837c16a60ebeb006416c0fa8c105e0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91163601"
---
# <a name="deploy-to-azure-kubernetes-service-aks"></a><span data-ttu-id="a848b-103">Implementación en Azure Kubernetes Service (AKS)</span><span class="sxs-lookup"><span data-stu-id="a848b-103">Deploy to Azure Kubernetes Service (AKS)</span></span>

<span data-ttu-id="a848b-104">Puede interactuar con AKS mediante el sistema operativo cliente que prefiera (Windows, macOS o Linux) con la interfaz de la línea de comandos de Azure (CLI de Azure) instalada.</span><span class="sxs-lookup"><span data-stu-id="a848b-104">You can interact with AKS using your preferred client operating system (Windows, macOS, or Linux) with Azure command-line interface(Azure CLI) installed.</span></span> <span data-ttu-id="a848b-105">Para obtener más detalles, vea la [documentación de la CLI de Azure](/cli/azure/?view=azure-cli-latest) y la [guía de instalación](/cli/azure/install-azure-cli?view=azure-cli-latest) de los entornos disponibles.</span><span class="sxs-lookup"><span data-stu-id="a848b-105">For more details, refer [Azure CLI documentation](/cli/azure/?view=azure-cli-latest) and [Installation guide](/cli/azure/install-azure-cli?view=azure-cli-latest) for the available environments.</span></span>

## <a name="create-the-aks-environment-in-azure"></a><span data-ttu-id="a848b-106">Creación del entorno de AKS en Azure</span><span class="sxs-lookup"><span data-stu-id="a848b-106">Create the AKS environment in Azure</span></span>

<span data-ttu-id="a848b-107">Existen varias formas de crear el entorno de AKS.</span><span class="sxs-lookup"><span data-stu-id="a848b-107">There are several ways to create the AKS Environment.</span></span> <span data-ttu-id="a848b-108">Puede hacerlo mediante comandos de la CLI de Azure o por medio de Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="a848b-108">It can be done by using Azure CLI commands or by using the Azure portal.</span></span>

<span data-ttu-id="a848b-109">Aquí puede ver algunos ejemplos de uso de la CLI de Azure para crear el clúster y de Azure Portal para revisar los resultados.</span><span class="sxs-lookup"><span data-stu-id="a848b-109">Here you can explore some examples using the Azure CLI to create the cluster and the Azure portal to review the results.</span></span> <span data-ttu-id="a848b-110">También deberá tener Kubectl y Docker en el equipo de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="a848b-110">You also need to have Kubectl and Docker in your development machine.</span></span>

## <a name="create-the-aks-cluster"></a><span data-ttu-id="a848b-111">Creación del clúster de AKS</span><span class="sxs-lookup"><span data-stu-id="a848b-111">Create the AKS cluster</span></span>

<span data-ttu-id="a848b-112">Cree el clúster de AKS con este comando (el grupo de recursos debe existir):</span><span class="sxs-lookup"><span data-stu-id="a848b-112">Create the AKS cluster using this command (the resource group must exist):</span></span>

```console
az aks create --resource-group explore-docker-aks-rg --name explore-docker-aks --node-vm-size Standard_B2s --node-count 1 --generate-ssh-keys --location westeurope
```

> [!NOTE]
> <span data-ttu-id="a848b-113">Los valores de los parámetros `--node-vm-size` y `--node-count` son lo bastante buenos para una aplicación de ejemplo o desarrollo.</span><span class="sxs-lookup"><span data-stu-id="a848b-113">The `--node-vm-size` and `--node-count` parameter values are good enough for a sample/dev application.</span></span>

<span data-ttu-id="a848b-114">Una vez finalizado el trabajo de creación, puede ver:</span><span class="sxs-lookup"><span data-stu-id="a848b-114">After the creation job finishes, you can see:</span></span>

- <span data-ttu-id="a848b-115">El clúster de AKS creado en el grupo de recursos inicial</span><span class="sxs-lookup"><span data-stu-id="a848b-115">The AKS cluster created in the initial resource group</span></span>
- <span data-ttu-id="a848b-116">Un nuevo grupo de recursos relacionado que contiene los recursos relacionados con el clúster de AKS, como se muestra en las siguientes imágenes.</span><span class="sxs-lookup"><span data-stu-id="a848b-116">A new, related resource group, containing the resources related to the AKS cluster, as show in the following images.</span></span>

<span data-ttu-id="a848b-117">El grupo de recursos inicial, con el clúster de AKS:</span><span class="sxs-lookup"><span data-stu-id="a848b-117">The initial resource group, with the AKS cluster:</span></span>

![Vista del explorador de un grupo de recursos de AKS.](media/deploy-azure-kubernetes-service/aks-cluster-view.png)

<span data-ttu-id="a848b-119">**Figura 4-17**.</span><span class="sxs-lookup"><span data-stu-id="a848b-119">**Figure 4-17**.</span></span> <span data-ttu-id="a848b-120">Vista de grupo de recursos de AKS en Azure.</span><span class="sxs-lookup"><span data-stu-id="a848b-120">AKS Resource Group view from Azure.</span></span>

<span data-ttu-id="a848b-121">El grupo de recursos del clúster de AKS:</span><span class="sxs-lookup"><span data-stu-id="a848b-121">The AKS cluster resource group:</span></span>

![Vista del explorador del grupo de recursos de Azure AKS.](media/deploy-azure-kubernetes-service/aks-resource-group-view.png)

<span data-ttu-id="a848b-123">**Figura 4-18**.</span><span class="sxs-lookup"><span data-stu-id="a848b-123">**Figure 4-18**.</span></span> <span data-ttu-id="a848b-124">Vista de AKS en Azure.</span><span class="sxs-lookup"><span data-stu-id="a848b-124">AKS view from Azure.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a848b-125">En general, no debería tener que modificar los recursos del grupo de recursos del clúster de AKS.</span><span class="sxs-lookup"><span data-stu-id="a848b-125">In general, you shouldn't need to modify the resources in the AKS cluster resource group.</span></span> <span data-ttu-id="a848b-126">Por ejemplo, el grupo de recursos se elimina al eliminar el clúster de AKS.</span><span class="sxs-lookup"><span data-stu-id="a848b-126">For example, the resource group is deleted when you delete the AKS cluster.</span></span>

<span data-ttu-id="a848b-127">También puede ver el nodo creado mediante `Azure CLI` y `Kubectl`.</span><span class="sxs-lookup"><span data-stu-id="a848b-127">You can also view the node created using `Azure CLI` and `Kubectl`.</span></span>

<span data-ttu-id="a848b-128">En primer lugar, obtenga las credenciales:</span><span class="sxs-lookup"><span data-stu-id="a848b-128">First, getting the credentials:</span></span>

```console
az aks get-credentials --resource-group explore-docker-aks-rg --name explore-docker-aks
```

![Salida de la consola del comando anterior: "explore-docker-aks" combinado como contexto actual de /home/miguel/.kube/config.](media/deploy-azure-kubernetes-service/get-credentials-command-result.png)

<span data-ttu-id="a848b-130">**Figura 4-19**.</span><span class="sxs-lookup"><span data-stu-id="a848b-130">**Figure 4-19**.</span></span> <span data-ttu-id="a848b-131">Resultado del comando `aks get-credentials`.</span><span class="sxs-lookup"><span data-stu-id="a848b-131">`aks get-credentials` command result.</span></span>

<span data-ttu-id="a848b-132">Después, obtenga los nodos de Kubectl:</span><span class="sxs-lookup"><span data-stu-id="a848b-132">And then, getting nodes from Kubectl:</span></span>

```console
kubectl get nodes
```

![Salida de la consola del comando anterior: Lista de nodos con estado, antigüedad (tiempo de ejecución) y versión](media/deploy-azure-kubernetes-service/kubectl-get-nodes-command-result.png)

<span data-ttu-id="a848b-134">**Figura 4-20**.</span><span class="sxs-lookup"><span data-stu-id="a848b-134">**Figure 4-20**.</span></span> <span data-ttu-id="a848b-135">Resultado del comando `kubectl get nodes`.</span><span class="sxs-lookup"><span data-stu-id="a848b-135">`kubectl get nodes` command result.</span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="a848b-136">[Anterior](orchestrate-high-scalability-availability.md)
> [Siguiente](docker-apps-development-environment.md)</span><span class="sxs-lookup"><span data-stu-id="a848b-136">[Previous](orchestrate-high-scalability-availability.md)
[Next](docker-apps-development-environment.md)</span></span>
