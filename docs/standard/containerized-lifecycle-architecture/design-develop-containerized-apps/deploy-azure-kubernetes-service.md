---
title: Orquestación de microservicios y aplicaciones de varios contenedores para una alta escalabilidad y disponibilidad
description: Obtenga información sobre cómo implementar una aplicación con Azure Kubernetes Service.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 82a1cf7f3cc367bfb8b8f67a130600815f2a21c4
ms.sourcegitcommit: 2b986afe4ce9e13bbeec929c9737757eb61de60e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/22/2019
ms.locfileid: "56664970"
---
# <a name="deploy-to-azure-kubernetes-service-aks"></a>Implementar en Azure Kubernetes Service (AKS)

Puede interactuar con AKS mediante el sistema operativo de cliente preferida, aquí se muestra cómo hacerlo con Microsoft Windows y una versión incrustada de Ubuntu Linux en Windows, mediante comandos de Bash.

Requisitos previos para tener antes de usar AKS son:

- Equipo de desarrollo de Linux o Mac
- Equipo de desarrollo de Windows
  - Modo de programador habilitado en Windows
  - Subsistema de Windows para Linux
- CLI de Azure instalada en [Windows, Mac o Linux](https://docs.microsoft.com/cli/azure/install-azure-cli?view=azure-cli-latest)

> [!NOTE]
> Para obtener información completa sobre:
>
> CLI de Azure: <https://docs.microsoft.com/cli/azure/index?view=azure-cli-latest>
>
> Subsistema de Windows para Linux: <https://docs.microsoft.com/windows/wsl/about>

## <a name="create-the-aks-environment-in-azure"></a>Crear el entorno de AKS en Azure

Hay varias maneras de crear el entorno de AKS. Puede realizarse mediante comandos de CLI de Azure o mediante el portal de Azure.

Aquí, puede explorar algunos ejemplos de uso de la CLI de Azure para crear el clúster y el portal de Azure para revisar los resultados. También deberá tener Kubectl y Docker en el equipo de desarrollo.  

## <a name="create-the-aks-cluster"></a>Crear el clúster de AKS

Crear el clúster AKS con este comando:

```console
az aks create --resource-group MSSampleResourceGroup --name MSSampleClusterK801 --agent-count 1 --generate-ssh-keys --location westus2
```

Cuando finalice el trabajo de creación, puede ver el AKS creado en el portal de Azure:

El grupo de recursos:

![Vista de explorador del grupo de recursos de AKS de Azure.](media/aks-resource-group-view.png)

**Figura 4-17**. Vista de grupo de recursos de AKS desde Azure.

El clúster de AKS:

![Vista del explorador de un grupo de recursos AKS.](media/aks-cluster-view.png)

**Figura 4-18**. Vista AKS desde Azure.

También puede ver el nodo creado mediante `Azure-CLI` y `Kubectl`.

En primer lugar, al obtener las credenciales:

```console
az aks get-credentials --resource-group MSSampleK8ClusterRG --name MSSampleK8Cluster
```

![Salida del comando anterior en la consola: Combinado "MsSampleK8Cluster como el contexto actual en /root/.kube/config.](media/get-credentials-command-result.png)

**Figura 4-19**. `aks get-credentials` resultado del comando.

Y, a continuación, obtener los nodos de Kubectl:

```console
kubectl get nodes
```

![Salida antes del comando en la consola: Lista de nodos con estado, la antigüedad (tiempo de ejecución) y versión](media/kubectl-get-nodes-command-result.png)

**Figura 4-20**. `kubectl get nodes` resultado del comando.

>[!div class="step-by-step"]
>[Anterior](orchestrate-high-scalability-availability.md)
>[Siguiente](docker-apps-development-environment.md)
