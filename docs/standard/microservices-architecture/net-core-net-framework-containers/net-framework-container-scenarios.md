---
title: Cuándo elegir .NET Framework para contenedores de Docker
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Cuándo elegir .NET Framework para contenedores de Docker
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 06/07/2018
ms.openlocfilehash: 06b67f702b38202f598745826fa48f1ca97b7282
ms.sourcegitcommit: 6c480773ae896f45af4671fb3e26611a50e4dd81
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2018
ms.locfileid: "35251040"
---
# <a name="when-to-choose-net-framework-for-docker-containers"></a>Cuándo elegir .NET Framework para contenedores de Docker

Mientras que .NET Core ofrece ventajas significativas para las aplicaciones nuevas y los patrones de aplicación, .NET Framework continuará siendo una buena elección para muchos escenarios existentes.

## <a name="migrating-existing-applications-directly-to-a-windows-server-container"></a>Migrar aplicaciones existentes directamente a un contenedor de Windows Server

Puede usar los contenedores de Docker simplemente para simplificar la implementación, incluso si no va a crear microservicios. Por ejemplo, es posible que quiera mejorar el flujo de trabajo de DevOps con Docker; los contenedores pueden proporcionarle entornos de prueba mejor aislados y también pueden eliminar los problemas de implementación causados por las dependencias que faltan al moverse a un entorno de producción. En estos casos, incluso si está implementando una aplicación monolítica, tiene sentido usar contenedores de Windows y Docker para las aplicaciones de .NET Framework actuales.

En la mayoría de los casos para este escenario, no deberá migrar las aplicaciones existentes a .NET Core; puede usar los contenedores de Docker que incluyen el .NET Framework tradicional. Sin embargo, un enfoque recomendado es usar .NET Core al extender una aplicación existente, como escribir un servicio nuevo en ASP.NET Core.

## <a name="using-third-party-net-libraries-or-nuget-packages-not-available-for-net-core"></a>Uso de bibliotecas .NET de terceros o paquetes de NuGet que no están disponibles para .NET Core

Las bibliotecas de terceros están adoptando rápidamente [.NET Standard](../../net-standard.md), que permite el uso compartido de código entre todos los tipos .NET, entre ellos .NET Core. Con la biblioteca .NET Standard 2.0 y versiones posteriores, la compatibilidad de la superficie de la API a través de diferentes marcos ha aumentado significativamente y en aplicaciones .NET Core 2.x también puede hacer referencia directamente a las bibliotecas de .NET Framework existentes (vea [corrección de compatibilidad](https://github.com/dotnet/standard/blob/master/docs/faq.md#how-does-net-standard-versioning-work)).

Sin embargo, incluso con ese avance excepcional desde .NET Standard 2.0 y .NET Core 2.0, puede haber casos en que ciertos paquetes de NuGet necesiten Windows para ejecutar y puede que no admitan .NET Core. Si los paquetes son críticos para la aplicación, entonces debe usar .NET Framework en los contenedores de Windows.

## <a name="using-net-technologies-not-available-for-net-core"></a>Uso de tecnologías de .NET que no están disponibles para .NET Core 

Algunas tecnologías de .NET Framework no están disponibles en la versión actual de .NET Core (versión 2.1 cuando se redactó este documento). Algunas estarán disponibles en versiones posteriores de .NET Core (.NET Core 2.x), pero otras no se aplican a los nuevos patrones de aplicaciones a los que se dirige .NET Core y puede que nunca estén disponibles.

En la lista siguiente se muestra la mayoría de las tecnologías que no están disponibles en .NET Core 2.1:

-   ASP.NET Web Forms. Esta tecnología solo está disponible en .NET Framework. Actualmente no está previsto migrar ASP.NET Web Forms a .NET Core.

-   Servicios WCF. Incluso cuando una [biblioteca de cliente WCF](https://github.com/dotnet/wcf) está disponible para consumir los servicios WCF de .NET Core. a partir de mediados de 2017, la implementación del servidor WCF solo está disponible en .NET Framework. Este escenario podría considerarse para futuras versiones de .NET Core.

-   Servicios relacionados con el flujo de trabajo. Windows Workflow Foundation (WF), Workflow Services (WCF + WF en un único servicio) y WCF Data Services (antes conocido como ADO.NET Data Services) solo están disponibles en .NET Framework. Actualmente no existen planes de ponerlos en .NET Core.

Además de las tecnologías indicadas en la [guía básica de .NET Core](https://github.com/aspnet/Home/wiki/Roadmap) oficial, se pueden pasar otras características a .NET Core. Para obtener una lista completa, examine los elementos etiquetados como [port-to-core](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aport-to-core) en el sitio de CoreFX GitHub. Tenga en cuenta que esta lista no representa ningún compromiso de Microsoft para llevar dichos componentes a .NET Core; los elementos simplemente capturan las solicitudes de la comunidad. Si le interesa cualquiera de los componentes mencionados anteriormente, puede participar en las discusiones en GitHub para que su voz pueda ser escuchada. Y si piensa que falta algo, [registre un nuevo problema en el repositorio de CoreFX](https://github.com/dotnet/corefx/issues/new).

## <a name="using-a-platform-or-api-that-does-not-support-net-core"></a>Uso de una plataforma o API no compatible con .NET Core

Algunas plataformas de Microsoft o de terceros no son compatibles con .NET Core. Por ejemplo, algunos servicios de Azure proporcionan un SDK que aún no está disponible para su consumo en .NET Core. Esto es temporal, porque todos los servicios acabarán usando .NET Core. Por ejemplo, el [Azure DocumentDB SDK para .NET Core](https://www.nuget.org/packages/Microsoft.Azure.DocumentDB.Core/1.2.1) se publicó como una versión preliminar el 16 de noviembre de 2016, pero ahora está disponible con carácter general (GA) como una versión estable.

Mientras tanto, si cualquier plataforma o servicio en Azure todavía no es compatible con .NET Core con la API de cliente, puede usar la API de REST equivalente del servicio de Azure o el SDK de cliente en .NET Framework.

### <a name="additional-resources"></a>Recursos adicionales

-   **.NET Core Guide (Guía de .NET Core)**
    [*https://docs.microsoft.com/dotnet/core/index*](../../../core/index.md)

-   **Porting from .NET Framework to .NET Core (Portabilidad a .NET Core desde .NET Framework)**
    [*https://docs.microsoft.com/dotnet/core/porting/index*](../../../core/porting/index.md)

-   **.NET Framework on Docker Guide (Guía de .NET Framework en Docker)**
    [*https://docs.microsoft.com/dotnet/framework/docker/*](../../../framework/docker/index.md)

-   **.NET Components Overview (Introducción a los componentes de .NET)**
    [*https://docs.microsoft.com/dotnet/standard/components*](../../components.md)




>[!div class="step-by-step"]
[Previous] (net-core-container-scenarios.md) [Next] (container-framework-choice-factors.md)
