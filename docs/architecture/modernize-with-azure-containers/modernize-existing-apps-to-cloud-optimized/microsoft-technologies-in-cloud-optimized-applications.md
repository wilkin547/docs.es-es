---
title: Tecnologías de Microsoft en aplicaciones optimizadas para la nube
description: Modernización de las aplicaciones .NET existentes con Azure Clour y contenedores Windows | Tecnologías de Microsoft en aplicaciones optimizadas para la nube
ms.date: 04/28/2018
ms.openlocfilehash: 915aa99d2331c5b9c46eabef3335fb809baa9370
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "69578228"
---
# <a name="microsoft-technologies-in-cloud-optimized-applications"></a>Tecnologías de Microsoft en aplicaciones optimizadas para la nube

En la lista siguiente se describen las herramientas, tecnologías y soluciones que se reconocen como requisitos para las aplicaciones optimizadas para la nube. Puede adoptar elementos optimizados para la nube de forma selectiva o gradual, en función de sus prioridades.

- **Infraestructura en la nube**: la infraestructura que proporciona la plataforma de proceso, el sistema operativo, la red y el almacenamiento. Microsoft Azure se coloca en este nivel.

- **Entorno de ejecución**: esta capa proporciona el entorno para la ejecución de la aplicación. Si usa contenedores, esta capa normalmente se basa en el [motor de Docker](https://docs.docker.com/engine/), que se ejecuta en hosts Linux o Windows. (Los [contenedores Windows](https://docs.microsoft.com/virtualization/windowscontainers/about/) se admiten a partir de Windows Server 2016. Los contenedores Windows son la mejor opción para las aplicaciones de .NET Framework existentes que se ejecutan en Windows).

- **Nube administrada**: cuando se elige una opción de nube administrada, se puede evitar el gasto y la complejidad de la administración y la compatibilidad de la infraestructura subyacente, las máquinas virtuales, las revisiones del sistema operativo y la configuración de red. Si decide migrar mediante IaaS, usted es responsable de todas estas tareas y de los costos asociados. En una opción de nube administrada, solo se administran las aplicaciones y los servicios que se desarrollan. Normalmente, el proveedor de servicios en la nube administra todo lo demás. Algunos ejemplos de servicios en la nube administrados de Azure son [Azure SQL Database](https://azure.microsoft.com/services/sql-database), [Azure Redis Cache](https://azure.microsoft.com/services/cache/), [Azure Cosmos DB](https://azure.microsoft.com/services/cosmos-db/), [Azure Storage](https://azure.microsoft.com/services/storage/), [Azure Database for MySQL](https://azure.microsoft.com/services/mysql/), [Azure Database for PostgreSQL](https://azure.microsoft.com/services/postgresql/), [Azure Active Directory](https://azure.microsoft.com/services/active-directory/) y servicios de proceso administrados como [VMSS](https://azure.microsoft.com/services/virtual-machine-scale-sets/), [Azure App Service](https://azure.microsoft.com/services/app-service/) y [Azure Kubernetes Service](https://azure.microsoft.com/services/container-service/).

- **Desarrollo de aplicaciones**: puede elegir entre muchos lenguajes al compilar aplicaciones que se ejecutan en contenedores. Esta guía se centra en [.NET](https://www.microsoft.com/net), pero puede desarrollar aplicaciones basadas en contenedores con otros lenguajes, como Node.js, Python, Spring/Java o Go.

- **Supervisión, telemetría, registro y auditoría**: la capacidad de supervisar y auditar aplicaciones y contenedores que se ejecutan en la nube es fundamental para cualquier aplicación optimizada para la nube. [Azure Application Insights](https://azure.microsoft.com/services/application-insights/) y [Microsoft Operations Management Suite](https://www.microsoft.com/cloud-platform/operations-management-suite) son las principales herramientas de Microsoft que proporcionan supervisión y auditoría para las aplicaciones optimizadas para la nube.

- **Aprovisionamiento**: Las herramientas de automatización le ayudan a aprovisionar la infraestructura e implementar una aplicación en varios entornos (producción, pruebas, ensayo). Puede usar herramientas como Chef y Puppet para administrar la configuración y el entorno de una aplicación. Este nivel también se puede implementar mediante enfoques más sencillos y directos. Por ejemplo, puede implementarlo directamente mediante herramientas de la interfaz de la línea de comandos de Azure (CLI de Azure) y, a continuación, usar las canalizaciones de implementación continua y administración de versiones en [Azure DevOps Services](https://azure.microsoft.com/services/devops/).

- **Ciclo de vida de la aplicación**: [Azure DevOps Services](https://azure.microsoft.com/services/devops/) y otras herramientas, como Jenkins, son servidores de automatización que le ayudan a implementar canalizaciones de CI/CD, e incluyen administración de versiones.

Las siguientes secciones de este capítulo y los tutoriales relacionados se centran específicamente en los detalles sobre el nivel de tiempo de ejecución (contenedores Windows). En la guía se describen las formas en que puede implementar contenedores Windows en máquinas virtuales con Windows Server 2016 (y versiones posteriores) y Azure Container Instances. También se tratan plataformas PaaS más avanzadas, como Azure App Service y un orquestador como Azure Kubernetes Service.

## <a name="monolithic-applications-can-be-cloud-optimized"></a>Las aplicaciones monolíticas *pueden* optimizarse para la nube

Es importante resaltar que las aplicaciones monolíticas (aplicaciones que no se basan en microservicios) *pueden* ser aplicaciones optimizadas para la nube. Puede crear y usar aplicaciones monolíticas que aprovechan las ventajas del modelo de informática en la nube mediante una combinación de contenedores, entrega continua y DevOps. Si una aplicación monolítica existente es adecuada para sus objetivos empresariales, puede modernizarla y hacer que esté optimizada para la nube.

Del mismo modo, si las aplicaciones monolíticas pueden ser aplicaciones optimizadas para la nube, otras arquitecturas más complejas, como las aplicaciones de N niveles, también se pueden modernizar como aplicaciones optimizadas para la nube.

>[!div class="step-by-step"]
>[Anterior](reasons-to-modernize-existing-net-apps-to-cloud-optimized-applications.md)
>[Siguiente](what-about-cloud-native-applications.md)
