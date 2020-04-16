---
title: Elección de la opción de hospedaje de Azure correcta
description: Vea cuál es la ruta de migración de Azure más adecuada para su aplicación web ASP.NET.
author: CESARDELATORRE
ms.author: cesardl
ms.date: 03/01/2020
ms.openlocfilehash: a8ad946b03f97272cb8685620858af6b21a372dc
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2020
ms.locfileid: "81433353"
---
# <a name="choose-the-right-azure-hosting-option"></a>Elección de la opción de hospedaje de Azure correcta

En este artículo se proporcionan consideraciones y comparaciones entre las varias opciones que tiene en Azure al migrar las aplicaciones de .NET Framework existentes de local a Azure.

Las áreas fundamentales que debe tener en cuenta a la hora de migrar aplicaciones de .NET existentes a Azure son:

1. Opciones de proceso
1. Opciones de base de datos
1. Consideraciones sobre redes y seguridad
1. Consideraciones sobre autenticación y autorización

## <a name="compute-choices"></a>Opciones de proceso

Hay varias opciones para migrar aplicaciones de .NET Framework existentes a Azure. Sin embargo, como .NET Framework depende de Windows, las siguientes opciones están limitadas a los servicios de proceso basados en Windows.

En la tabla siguiente se muestran varias comparaciones y recomendaciones para ayudarle a elegir la ruta adecuada para migrar su aplicación de .NET existente.

|                 | Máquinas virtuales de Azure | Azure App Service | Contenedores de Windows |
|-----------------|-----------|-------------------|--------------------|
|Cuándo se usa      |<ul><li>La aplicación tiene fuertes dependencias en las instalaciones de .msi local y de servidor.</li><li>Desea la ruta de migración de aplicaciones más sencilla</li></ul>|La aplicación no tiene ninguna dependencia en el servidor, es una aplicación web ASP.NET (MVC, WebForm) limpia o una aplicación de N niveles (Web API, WCF) con acceso a un servidor de base de datos. |<ul><li>La aplicación tiene dependencias en el servidor original, pero esas dependencias pueden incluirse en la imagen Windows de Docker.</li><li>¿Quieres modernizar la aplicación para que esté [lista para devOps en la nube?](../../architecture/modernize-with-azure-containers/modernize-existing-apps-to-cloud-optimized/reasons-to-modernize-existing-net-apps-to-cloud-optimized-applications.md)</li></ul>|
|Ventajas y beneficios  |<ul><li>Ruta de migración más sencilla</li><li>Entorno familiar. El entorno de implementación es una máquina virtual, por lo que es similar a los servidores locales.</li></ul> |Mantenimiento de PaaS continuado, la forma de más sencilla de administrar y escalar aplicaciones en Azure. |<ul><li>Preparado para el futuro, Cloud DevOps-Ready con dependencias incluidas en los contenedores de la aplicación.</li><li>Casi no es necesario refactorizar el código de .NET /C.</li></ul> |
|Desventajas             |Es IaaS. El mantenimiento es costoso. Debe administrar la infraestructura de la máquina virtual sobre redes, equilibrador de carga, escalado horizontal, administración de IIS, etc. |<ul><li>No todas las aplicaciones son [compatibles](https://appmigration.microsoft.com/assessment)</li><li>Es posible que algunas aplicaciones deban refactorizarse e incluso volver a diseñarse ligeramente, por lo que admiten Azure App Service.</li></ul> |<ul><li>Curva de aprendizaje de habilidades de Docker</li><li>Algunos cambios en el código y la configuración de la aplicación</li></ul>|
|Requisitos |Máquina virtual Windows Server con los mismos requisitos que la aplicación en el entorno local | Requisitos de Azure App Service especificados en Comprobaciones de [preparación](https://github.com/Azure/App-Service-Migration-Assistant/wiki/Readiness-Checks). |<ul><li>[Docker Engine - Enterprise para Windows Server 2019](https://azuremarketplace.microsoft.com/marketplace/apps/cloud-infrastructure-services.docker-windows-2019)<br />or</li><li>[Azure Container Service (AKS)](https://azure.microsoft.com/services/container-service/) (el orquestador de Kubernetes)<br />or<li>Orquestador de [Azure Service Fabric](https://azure.microsoft.com/services/service-fabric/)</li></ul> |
|Cómo migrar |Consulte [Migración a máquinas virtuales de Azure](vm.md) | Consulte [Migración a Azure App Service](app-service.md) | Siga las consideraciones, escenarios y tutoriales que se explican en el libro electrónico Modernización de [aplicaciones .NET existentes con contenedores](https://aka.ms/liftandshiftwithcontainersebook) de Azure y Windows |

El siguiente diagrama de diagrama de flujo muestra un árbol de decisión al planear una migración a Azure para las aplicaciones de .NET Framework existentes. Si es viable, pruebe primero la opción A, pero la opción B es la ruta más fácil de realizar.

![Diagrama que muestra el árbol de decisión de hospedaje](../media/migration/choose/decision-tree.png)

## <a name="database-choices"></a>Opciones de base de datos

Hay varias opciones para migrar las bases de datos relacionales a Azure. Consulte [Migración de su base de datos SQL Server a Azure SQL Database](sql.md) como ayuda para elegir la ruta de migración correcta de la base de datos para la aplicación de .NET existente.

## <a name="networking-and-security-considerations"></a>Consideraciones sobre redes y seguridad

Al implementar aplicaciones en una nube pública como Microsoft Azure, quizás quiera aislar y proteger determinadas redes mediante la [creación de redes perimetrales](https://docs.microsoft.com/azure/architecture/reference-architectures/dmz/), por ejemplo, una [red perimetral entre Azure y el entorno local](https://docs.microsoft.com/azure/architecture/reference-architectures/dmz/secure-vnet-hybrid) o una [red perimetral entre Azure e Internet](https://docs.microsoft.com/azure/architecture/reference-architectures/dmz/secure-vnet-dmz). Las redes perimetrales se pueden implementar con [Azure Virtual Network](https://docs.microsoft.com/azure/virtual-network/virtual-networks-overview).

Azure Virtual Network permite:

- Crear una infraestructura híbrida bajo su control
- Traer sus propias direcciones IP y servidores DNS
- Proteja sus conexiones con una red VPN IPsec o ExpressRoute
- Obtenga control detallado del tráfico entre las subredes
- Cree topologías de red sofisticadas con aplicaciones virtuales
- Obtenga un entorno aislado y altamente seguro para sus aplicaciones

Para empezar a crear su propia red virtual, consulte la [documentación de Azure Virtual Network](https://docs.microsoft.com/azure/virtual-network/).

## <a name="authentication-and-authorization-considerations-when-migrating-to-azure"></a>Consideraciones sobre autenticación y autorización para migrar a Azure

Una de las principales preocupaciones de una organización a la hora de trasladarse a la nube es la seguridad. La mayoría de las empresas han invertido una cantidad sustancial de tiempo, dinero e ingeniería en el diseño y desarrollo de un modelo de seguridad, y es importante que puedan aprovechar las inversiones existentes, como almacenes de identidades y soluciones de inicio de sesión único.

Muchas aplicaciones B2E empresariales de .NET existentes que se ejecutan en entornos locales usan Active Directory para la autenticación y administración de identidades. Azure AD Connect permite integrar sus directorios locales con Azure Active Directory. Para comenzar, consulte [Integración de los directorios locales con Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).

Vea los [requisitos de identidad para su solución de identidad híbrida](https://docs.microsoft.com/azure/active-directory/active-directory-hybrid-identity-design-considerations-business-needs) para poder continuar el planeamiento en relación con Azure Active Directory.

Otras opciones de protocolo de autenticación son [OAuth](https://en.wikipedia.org/wiki/OAuth) y [OpenID](https://en.wikipedia.org/wiki/OpenID), que son comunes en las aplicaciones orientadas al consumidor. Cuando se utilizan bases de datos de identidad autónomas, como una base de datos SQL de ASP.NET Identity encapsulada por IdentityServer4 que usa OAuth, normalmente no se necesita conectividad a bases de datos o directorios locales.

## <a name="next-steps"></a>Pasos siguientes

> [!div class="nextstepaction"]
> [Migrar una aplicación web ASP.NET a Azure App Service](app-service.md)
