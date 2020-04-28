---
title: Otras opciones de implementación de contenedores
description: Otras opciones de implementación de contenedores con Azure
ms.date: 04/13/2020
ms.openlocfilehash: 3cae771b3877215a7fc91afd4f406fdfc9ff2771
ms.sourcegitcommit: 5988e9a29cedb8757320817deda3c08c6f44a6aa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2020
ms.locfileid: "82200007"
---
# <a name="other-container-deployment-options"></a>Otras opciones de implementación de contenedores

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Aparte de Azure Kubernetes Service (AKS), también puede implementar contenedores en Azure App Service para contenedores y Azure Container Instances.

## <a name="when-does-it-make-sense-to-deploy-to-app-service-for-containers"></a>¿Cuándo tiene sentido implementar en App Service para contenedores?

Las aplicaciones de producción sencillas que no requieren orquestación son adecuadas para Azure App Service para contenedores.

## <a name="how-to-deploy-to-app-service-for-containers"></a>Cómo implementar en App Service para contenedores

Para implementar en [Azure App Service para contenedores](https://azure.microsoft.com/services/app-service/containers/), necesitará una instancia de Azure Container Registry (ACR) y las credenciales para acceder a ella. Inserte la imagen de contenedor en el repositorio de ACR para que se pueda extraer en el Azure App Service. Una vez que haya finalizado, puede configurar la aplicación para la implementación continua. Si lo hace, se implementarán automáticamente las actualizaciones cada vez que la imagen cambie en ACR.

## <a name="when-does-it-make-sense-to-deploy-to-azure-container-instances"></a>¿Cuándo tiene sentido implementar en Azure Container Instances?

[Azure Container Instances (ACI)](https://azure.microsoft.com/services/container-instances/) permite ejecutar contenedores de Docker en un entorno en la nube administrado y sin servidor, sin tener que configurar máquinas virtuales o clústeres. Es una solución excelente para cargas de trabajo de ejecución breve que se pueden ejecutar en un contenedor aislado. Considere ACI para servicios simples, escenarios de prueba, automatización de tareas y trabajos de compilación. ACI gira una instancia de contenedor, realiza la tarea y, a continuación, la pone en marcha.

## <a name="how-to-deploy-an-app-to-azure-container-instances"></a>Cómo implementar una aplicación en Azure Container Instances

Para implementar en [Azure Container Instances (ACI)](https://docs.microsoft.com/azure/container-instances/), necesita una Azure Container Registry (ACR) y credenciales para tener acceso a ella. Una vez que inserte la imagen de contenedor en el repositorio, estará disponible para la extracción en ACI. Puede trabajar con ACI mediante el Azure Portal o la interfaz de la línea de comandos. ACR proporciona una estrecha integración con ACI. En la figura 3-14 se muestra cómo introducir una imagen de contenedor individual en ACR.

![Azure Container Registry ejecutar instancia](./media/acr-runinstance-contextmenu.png)

**Figura 3-14**. Azure Container Registry ejecutar instancia

La creación de una instancia en ACI puede realizarse rápidamente. Especifique el registro de la imagen, la información del grupo de recursos de Azure, la cantidad de memoria que se va a asignar y el puerto en el que se va a realizar la escucha. En esta guía de [Inicio rápido se muestra cómo implementar una instancia de contenedor en ACI mediante el Azure portal](https://docs.microsoft.com/azure/container-instances/container-instances-quickstart-portal).

Una vez finalizada la implementación, busque la dirección IP del contenedor recién implementado y comuníquese con ella a través del puerto especificado.

Azure Container Instances ofrece la manera más rápida de ejecutar cargas de trabajo de contenedor simples en Azure. No es necesario configurar un servicio de aplicaciones, orquestador o máquina virtual. En escenarios donde se requiere orquestación de contenedores completa, detección de servicios, escalado automático o actualizaciones coordinadas, se recomienda Azure Kubernetes Service (AKS).

## <a name="references"></a>Referencias

- [¿Qué es Kubernetes?](https://blog.newrelic.com/engineering/what-is-kubernetes/)
- [Instalación de Kubernetes con Minikube](https://kubernetes.io/docs/setup/learning-environment/minikube/)
- [MiniKube frente a Docker Desktop](https://medium.com/containers-101/local-kubernetes-for-windows-minikube-vs-docker-desktop-25a1c6d3b766)
- [Visual Studio Tools para Docker](https://docs.microsoft.com/dotnet/standard/containerized-lifecycle-architecture/design-develop-containerized-apps/visual-studio-tools-for-docker)
- [Descripción del inicio en frío sin servidor](https://azure.microsoft.com/blog/understanding-serverless-cold-start/)
- [Instancias de Azure Functions precalentadas](https://docs.microsoft.com/azure/azure-functions/functions-premium-plan#pre-warmed-instances)
- [Creación de una función en Linux con una imagen personalizada](https://docs.microsoft.com/azure/azure-functions/functions-create-function-linux-custom-image)
- [Ejecución de Azure Functions en un contenedor de Docker](https://markheath.net/post/azure-functions-docker)
- [Creación de una función en Linux con una imagen personalizada](https://docs.microsoft.com/azure/azure-functions/functions-create-function-linux-custom-image)
- [Azure Functions con el escalado automático basado en eventos de Kubernetes](https://docs.microsoft.com/azure/azure-functions/functions-kubernetes-keda)
- [Versión Canarias](https://martinfowler.com/bliki/CanaryRelease.html)
- [Azure Dev Spaces con VS Code](https://docs.microsoft.com/azure/dev-spaces/quickstart-netcore)
- [Azure Dev Spaces con Visual Studio](https://docs.microsoft.com/azure/dev-spaces/quickstart-netcore-visualstudio)
- [Grupos de varios nodos de AKS](https://docs.microsoft.com/azure/aks/use-multiple-node-pools)
- [Escalador automático de clústeres de AKS](https://docs.microsoft.com/azure/aks/cluster-autoscaler)
- [Tutorial: escalado de aplicaciones en AKS](https://docs.microsoft.com/azure/aks/tutorial-kubernetes-scale)
- [Escalado y hospedaje de Azure Functions](https://docs.microsoft.com/azure/azure-functions/functions-scale)
- [Azure Container Instances docs](https://docs.microsoft.com/azure/container-instances/)
- [Implementación de la instancia de contenedor desde ACR](https://docs.microsoft.com/azure/container-instances/container-instances-using-azure-container-registry#deploy-with-azure-portal)

>[!div class="step-by-step"]
>[Anterior](scale-containers-serverless.md)
>[Siguiente](communication-patterns.md)
