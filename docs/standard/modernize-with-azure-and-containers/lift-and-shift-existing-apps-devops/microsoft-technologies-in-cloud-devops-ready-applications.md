---
title: Tecnologías de Microsoft en aplicaciones de uso de devops de nube
description: Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Tecnologías de Microsoft en aplicaciones de uso de DevOps en la nube
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.prod: .net
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: d3a0572b833a4ca3be1db3b3b531a76ca34fe4ab
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2018
---
# <a name="microsoft-technologies-in-cloud-devops-ready-applications"></a>Tecnologías de Microsoft en aplicaciones de uso de devops de nube

En la lista siguiente describe las herramientas, tecnologías y soluciones que se reconocen como requisitos de aplicaciones compatibles con DevOps en la nube. Puede adoptar aplicaciones compatibles con DevOps en la nube de forma selectiva o gradualmente, dependiendo de sus prioridades.

-   **Infraestructura de nube**: la infraestructura que proporciona la plataforma de proceso, el sistema operativo, la red y el almacenamiento. Microsoft Azure se coloca en este nivel.

-   **En tiempo de ejecución**: esta capa proporciona el entorno para ejecutar la aplicación. Si usas contenedores, este nivel normalmente se basa en [motor de Docker](https://docs.docker.com/engine/), la ejecución en hosts de Linux o en hosts de Windows. ([Contenedores de Windows](https://docs.microsoft.com/virtualization/windowscontainers/about/) se admite a partir de Windows Server 2016. Contenedores de Windows es la mejor opción para las aplicaciones existentes de .NET Framework que se ejecutan en Windows).

-   **Administra la nube**: cuando se elige una opción en la nube administrado, puede evitar los gastos y la complejidad de administrar y admitir las revisiones de sistema operativo subyacentes de infraestructura, las máquinas virtuales y configuración de red. Si decide migrar mediante el uso de IaaS, es responsable de todas estas tareas y para los costos asociados. En una opción en la nube administrados, administrar las aplicaciones y los servicios que desarrolla. Normalmente, el proveedor de servicios de nube administra todo lo demás. Ejemplos de servicios de nube administrado de Azure [base de datos de SQL Azure](https://azure.microsoft.com/services/sql-database), [Azure Redis Cache](https://azure.microsoft.com/services/cache/), [base de datos de Azure Cosmos](https://azure.microsoft.com/services/cosmos-db/), [el almacenamiento de Azure](https://azure.microsoft.com/services/storage/), [Base de datos de azure para MySQL](https://azure.microsoft.com/services/mysql/), [base de datos de Azure para PostgreSQL](https://azure.microsoft.com/services/postgresql/), [Azure Active Directory](https://azure.microsoft.com/services/active-directory/)y administran los servicios de proceso como [escalas de VM establece](https://azure.microsoft.com/services/virtual-machine-scale-sets/), [Azure Service Fabric](https://azure.microsoft.com/services/service-fabric/), [servicio de aplicaciones de Azure](https://azure.microsoft.com/services/app-service/), y [servicio de contenedor de Azure](https://azure.microsoft.com/services/container-service/).

-   **Desarrollo de aplicaciones**: puede elegir entre muchos idiomas al compilar aplicaciones que se ejecutan en contenedores. Esta guía se centra en [.NET](https://www.microsoft.com/net), pero puede desarrollar aplicaciones basadas en el contenedor mediante el uso de otros lenguajes, como Node.js, Python, Java/Spring o GoLang.

-   **Supervisión de telemetría, registro y auditoría**: la capacidad para las aplicaciones de supervisión y auditoría y otros contenedores que se ejecutan en la nube es fundamental para cualquier aplicación preparada para DevOps la nube. [Azure Application Insights](https://azure.microsoft.com/services/application-insights/) y [Microsoft Operations Management Suite](https://www.microsoft.com/cloud-platform/operations-management-suite) son las principales herramientas de Microsoft que proporcionan auditoría y supervisión de aplicaciones compatibles con DevOps en la nube.

-   **Aprovisionamiento**: herramientas de automatización le ayudarán a aprovisionar la infraestructura e implementar una aplicación para varios entornos (producción, pruebas, ensayo). También puede usar herramientas como Chef y posición libre para administrar la configuración y el entorno de una aplicación. Este nivel también puede implementarse utilizando los enfoques más sencillas y más directos. Por ejemplo, puede implementar directamente mediante Azure interfaz de línea de comandos (CLI de Azure), herramientas y, a continuación, usar la implementación continua y las canalizaciones de administración en la versión [Visual Studio Team Services](https://www.visualstudio.com/team-services/).

-   **Ciclo de vida de aplicación**: [Visual Studio Team Services](https://www.visualstudio.com/team-services/) y otras herramientas, como Jenkins, son servidores de automatización de compilación que le ayudarán a implementan canalizaciones CI/CD, incluida la administración de versión.

Las secciones siguientes de este capítulo y los tutoriales relacionados, se centran específicamente en los detalles sobre la capa en tiempo de ejecución (contenedores de Windows). Las instrucciones describe lo que se puede implementar máquinas virtuales de los contenedores de Windows en Windows Server 2016 (y versiones posteriores). Además se ocupa de las capas de orchestrator más avanzadas, como Azure Service Fabric, Kubernetes y el servicio de contenedor de Azure. Configuración de las capas de orchestrator es un requisito fundamental para modernizar las aplicaciones existentes (basado en Windows) .NET Framework como aplicaciones de uso de DevOps en la nube.

## <a name="monolithic-applications-can-be-cloud-devops-ready"></a>Aplicaciones monolíticas *puede* está listo en la nube DevOps

Es importante resaltar que monolítico aplicaciones (que no se basan en microservicios) *puede* ser aplicaciones de uso de DevOps en la nube. Puede crear y operar monolíticas aplicaciones que aprovechan las ventajas de la informática modelo mediante una combinación de contenedores, la entrega continua y DevOps en la nube. Si una aplicación monolítica existente es el adecuado para sus objetivos empresariales, puede modernizar y hacerla preparada para DevOps la nube.

De forma similar, si monolíticas aplicaciones pueden ser aplicaciones de uso de DevOps en la nube, arquitecturas de otras, más complejas como aplicaciones de N niveles también pueden ser y modernizadas como aplicaciones de uso de DevOps en la nube.

>[!div class="step-by-step"]
[Anterior](reasons-to-lift-and-shift-existing-net-apps-to-cloud-devops-ready-applications.md)
[Siguiente](what-about-cloud-optimized-applications.md)
