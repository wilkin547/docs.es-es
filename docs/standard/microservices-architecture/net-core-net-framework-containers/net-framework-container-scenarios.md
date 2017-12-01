---
title: "Cuándo se debe elegir .NET Framework para contenedores de Docker"
description: "Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Cuándo se debe elegir .NET Framework para contenedores de Docker"
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 1bf1f055f040e7f3dc575b7a04140ebf0c599f98
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="when-to-choose-net-framework-for-docker-containers"></a>Cuándo se debe elegir .NET Framework para contenedores de Docker

Mientras que .NET Core ofrece ventajas significativas para las aplicaciones nuevas y patrones de aplicación, .NET Framework continuará siendo una buena elección para muchos escenarios existentes.

## <a name="migrating-existing-applications-directly-to-a-windows-server-container"></a>Migrar aplicaciones existentes directamente a un contenedor de Windows Server

Puede utilizar los contenedores de Docker simplemente para simplificar la implementación, incluso si no va a crear microservicios. Por ejemplo, es posible que desee mejorar el flujo de trabajo de DevOps con Docker, contenedores, puede proporcionar entornos de prueba aislada mejor y también puede eliminar los problemas de implementación causados por las dependencias que faltan cuando se mueve a un entorno de producción. En estos casos, incluso si está implementando una aplicación monolítica, tiene sentido usar contenedores de Windows y Docker para las aplicaciones de .NET Framework actuales.

En la mayoría de los casos para este escenario, no necesitará migrar las aplicaciones existentes a .NET Core; Puede utilizar los contenedores de Docker que incluyen .NET Framework tradicionales. Sin embargo, un enfoque recomendado es usar .NET Core como extender una aplicación existente, como escribir un nuevo servicio en ASP.NET Core.

## <a name="using-third-party-net-libraries-or-nuget-packages-not-available-for-net-core"></a>Uso de las bibliotecas .NET de terceros o paquetes de NuGet no está disponible para .NET Core

Bibliotecas de otros fabricantes están adoptando rápidamente la [.NET estándar](https://docs.microsoft.com/dotnet/standard/net-standard), lo que permite el uso compartido entre todos los tipos. NET, incluido .NET Core de código. Con la biblioteca de estándar de .NET 2.0 y más allá de la superficie de API compatibilidad a través de diferentes marcos de trabajo ha aumentado significativamente mayor y en .NET Core 2.0 aplicaciones pueden hacer referencia directamente a las bibliotecas de .NET Framework existentes (vea [compatibilidad corrección de compatibilidad](https://github.com/dotnet/standard/blob/master/docs/faq.md#how-does-net-standard-versioning-work)).

Sin embargo, incluso con ese avance excepcional desde estándar de .NET 2.0 y .NET Core 2.0, puede haber casos en que ciertos paquetes de NuGet necesitan Windows para ejecutar y puede que no admitan .NET Core. Si los paquetes son críticos para la aplicación, a continuación, debe utilizar .NET Framework en los contenedores de Windows.

## <a name="usingnet-technologies-not-available-for-net-core"></a>Tecnologías de Using.NET no está disponibles para .NET Core 

Algunas tecnologías de .NET Framework no están disponibles en la versión actual de .NET Core (versión 2.0 cuando se redactó este documento). Algunas de ellas estará disponibles en las versiones posteriores de .NET Core (.NET Core 2.x), pero otros no se aplican a la nueva aplicación patrones de destino de .NET Core y podrían no estar disponible.

La siguiente lista muestra la mayoría de las tecnologías que no están disponibles en .NET Core 2.0:

-   Formularios Web Forms ASP.NET. Esta tecnología sólo está disponible en .NET Framework. Actualmente no está previsto migrar ASP.NET Web Forms a .NET Core.

-   Servicios de WCF. Incluso cuando una [biblioteca de cliente de WCF](https://github.com/dotnet/wcf) está disponible para consumir los servicios WCF de .NET Core. a partir de mediados de 2017, la implementación del servidor WCF sólo está disponible en .NET Framework. Este escenario podría considerarse para futuras versiones de .NET Core.

-   Servicios relacionados con el flujo de trabajo. Windows Workflow Foundation (WF), servicios de flujo de trabajo (WCF y WF en un único servicio) y WCF Data Services (anteriormente conocido como ADO.NET Data Services) solo están disponibles en .NET Framework. Actualmente no existen planes para ponerlos a .NET Core.

Además de las tecnologías que se muestran en el oficial [guía básica de .NET Core](https://github.com/aspnet/Home/wiki/Roadmap), otras características se pueden pasar a .NET Core. Para obtener una lista completa, examine los elementos etiquetados como [puerto-a-core](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aport-to-core) en el sitio de CoreFX GitHub. Tenga en cuenta que esta lista no representa un compromiso de Microsoft para lograr dichos componentes .NET Core, los elementos simplemente capturar las solicitudes de la Comunidad. Si le interesa cualquiera de los componentes enumerados anteriormente, considere la posibilidad de participar en las discusiones en GitHub para que se pueda oír la voz. Y si piensa que falta algo, [registre un nuevo problema en el repositorio de CoreFX](https://github.com/dotnet/corefx/issues/new).

## <a name="using-a-platform-or-api-that-does-not-support-net-core"></a>Uso de una plataforma o las API no compatibles con .NET Core

Algunas plataformas de terceros o Microsoft son compatibles con .NET Core. Por ejemplo, algunos servicios de Azure proporcionan un SDK que aún no está disponible para su uso en .NET Core. Esto es temporal, porque todos los servicios de Azure va a usar .NET Core. Por ejemplo, el [DocumentDB de Azure SDK para .NET Core](https://www.nuget.org/packages/Microsoft.Azure.DocumentDB.Core/1.2.1) se publicó como una vista previa de 16 de noviembre de 2016, pero ahora está disponible con carácter general (GA) como una versión estable.

Mientras tanto, si cualquier plataforma o servicio en Azure todavía no es compatible con .NET Core con la API de cliente, puede usar la API de REST equivalente del servicio de Azure o el SDK del cliente en .NET Framework.

### <a name="additional-resources"></a>Recursos adicionales

-   **Guía de .NET core**
    [*https://docs.microsoft.com/dotnet/core/index*](https://docs.microsoft.com/dotnet/core/index)

-   **Migrar desde .NET Framework a .NET Core**
    [*https://docs.microsoft.com/dotnet/core/porting/index*](https://docs.microsoft.com/dotnet/core/porting/index)

-   **.NET framework en la Guía de Docker**
    [*https://docs.microsoft.com/dotnet/framework/docker/*](https://docs.microsoft.com/dotnet/framework/docker/)

-   **Información general de componentes de .NET**
    [*https://docs.microsoft.com/dotnet/standard/components*](https://docs.microsoft.com/dotnet/standard/components)




>[!div class="step-by-step"]
[Anterior] (net-core-contenedor-scenarios.md) [siguiente] (contenedor framework-elección factors.md)
