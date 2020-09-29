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
# <a name="deploy-to-azure-kubernetes-service-aks"></a>Implementación en Azure Kubernetes Service (AKS)

Puede interactuar con AKS mediante el sistema operativo cliente que prefiera (Windows, macOS o Linux) con la interfaz de la línea de comandos de Azure (CLI de Azure) instalada. Para obtener más detalles, vea la [documentación de la CLI de Azure](/cli/azure/?view=azure-cli-latest) y la [guía de instalación](/cli/azure/install-azure-cli?view=azure-cli-latest) de los entornos disponibles.

## <a name="create-the-aks-environment-in-azure"></a>Creación del entorno de AKS en Azure

Existen varias formas de crear el entorno de AKS. Puede hacerlo mediante comandos de la CLI de Azure o por medio de Azure Portal.

Aquí puede ver algunos ejemplos de uso de la CLI de Azure para crear el clúster y de Azure Portal para revisar los resultados. También deberá tener Kubectl y Docker en el equipo de desarrollo.

## <a name="create-the-aks-cluster"></a>Creación del clúster de AKS

Cree el clúster de AKS con este comando (el grupo de recursos debe existir):

```console
az aks create --resource-group explore-docker-aks-rg --name explore-docker-aks --node-vm-size Standard_B2s --node-count 1 --generate-ssh-keys --location westeurope
```

> [!NOTE]
> Los valores de los parámetros `--node-vm-size` y `--node-count` son lo bastante buenos para una aplicación de ejemplo o desarrollo.

Una vez finalizado el trabajo de creación, puede ver:

- El clúster de AKS creado en el grupo de recursos inicial
- Un nuevo grupo de recursos relacionado que contiene los recursos relacionados con el clúster de AKS, como se muestra en las siguientes imágenes.

El grupo de recursos inicial, con el clúster de AKS:

![Vista del explorador de un grupo de recursos de AKS.](media/deploy-azure-kubernetes-service/aks-cluster-view.png)

**Figura 4-17**. Vista de grupo de recursos de AKS en Azure.

El grupo de recursos del clúster de AKS:

![Vista del explorador del grupo de recursos de Azure AKS.](media/deploy-azure-kubernetes-service/aks-resource-group-view.png)

**Figura 4-18**. Vista de AKS en Azure.

> [!IMPORTANT]
> En general, no debería tener que modificar los recursos del grupo de recursos del clúster de AKS. Por ejemplo, el grupo de recursos se elimina al eliminar el clúster de AKS.

También puede ver el nodo creado mediante `Azure CLI` y `Kubectl`.

En primer lugar, obtenga las credenciales:

```console
az aks get-credentials --resource-group explore-docker-aks-rg --name explore-docker-aks
```

![Salida de la consola del comando anterior: "explore-docker-aks" combinado como contexto actual de /home/miguel/.kube/config.](media/deploy-azure-kubernetes-service/get-credentials-command-result.png)

**Figura 4-19**. Resultado del comando `aks get-credentials`.

Después, obtenga los nodos de Kubectl:

```console
kubectl get nodes
```

![Salida de la consola del comando anterior: Lista de nodos con estado, antigüedad (tiempo de ejecución) y versión](media/deploy-azure-kubernetes-service/kubectl-get-nodes-command-result.png)

**Figura 4-20**. Resultado del comando `kubectl get nodes`.

> [!div class="step-by-step"]
> [Anterior](orchestrate-high-scalability-availability.md)
> [Siguiente](docker-apps-development-environment.md)
