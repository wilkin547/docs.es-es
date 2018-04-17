---
title: Administrar entornos de producción Docker
description: Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft
ms.prod: .net
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 72ae92c89ed9b51815016205e20b09fc4dced1e1
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2018
---
# <a name="manage-production-docker-environments"></a>Administrar entornos de producción Docker

Administración de clúster y la orquestación es el proceso de control de un grupo de hosts. Esto puede incluir agregar y quitar hosts de un clúster, obtener información sobre el estado actual de los hosts y contenedores e iniciar y detener procesos. Orquestación y administración del clúster están estrechamente Unidos a la programación porque el programador debe tener acceso a cada host del clúster con el fin de programar servicios. Por este motivo, la misma herramienta se usa a menudo para ambos fines.

## <a name="container-service-and-management-tools"></a>Herramientas de administración y servicio de contenedor

Servicio de contenedor proporciona una implementación rápida de las soluciones de agrupación en clústeres y orquestación de contenedor de código abierto populares. Usa imágenes de Docker para asegurarse de que los contenedores de la aplicación sean totalmente portables. Mediante el servicio de contenedor, puede implementar DC/OS (con la tecnología Mesosphere y Apache Mesos) y clústeres con plantillas del Administrador de recursos de Azure o el portal de Azure para asegurarse de que se pueden escalar estas aplicaciones a miles de Docker Swarm: incluso decenas de miles, de contenedores.

Implementar estos clústeres mediante conjuntos de escalas de máquina Virtual de Azure y los clústeres de aprovechar las ventajas de las ofertas de redes y almacenamiento de Azure. Para obtener acceso a servicio de contenedor, necesita una suscripción a Azure. Con el servicio de contenedor, puede sacar partido de las características de nivel empresarial de Azure manteniendo la portabilidad de aplicación, incluidos en las capas de la orquestación.

Tabla 6-1 se muestran las herramientas de administración habituales relacionados con sus orchestrators, programadores y plataforma de agrupación en clústeres.

Herramientas de administración de Docker de la tabla 6-1:


| Herramientas de administración      | Descripción           | Orchestrators relacionados |
|-----------------------|-----------------------|-----------------------|
| Servicio de contenedor\(administración de la interfaz de usuario en el portal de Azure) | [Servicio de contenedor](https://azure.microsoft.com/en-us/services/container-service/) proporciona una forma sencilla de obtener iniciado podrán [implementar un clúster de contenedor en Azure](https://docs.microsoft.com/azure/container-service/dcos-swarm/container-service-deployment) tomando como base orchestrators populares como Mesosphere DC/OS, Kubernetes y Docker Swarm. <br /><br /> Servicio de contenedor optimiza la configuración de esas plataformas. Basta con seleccionar el tamaño, el número de hosts y la elección de las herramientas de orchestrator y servicio de contenedor controla todo lo demás. | Mesosphere DC/OS <br /><br /> Kubernetes <br /><br /> Docker Swarm |
| Plano de Control Universal de docker\(en la nube o local) | [Plano de Control Universal docker](https://docs.docker.com/v1.11/ucp/overview/) es la solución de administración de clúster de nivel empresarial de Docker. Le ayuda a administrar todo el clúster desde un único lugar. <br /><br /> Plano de Control Universal de docker se incluye como parte del producto comercial con el nombre de centro de datos de Docker que proporciona servicios de plano de Control Universal de Docker y Docker Swarm, registro de confianza de Docker. <br /><br /> Centro de datos de docker puede ser instalado en local o aprovisionado desde una nube pública, como Azure. | Docker Swarm\(compatible con el servicio de contenedor) |
| En la nube docker\(también conocido como Tutum; en la nube SaaS) | [En la nube docker](https://docs.docker.com/docker-cloud/) es un servicio de administración hospedado (SaaS) que proporciona capacidades de orquestación y un registro de Docker con compilación y las instalaciones de prueba para las imágenes de aplicación Dockerized, herramientas para ayudarle a configurar y administrar su infraestructura de host y características de implementación para ayudarle a automatizar la implementación de las imágenes en la infraestructura concreta. Puede conectar su cuenta de nube de SaaS Docker a la infraestructura de servicio de contenedor que se ejecuta un clúster con Docker Swarm. | Docker Swarm\(compatible con el servicio de contenedor) |
| Maratón de mesosphere\(en la nube o local) | [Maratón](https://mesosphere.github.io/marathon/docs/marathon-ui.html) es una plataforma de orquestación y programador de contenedor de producción automatizado para del Mesosphere controlador de dominio/OS y Mesos de Apache. <br /><br /> Funciona con Mesos (controlador de dominio/OS se basa en Apache Mesos) al control de ejecución prolongada de servicios y proporciona un [interfaz de usuario web para la administración de proceso y el contenedor](https://mesosphere.github.io/marathon/docs/marathon-ui.html). Proporciona una herramienta de administración de la interfaz de usuario de web | Mesosphere DC/OS\(basado en Apache Mesos; compatible con el servicio de contenedor) |
| Google Kubernetes | [Kubernetes](http://kubernetes.io/docs/user-guide/ui/#dashboard-access) abarca orquestar, la programación y la infraestructura de clúster. Es una plataforma de código abierto para automatizar la implementación, la escala y las operaciones de contenedores de aplicaciones a través de clústeres de hosts, proporciona la infraestructura centrada en el contenedor. | Google Kubernetes\(compatible con el servicio de contenedor) |

## <a name="azure-service-fabric"></a>Azure Service Fabric

Otra opción para la administración e implementación de clúster es Azure Service Fabric. [Service Fabric](https://azure.microsoft.com/en-us/services/service-fabric/) es una plataforma de microservicios de Microsoft que incluye la orquestación de contenedor, así como para desarrolladores de programación de modelos para crear aplicaciones de microservicios altamente escalable. Service Fabric admite Docker en versiones recientes de vista previa de Linux, como en el [vista previa de Service Fabric en Linux](https://docs.microsoft.com/azure/service-fabric/service-fabric-deploy-anywhere)y para los contenedores de Windows [en la próxima versión](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview).

Siguientes son herramientas de administración de Service Fabric:

-   [Portal de Azure para Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-creation-via-portal) operaciones relacionadas con el clúster (crear/actualizar/eliminar) un clúster o configurar su infraestructura (máquinas virtuales, equilibrador de carga, redes, etcetera.)

-   [Azure Service Fabric Explorer](https://docs.microsoft.com/azure/service-fabric/service-fabric-visualizing-your-cluster) es una herramienta de interfaz de usuario web especializada que proporciona visión y ciertas operaciones en el clúster de Service Fabric desde el punto de vista de nodos y máquinas virtuales y de punto de vista de la aplicación y los servicios.


>[!div class="step-by-step"]
[Anterior] (run-microservices-based-applications-in-production.md) [siguiente] (monitor-en contenedores-aplicaciones-services.md)
