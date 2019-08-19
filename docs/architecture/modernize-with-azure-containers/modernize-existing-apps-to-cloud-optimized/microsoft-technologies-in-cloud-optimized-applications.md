---
title: Tecnologías de Microsoft en aplicaciones optimizadas para la nube
description: Modernización de las aplicaciones .NET existentes con la nube de Azure y los contenedores de Windows | Tecnologías de Microsoft en aplicaciones optimizadas para la nube
ms.date: 04/28/2018
ms.openlocfilehash: 915aa99d2331c5b9c46eabef3335fb809baa9370
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "69578228"
---
# <a name="microsoft-technologies-in-cloud-optimized-applications"></a>Tecnologías de Microsoft en aplicaciones optimizadas para la nube

En la lista siguiente se describen las herramientas, tecnologías y soluciones que se reconocen como requisitos para las aplicaciones optimizadas para la nube. Puede adoptar elementos optimizados para la nube de forma selectiva o gradual, en función de sus prioridades.

- **Infraestructura de la nube**: La infraestructura que proporciona la plataforma de proceso, el sistema operativo, la red y el almacenamiento. Microsoft Azure se coloca en este nivel.

- **Tiempo de ejecución**: Esta capa proporciona el entorno para la ejecución de la aplicación. Si usa contenedores, esta capa normalmente se basa en el [motor](https://docs.docker.com/engine/)de Docker, que se ejecuta en hosts de Linux o en hosts de Windows. (Los[contenedores de Windows](https://docs.microsoft.com/virtualization/windowscontainers/about/) se admiten a partir de windows Server 2016. Los contenedores de Windows son la mejor opción para las aplicaciones de .NET Framework existentes que se ejecutan en Windows).

- **Nube administrada**: Cuando se elige una opción en la nube administrada, se puede evitar el gasto y la complejidad de la administración y la compatibilidad de la infraestructura subyacente, las máquinas virtuales, las revisiones del sistema operativo y la configuración de red. Si decide migrar mediante IaaS, es responsable de todas estas tareas y de los costos asociados. En una opción en la nube administrada, solo se administran las aplicaciones y los servicios que se desarrollan. Normalmente, el proveedor de servicios en la nube administra todo lo demás. Entre los ejemplos de servicios en la nube administrados en Azure se incluyen [Azure SQL Database](https://azure.microsoft.com/services/sql-database), [Azure Redis cache](https://azure.microsoft.com/services/cache/), [Azure Cosmos dB](https://azure.microsoft.com/services/cosmos-db/), [Azure Storage](https://azure.microsoft.com/services/storage/), [Azure Database for MySQL](https://azure.microsoft.com/services/mysql/), [Azure Database for PostgreSQL](https://azure.microsoft.com/services/postgresql/), [Azure Active ](https://azure.microsoft.com/services/active-directory/)Y servicios de proceso administrados como conjuntos de escalado de [máquinas virtuales](https://azure.microsoft.com/services/virtual-machine-scale-sets/), [Azure App Service](https://azure.microsoft.com/services/app-service/)y [Azure Kubernetes Service](https://azure.microsoft.com/services/container-service/).

- **Desarrollo de aplicaciones**: Puede elegir entre muchos idiomas al compilar aplicaciones que se ejecutan en contenedores. Esta guía se centra en [.net](https://www.microsoft.com/net), pero puede desarrollar aplicaciones basadas en contenedores con otros lenguajes, como node. js, Python, Spring/Java o go.

- **Supervisión, telemetría, registro y auditoría**: La capacidad de supervisar y auditar aplicaciones y contenedores que se ejecutan en la nube es fundamental para cualquier aplicación optimizada para la nube. [Aplicación de Azure Insights](https://azure.microsoft.com/services/application-insights/) y [Microsoft Operations Management Suite](https://www.microsoft.com/cloud-platform/operations-management-suite) son las principales herramientas de Microsoft que proporcionan supervisión y auditoría para las aplicaciones optimizadas para la nube.

- **Aprovisionamiento**: Las herramientas de automatización le ayudan a aprovisionar la infraestructura e implementar una aplicación en varios entornos (producción, pruebas, ensayo). Puede usar herramientas como chef y posición libre para administrar la configuración y el entorno de una aplicación. Este nivel también se puede implementar mediante enfoques más sencillos y más directos. Por ejemplo, puede implementar directamente mediante herramientas de la interfaz de la línea de comandos de Azure (CLI de Azure) y, a continuación, usar las canalizaciones de implementación continua y administración de versiones en [Azure DevOps Services](https://azure.microsoft.com/services/devops/).

- **Ciclo de vida**de la aplicación: [Azure DevOps Services](https://azure.microsoft.com/services/devops/) y otras herramientas, como Jenkins, son servidores de automatización integrados que ayudan a implementar canalizaciones de CI/CD, incluida Release Management.

En las siguientes secciones de este capítulo y en los tutoriales relacionados, se centra específicamente en los detalles sobre la capa de tiempo de ejecución (contenedores de Windows). En la guía se describen las formas en que puede implementar contenedores de Windows en máquinas virtuales de Windows Server 2016 (y versiones posteriores) y Azure Container Instances. También se tratan plataformas PaaS más avanzadas, como Azure App Service y Orchestrator como Azure Kubernetes Service.

## <a name="monolithic-applications-can-be-cloud-optimized"></a>Las aplicaciones monolíticas *pueden* estar optimizadas para la nube

Es importante resaltar que las aplicaciones monolíticas (aplicaciones que no están basadas en microservicios) *pueden* ser aplicaciones optimizadas para la nube. Puede compilar y usar aplicaciones monolíticas que aprovechan el modelo de informática en la nube mediante una combinación de contenedores, entrega continua y DevOps. Si una aplicación monolítica existente es adecuada para sus objetivos empresariales, puede modernizarla y hacer que esté optimizada para la nube.

Del mismo modo, si las aplicaciones monolíticas pueden ser aplicaciones optimizadas para la nube, otras arquitecturas más complejas, como las aplicaciones de N niveles, también se pueden modernizar como aplicaciones optimizadas para la nube.

>[!div class="step-by-step"]
>[Anterior](reasons-to-modernize-existing-net-apps-to-cloud-optimized-applications.md)
>[Siguiente](what-about-cloud-native-applications.md)
