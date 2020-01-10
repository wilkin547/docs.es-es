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
# <a name="monitoring-in-azure-kubernetes-services"></a><span data-ttu-id="54823-103">Supervisión en Azure Kubernetes Service</span><span class="sxs-lookup"><span data-stu-id="54823-103">Monitoring in Azure Kubernetes Services</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="54823-104">El registro integrado en Kubernetes es primitivo.</span><span class="sxs-lookup"><span data-stu-id="54823-104">The built-in logging in Kubernetes is primitive.</span></span> <span data-ttu-id="54823-105">Sin embargo, hay algunas opciones excelentes para obtener los registros de Kubernetes y en un lugar donde se pueden analizar correctamente.</span><span class="sxs-lookup"><span data-stu-id="54823-105">However, there are some great options for getting the logs out of Kubernetes and into a place where they can be properly analyzed.</span></span> <span data-ttu-id="54823-106">Si necesita supervisar los clústeres de AKS, la configuración de la pila elástica para Kubernetes es una solución excelente.</span><span class="sxs-lookup"><span data-stu-id="54823-106">If you need to monitor your AKS clusters, configuring Elastic Stack for Kubernetes is a great solution.</span></span>

## <a name="elastic-stack"></a><span data-ttu-id="54823-107">Pila elástica</span><span class="sxs-lookup"><span data-stu-id="54823-107">Elastic Stack</span></span>

<span data-ttu-id="54823-108">La pila elástica es una opción eficaz para recopilar información de un clúster de Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="54823-108">The Elastic Stack is a powerful option for gathering information from a Kubernetes cluster.</span></span> <span data-ttu-id="54823-109">Kubernetes admite el envío de registros a un punto de conexión de Elasticsearch y, en su [mayor parte](https://kubernetes.io/docs/tasks/debug-application-cluster/logging-elasticsearch-kibana/), todo lo que necesita para empezar es establecer las variables de entorno como se muestra en la figura 7-5:</span><span class="sxs-lookup"><span data-stu-id="54823-109">Kubernetes supports sending logs to an Elasticsearch endpoint, and for the [most part](https://kubernetes.io/docs/tasks/debug-application-cluster/logging-elasticsearch-kibana/), all you need to get started is to set the environment variables as shown in Figure 7-5:</span></span>

```kubernetes
KUBE_LOGGING_DESTINATION=elasticsearch
KUBE_ENABLE_NODE_LOGGING=true
```

<span data-ttu-id="54823-110">**Figura 7-5** : variables de configuración para Kubernetes</span><span class="sxs-lookup"><span data-stu-id="54823-110">**Figure 7-5** - Configuration variables for Kubernetes</span></span>

<span data-ttu-id="54823-111">Con esto se instalará Elasticsearch en el clúster y se le enviarán todos los registros de clúster.</span><span class="sxs-lookup"><span data-stu-id="54823-111">This will install Elasticsearch on the cluster and target sending all the cluster logs to it.</span></span>

<span data-ttu-id="54823-112">![un ejemplo de un panel de Kibana que muestra los resultados de una consulta en los registros ingeridos de Kubernetes](./media/kibana-dashboard.png)
**figura 7-6**.</span><span class="sxs-lookup"><span data-stu-id="54823-112">![An example of a Kibana dashboard showing the results of a query against logs ingested from Kubernetes](./media/kibana-dashboard.png)
**Figure 7-6**.</span></span> <span data-ttu-id="54823-113">Un ejemplo de un panel de Kibana que muestra los resultados de una consulta en los registros que se introducen en Kubernetes</span><span class="sxs-lookup"><span data-stu-id="54823-113">An example of a Kibana dashboard showing the results of a query against logs that are ingested from Kubernetes</span></span>

## <a name="azure-container-monitoring"></a><span data-ttu-id="54823-114">Supervisión de contenedores de Azure</span><span class="sxs-lookup"><span data-stu-id="54823-114">Azure Container Monitoring</span></span>

<span data-ttu-id="54823-115">La supervisión de contenedores de Azure admite el consumo de registros no solo de Kubernetes, sino también de otros motores de orquestación como DC/OS, Docker Swarm y Red Hat OpenShift.</span><span class="sxs-lookup"><span data-stu-id="54823-115">Azure Container Monitoring supports consuming logs from not just Kubernetes but also from other orchestration engines such as DC/OS, Docker Swarm, and Red Hat OpenShift.</span></span>

<span data-ttu-id="54823-116">![consumo de registros de varios contenedores](./media/containers-diagram.png)
la **figura 7-7**.</span><span class="sxs-lookup"><span data-stu-id="54823-116">![Consuming logs from various containers](./media/containers-diagram.png)
**Figure 7-7**.</span></span>  <span data-ttu-id="54823-117">Consumo de registros de varios contenedores</span><span class="sxs-lookup"><span data-stu-id="54823-117">Consuming logs from various containers</span></span>

<span data-ttu-id="54823-118">La información de registro y métrica se recopila no solo de los contenedores que se ejecutan en el clúster, sino también de los propios hosts del clúster.</span><span class="sxs-lookup"><span data-stu-id="54823-118">Log and metric information is gathered not just from the containers running in the cluster but also from the cluster hosts themselves.</span></span> <span data-ttu-id="54823-119">Permite correlacionar la información de registro de las dos, lo que hace que sea mucho más fácil realizar un seguimiento de un error.</span><span class="sxs-lookup"><span data-stu-id="54823-119">It allows correlating log information from the two making it much easier to track down an error.</span></span>

<span data-ttu-id="54823-120">La instalación de los recopiladores de registros es diferente en los clústeres de [Windows](https://docs.microsoft.com/azure/azure-monitor/insights/containers#configure-a-log-analytics-windows-agent-for-kubernetes) y [Linux](https://docs.microsoft.com/azure/azure-monitor/insights/containers#configure-a-log-analytics-linux-agent-for-kubernetes) .</span><span class="sxs-lookup"><span data-stu-id="54823-120">Installing the log collectors differs on [Windows](https://docs.microsoft.com/azure/azure-monitor/insights/containers#configure-a-log-analytics-windows-agent-for-kubernetes) and [Linux](https://docs.microsoft.com/azure/azure-monitor/insights/containers#configure-a-log-analytics-linux-agent-for-kubernetes) clusters.</span></span> <span data-ttu-id="54823-121">Sin embargo, en ambos casos, la colección de registros se implementa como un [DaemonSet](https://kubernetes.io/docs/concepts/workloads/controllers/daemonset/)Kubernetes, lo que significa que el recopilador de registros se ejecuta como un contenedor en cada uno de los nodos.</span><span class="sxs-lookup"><span data-stu-id="54823-121">But in both cases the log collection is implemented as a Kubernetes [DaemonSet](https://kubernetes.io/docs/concepts/workloads/controllers/daemonset/), meaning that the log collector is run as a container on each of the nodes.</span></span>

<span data-ttu-id="54823-122">Independientemente del orquestador o del sistema operativo que ejecute el demonio de Azure Monitor, la información de registro se reenvía a las mismas herramientas de Azure Monitor con las que los usuarios están familiarizados.</span><span class="sxs-lookup"><span data-stu-id="54823-122">No matter which orchestrator or operating system is running the Azure Monitor daemon, the log information is forwarded to the same Azure Monitor tools with which users are familiar.</span></span> <span data-ttu-id="54823-123">Esto garantiza una experiencia paralela en entornos que mezclen distintos orígenes de registro, como un entorno híbrido de Kubernetes/Azure Functions.</span><span class="sxs-lookup"><span data-stu-id="54823-123">This ensures a parallel experience in environments that mix different log sources such as a hybrid Kubernetes/Azure Functions environment.</span></span>

<span data-ttu-id="54823-124">![un panel de ejemplo que muestra información de registro y métrica de varios contenedores en ejecución.](./media/containers-dashboard.png)
**figura 7-8**.</span><span class="sxs-lookup"><span data-stu-id="54823-124">![A sample dashboard showing logging and metric information from a number of running containers.](./media/containers-dashboard.png)
**Figure 7-8**.</span></span> <span data-ttu-id="54823-125">Un panel de ejemplo que muestra información de registro y métrica de varios contenedores en ejecución.</span><span class="sxs-lookup"><span data-stu-id="54823-125">A sample dashboard showing logging and metric information from a number of running containers.</span></span>

## <a name="logfinalize"></a><span data-ttu-id="54823-126">Log. Finalize ()</span><span class="sxs-lookup"><span data-stu-id="54823-126">Log.Finalize()</span></span>

<span data-ttu-id="54823-127">El registro es una de las partes más informadas y, a la mayor parte de lo importante, de la implementación de cualquier aplicación a escala.</span><span class="sxs-lookup"><span data-stu-id="54823-127">Logging is one of the most overlooked and yet most important parts of deploying any application at scale.</span></span> <span data-ttu-id="54823-128">A medida que aumentan el tamaño y la complejidad de las aplicaciones, lo que hace es la dificultad de depurarlos.</span><span class="sxs-lookup"><span data-stu-id="54823-128">As the size and complexity of applications increase, then so does the difficulty of debugging them.</span></span> <span data-ttu-id="54823-129">Tener los registros de alta calidad disponibles hace que la depuración sea mucho más fácil y la mueve del dominio "casi imposible" a la "experiencia agradable".</span><span class="sxs-lookup"><span data-stu-id="54823-129">Having top quality logs available makes debugging much easier and moves it from the realm of "nearly impossible" to "a pleasant experience".</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="54823-130">[Anterior](logging-with-elastic-stack.md)
>[Siguiente](azure-monitor.md)</span><span class="sxs-lookup"><span data-stu-id="54823-130">[Previous](logging-with-elastic-stack.md)
[Next](azure-monitor.md)</span></span>
