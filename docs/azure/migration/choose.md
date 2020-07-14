---
title: Elección de la opción de hospedaje de Azure correcta
description: Vea cuál es la ruta de migración de Azure más adecuada para su aplicación web ASP.NET.
author: CESARDELATORRE
ms.author: cesardl
ms.date: 03/01/2020
ms.openlocfilehash: 162dc8eb87dfd78d050b93b1c24ac573d7092126
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174301"
---
# <a name="choose-the-right-azure-hosting-option"></a>Elección de la opción de hospedaje de Azure correcta

En este artículo se ofrecen consideraciones y comparaciones entre las distintas opciones disponibles en Azure para migrar aplicaciones de .NET Framework existentes desde el entorno local a Azure.

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
|Cuándo utilizarlo      |<ul><li>La aplicación tiene fuertes dependencias en las instalaciones de .msi local y de servidor.</li><li>Desea la ruta de migración de aplicaciones más sencilla</li></ul>|La aplicación no tiene ninguna dependencia en el servidor, es una aplicación web ASP.NET (MVC, WebForm) limpia o una aplicación de N niveles (Web API, WCF) con acceso a un servidor de base de datos. |<ul><li>La aplicación tiene dependencias en el servidor original, pero esas dependencias pueden incluirse en la imagen Windows de Docker.</li><li>Quiere modernizar la aplicación para que esté [preparada para DevOps en la nube](../../architecture/modernize-with-azure-containers/modernize-existing-apps-to-cloud-optimized/reasons-to-modernize-existing-net-apps-to-cloud-optimized-applications.md)</li></ul>|
|Ventajas y beneficios  |<ul><li>Ruta de migración más sencilla</li><li>Entorno familiar. El entorno de implementación es una máquina virtual, por lo que es similar a los servidores locales.</li></ul> |Mantenimiento de PaaS continuado, la forma de más sencilla de administrar y escalar aplicaciones en Azure. |<ul><li>Preparada para el futuro, preparada para DevOps en la nube con dependencias incluidas en los contenedores de la aplicación.</li><li>Casi no es necesario refactorizar el código de .NET o C#.</li></ul> |
|Desventajas             |Es IaaS. El mantenimiento es costoso. Tiene que administrar la infraestructura de la máquina virtual relacionada con las redes, el equilibrador de carga, la escalabilidad horizontal, la administración de IIS, etc. |<ul><li>No todas las aplicaciones son [compatibles](https://appmigration.microsoft.com/assessment)</li><li>Es posible que sea necesario refactorizar algunas aplicaciones e, incluso, volver a diseñarlas ligeramente, para que admitan Azure App Service.</li></ul> |<ul><li>Curva de aprendizaje de los conocimientos de Docker</li><li>Algunos cambios en el código y la configuración de la aplicación</li></ul>|
|Requisitos |Máquina virtual Windows Server con los mismos requisitos que la aplicación en el entorno local | Requisitos de Azure App Service especificados en [Comprobaciones de disponibilidad](https://github.com/Azure/App-Service-Migration-Assistant/wiki/Readiness-Checks). |<ul><li>[Motor de Docker: Enterprise para Windows Server 2019](https://azuremarketplace.microsoft.com/marketplace/apps/cloud-infrastructure-services.docker-windows-2019)<br />o</li><li>[Azure Container Service (AKS)](https://azure.microsoft.com/services/container-service/) (el orquestador de Kubernetes)<br />o<li>Orquestador de [Azure Service Fabric](https://azure.microsoft.com/services/service-fabric/)</li></ul> |
|Cómo migrar |Consulte [Migración a máquinas virtuales de Azure](vm.md) | Consulte [Migración a Azure App Service](app-service.md) | Siga las consideraciones, los escenarios y los tutoriales que se explican en el libro electrónico [Modernización de las aplicaciones .NET existentes con Azure y Windows Containers](https://aka.ms/liftandshiftwithcontainersebook) |

En el diagrama de flujo siguiente se muestra un árbol de decisión al planear una migración a Azure para las aplicaciones existentes de .NET Framework. Si es posible, pruebe primero la opción A, pero la opción B es más fácil de realizar.

![Diagrama que muestra el árbol de decisión de hospedaje](../media/migration/choose/decision-tree.png)

## <a name="database-choices"></a>Opciones de base de datos

Hay varias opciones para migrar las bases de datos relacionales a Azure. Consulte [Migración de su base de datos SQL Server a Azure SQL Database](sql.md) como ayuda para elegir la ruta de migración correcta de la base de datos para la aplicación de .NET existente.

## <a name="networking-and-security-considerations"></a>Consideraciones sobre redes y seguridad

Al implementar aplicaciones en una nube pública como Microsoft Azure, quizás quiera aislar y proteger determinadas redes mediante la [creación de redes perimetrales](/azure/architecture/reference-architectures/dmz/), por ejemplo, una [red perimetral entre Azure y el entorno local](/azure/architecture/reference-architectures/dmz/secure-vnet-hybrid) o una [red perimetral entre Azure e Internet](/azure/architecture/reference-architectures/dmz/secure-vnet-dmz). Las redes perimetrales se pueden implementar con [Azure Virtual Network](/azure/virtual-network/virtual-networks-overview).

Azure Virtual Network permite:

- Crear una infraestructura híbrida bajo su control
- Traer sus propias direcciones IP y servidores DNS
- Proteja sus conexiones con una red VPN IPsec o ExpressRoute
- Obtenga control detallado del tráfico entre las subredes
- Cree topologías de red sofisticadas con aplicaciones virtuales
- Obtener un entorno aislado y de alta seguridad para las aplicaciones

Para empezar a crear su propia red virtual, consulte la [documentación de Azure Virtual Network](/azure/virtual-network/).

## <a name="authentication-and-authorization-considerations-when-migrating-to-azure"></a>Consideraciones sobre autenticación y autorización para migrar a Azure

Una de las principales preocupaciones de una organización a la hora de trasladarse a la nube es la seguridad. La mayoría de las empresas ha invertido una cantidad considerable de tiempo, dinero e ingeniería en diseñar y desarrollar un modelo de seguridad, y es importante que puedan aprovechar las inversiones existentes, como los almacenes de identidades y las soluciones de inicio de sesión único.

Muchas aplicaciones B2E empresariales de .NET existentes que se ejecutan en entornos locales usan Active Directory para la autenticación y administración de identidades. Azure AD Connect permite integrar sus directorios locales con Azure Active Directory. Para comenzar, consulte [Integración de los directorios locales con Azure Active Directory](/azure/active-directory/connect/active-directory-aadconnect).

Vea los [requisitos de identidad para su solución de identidad híbrida](/azure/active-directory/active-directory-hybrid-identity-design-considerations-business-needs) para poder continuar el planeamiento en relación con Azure Active Directory.

Otras opciones de protocolo de autenticación son [OAuth](https://en.wikipedia.org/wiki/OAuth) y [OpenID](https://en.wikipedia.org/wiki/OpenID), que son comunes en las aplicaciones orientadas al consumidor. Cuando se utilizan bases de datos de identidad autónomas, como una base de datos SQL de ASP.NET Identity encapsulada por IdentityServer4 que usa OAuth, normalmente no se necesita conectividad a bases de datos o directorios locales.

## <a name="next-steps"></a>Pasos siguientes

> [!div class="nextstepaction"]
> [Migración de una aplicación web ASP.NET a Azure App Service](app-service.md)
