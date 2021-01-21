---
title: Cuándo elegir .NET Framework para contenedores de Docker
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Cuándo elegir .NET Framework para contenedores de Docker
ms.date: 01/13/2021
ms.openlocfilehash: 476f891a70a220172f84d8168c8492416b8e56bd
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2021
ms.locfileid: "98188120"
---
# <a name="when-to-choose-net-framework-for-docker-containers"></a>Cuándo elegir .NET Framework para contenedores de Docker

Mientras que .NET 5 ofrece ventajas significativas para las aplicaciones nuevas y los patrones de aplicación, .NET Framework continuará siendo una buena elección para muchos escenarios existentes.

## <a name="migrating-existing-applications-directly-to-a-windows-server-container"></a>Migrar aplicaciones existentes directamente a un contenedor de Windows Server

Puede usar los contenedores de Docker simplemente para simplificar la implementación, incluso si no va a crear microservicios. Por ejemplo, es posible que quiera mejorar el flujo de trabajo de DevOps con Docker; los contenedores pueden proporcionarle entornos de prueba mejor aislados y también pueden eliminar los problemas de implementación causados por las dependencias que faltan al moverse a un entorno de producción. En estos casos, incluso si está implementando una aplicación monolítica, tiene sentido usar contenedores de Windows y Docker para las aplicaciones de .NET Framework actuales.

En la mayoría de los casos en este escenario, no deberá migrar las aplicaciones existentes a .NET 5; puede usar los contenedores de Docker que incluyen la versión tradicional de .NET Framework. Sin embargo, un enfoque recomendado es usar .NET 5 al extender una aplicación existente, como escribir un servicio nuevo en ASP.NET Core.

## <a name="using-third-party-net-libraries-or-nuget-packages-not-available-for-net-5"></a>Uso de bibliotecas de .NET de terceros o paquetes NuGet no disponibles para .NET 5

Las bibliotecas de terceros están adoptando rápidamente [.NET Standard](../../../standard/net-standard.md), que permite el uso compartido de código entre todos los tipos .NET, entre ellos .NET 5. Con .NET Standard 2.0 y versiones posteriores, la compatibilidad de la superficie de API entre diferentes marcos ahora es mayor. Y no solo eso, pues las aplicaciones de .NET Core 2.x y versiones más recientes también pueden hacer referencia directamente a las bibliotecas de .NET Framework existentes. (Consulte [.NET Framework 4.6.1 compatible con .NET Standard 2.0](https://github.com/dotnet/standard/blob/master/docs/planning/netstandard-2.0/README.md#net-framework-461-supporting-net-standard-20)).

Además, el [paquete de compatibilidad de Windows](../../../core/porting/windows-compat-pack.md) amplía la superficie de API disponible para .NET Standard 2.0 en Windows. Este paquete permite volver a compilar la mayoría del código existente para .NET Standard 2.x con poca o ninguna modificación para ejecutarse en Windows.

Sin embargo, incluso con ese avance excepcional desde .NET Standard 2.0 y .NET Core 2.1 o versiones posteriores, puede haber casos en los que ciertos paquetes NuGet necesiten Windows para ejecutarse, y puede que no admitan .NET Core o versiones posteriores. Si los paquetes son críticos para la aplicación, entonces debe usar .NET Framework en los contenedores de Windows.

## <a name="using-net-technologies-not-available-for-net-5"></a>Uso de tecnologías de .NET no disponibles para .NET 5

Algunas tecnologías de .NET Framework no están disponibles en la versión actual de .NET (5.0 en el momento de la redacción). Es posible que algunas estén disponibles en versiones posteriores de .NET Core, pero otras no se adaptan a los nuevos patrones de aplicaciones a los que se dirige .NET Core y puede que nunca estén disponibles.

En la lista siguiente se muestra la mayoría de las tecnologías que no están disponibles en .NET 5:

- ASP.NET Web Forms. Esta tecnología solo está disponible en .NET Framework. Actualmente no está previsto migrar ASP.NET Web Forms a .NET o versiones posteriores.

- Servicios WCF. Aunque hay una [biblioteca cliente de WCF](https://github.com/dotnet/wcf) disponible para consumir servicios WCF desde .NET 5, a partir de enero de 2021 la implementación del servidor WCF solo está disponible en .NET Framework.

- Servicios relacionados con el flujo de trabajo. Windows Workflow Foundation (WF), Workflow Services (WCF + WF en un único servicio) y WCF Data Services (antes conocido como ADO.NET Data Services) solo están disponibles en .NET Framework. Actualmente no existen planes para incluirlos en .NET 5.

Además de las tecnologías indicadas en la [guía básica de .NET](https://github.com/dotnet/core/blob/master/roadmap.md) oficial, se pueden portar otras características a la nueva [plataforma unificada de .NET](https://devblogs.microsoft.com/dotnet/introducing-net-5/). Puede interesarle participar en las discusiones en GitHub para que su voz pueda ser escuchada. Asimismo, si piensa que falta algo, registre un nuevo problema en el repositorio de GitHub de [dotnet/runtime](https://github.com/dotnet/runtime/issues/new).

## <a name="using-a-platform-or-api-that-doesnt-support-net-5"></a>Uso de una plataforma o API no compatible con .NET 5

Algunas plataformas de terceros y de Microsoft no son compatibles con .NET 5. Por ejemplo, algunos servicios de Azure proporcionan un SDK que aún no está disponible para su consumo en .NET 5. La mayoría de los SDK de Azure con el tiempo se deberían portar a .NET 5/Standard, pero con algunos puede que no sea posible por varias razones. Puede ver los SDK de Azure disponibles en la página [Versiones más recientes del SDK de Azure](https://azure.github.io/azure-sdk/releases/latest/index.html).

Mientras tanto, si alguna plataforma o servicio en Azure todavía no es compatible con .NET 5 con la API de cliente, puede usar la API REST equivalente del servicio de Azure o el SDK de cliente en .NET Framework.

### <a name="additional-resources"></a>Recursos adicionales

- **Aspectos básicos de .NET** \
  [https://docs.microsoft.com/dotnet/fundamentals](../../../fundamentals/index.yml)

- **Portado de proyectos a .NET 5** \
  [https://channel9.msdn.com/Events/dotnetConf/2020/Porting-Projects-to-NET-5](https://channel9.msdn.com/Events/dotnetConf/2020/Porting-Projects-to-NET-5)

- **Guía de .NET en Docker** \
  [https://docs.microsoft.com/dotnet/core/docker/introduction](../../../core/docker/introduction.md)

- **Introducción a los componentes de .NET** \
  [https://docs.microsoft.com/dotnet/standard/components](../../../standard/components.md)

>[!div class="step-by-step"]
>[Anterior](net-core-container-scenarios.md)
>[Siguiente](container-framework-choice-factors.md)
