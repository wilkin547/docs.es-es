---
title: Administración de entornos de Docker en producción
description: Familiarícese con los puntos clave para administrar un entorno de producción basadas en contenedores.
ms.date: 02/15/2019
ms.openlocfilehash: 7d10f670745f8bac1084b8c33c5acde67bac6229
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641071"
---
# <a name="manage-production-docker-environments"></a>Administración de entornos de Docker en producción

Administración del clúster y la orquestación es el proceso de control de un grupo de hosts. Esto puede implicar la adición y eliminación de hosts de un clúster, obtener información sobre el estado actual de hosts y contenedores e iniciar y detener los procesos. Orquestación y administración del clúster están estrechamente relacionadas con la programación porque el programador debe tener acceso a cada host del clúster con el fin de programar servicios. Por este motivo, la misma herramienta que se usa a menudo para ambos fines.

## <a name="container-service-and-management-tools"></a>Herramientas de administración y servicio de contenedor

Container Service proporciona una implementación rápida de soluciones de agrupación en clústeres y orquestación de contenedores de código abierto populares. Imágenes de Docker usa para asegurarse de que los contenedores de su aplicación sean completamente portátiles. Mediante el servicio de contenedor, puede implementar (con tecnología de Mesosphere y Apache Mesos) en DC/OS y Docker Swarm con plantillas de Azure Resource Manager o el portal de Azure para asegurarse de que se pueda escalar estas aplicaciones a miles de clústeres, incluso a decenas de miles, de contenedores.

Estos clústeres se implementan mediante el uso de conjuntos de escalado de máquinas virtuales de Azure y los clústeres de aprovechan las ventajas de las ofertas de redes y almacenamiento de Azure. Para obtener acceso a Container Service, necesita una suscripción de Azure. Con Container Service, puede aprovechar las características de nivel empresarial de Azure sin perder la portabilidad de aplicaciones, incluso en las capas de orquestación.

Tabla 6-1 se enumeran las herramientas de administración comunes relacionados con su plataforma agrupación en clústeres, los programadores y orquestadores.

**Tabla 6-1**. Herramientas de administración de docker

| Herramientas de administración | Descripción | Orquestadores relacionados |
|------------------|-------------|-----------------------|
| [Azure Monitor para contenedores](https://docs.microsoft.com/azure/monitoring/monitoring-container-insights-overview) | Herramienta de administración de Kubernetes Azure dedicado | Azure Kubernetes Service (AKS) |
| [Kubernetes Web UI (panel)](https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard/) | Herramienta de administración de Kubernetes, puede supervisar y administrar un clúster local de Kubernetes | Azure Kubernetes Service (AKS)<br/>Kubernetes local |
| [Portal de Azure para Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-creation-via-portal)<br/>[Explorador de Azure Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-visualizing-your-cluster) | Versión de escritorio y en línea para administrar clústeres de Service Fabric en Azure, en el entorno local, el desarrollo local y otras nubes | Azure Service Fabric |
| [Contenedor de supervisión (Monitor de Azure)](https://docs.microsoft.com/azure/azure-monitor/insights/containers) | Administración de contenedor general y solución de supervisión. Puede administrar clústeres de Kubernetes mediante [Azure Monitor para contenedores](https://docs.microsoft.com/azure/monitoring/monitoring-container-insights-overview). | Azure Service Fabric<br/>Azure Kubernetes Service (AKS)<br/>Mesosphere DC/OS y otros. |

## <a name="azure-service-fabric"></a>Azure Service Fabric

Otra opción para la administración y la implementación del clúster es Azure Service Fabric. [Service Fabric](https://azure.microsoft.com/services/service-fabric/) es una plataforma de microservicios de Microsoft que incluye la orquestación de contenedores, así como para desarrolladores de programación modelos para crear aplicaciones de microservicios muy escalable. Service Fabric es compatible con Docker en contenedores de Windows y Linux y se pueden ejecutar en servidores Windows y Linux.

Estos son las herramientas de administración de Service Fabric:

- [Portal de Azure para Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-creation-via-portal) operaciones relacionadas con el clúster (crear/actualizar/eliminar) un clúster o configurar su infraestructura (máquinas virtuales, equilibradores de carga, redes, etcetera.)

- [Azure Service Fabric Explorer](https://docs.microsoft.com/azure/service-fabric/service-fabric-visualizing-your-cluster) está especializada en una interfaz de usuario y de escritorio herramienta multiplataforma que proporciona información y ciertas operaciones en el clúster de Service Fabric desde el punto de vista de nodos o máquinas virtuales y desde el punto de vista de la aplicación y los servicios web.

>[!div class="step-by-step"]
>[Anterior](run-microservices-based-applications-in-production.md)
>[Siguiente](monitor-containerized-application-services.md)
