---
title: Orquestación de microservicios y aplicaciones de varios contenedores para una alta escalabilidad y disponibilidad
description: Obtenga información sobre cómo implementar una aplicación con Azure Kubernetes Service.
ms.date: 02/15/2019
ms.openlocfilehash: 0aa2f83fbf8f9a8815d65730002943cca748643d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "71182371"
---
# <a name="deploy-to-azure-kubernetes-service-aks"></a>Implementación en Azure Kubernetes Service (AKS)

Puede interactuar con AKS con su sistema operativo cliente preferido. Aquí le mostraremos cómo hacerlo con Microsoft Windows y una versión insertada de Ubuntu Linux en Windows, mediante el uso de comandos de Bash.

Estos son los requisitos previos para el uso de AKS:

- Máquina de desarrollo Linux o Mac
- Máquina de desarrollo Windows
  - Modo de desarrollador habilitado en Windows
  - Subsistema de Windows para Linux
- CLI de Azure instalada en [Windows, Mac o Linux](https://docs.microsoft.com/cli/azure/install-azure-cli)

> [!NOTE]
> Aquí encontrará información completa sobre los siguientes temas:
>
> CLI de Azure: <https://docs.microsoft.com/cli/azure/index>
>
> Subsistema Windows para Linux: <https://docs.microsoft.com/windows/wsl/about>

## <a name="create-the-aks-environment-in-azure"></a>Creación del entorno de AKS en Azure

Existen varias formas de crear el entorno de AKS. Puede hacerlo mediante comandos de la CLI de Azure o a través de Azure Portal.

Aquí puede explorar algunos ejemplos sobre el uso de la CLI de Azure para crear el clúster y de Azure Portal para revisar los resultados. También deberá tener Kubectl y Docker en el equipo de desarrollo.  

## <a name="create-the-aks-cluster"></a>Creación del clúster de AKS

Cree el clúster de AKS con este comando:

```console
az aks create --resource-group MSSampleResourceGroup --name MSSampleClusterK801 --agent-count 1 --generate-ssh-keys --location westus2
```

Cuando finalice el trabajo de creación, puede verlo creado en Azure Portal:

Grupo de recursos:

![Vista del explorador del grupo de recursos de Azure AKS.](media/aks-resource-group-view.png)

**Figura 4-17**. Vista de grupo de recursos de AKS en Azure.

Clúster de AKS:

![Vista del explorador de un grupo de recursos de AKS.](media/aks-cluster-view.png)

**Figura 4-18**. Vista de AKS en Azure.

También puede ver el nodo creado mediante `Azure-CLI` y `Kubectl`.

En primer lugar, obtenga las credenciales:

```console
az aks get-credentials --resource-group MSSampleK8ClusterRG --name MSSampleK8Cluster
```

![Salida de la consola del comando anterior: Merged "MSSampleK8Cluster" as current context in /root/.kube/config](media/get-credentials-command-result.png)

**Figura 4-19**. Resultado del comando `aks get-credentials`.

Después, obtenga los nodos de Kubectl:

```console
kubectl get nodes
```

![Salida de la consola del comando anterior: Lista de nodos con estado, antigüedad (tiempo de ejecución) y versión](media/kubectl-get-nodes-command-result.png)

**Figura 4-20**. Resultado del comando `kubectl get nodes`.

>[!div class="step-by-step"]
>[Anterior](orchestrate-high-scalability-availability.md)
>[Siguiente](docker-apps-development-environment.md)
