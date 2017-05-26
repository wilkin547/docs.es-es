---
title: "Selección entre .NET Core y .NET Framework para aplicaciones de servidor"
description: "Una guía sobre el tipo de .NET que debe tener en cuenta al crear una aplicación de servidor en .NET."
keywords: .NET, .NET Core, .NET Framework
author: cartermp
ms.author: mairaw
ms.date: 11/16/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 155553e4-89a2-418d-be88-4e75f6c3cc69
ms.translationtype: Human Translation
ms.sourcegitcommit: 405bac1faa446687a4acdcf2d5536ee31f31f246
ms.openlocfilehash: 7151c87d373afce88c83239499ba33980383ab98
ms.contentlocale: es-es
ms.lasthandoff: 04/18/2017

---

# <a name="choosing-between-net-core-and-net-framework-for-server-apps"></a>Selección entre .NET Core y .NET Framework para aplicaciones de servidor

Existen dos opciones admitidas de tiempo de ejecución al crear aplicaciones de servidor con .NET: .NET Framework y .NET Core. Ambas comparten muchos de los mismos componentes de la plataforma .NET y es posible compartir código entre ellas. Sin embargo, presentan diferencias fundamentales y su elección dependerá de lo que desee realizar.  En este artículo se proporcionan orientaciones sobre cuándo usar cada una.

Utilice .NET Core para la aplicación de servidor en los siguientes casos:

* Tenga necesidades multiplataforma.
* Tenga como objetivo los microservicios.
* Vaya a usar contenedores de Docker.
* Necesite sistemas escalables y de alto rendimiento.
* Necesite versiones de .NET en paralelo por aplicación.

Utilice .NET Framework para su aplicación de servidor en los siguientes casos:

* La aplicación utiliza actualmente .NET Framework (la recomendación es extender en lugar de migrar).
* Necesita usar bibliotecas .NET de terceros o paquetes de NuGet que no están disponibles para .NET Core.
* Deba usar tecnologías de .NET que no están disponibles para .NET Core.
* Deba usar una plataforma que no es compatible con .NET Core.

## <a name="when-to-choose-net-core"></a>Cuándo elegir .NET Core

A continuación se explican de manera más detallada las razones indicadas anteriormente para elegir .NET Core.

### <a name="cross-platform-needs"></a>Necesidades multiplataforma

Claramente, si su objetivo es tener una aplicación (web o servicio) que pueda funcionar en todas las plataformas (Windows, Linux y macOS), la mejor opción es usar .NET Core.

.NET Core también admite los sistemas operativos mencionados anteriormente como estación de trabajo de desarrollo. Visual Studio proporciona un entorno de desarrollo integrado (IDE) para Windows.  También puede usar Visual Studio Code en macOS, Linux y Windows, ya que es completamente compatible con .NET Core, lo que incluye IntelliSense y la depuración. Asimismo, puede desarrollar para .NET Core con la mayoría de editores de terceros, como Sublime, Emacs, VI y puede obtener el editor IntelliSense mediante el proyecto [Omnisharp](http://www.omnisharp.net/) de código abierto. También puede evitar el uso de un editor de código y utilizar directamente las herramientas de línea de comandos de .NET Core, disponibles para todas las plataformas compatibles.

### <a name="microservices-architecture"></a>Arquitectura de microservicios

.NET Core es la mejor candidata si piensa adoptar un sistema orientado a microservicios compuesto por varios microservicios con estado o sin él, escalables dinámicamente e independientes. .NET Core es ligera y su superficie de API se puede minimizar al ámbito del microservicio. Una arquitectura de microservicios también permite mezclar tecnologías a través de un límite de servicio, lo que hace posible la adopción gradual de .NET para nuevos microservicios que residen con otros miroservicios o servicios desarrollados con .NET Framework, Java, Ruby u otras tecnologías monolíticas.

Son muchas las plataformas de infraestructura que podría utilizar. Para sistemas de microservicios grandes y complejos, puede utilizar [Azure Service Fabric](https://azure.microsoft.com/services/service-fabric/). Para microservicios sin estado, también puede utilizar otros productos como [Azure App Service](https://azure.microsoft.com/services/app-service/). Microservicios alternativos basados en Docker también encajan en cualquier enfoque de microservicios, como se explica a continuación. Todas estas plataformas admiten .NET Core, lo que hace que resulten perfectas para hospedar sus microservicios.

### <a name="containers"></a>Contenedores

Los contenedores se usan normalmente en combinación con una arquitectura de microservicios, aunque también se pueden usar para contener aplicaciones o servicio web que siguen cualquier modelo de arquitectura. Aunque puede usar .NET Framework con contenedores de Windows, la modularidad y ligereza de .NET Core la convierten en perfecta para los contenedores. Al crear e implementar un contenedor, el tamaño de su imagen es bastante más pequeño con .NET Core que con .NET Framework. Como es multiplataforma, puede implementar aplicaciones de servidor en contenedores de Linux Docker, por ejemplo.

Luego puede hospedar los contenedores de Docker en su propia infraestructura de Linux o Windows, o usar un servicio en la nube como [Azure Container Service](https://azure.microsoft.com/services/container-service/) que puede administrar, organizar y escalar la aplicación basada en contenedor en la nube.

### <a name="a-need-for-high-performance-and-scalable-systems"></a>Necesidad de sistemas escalables y de alto rendimiento

Cuando el sistema necesite el mejor rendimiento y escalabilidad posible, .NET Core y ASP.NET Core son sus mejores opciones. ASP.NET Core supera a ASP.NET en un factor de 10 y lidera otras tecnologías conocidas del sector para microservicios, como servlets de Java, Go y Node.js.

Esto es especialmente importante para las arquitecturas de microservicios, donde podría tener cientos de microservicios en funcionamiento. Con ASP.NET Core podrá ejecutar el sistema con un número mucho menor de servidores y máquinas virtuales, con lo que a la larga ahorrará costos en infraestructura y hospedaje.

### <a name="a-need-for-side-by-side-of-net-versions-per-application-level"></a>Necesidad de versiones de .NET en paralelo por nivel de aplicación

Si quiere poder instalar aplicaciones con dependencias en diferentes versiones de marcos en .NET, deberá usar .NET Core, que proporciona un paralelismo del 100 %. La instalación sencilla en paralelo de diferentes versiones de .NET Core en la misma máquina le permite tener varios servicios en el mismo servidor, cada uno de ellos con su propia versión de .NET Core. De esta manera, se eliminan riesgos y se ahorra dinero en actualizaciones de aplicaciones y operaciones de TI.

## <a name="when-to-choose-net-framework"></a>Cuándo elegir .NET Framework

Aunque .NET Core ofrece importantes ventajas para nuevas aplicaciones y patrones de aplicaciones, .NET Framework seguirá siendo la elección natural para muchos escenarios existentes y como tal, no se sustituirá por .NET Core en todas las aplicaciones de servidor.

### <a name="current-net-framework-applications"></a>Aplicaciones actuales de .NET Framework

En la mayoría de los casos, no necesitará migrar sus aplicaciones existentes a .NET Core. En su lugar, un enfoque recomendado es usar .NET Core al extender una aplicación existente, como escribir un nuevo servicio web en ASP.NET Core.

### <a name="a-need-to-use-third-party-net-libraries-or-nuget-packages-not-available-for-net-core"></a>Necesidad de usar bibliotecas .NET de terceros o paquetes de NuGet que no están disponibles para .NET Core

Las bibliotecas están adoptando rápidamente .NET Standard, que permite el uso compartido de código entre todos los tipos .NET, entre ellos .NET Core. Con .NET Standard 2.0 esto será incluso más fácil, dado que la superficie de la API de .NET Core se hará bastante más grande y las aplicaciones de .NET Core podrán usar directamente las bibliotecas de .NET Framework existentes. Sin embargo, esta transición no será inmediata, por lo que recomendamos comprobar las bibliotecas específicas que requiere su aplicación antes de tomar una decisión en una u otra dirección.

### <a name="a-need-to-use-net-technologies-not-available-for-net-core"></a>Necesidad de usar tecnologías de .NET que no están disponibles para .NET Core

Algunas tecnologías de .NET Framework no están disponibles en .NET Core. Unas estarán disponibles en versiones posteriores de .NET Core, pero otras no se aplican a los nuevos patrones de aplicaciones a los que se dirige .NET Core y puede que nunca estén disponibles. En la siguiente lista se muestran las tecnologías más comunes que no se encuentran en .NET Core 1.0:

* Aplicaciones de ASP.NET Web Forms: ASP.NET Web Forms solo está disponible en .NET Framework, así que no puede usar ASP.NET Core/.NET Core en este escenario. Actualmente no está previsto migrar ASP.NET Web Forms a .NET Core.

* Aplicaciones de ASP.NET Web Pages: ASP.NET Web Pages no se incluye en ASP.NET Core 1.0, aunque lo estará en una versión futura, como se explica en el [mapa de ruta de .NET Core](https://github.com/aspnet/Home/wiki/Roadmap).

* Implementación de servidor y cliente de ASP.NET SignalR. En el período de tiempo de la versión .NET Core 1.0 (junio de 2016), ASP.NET SignalR no está disponible para ASP.NET Core (ni cliente ni servidor), aunque está previsto incluirlo en una versión futura, como se explica en el [mapa de ruta de .NET Core](https://github.com/aspnet/Home/wiki/Roadmap). El estado de versión preliminar está disponible en los repositorios de GitHub del [lado servidor](https://github.com/aspnet/SignalR-Server) y la [biblioteca cliente](https://github.com/aspnet/SignalR-Client-Net).

* Implementación de servicios WCF. Aunque hay una [biblioteca cliente de WCF](https://github.com/dotnet/wcf) para consumir servicios WCF desde .NET Core, a partir de junio de 2016, la implementación del servidor WCF solo estará disponible en .NET Framework. Este escenario no es parte del plan actual de .NET Core, pero se está considerando para el futuro.

* Servicios relacionados con el flujo de trabajo: Windows Workflow Foundation (WF), Workflow Services (WCF + WF en un único servicio) y WCF Data Services (antes conocido como "ADO.NET Data Services") solo están disponibles en .NET Framework y no está previsto migrarlos a .NET Core.

* Windows Presentation Foundation (WPF) y Windows Forms: las aplicaciones WPF y Windows Forms solo están disponibles en .NET Framework. No existen planes para migrarlas a .NET Core. 

* Compatibilidad con lenguajes: Visual Basic y F# no tienen actualmente herramientas compatibles con .NET Core, pero ambos se admitirán en Visual Studio 2017 y versiones posteriores de Visual Studio.

Además del mapa de ruta oficial, hay otros marcos para migrar a .NET Core. Para ver una lista completa, eche un vistazo a los problemas de CoreFX macados como [port-to-core](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aport-to-core) (migrar a core). Tenga en cuenta que esta lista no representa un compromiso de Microsoft para migrar estos componentes a .NET Core, sino que simplemente capturan el deseo de la comunidad de hacerlo. Dicho esto, si le interesa cualquiera de los componentes mencionados anteriormente, puede participar en las discusiones en GitHub para que su voz pueda ser escuchada. Y si piensa que falta algo, [registre un nuevo problema en el repositorio de CoreFX](https://github.com/dotnet/corefx/issues/new).

### <a name="a-need-to-use-a-platform-that-doesnt-support-net-core"></a>Necesidad de usar una plataforma que no es compatible con .NET Core

Algunas plataformas de terceros o de Microsoft no son compatibles con .NET Core. Por ejemplo, algunos servicios de Azure, como Service Fabric Stateful Reliable Services y Service Fabric Reliable Actors requieren .NET Framework. Otros servicios proporcionan un SDK que aún no se encuentra disponible para consumo en .NET Core. Esta es una circunstancia transitoria, dado que todos los servicios de Azure usan .NET Core. Mientras tanto, siempre puede utilizar la API de REST equivalente en lugar del SDK de cliente.

## <a name="further-resources"></a>Recursos adicionales

* [Guía de .NET Core](../core/index.md)
* [Portabilidad de .NET Framework a .NET Core](../core/porting/index.md)
* [Guía de .NET Framework en Docker](../framework/index.md)
* [Introducción a los componentes de .NET](components.md)

