---
title: Supervisión en Azure Kubernetes Service
description: Supervisión en Azure Kubernetes Service
ms.date: 09/23/2019
ms.openlocfilehash: fc9d84fd738ff1c40d25860680e14313c9323517
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711654"
---
# <a name="monitoring-in-azure-kubernetes-services"></a>Supervisión en Azure Kubernetes Service

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

El registro integrado en Kubernetes es primitivo. Sin embargo, hay algunas opciones excelentes para obtener los registros de Kubernetes y en un lugar donde se pueden analizar correctamente. Si necesita supervisar los clústeres de AKS, la configuración de la pila elástica para Kubernetes es una solución excelente.

## <a name="elastic-stack"></a>Pila elástica

La pila elástica es una opción eficaz para recopilar información de un clúster de Kubernetes. Kubernetes admite el envío de registros a un punto de conexión de Elasticsearch y, en su [mayor parte](https://kubernetes.io/docs/tasks/debug-application-cluster/logging-elasticsearch-kibana/), todo lo que necesita para empezar es establecer las variables de entorno como se muestra en la figura 7-5:

```kubernetes
KUBE_LOGGING_DESTINATION=elasticsearch
KUBE_ENABLE_NODE_LOGGING=true
```

**Figura 7-5** : variables de configuración para Kubernetes

Con esto se instalará Elasticsearch en el clúster y se le enviarán todos los registros de clúster.

![un ejemplo de un panel de Kibana que muestra los resultados de una consulta en los registros ingeridos de Kubernetes](./media/kibana-dashboard.png)
**figura 7-6**. Un ejemplo de un panel de Kibana que muestra los resultados de una consulta en los registros que se introducen en Kubernetes

## <a name="azure-container-monitoring"></a>Supervisión de contenedores de Azure

La supervisión de contenedores de Azure admite el consumo de registros no solo de Kubernetes, sino también de otros motores de orquestación como DC/OS, Docker Swarm y Red Hat OpenShift.

![consumo de registros de varios contenedores](./media/containers-diagram.png)
la **figura 7-7**.  Consumo de registros de varios contenedores

La información de registro y métrica se recopila no solo de los contenedores que se ejecutan en el clúster, sino también de los propios hosts del clúster. Permite correlacionar la información de registro de las dos, lo que hace que sea mucho más fácil realizar un seguimiento de un error.

La instalación de los recopiladores de registros es diferente en los clústeres de [Windows](https://docs.microsoft.com/azure/azure-monitor/insights/containers#configure-a-log-analytics-windows-agent-for-kubernetes) y [Linux](https://docs.microsoft.com/azure/azure-monitor/insights/containers#configure-a-log-analytics-linux-agent-for-kubernetes) . Sin embargo, en ambos casos, la colección de registros se implementa como un [DaemonSet](https://kubernetes.io/docs/concepts/workloads/controllers/daemonset/)Kubernetes, lo que significa que el recopilador de registros se ejecuta como un contenedor en cada uno de los nodos.

Independientemente del orquestador o del sistema operativo que ejecute el demonio de Azure Monitor, la información de registro se reenvía a las mismas herramientas de Azure Monitor con las que los usuarios están familiarizados. Esto garantiza una experiencia paralela en entornos que mezclen distintos orígenes de registro, como un entorno híbrido de Kubernetes/Azure Functions.

![un panel de ejemplo que muestra información de registro y métrica de varios contenedores en ejecución.](./media/containers-dashboard.png)
**figura 7-8**. Un panel de ejemplo que muestra información de registro y métrica de varios contenedores en ejecución.

## <a name="logfinalize"></a>Log. Finalize ()

El registro es una de las partes más informadas y, a la mayor parte de lo importante, de la implementación de cualquier aplicación a escala. A medida que aumentan el tamaño y la complejidad de las aplicaciones, lo que hace es la dificultad de depurarlos. Tener los registros de alta calidad disponibles hace que la depuración sea mucho más fácil y la mueve del dominio "casi imposible" a la "experiencia agradable".

>[!div class="step-by-step"]
>[Anterior](logging-with-elastic-stack.md)
>[Siguiente](azure-monitor.md)
