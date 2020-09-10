---
title: Cuándo elegir .NET Framework para contenedores de Docker
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Cuándo elegir .NET Framework para contenedores de Docker
ms.date: 01/30/2020
ms.openlocfilehash: 116ba02878a60487f1af3c2b2e084307fad29618
ms.sourcegitcommit: b1f4756120deaecb8b554477bb040620f69a4209
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2020
ms.locfileid: "89414427"
---
# <a name="when-to-choose-net-framework-for-docker-containers"></a>Cuándo elegir .NET Framework para contenedores de Docker

Mientras que .NET Core ofrece ventajas significativas para las aplicaciones nuevas y los patrones de aplicación, .NET Framework continuará siendo una buena elección para muchos escenarios existentes.

## <a name="migrating-existing-applications-directly-to-a-windows-server-container"></a>Migrar aplicaciones existentes directamente a un contenedor de Windows Server

Puede usar los contenedores de Docker simplemente para simplificar la implementación, incluso si no va a crear microservicios. Por ejemplo, es posible que quiera mejorar el flujo de trabajo de DevOps con Docker; los contenedores pueden proporcionarle entornos de prueba mejor aislados y también pueden eliminar los problemas de implementación causados por las dependencias que faltan al moverse a un entorno de producción. En estos casos, incluso si está implementando una aplicación monolítica, tiene sentido usar contenedores de Windows y Docker para las aplicaciones de .NET Framework actuales.

En la mayoría de los casos para este escenario, no deberá migrar las aplicaciones existentes a .NET Core; puede usar los contenedores de Docker que incluyen el .NET Framework tradicional. Sin embargo, un enfoque recomendado es usar .NET Core al extender una aplicación existente, como escribir un servicio nuevo en ASP.NET Core.

## <a name="using-third-party-net-libraries-or-nuget-packages-not-available-for-net-core"></a>Uso de bibliotecas .NET de terceros o paquetes de NuGet que no están disponibles para .NET Core

Las bibliotecas de terceros están adoptando rápidamente [.NET Standard](../../../standard/net-standard.md), que permite el uso compartido de código entre todos los tipos .NET, entre ellos .NET Core. Con .NET Standard 2.0 y versiones posteriores, la compatibilidad de la superficie de API entre diferentes marcos ahora es mayor. Y no solo eso, pues las aplicaciones de .NET Core 2.x y versiones más recientes también pueden hacer referencia directamente a las bibliotecas de .NET Framework existentes. (Consulte [.NET Framework 4.6.1 compatible con .NET Standard 2.0](https://github.com/dotnet/standard/blob/master/docs/planning/netstandard-2.0/README.md#net-framework-461-supporting-net-standard-20)).

Además, el [paquete de compatibilidad de Windows](../../../core/porting/windows-compat-pack.md) amplía la superficie de API disponible para .NET Standard 2.0 en Windows. Este paquete permite volver a compilar la mayoría del código existente para .NET Standard 2.x con poca o ninguna modificación para ejecutarse en Windows.

Sin embargo, incluso con ese avance excepcional desde .NET Standard 2.0 y .NET Core 2.1, puede haber casos en que ciertos paquetes de NuGet necesiten Windows para ejecutar y puede que no admitan .NET Core. Si los paquetes son críticos para la aplicación, entonces debe usar .NET Framework en los contenedores de Windows.

## <a name="using-net-technologies-not-available-for-net-core"></a>Uso de tecnologías de .NET que no están disponibles para .NET Core

Algunas tecnologías de .NET Framework no están disponibles en la versión actual de .NET Core (3.1 en el momento de la redacción). Es posible que algunas estén disponibles en versiones posteriores de .NET Core, pero otras no se adaptan a los nuevos patrones de aplicaciones a los que se dirige .NET Core y puede que nunca estén disponibles.

En la lista siguiente se muestra la mayoría de las tecnologías que no están disponibles en .NET Core 3.1:

- ASP.NET Web Forms. Esta tecnología solo está disponible en .NET Framework. Actualmente no está previsto migrar ASP.NET Web Forms a .NET Core.

- Servicios WCF. Aunque hay una [biblioteca cliente de WCF](https://github.com/dotnet/wcf) disponible para consumir servicios WCF desde .NET Core, a partir de febrero de 2020 la implementación del servidor WCF solo está disponible en .NET Framework. Este escenario podría considerarse para futuras versiones de .NET Core; incluso se contempla la inclusión de algunas API en el [paquete de compatibilidad de Windows](../../../core/porting/windows-compat-pack.md).

- Servicios relacionados con el flujo de trabajo. Windows Workflow Foundation (WF), Workflow Services (WCF + WF en un único servicio) y WCF Data Services (antes conocido como ADO.NET Data Services) solo están disponibles en .NET Framework. Actualmente no existen planes de ponerlos en .NET Core.

Además de las tecnologías indicadas en la [guía básica de .NET Core](https://github.com/dotnet/core/blob/master/roadmap.md) oficial, se pueden portar otras características a .NET Core o la nueva [plataforma unificada .NET](https://devblogs.microsoft.com/dotnet/introducing-net-5/). Puede interesarle participar en las discusiones en GitHub para que su voz pueda ser escuchada. Asimismo, si piensa que falta algo, registre un nuevo problema en el repositorio de GitHub de [dotnet/runtime](https://github.com/dotnet/runtime/issues/new).

## <a name="using-a-platform-or-api-that-doesnt-support-net-core"></a>Uso de una plataforma o API no compatible con .NET Core

Algunas plataformas de terceros y de Microsoft no son compatibles con .NET Core. Por ejemplo, algunos servicios de Azure proporcionan un SDK que aún no está disponible para su consumo en .NET Core. La mayoría de los SDK de Azure con el tiempo se deberían portar a .NET Core/Standard, pero con algunos puede que no sea posible por varias razones. Puede ver los SDK de Azure disponibles en la página [Versiones más recientes del SDK de Azure](https://azure.github.io/azure-sdk/releases/latest/index.html).

Mientras tanto, si cualquier plataforma o servicio en Azure todavía no es compatible con .NET Core con la API de cliente, puede usar la API de REST equivalente del servicio de Azure o el SDK de cliente en .NET Framework.

### <a name="additional-resources"></a>Recursos adicionales

- **Aspectos básicos de .NET** \
  [https://docs.microsoft.com/dotnet/fundamentals](../../../fundamentals/index.yml)

- **Portabilidad a .NET Core desde .NET Framework** \
  [https://docs.microsoft.com/dotnet/core/porting/index](../../../core/porting/index.md)

- **.NET Core en la guía de Docker** \
  [https://docs.microsoft.com/dotnet/core/docker/introduction](../../../core/docker/introduction.md)

- **Introducción a los componentes de .NET** \
  [https://docs.microsoft.com/dotnet/standard/components](../../../standard/components.md)

>[!div class="step-by-step"]
>[Anterior](net-core-container-scenarios.md)
>[Siguiente](container-framework-choice-factors.md)
