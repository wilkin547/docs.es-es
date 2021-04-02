---
title: Estrategias de implementación
description: ¿Qué estrategias de implementación pueden usar los equipos al migrar de ASP.NET a ASP.NET Core? ¿Una migración incremental permite la implementación en paralelo de .NET Framework y aplicaciones de .NET Core, lo que proporciona una experiencia de usuario final sin problemas?
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: 4c69f049611e4995cdb1905c89afe6973994f20d
ms.sourcegitcommit: b5d2290673e1c91260c9205202dd8b95fbab1a0b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "106122942"
---
# <a name="deployment-strategies"></a>Estrategias de implementación

Una consideración a la hora de planear la migración de la aplicación grande de ASP.NET a ASP.NET Core es cómo se implementará la nueva aplicación. Con ASP.NET, las opciones de implementación se limitaban a IIS en Windows. Con ASP.NET Core, hay disponible una matriz mucho más amplia de opciones de implementación.

## <a name="cross-platform-options"></a>Opciones multiplataforma

Dado que .NET Core se ejecuta en Linux, encontrará algunas opciones de hospedaje disponibles que no se han tenido en cuenta previamente. El hospedaje basado en Linux puede ser preferible por los siguientes motivos:

* Su organización tiene una infraestructura o experiencia.
* Los proveedores de hospedaje ofrecen características atractivas o precios para el hospedaje basado en Linux.

.NET Core abre la puerta a estas opciones.

## <a name="cloud-native-development"></a>Desarrollo nativo en la nube

Hoy en día, la mayoría de las organizaciones usan plataformas de nube para al menos algunas de sus funcionalidades de software. Con una migración de aplicaciones a .NET Core, es un buen momento para considerar si la aplicación debe escribirse intencionadamente con hospedaje en la nube en mente. Estas aplicaciones *nativas en la nube* mejoran la capacidad de aplicar funcionalidades en la nube como servidores sin servidor y microservicios, y pueden ser menos preocupables con los detalles de bajo nivel sobre cómo y dónde se pueden implementar.

Obtenga más información sobre el desarrollo de aplicaciones nativas en la nube en este libro electrónico gratuito, que [diseña aplicaciones .net nativas en la nube para Azure](../cloud-native/index.md).

## <a name="leverage-containers"></a>Aprovechar los contenedores

A menudo, las aplicaciones modernas aprovechan los contenedores como un medio para reducir la variación entre los entornos de hospedaje. Mediante la implementación de una aplicación en un contenedor determinado, la aplicación hospedada en contenedor se ejecutará de la misma manera tanto si se ejecuta en el equipo portátil de un desarrollador como en el entorno de producción. Como parte de una migración a .NET Core, puede tener sentido considerar si la aplicación se beneficiaría de la implementación a través de un contenedor, como un monolito completo o dividido en varias aplicaciones en contenedores más pequeñas.

## <a name="side-by-side-deployment-options"></a>Opciones de implementación en paralelo

La migración de aplicaciones de gran .NET Framework a .NET Core suele requerir un esfuerzo sustancial. La mayoría de las organizaciones querrán poder interrumpir este esfuerzo de algún modo, de modo que las partes de la aplicación se puedan migrar e implementar en producción antes de que se complete toda la migración. La ejecución de la aplicación ASP.NET original y de las subaplicacións de ASP.NET Core recién migradas en paralelo es un objetivo que se suele mencionar. Esto se puede lograr a través de una serie de mecanismos, incluido el uso del enrutamiento de IIS, que se describe en el [capítulo 5](deployment-scenarios.md). Otras opciones incluyen el uso de puertas de enlace de aplicaciones o patrones de diseño en la nube, como [back-ends para los front-ends](/azure/architecture/patterns/backends-for-frontends) , para administrar conjuntos de API Web de ASP.net y puntos de conexión de api de ASP.net Core.

## <a name="iis-on-windows"></a>IIS en Windows

Puede seguir hospedando sus aplicaciones en IIS que se ejecutan en Windows. Se trata de una opción muy buena para los clientes que quieren aprovechar las características ASP.NET Core sin cambiar su modelo de implementación actual. Al pasar a ASP.NET Core proporciona más opciones en cuanto a cómo y dónde implementar las aplicaciones, no es necesario cambiar desde el estado quo del uso de la combinación comprobada de IIS en Windows.

## <a name="other-options-on-windows"></a>Otras opciones de Windows

Puede hospedar aplicaciones en paralelo en Windows con cualquier combinación de Kestrel, HTTP.sys e hosts de IIS, además de los contenedores de Docker, si es necesario. Si su aplicación requiere una combinación de servicios de Windows y Linux, el hospedaje en un servidor de Windows con [WSL](/windows/wsl/about) y/o contenedores de Docker de Linux proporciona una solución de un solo servidor para hospedar todas las partes de la aplicación.

## <a name="references"></a>Referencias

- [Hospedar e implementar ASP.NET Core](/aspnet/core/host-and-deploy/)
- [Hospedaje de ASP.NET Core en Windows con IIS](/aspnet/core/host-and-deploy/iis/)
- [Solución de problemas de ASP.NET Core en Azure App Service e IIS](/aspnet/core/test/troubleshoot-azure-iis)

>[!div class="step-by-step"]
>[Anterior](migrate-web-forms.md)
>[Siguiente](additional-migration-resources.md)
