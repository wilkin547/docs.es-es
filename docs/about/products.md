---
title: Productos .NET
description: Productos .NET
keywords: .NET, .NET Core
author: richlander
manager: wpickett
ms.date: 06/23/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 2e38e9d9-8284-46ee-a15f-199adc4f26f4
translationtype: Human Translation
ms.sourcegitcommit: 15c55a87beb64f265a164db918c7721c7690fadf
ms.openlocfilehash: 90deb1903eea6ae1336326ca91f1e7863485dfd1

---

# <a name="net-products"></a>Productos .NET

.NET es una [especificación](https://github.com/dotnet/coreclr/blob/master/Documentation/project-docs/dotnet-standards.md) muy flexible, de uso general e intrínsecamente multiplataforma para la creación de productos para desarrolladores. Se usa para todas las categorías de aplicaciones más populares: escritorio, móvil, nube, juegos e IoT.

En este documento se usan dos términos con una diferencia muy sutil:

- "Producto .NET": permite compilar una aplicación para una o varias plataformas de destino.
- "Implementación .NET": combinación de un tiempo de ejecución, un marco y unas herramientas que pueden ejecutar el "código .NET" en el que se basan los productos.

## <a name="product-categories"></a>Categorías de productos

Los productos .NET están disponibles para cada una de las siguientes categorías de productos.

### <a name="desktop"></a>Escritorio

Puede compilar aplicaciones de escritorio para Windows y macOS.

- [Aplicaciones universales de Windows](https://developer.microsoft.com/windows) con [.NET Native](#net-native)
- [Windows Presentation Foundation (WPF)](https://msdn.microsoft.com/library/ms754130.aspx) para Windows con [.NET Framework](#net-framework)
- [Windows Forms](https://msdn.microsoft.com/library/dd30h2yb.aspx) para Windows con [.NET Framework](#net-framework)
- Cocoa para macOS con [Xamarin](#xamarin-sdk)
- [Electron](http://electron.atom.io/) para escritorio multiplataforma con [electron-edge](https://github.com/kexplo/electron-edge)

### <a name="games"></a>Juegos

Puede compilar juegos para muchos dispositivos de escritorio, portátiles, de consola y de realidad virtual y aumentada.

- [CRYENGINE](http://docs.cryengine.com/display/CEPROG/CE%23+Programming) con [Mono](#mono)
- [MonoGame](http://www.monogame.net/documentation/?page=main) con [Mono](#mono)
- [Unity](http://docs.unity3d.com/Manual/index.html) con [Mono](#mono)

### <a name="iot"></a>IoT

Puede compilar aplicaciones de IoT para Windows 10 IoT Core, incluidos Raspberry Pi 2/3.

- [Windows 10 IoT Core](https://developer.microsoft.com/windows/iot) con [.NET Native](#net-native)

### <a name="mobile"></a>Móvil

Puede compilar aplicaciones móviles para iOS, Android y Windows.

- Aplicación iOS con [Xamarin](#xamarin-sdk)
- Aplicación Android con [Xamarin](#xamarin-sdk)
- [Aplicaciones universales de Windows](https://developer.microsoft.com/windows) con [.NET Native](#net-native)

### <a name="web-and-cloud"></a>Web y nube

Puede compilar aplicaciones web y de nube para Windows y Linux.

- [ASP.NET](http://www.asp.net/) para Windows con [.NET Framework](#net-framework)
- [ASP.NET Core](http://docs.asp.net/) para Windows, macOS y Linux con [.NET Core](#net-core)

## <a name="net-implementations"></a>Implementaciones de .NET

A continuación se enumeran en orden alfabético las principales implementaciones de .NET comerciales y de código abierto.

### <a name="net-core"></a>Núcleo de .NET

.NET Core se usa para compilar aplicaciones de dispositivo, web, nube e incrustadas/IoT. Es de [código abierto](https://github.com/dotnet/core) y multiplataforma, compatible con Windows, macOS y Linux. [ASP.NET Core](http://docs.asp.net/) es la carga de trabajo más popular para .NET Core. Puede usarlo para compilar servicios y aplicaciones web para implementaciones locales y en la nube. También puede usar .NET Core para compilar herramientas, utilidades y aplicaciones de trabajo en la nube.

- Obtener información sobre [.NET Core](../core/index.md)
- Obtener información sobre [ASP.NET Core](http://docs.asp.net/)
- [Descargar .NET Core](http://dot.net/core)

Estas son las principales características de .NET Core:

**Multiplataforma**: .NET Core es compatible con tres familias de sistemas operativos: Linux, Windows y macOS. Las aplicaciones .NET Core son multiplataforma de forma predeterminada. Puede escribir aplicaciones y bibliotecas que se ejecutan sin modificaciones en sistemas operativos compatibles.

**Código abierto** - [.NET Core](https://github.com/dotnet/core) está disponible en GitHub, con licencias de [MIT](https://github.com/dotnet/coreclr/blob/master/LICENSE.TXT) y [Apache 2](https://github.com/dotnet/roslyn/blob/master/License.txt) (la concesión de licencias se realiza por componente). La documentación es [CC-BY](https://github.com/dotnet/docs/blob/master/license.txt). .NET Core también usa un conjunto importante de dependencias del sector de código abierto, que se muestran en las [notas de la versión de .NET Core](https://github.com/dotnet/core/releases). 

**Adquisición natural**: .NET Core se distribuye de varias formas, en función de las necesidades específicas del desarrollador. Puede adquirir .NET Core con el instalador del [SDK de .NET Core](https://dot.net/core) (o archivos ZIP) o mediante los administradores de paquetes específicos del sistema operativo, como APT y Yum. En Docker Hub hay disponibles [imágenes oficiales de Docker para .NET Core](https://hub.docker.com/r/microsoft/dotnet/). En [NuGet](http://www.nuget.org/) hay disponibles bibliotecas de Framework de alto nivel y el mayor ecosistema de bibliotecas de .NET. 

**Plataforma modular**: .NET Core se ha creado con un diseño modular que permite que las aplicaciones incluyan solo las bibliotecas de .NET Core y las dependencias necesarias. Cada aplicación toma sus propias decisiones de control de versiones de .NET Core, con lo que se evitan conflictos con los componentes compartidos. Este enfoque se alinea con la tendencia de desarrollo de software mediante tecnologías de contenedor como Docker.

### <a name="net-framework"></a>.NET Framework

.NET Framework se usa para compilar aplicaciones para Windows y Windows Server. Puede usarlo para compilar interfaces de usuario enriquecidas con Windows Presentation Framework (WPF) y Windows Forms. También permite compilar aplicaciones de servidor con ASP.NET Web Forms, ASP.NET MVC y Windows Communication Framework (WCF). Visual Studio proporciona experiencias de diseñador enriquecidas para .NET Framework, lo que facilita la compilación de aplicaciones cliente y servidor. Es la mejor opción para escribir aplicaciones para Windows.

- Obtener información sobre [.NET Framework](https://msdn.microsoft.com/library/w0x726c2.aspx)
- [Descargar .NET Framework](https://dot.net)

[Windows Forms](https://msdn.microsoft.com/library/dd30h2yb.aspx) permite compilar una interfaz de usuario de escritorio de "formularios sobre datos" mucho más rápido que cualquier otra tecnología. Usa un diseñador que permite arrastrar y colocar controles de interfaz de usuario y que no son de interfaz de usuario, lo que reduce la mayoría de las tareas de desarrollo a un solo modelo gestual y conceptual.

[Windows Presentation Foundation (WPF)](https://msdn.microsoft.com/library/ms754130.aspx) separa las cuestiones relacionadas con el código de las relacionadas con la interfaz de usuario, ya que describe la interfaz de usuario con el lenguaje de marcado [XAML](https://msdn.microsoft.com/library/ms752059.aspx). WPF es muy flexible y se suele usar para las interfaces de usuario que requieren un modelo de usuario más complejo o un aspecto más elegante.

[Windows Communication Foundation (WCF)](https://msdn.microsoft.com/library/ms731082.aspx) es un conjunto de bibliotecas para servicios web de SOAP. Permite crear servicios que pueden comunicarse a través de varios protocolos compatibles con diversos formatos de datos y que se pueden hospedar en cualquier proceso que elija. Esto nos lleva a una de las principales características de WCF: los servicios no están atados a ningún enfoque o estrategia de hospedaje concretos.

[ASP.NET](http://www.asp.net/) es un marco web. Tiene diferentes partes que se usan para generar aplicaciones web modernas y de alto rendimiento. 

- [ASP.NET Web Forms](http://www.asp.net/web-forms) permite compilar una interfaz de usuario de "formularios sobre datos" más rápidamente que la mayoría de las tecnologías de web, con un diseñador que permite arrastrar y colocar controles web. 
- [ASP.NET MVC](http://www.asp.net/mvc) ofrece un mayor control sobre la canalización de todo el sitio web, desde la capa HTTP hasta la interfaz de usuario. 
- [ASP.NET WebAPI](http://www.asp.net/web-api) es un marco basado en convenciones para crear servicios REST. 
- [SignalR](http://www.asp.net/signalr) permite proporcionar comunicación basada en inserción a las aplicaciones web mediante el protocolo [WebSocket](https://en.wikipedia.org/wiki/WebSocket).

### <a name="net-native"></a>.NET Native

.NET Native es un conjunto de herramientas de compilación nativas para .NET Core. .NET Native es una cadena de herramientas Ahead Of Time (AOT) que produce aplicaciones nativas al compilar código de byte de IL en código máquina nativo. Esto significa que el archivo binario resultante es lo que el sistema operativo ejecuta. No hay ninguna operación de JIT ni compilación en tiempo de ejecución. Esto produce un mejor rendimiento de inicio, así como algunas ventajas de seguridad.

.NET Native se usa principalmente en aplicaciones de [Plataforma universal de Windows (UWP)](https://msdn.microsoft.com/library/windows/apps/dn726767.aspx) de .NET.

### <a name="mono"></a>Mono

[Mono](http://www.mono-project.com/docs/about-mono/) es la implementación original multiplataforma y de código abierto de. NET, de la comunidad [Mono Project](http://mono-project.com). En la actualidad, está patrocinado por Microsoft. Se puede considerar una versión abierta y multiplataforma de .NET Framework. Sus API siguen el progreso de .NET Framework, no de .NET Core.

Mono está integrado por varios componentes:

**Compilador de C#**: el compilador de C# de Mono es una característica completada para C# 6.

**Tiempo de ejecución Mono**: el tiempo de ejecución implementa Common Language Infrastructure (CLI) de ECMA. El tiempo de ejecución proporciona un compilador Just-In-Time (JIT), un compilador Ahead Of Time (AOT), un cargador de bibliotecas, el recolector de elementos no utilizados, un sistema de subprocesos y funcionalidad de interoperabilidad.

**Biblioteca de clases base**: la plataforma Mono ofrece un conjunto completo de clases que proporcionan una base sólida sobre la que compilar aplicaciones. Estas clases son compatibles con las clases de .NET Framework de Microsoft.

**Biblioteca de clases de Mono**: Mono también proporciona muchas clases que van más allá de la biblioteca de clases base proporcionada por .NET Framework. Ofrecen una funcionalidad adicional que resulta muy útil, sobre todo para compilar aplicaciones de Linux. Algunos ejemplos son las clases para Gtk+, archivos ZIP, LDAP, OpenGL, Cairo, POSIX, etc.

### <a name="xamarin-sdk"></a>SDK de Xamarin

El [SDK de Xamarin](http://open.xamarin.com) se usa para compilar aplicaciones nativas móviles y para dispositivos, principalmente para los ecosistemas de Apple y Google. Se basa en Mono y es de código abierto con el uso de la licencia MIT. Puede usarlo para compilar aplicaciones iOS y Android para teléfonos, tabletas y relojes. [Xamarin.Forms](https://www.xamarin.com/forms) es una forma popular de escribir las interfaces de usuario reutilizables en aplicaciones de Apple, Google y Windows.

- Obtener información sobre el [SDK de Xamarin](https://developer.xamarin.com/)
- [Descargar Xamarin](https://www.xamarin.com/platform)



<!--HONumber=Nov16_HO1-->


