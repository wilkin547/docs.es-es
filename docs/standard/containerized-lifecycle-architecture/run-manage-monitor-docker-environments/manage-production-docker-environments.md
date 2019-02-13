---
title: Administrar entornos de producción de Docker
description: Familiarícese con los puntos clave para administrar un entorno de producción basadas en contenedores.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/23/2018
ms.openlocfilehash: 54e2b999f744600d3b6853442bb9ccca004f4e76
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/13/2019
ms.locfileid: "56219495"
---
# <a name="manage-production-docker-environments"></a>Administrar entornos de producción de Docker

Administración del clúster y la orquestación es el proceso de control de un grupo de hosts. Esto puede implicar la adición y eliminación de hosts de un clúster, obtener información sobre el estado actual de hosts y contenedores e iniciar y detener los procesos. Orquestación y administración del clúster están estrechamente relacionadas con la programación porque el programador debe tener acceso a cada host del clúster con el fin de programar servicios. Por este motivo, la misma herramienta que se usa a menudo para ambos fines.

## <a name="container-service-and-management-tools"></a>Herramientas de administración y servicio de contenedor

Container Service proporciona una implementación rápida de soluciones de agrupación en clústeres y orquestación de contenedores de código abierto populares. Imágenes de Docker usa para asegurarse de que los contenedores de su aplicación sean completamente portátiles. Mediante el servicio de contenedor, puede implementar (con tecnología de Mesosphere y Apache Mesos) en DC/OS y Docker Swarm con plantillas de Azure Resource Manager o el portal de Azure para asegurarse de que se pueda escalar estas aplicaciones a miles de clústeres, incluso a decenas de miles, de contenedores.

Estos clústeres se implementan mediante el uso de conjuntos de escalado de máquinas virtuales de Azure y los clústeres de aprovechan las ventajas de las ofertas de redes y almacenamiento de Azure. Para obtener acceso a Container Service, necesita una suscripción de Azure. Con Container Service, puede aprovechar las características de nivel empresarial de Azure sin perder la portabilidad de aplicaciones, incluso en las capas de orquestación.

Tabla 6-1 se enumeran las herramientas de administración comunes relacionados con su plataforma agrupación en clústeres, los programadores y orquestadores.

Tabla 6-1: Herramientas de administración de docker


| Herramientas de administración      | Descripción           | Orquestadores relacionados |
|-----------------------|-----------------------|-----------------------|
| Container Service\(administración de la interfaz de usuario en Azure portal) | [Servicio de contenedor](https://azure.microsoft.com/services/container-service/) proporciona una forma sencilla de obtener iniciado de manera [implementar un clúster de contenedor en Azure](https://docs.microsoft.com/azure/container-service/dcos-swarm/container-service-deployment) según los orquestadores más populares, como Mesosphere DC/OS, Kubernetes y Docker Swarm. <br /><br /> Container Service optimiza la configuración de estas plataformas. Basta con seleccionar el tamaño, el número de hosts y las herramientas del orquestador y Container Service controla todo lo demás. | Mesosphere DC/OS <br /><br /> Kubernetes <br /><br /> Docker Swarm |
| Docker Universal Control plano\(de forma local o en la nube) | [Docker Universal Control plano](https://docs.docker.com/v1.11/ucp/overview/) es la solución de administración de clúster de nivel empresarial de Docker. Le ayuda a administrar todo el clúster desde un único lugar. <br /><br /> Plano de Control Universal de docker se incluye como parte de los productos comerciales denominado Docker Datacenter que proporciona servicios de plano de Control Universal de Docker y Docker Swarm, Docker Trusted Registry. <br /><br /> Centro de datos de docker puede ser instalado en el entorno local o aprovisionada desde una nube pública como Azure. | Docker Swarm\(compatibles con Container Service) |
| Docker Cloud\(también se denomina Tutum; SaaS en la nube) | [Docker en la nube](https://docs.docker.com/docker-cloud/) es un servicio de administración hospedado (SaaS) que proporciona funcionalidades de orquestación y un registro de Docker con la compilación y capacidades de pruebas para las imágenes de aplicación "dockerizadas", las herramientas que le ayudarán a configurar y administrar su infraestructura de host y las características de implementación para ayudarle a automatizar la implementación de las imágenes en su infraestructura concreta. Puede conectar su cuenta de Docker de SaaS en la nube a su infraestructura en Container Service ejecutándose en un clúster de Docker Swarm. | Docker Swarm\(compatibles con Container Service) |
| Mesosphere Marathon\(de forma local o en la nube) | [Marathon](https://mesosphere.github.io/marathon/docs/marathon-ui.html) es una plataforma de orquestación y el programador de contenedor de producción para de Mesosphere DC/OS y Apache Mesos. <br /><br /> Funciona con Mesos (DC/OS se basa en Apache Mesos) al control de ejecución prolongada de servicios y proporciona un [interfaz de usuario web para la administración de proceso y el contenedor](https://mesosphere.github.io/marathon/docs/marathon-ui.html). Proporciona una herramienta de administración de la interfaz de usuario web | Mesosphere DC/OS\(basado en Apache Mesos; compatible con Container Service) |
| Google Kubernetes | [Kubernetes](https://kubernetes.io/docs/user-guide/ui/#dashboard-access) abarca la coordinación, la programación y la infraestructura del clúster. Es una plataforma de código abierto para automatizar la implementación, escalado y las operaciones de contenedores de aplicaciones en clústeres de hosts, que proporciona una infraestructura centrada en el contenedor. | Google Kubernetes\(compatibles con Container Service) |

## <a name="azure-service-fabric"></a>Azure Service Fabric

Otra opción para la administración y la implementación del clúster es Azure Service Fabric. [Service Fabric](https://azure.microsoft.com/services/service-fabric/) es una plataforma de microservicios de Microsoft que incluye la orquestación de contenedores, así como para desarrolladores de programación modelos para crear aplicaciones de microservicios muy escalable. Service Fabric admite Docker en las versiones actuales de versión preliminar de Linux, como en el [versión preliminar de Service Fabric en Linux](https://docs.microsoft.com/azure/service-fabric/service-fabric-deploy-anywhere)y para los contenedores de Windows [en la próxima versión](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview).

Estos son las herramientas de administración de Service Fabric:

-   [Portal de Azure para Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-creation-via-portal) operaciones relacionadas con el clúster (crear/actualizar/eliminar) un clúster o configurar su infraestructura (máquinas virtuales, equilibradores de carga, redes, etcetera.)

-   [Azure Service Fabric Explorer](https://docs.microsoft.com/azure/service-fabric/service-fabric-visualizing-your-cluster) es una herramienta de interfaz de usuario web especializado que proporciona información y ciertas operaciones en el clúster de Service Fabric desde el punto de vista de nodos o máquinas virtuales y desde el punto de vista de la aplicación y los servicios.

>[!div class="step-by-step"]
>[Anterior](run-microservices-based-applications-in-production.md)
>[Siguiente](monitor-containerized-application-services.md)