---
title: Supervisión en Azure Kubernetes Service
description: Supervisión en Azure Kubernetes Service
ms.date: 05/13/2020
ms.openlocfilehash: 3900f169b9be4f807e72392da38a1224d6ce28e3
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91163705"
---
# <a name="monitoring-in-azure-kubernetes-services"></a>Supervisión en Azure Kubernetes Service

El registro integrado en Kubernetes es primitivo. Sin embargo, hay algunas opciones excelentes para obtener los registros de Kubernetes y en un lugar donde se pueden analizar correctamente. Si necesita supervisar los clústeres de AKS, la configuración de la pila elástica para Kubernetes es una solución excelente.

## <a name="azure-monitor-for-containers"></a>Azure Monitor para contenedores

[Azure monitor para contenedores](/azure/azure-monitor/insights/container-insights-overview) admite el consumo de registros no solo de Kubernetes, sino también de otros motores de orquestación como DC/os, Docker Swarm y Red Hat OpenShift.

![Consumo de registros de varios contenedores ](./media/containers-diagram.png)
 **figura 7-10**. Consumo de registros de varios contenedores

[Prometheus](https://prometheus.io/) es una conocida solución de supervisión de métricas de código abierto. Forma parte de la base de cálculo nativa de la nube. Normalmente, el uso de Prometheus requiere la administración de un servidor de Prometheus con su propio almacén. Sin embargo, [Azure monitor para contenedores proporciona integración directa con puntos de conexión de métricas de Prometheus](/azure/azure-monitor/insights/container-insights-prometheus-integration), por lo que no es necesario un servidor independiente.

La información de registro y métrica se recopila no solo de los contenedores que se ejecutan en el clúster, sino también de los propios hosts del clúster. Permite correlacionar la información de registro de las dos, lo que hace que sea mucho más fácil realizar un seguimiento de un error.

La instalación de los recopiladores de registros es diferente en los clústeres de [Windows](/azure/azure-monitor/insights/containers#configure-a-log-analytics-windows-agent-for-kubernetes) y [Linux](/azure/azure-monitor/insights/containers#configure-a-log-analytics-linux-agent-for-kubernetes) . Sin embargo, en ambos casos, la colección de registros se implementa como un [DaemonSet](https://kubernetes.io/docs/concepts/workloads/controllers/daemonset/)Kubernetes, lo que significa que el recopilador de registros se ejecuta como un contenedor en cada uno de los nodos.

Independientemente del orquestador o del sistema operativo que ejecute el demonio de Azure Monitor, la información de registro se reenvía a las mismas herramientas de Azure Monitor con las que los usuarios están familiarizados. Esto garantiza una experiencia paralela en entornos que mezclen distintos orígenes de registro, como un entorno híbrido de Kubernetes/Azure Functions.

![Un panel de ejemplo que muestra información de registro y métrica de varios contenedores en ejecución. ](./media/containers-dashboard.png)
 **Figura 7-11**. Un panel de ejemplo que muestra información de registro y métrica de varios contenedores en ejecución.

## <a name="logfinalize"></a>Log. Finalize ()

El registro es una de las partes más informadas y, a la mayor parte de lo importante, de la implementación de cualquier aplicación a escala. A medida que aumentan el tamaño y la complejidad de las aplicaciones, lo que hace es la dificultad de depurarlos. Tener los registros de alta calidad disponibles hace que la depuración sea mucho más fácil y la mueve del dominio "casi imposible" a la "experiencia agradable".

>[!div class="step-by-step"]
>[Anterior](logging-with-elastic-stack.md)
>[Siguiente](azure-monitor.md)
