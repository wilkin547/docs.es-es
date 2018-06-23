---
title: Tecnologías de Microsoft en aplicaciones optimizada para la nube
description: Modernizar las aplicaciones .NET existentes con contenedores de Windows y de nube de Azure | Tecnologías de Microsoft en aplicaciones optimizada para la nube
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: 3c5886dc3583a5d4a6cc9566556edbe1822ad6d1
ms.sourcegitcommit: c217b067985905cb21eafc5dd9a83568d7ff4e45
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/22/2018
ms.locfileid: "36315185"
---
# <a name="microsoft-technologies-in-cloud-optimized-applications"></a>Tecnologías de Microsoft en aplicaciones optimizada para la nube

En la lista siguiente describe las herramientas, tecnologías y soluciones que se reconocen como requisitos de las aplicaciones optimizada para la nube. Puede adoptar elementos optimizada para la nube de forma selectiva o gradualmente, dependiendo de sus prioridades.

-   **Infraestructura de nube**: la infraestructura que proporciona la plataforma de proceso, el sistema operativo, la red y el almacenamiento. Microsoft Azure se coloca en este nivel.

-   **En tiempo de ejecución**: esta capa proporciona el entorno para ejecutar la aplicación. Si usas contenedores, este nivel normalmente se basa en [motor de Docker](https://docs.docker.com/engine/), la ejecución en hosts de Linux o en hosts de Windows. ([Contenedores de Windows](https://docs.microsoft.com/virtualization/windowscontainers/about/) se admite a partir de Windows Server 2016. Contenedores de Windows es la mejor opción para las aplicaciones existentes de .NET Framework que se ejecutan en Windows).

-   **Administra la nube**: cuando se elige una opción en la nube administrado, puede evitar los gastos y la complejidad de administrar y admitir las revisiones de sistema operativo subyacentes de infraestructura, las máquinas virtuales y configuración de red. Si decide migrar mediante el uso de IaaS, es responsable de todas estas tareas y para los costos asociados. En una opción en la nube administrados, administrar las aplicaciones y los servicios que desarrolla. Normalmente, el proveedor de servicios de nube administra todo lo demás. Examples of managed cloud services in Azure include [Azure SQL Database](https://azure.microsoft.com/services/sql-database), [Azure Redis Cache](https://azure.microsoft.com/services/cache/), [Azure Cosmos DB](https://azure.microsoft.com/services/cosmos-db/), [Azure Storage](https://azure.microsoft.com/services/storage/), [Azure Database for MySQL](https://azure.microsoft.com/services/mysql/), [Azure Database for PostgreSQL](https://azure.microsoft.com/services/postgresql/), [Azure Active Directory](https://azure.microsoft.com/services/active-directory/), and managed compute services like [VM scale sets](https://azure.microsoft.com/services/virtual-machine-scale-sets/), [Azure Service Fabric](https://azure.microsoft.com/services/service-fabric/), [Azure App Service](https://azure.microsoft.com/services/app-service/), and [Azure Kubernetes Service](https://azure.microsoft.com/services/container-service/).

-   **Desarrollo de aplicaciones**: puede elegir entre muchos idiomas al compilar aplicaciones que se ejecutan en contenedores. Esta guía se centra en [.NET](https://www.microsoft.com/net), pero, puede desarrollar aplicaciones basadas en el contenedor mediante el uso de otros lenguajes, como Node.js, Python, Spring/Java, o.

-   **Supervisión de telemetría, registro y auditoría**: la capacidad para las aplicaciones de supervisión y auditoría y otros contenedores que se ejecutan en la nube es fundamental para cualquier aplicación optimizada para la nube. [Azure Application Insights](https://azure.microsoft.com/services/application-insights/) y [Microsoft Operations Management Suite](https://www.microsoft.com/cloud-platform/operations-management-suite) son las principales herramientas de Microsoft que proporcionan auditoría y supervisión para aplicaciones optimizada para la nube.

-   **Aprovisionamiento**: herramientas de automatización le ayudarán a aprovisionar la infraestructura e implementar una aplicación para varios entornos (producción, pruebas, ensayo). También puede usar herramientas como Chef y posición libre para administrar la configuración y el entorno de una aplicación. Este nivel también puede implementarse utilizando los enfoques más sencillas y más directos. Por ejemplo, puede implementar directamente mediante Azure interfaz de línea de comandos (CLI de Azure), herramientas y, a continuación, usar la implementación continua y las canalizaciones de administración en la versión [Visual Studio Team Services](https://visualstudio.microsoft.com/team-services/).

-   **Ciclo de vida de aplicación**: [Visual Studio Team Services](https://visualstudio.microsoft.com/team-services/) y otras herramientas, como Jenkins, son servidores de automatización integrada que le ayudarán a implementar canalizaciones CI/CD, incluida la administración de versión.

Las secciones siguientes de este capítulo y los tutoriales relacionados, se centran específicamente en los detalles sobre la capa en tiempo de ejecución (contenedores de Windows). Las instrucciones describe lo que se puede implementar máquinas virtuales de los contenedores de Windows en Windows Server 2016 (y versiones posteriores) e instancias de contenedor de Azure. También cubre más avanzadas PaaS de plataformas, como servicio de aplicaciones de Azure y orchestrator como servicio de Kubernetes de Azure y Azure Service Fabric.

## <a name="monolithic-applications-can-be-cloud-optimized"></a>Aplicaciones monolíticas *puede* estar optimizada para la nube

Es importante resaltar que monolítico aplicaciones (que no se basan en microservicios) *puede* aplicaciones optimizada para la nube. Puede crear y operar monolíticas aplicaciones que aprovechan las ventajas de la informática modelo mediante una combinación de contenedores, la entrega continua y DevOps en la nube. Si una aplicación monolítica existente es el adecuado para sus objetivos empresariales, puede modernizar y hacer que optimizada para la nube.

De forma similar, si las aplicaciones monolíticas pueden ser aplicaciones optimizada para la nube, también se modernizado arquitecturas más complejas, otras como aplicaciones de N niveles como aplicaciones optimizada para la nube.

>[!div class="step-by-step"]
[Anterior](reasons-to-modernize-existing-net-apps-to-cloud-optimized-applications.md)
[Siguiente](what-about-cloud-native-applications.md)
