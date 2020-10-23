---
title: Selección entre .NET 5 y .NET Framework para aplicaciones de servidor
description: Guía para ayudarle a decidir qué implementación de .NET usar al compilar una aplicación de servidor.
author: cartermp
ms.date: 10/06/2020
ms.openlocfilehash: d9dce0343f9d37e976472b818e896a5b0a661e76
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160456"
---
# <a name="net-5-vs-net-framework-for-server-apps"></a>Diferencias entre .NET 5 y .NET Framework en cuanto a aplicaciones de servidor

Existen dos implementaciones de .NET admitidas para compilar aplicaciones del lado servidor: .NET Framework y .NET 5 (incluido .NET Core). Ambas comparten muchos de los mismos componentes y es posible compartir código entre ellas. En cambio, presentan diferencias fundamentales y su elección depende de lo que quiera realizar. En este artículo se proporcionan orientaciones sobre cuándo usar cada una.

Use .NET 5 para la aplicación de servidor cuando:

- Tenga necesidades multiplataforma.
- Tenga los microservicios como objetivo.
- Vaya a usar contenedores de Docker.
- Necesite sistemas escalables y de alto rendimiento.
- Necesite versiones de .NET en paralelo por aplicación.

Use .NET Framework para su aplicación de servidor cuando:

- La aplicación usa actualmente .NET Framework (la recomendación es extender en lugar de migrar).
- La aplicación usa bibliotecas .NET de terceros o paquetes NuGet que no están disponibles para .NET 5.
- La aplicación usa tecnologías de .NET que no están disponibles para .NET 5.
- La aplicación usa una plataforma que no es compatible con .NET 5.

## <a name="when-to-choose-net-5"></a>Cuándo elegir .NET 5

En las secciones siguientes se explican de manera más detallada las razones indicadas anteriormente para elegir .NET 5.

### <a name="cross-platform-needs"></a>Necesidades multiplataforma

Si la aplicación (web o servicio) se tiene que ejecutar en varias plataformas (Windows, Linux y macOS), use .NET 5.

.NET 5 admite los sistemas operativos mencionados anteriormente como estación de trabajo de desarrollo. Visual Studio proporciona un entorno de desarrollo integrado (IDE) para Windows y macOS. También puede usar Visual Studio Code, que se ejecuta en macOS, Linux y Windows. Visual Studio Code es compatible con .NET 5, incluidos IntelliSense y la depuración. La mayoría de los editores de terceros, como Sublime, Emacs y VI, funcionan con .NET 5. Estos editores de terceros obtienen el editor de IntelliSense mediante [Omnisharp](https://www.omnisharp.net/). También puede evitar el uso de un editor de código y usar directamente la [CLI de .NET Core](../core/tools/index.md), disponibles para todas las plataformas compatibles.

### <a name="microservices-architecture"></a>Arquitectura de microservicios

Una arquitectura de microservicios permite una combinación de tecnologías en un límite de servicio. Esta combinación de tecnología permite un adopción gradual de .NET 5 para los microservicios nuevos que funcionan con otros servicios o microservicios. Por ejemplo, puede combinar microservicios o servicios desarrollados con .NET Framework, Java, Ruby u otras tecnologías monolíticas.

Existen muchas plataformas de infraestructura. [Azure Service Fabric](https://azure.microsoft.com/services/service-fabric/) está diseñada para sistemas de microservicios grandes y complejos. [Azure App Service](https://azure.microsoft.com/services/app-service/) es una buena elección para microservicios sin estado. Los microservicios alternativos basados en Docker encajan en cualquier enfoque de microservicios, como se explica en la sección [Contenedores](#containers). Todas estas plataformas admiten .NET 5, lo que hace que resulten perfectas para hospedar microservicios.

Para obtener más información sobre la arquitectura de microservicios, consulte [.NET Microservices. Architecture for Containerized .NET Applications](../architecture/microservices/index.md) (Microservicios de .NET: Arquitectura para aplicaciones .NET en contenedor).

### <a name="containers"></a>Contenedores

Los contenedores se usan normalmente junto con una arquitectura de microservicios. Los contenedores también se pueden usar para incluir las aplicaciones web o los servicios en contenedores que sigan cualquier patrón de arquitectura. .NET Framework se puede usar en contenedores de Windows, pero la naturaleza modular y ligera de .NET 5 la convierten en una mejor elección para los contenedores. Al crear e implementar un contenedor, el tamaño de su imagen es mucho más pequeño con .NET 5 que con .NET Framework. Como es multiplataforma, puede implementar aplicaciones de servidor en contenedores de Docker de Linux, por ejemplo.

Los contenedores de Docker pueden hospedarse en su propia infraestructura de Linux o Windows, o en un servicio en la nube como [Azure Kubernetes Service](https://azure.microsoft.com/services/kubernetes-service/). Azure Kubernetes Service puede administrar, organizar y escalar aplicaciones basadas en contenedores en la nube.

### <a name="high-performance-and-scalable-systems"></a>Sistemas escalables y de alto rendimiento

Cuando el sistema necesite el mejor rendimiento y escalabilidad posibles, .NET 5 y ASP.NET Core son las mejores opciones. El entorno de ejecución de servidor de alto rendimiento para Windows Server y Linux convierte .NET en un marco web de gran rendimiento en los bancos de pruebas de [TechEmpower](https://www.techempower.com/benchmarks/#hw=ph&test=plaintext).

El rendimiento y la escalabilidad son especialmente importantes para las arquitecturas de microservicios, donde podrían ejecutarse cientos de microservicios. Con ASP.NET Core, los sistemas se ejecutan con un número mucho menor de servidores/máquinas virtuales. Al usar menos servidores/máquinas virtuales, se ahorran costos de infraestructura y hospedaje.

### <a name="side-by-side-net-versions-per-application-level"></a>Versiones de .NET en paralelo por nivel de aplicación

Para instalar aplicaciones con dependencias en otras versiones de .NET, se recomienda .NET 5. .NET 5 admite la instalación en paralelo de otras versiones del tiempo de ejecución de .NET 5 en el mismo equipo. Esta instalación en paralelo permite varios servicios en el mismo servidor, cada uno en una versión propia de .NET 5 (o bien, .NET Core 2.1 o 3.1). También reduce los riesgos y ahorra dinero en las operaciones de TI y las actualizaciones de aplicaciones.

La instalación en paralelo no es posible con .NET Framework. Se trata de un componente de Windows, y solo puede existir una versión en un equipo a la vez. Cada versión de .NET Framework reemplaza la anterior. Si instala una aplicación nueva que tenga como destino una versión posterior de .NET Framework, es posible que se interrumpan las aplicaciones existentes que se ejecutan en la máquina, ya que se ha reemplazado la versión anterior.

## <a name="when-to-choose-net-framework"></a>Cuándo elegir .NET Framework

.NET 5 ofrece ventajas significativas para las aplicaciones nuevas y los patrones de aplicación. Pero .NET Framework sigue siendo la opción natural para muchos escenarios existentes y, por tanto, no se reemplaza por .NET 5 para todas las aplicaciones de servidor.

### <a name="current-net-framework-applications"></a>Aplicaciones actuales de .NET Framework

En la mayoría de los casos, no tendrá que migrar las aplicaciones existentes a .NET 5. En su lugar, un enfoque recomendado consiste en usar .NET 5 al extender una aplicación existente, como al escribir un nuevo servicio web en ASP.NET Core.

### <a name="third-party-libraries-or-nuget-packages-not-available-for-net-5"></a>Bibliotecas de terceros o paquetes NuGet no disponibles para .NET 5

.NET Standard permite compartir código entre todas las implementaciones de .NET, incluido .NET 5. Con .NET Standard 2.0, un modo de compatibilidad permite que los proyectos de .NET Standard y .NET 5 hagan referencia a bibliotecas de .NET Framework. Para obtener más información, vea [Compatibilidad con las bibliotecas de .NET Framework](whats-new/whats-new-in-dotnet-standard.md#support-for-net-framework-libraries).

Tendrá que utilizar .NET Framework solo cuando en las bibliotecas o los paquetes NuGet se usen tecnologías que no estén disponibles en .NET Standard o .NET 5.

### <a name="net-technologies-not-available-for-net-5"></a>Tecnologías de .NET no disponibles para .NET 5

Algunas tecnologías de .NET Framework no están disponibles en .NET 5. En la lista siguiente se muestran las tecnologías más comunes que no se encuentran en .NET 5:

- Aplicaciones de formularios Web Forms ASP.NET: ASP.NET Web Forms solo está disponible en .NET Framework. No se puede usar ASP.NET Core para ASP.NET Web Forms.

- Aplicaciones de ASP.NET Web Pages: ASP.NET Web Pages no se incluye en ASP.NET Core.

- Implementación de servicios WCF. Aunque hay una [biblioteca cliente de WCF](https://github.com/dotnet/wcf) para consumir servicios WCF desde .NET 5, actualmente la implementación del servidor WCF solo está disponible en .NET Framework.

- Servicios relacionados con flujos de trabajo: Windows Workflow Foundation (WF), Workflow Services (WCF y WF en un único servicio) y WCF Data Services (antes conocido como "ADO.NET Data Services") solo están disponibles en .NET Framework.

- Compatibilidad con lenguajes: En la actualidad, Visual Basic y F# se admiten en .NET 5, pero no para todos los tipos de proyecto. Para obtener una lista de plantillas de proyecto compatibles, consulte [Opciones de plantilla para dotnet new](../core/tools/dotnet-new.md#arguments).

Para obtener más información, vea [Tecnologías de .NET Framework no disponibles en .NET 5](../core/porting/net-framework-tech-unavailable.md).

### <a name="platform-doesnt-support-net-5"></a>Plataformas no compatibles con .NET 5

Algunas plataformas de terceros o de Microsoft no son compatibles con .NET 5. Algunos servicios de Azure proporcionan un SDK que todavía no está disponible para su consumo en .NET 5. En esos casos, puede usar la API REST equivalente en lugar del SDK de cliente.

## <a name="see-also"></a>Vea también

- [Elegir entre ASP.NET y ASP.NET Core](/aspnet/core/choose-aspnet-framework)
- [ASP.NET Core con .NET Framework como destino](/aspnet/core/introduction-to-aspnet-core?view=aspnetcore-2.2&preserve-view=true#aspnet-core-targeting-net-framework)
- [Marcos de trabajo de destino](frameworks.md)
- [Introducción a .NET](../core/introduction.md)
- [Portabilidad de .NET Framework a .NET 5](../core/porting/index.md)
- [Introducción a .NET y Docker](../core/docker/introduction.md)
- [Introducción a los componentes de .NET](components.md)
- [Microservicios de .NET: Arquitectura para aplicaciones .NET en contenedor](../architecture/microservices/index.md)
