---
title: Escalado de contenedores y aplicaciones sin servidor
description: Escalado de aplicaciones nativas en la nube con Azure Kubernetes Service para satisfacer la demanda de los usuarios.
ms.date: 05/13/2020
ms.openlocfilehash: a5e1e8df785fd08901d9be41c0a06db35e09296b
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83613725"
---
# <a name="scaling-containers-and-serverless-applications"></a>Escalado de contenedores y aplicaciones sin servidor

Hay dos formas de escalar una aplicación: hacia arriba o hacia fuera. El primero hace referencia a agregar capacidad a un solo recurso, mientras que el último hace referencia a la adición de más recursos para aumentar la capacidad.

## <a name="the-simple-solution-scaling-up"></a>Solución simple: escalado vertical

La actualización de un servidor host existente con mayor CPU, memoria, velocidad de e/s de disco y velocidad de e/s de red se conoce como *escalado*vertical. El escalado vertical de una aplicación nativa en la nube implica la elección de más recursos para el proveedor en la nube. Por ejemplo, puede tener un nuevo grupo de nodos con máquinas virtuales de mayor tamaño en el clúster de Kubernetes. A continuación, migre los servicios en contenedores al nuevo grupo.

Las aplicaciones sin servidor se escalan verticalmente eligiendo el [plan de funciones Premium](https://docs.microsoft.com/azure/azure-functions/functions-scale) o los tamaños de instancia Premium de un plan de App Service dedicado.

## <a name="scaling-out-cloud-native-apps"></a>Escalado horizontal de aplicaciones nativas en la nube

A menudo, las aplicaciones nativas en la nube experimentan grandes fluctuaciones en la demanda y requieren una escala en el aviso de un momento. Favorecen el escalado horizontal. El escalado horizontal se realiza horizontalmente agregando equipos adicionales (denominados nodos) o instancias de aplicación a un clúster existente. En Kubernetes, se puede escalar manualmente ajustando los valores de configuración de la aplicación (por ejemplo, [escalando un grupo de nodos](https://docs.microsoft.com/azure/aks/use-multiple-node-pools#scale-a-node-pool-manually)) o mediante el escalado automático.

Los clústeres de AKS se pueden escalar automáticamente de una de estas dos maneras:

En primer lugar, el [escalador automático del Pod horizontal](https://docs.microsoft.com/azure/aks/tutorial-kubernetes-scale#autoscale-pods) supervisa la demanda de recursos y escala automáticamente las réplicas de POD para que se cumplan. Cuando aumenta el tráfico, se aprovisionan réplicas adicionales automáticamente para escalar horizontalmente los servicios. Del mismo modo, cuando la demanda disminuye, se quitan del escalado en los servicios. Defina la métrica en la que se va a escalar, por ejemplo, el uso de la CPU. También puede especificar el número mínimo y máximo de réplicas que se van a ejecutar. AKS supervisa esa métrica y escala en consecuencia.

A continuación, la característica de [escalado automático del clúster de AKS](https://docs.microsoft.com/azure/aks/cluster-autoscaler) le permite escalar automáticamente los nodos de proceso en un clúster de Kubernetes para satisfacer la demanda. Con él, puede Agregar automáticamente nuevas máquinas virtuales al conjunto de escalado de máquinas virtuales de Azure subyacente siempre que se necesite más capacidad de proceso de. También quita los nodos cuando ya no son necesarios.

En la figura 3-13 se muestra la relación entre estos dos servicios de escalado.

![Escalado horizontal de un plan de App Service.](./media/aks-cluster-autoscaler.png)

**Figura 3-13**. Escalado horizontal de un plan de App Service.

En conjunto, ambos garantizan un número óptimo de instancias de contenedor y nodos de proceso para admitir la demanda fluctuante. El escalador automático del Pod horizontal optimiza el número de pods requeridos. El escalador automático del clúster optimiza el número de nodos necesarios.

### <a name="scaling-azure-functions"></a>Escalado de Azure Functions

Azure Functions escalar horizontalmente de forma automática a petición. Los recursos del servidor se asignan y se quitan dinámicamente según el número de eventos desencadenados. Solo se cobran los recursos de proceso consumidos cuando se ejecutan las funciones. La facturación se basa en el número de ejecuciones, el tiempo de ejecución y la memoria usada.

Aunque el plan de consumo predeterminado proporciona una solución económica y escalable para la mayoría de las aplicaciones, la opción Premium permite a los desarrolladores disponer de flexibilidad para los requisitos de Azure Functions personalizados. La actualización al plan Premium proporciona control sobre los tamaños de instancia, instancias previamente preparadas (para evitar retrasos de inicio en frío) y máquinas virtuales dedicadas.

>[!div class="step-by-step"]
>[Anterior](deploy-containers-azure.md)
>[Siguiente](other-deployment-options.md)
