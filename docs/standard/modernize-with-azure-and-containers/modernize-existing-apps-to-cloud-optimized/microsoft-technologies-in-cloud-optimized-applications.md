---
title: Tecnologías de Microsoft en aplicaciones optimizadas para la nube
description: Modernizar aplicaciones .NET existentes con contenedores de Windows y la nube de Azure | Tecnologías de Microsoft en aplicaciones optimizadas para la nube
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: 874eeffe77d7f5e459be4d1a93cc2c45e8f8711a
ms.sourcegitcommit: ba5c189bf44d44204a3e8838e59ec378a62d82f3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2018
ms.locfileid: "44698986"
---
# <a name="microsoft-technologies-in-cloud-optimized-applications"></a>Tecnologías de Microsoft en aplicaciones optimizadas para la nube

En la lista siguiente describe las herramientas, tecnologías y soluciones que se reconocen como requisitos para las aplicaciones optimizadas para la nube. Puede adoptar gradualmente, o de forma selectiva elementos optimizada para la nube según sus prioridades.

-   **Infraestructura de nube**: la infraestructura que proporciona la plataforma de proceso, sistema operativo, red y almacenamiento. Microsoft Azure se coloca en este nivel.

-   **En tiempo de ejecución**: esta capa proporciona el entorno para ejecutar la aplicación. Si usa contenedores, esta capa normalmente se basa en [Docker Engine](https://docs.docker.com/engine/), ejecutándose en hosts de Linux o en hosts de Windows. ([Contenedores Windows](https://docs.microsoft.com/virtualization/windowscontainers/about/) se admite a partir de Windows Server 2016. Contenedores de Windows es la mejor opción para las aplicaciones existentes de .NET Framework que se ejecutan en Windows).

-   **Administra la nube**: al elegir una opción en la nube administrado, puede evitar el gasto y la complejidad de administrar y admitir las revisiones de sistema operativo subyacentes de infraestructura, las máquinas virtuales y configuración de red. Si opta por migrar mediante el uso de IaaS, usted es responsable de todas estas tareas y para los costos asociados. En una opción en la nube administrado, administrar solo las aplicaciones y servicios que desarrolla. Normalmente, el proveedor de servicios en la nube administra todo lo demás. Ejemplos de servicios en la nube administrado de Azure [Azure SQL Database](https://azure.microsoft.com/services/sql-database), [Azure Redis Cache](https://azure.microsoft.com/services/cache/), [Azure Cosmos DB](https://azure.microsoft.com/services/cosmos-db/), [Azure Storage](https://azure.microsoft.com/services/storage/), [-Azure Database for MySQL](https://azure.microsoft.com/services/mysql/), [-Azure Database for PostgreSQL](https://azure.microsoft.com/services/postgresql/), [Azure Active Directory](https://azure.microsoft.com/services/active-directory/)y administra los servicios de proceso como [escalado de máquinas virtuales establece](https://azure.microsoft.com/services/virtual-machine-scale-sets/), [Azure Service Fabric](https://azure.microsoft.com/services/service-fabric/), [Azure App Service](https://azure.microsoft.com/services/app-service/), y [Azure Kubernetes Service](https://azure.microsoft.com/services/container-service/).

-   **Desarrollo de aplicaciones**: puede elegir entre muchos idiomas al compilar aplicaciones que se ejecutan en contenedores. Esta guía se centra en [.NET](https://www.microsoft.com/net), sin embargo, puede desarrollar aplicaciones basadas en contenedor mediante el uso de otros lenguajes, como Node.js, Python, Java/Spring o ir.

-   **Supervisión, telemetría, registro y auditoría**: la capacidad a aplicaciones supervise y audite y contenedores que se ejecutan en la nube es fundamental para cualquier aplicación optimizada para la nube. [Azure Application Insights](https://azure.microsoft.com/services/application-insights/) y [Microsoft Operations Management Suite](https://www.microsoft.com/cloud-platform/operations-management-suite) son las principales herramientas de Microsoft que proporcionan la supervisión y auditoría para las aplicaciones optimizadas para la nube.

-   **Aprovisionamiento**: herramientas de automatización le ayudarán a aprovisionar la infraestructura e implementar una aplicación en varios entornos (producción, pruebas, almacenamiento provisional). Puede usar herramientas como Chef y Puppet para administrar el entorno y la configuración de una aplicación. Este nivel también puede implementarse mediante los enfoques más sencillas y directos. Por ejemplo, puede implementar directamente mediante Azure interfaz de línea de comandos (CLI de Azure), herramientas y, a continuación, usar la implementación continua y liberar las canalizaciones de administración en [servicios de Azure DevOps](https://visualstudio.microsoft.com/team-services/).

-   **Ciclo de vida de aplicación**: [servicios de Azure DevOps](https://visualstudio.microsoft.com/team-services/) y otras herramientas como Jenkins, son servidores de automatización integradas que le ayudarán a implementar canalizaciones de CI/CD, incluida la administración de versión.

Las secciones siguientes de este capítulo y los tutoriales relacionados, se centran específicamente en los detalles acerca de la capa en tiempo de ejecución (contenedores de Windows). La guía describe los modos de implementación de máquinas virtuales de los contenedores de Windows en Windows Server 2016 (y versiones posteriores) y Azure Container Instances. También se tratan más avanzadas plataformas PaaS como Azure App Service y orchestrator como Azure Service Fabric y Azure Kubernetes Service.

## <a name="monolithic-applications-can-be-cloud-optimized"></a>Las aplicaciones monolíticas *puede* estar optimizada para la nube

Es importante destacar que las aplicaciones monolíticas (aplicaciones que no están basadas en microservicios) *puede* aplicaciones optimizadas para la nube. Puede crear y operar aplicaciones monolíticas que aprovechan las ventajas de informática de modelo mediante una combinación de contenedores, la entrega continua y DevOps en la nube. Si una aplicación monolítica existente es el adecuado para sus objetivos empresariales, puede modernizarlo y ponerla a optimizada para la nube.

De forma similar, si las aplicaciones monolíticas pueden ser aplicaciones optimizadas para la nube, también puede modernizarse arquitecturas de otras, más complejas, como aplicaciones de N niveles como aplicaciones optimizadas para la nube.

>[!div class="step-by-step"]
[Anterior](reasons-to-modernize-existing-net-apps-to-cloud-optimized-applications.md)
[Siguiente](what-about-cloud-native-applications.md)
