---
title: "Guía de .NET Core"
description: ".NET Core es una implementación modular y de alto rendimiento de .NET para crear aplicaciones de Windows, Linux y Mac. Obtenga información sobre .NET Core para comenzar."
keywords: .NET, .NET Core
author: richlander
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: f2b312cb-f80c-4b0d-9101-93908f06a6fa
ms.translationtype: HT
ms.sourcegitcommit: 9f2128080d34e78733cec926e59ee5dbe9b98a0d
ms.openlocfilehash: 14e72dad71b8d99cea947e14f2ac77aedcfb5672
ms.contentlocale: es-es
ms.lasthandoff: 08/07/2017

---

# <a name="net-core-guide"></a>Guía de .NET Core

> Consulte los [tutoriales de introducción](get-started.md) para aprender a crear una aplicación .NET Core sencilla. En unos minutos su primera aplicación estará lista y funcionando.

.NET Core es una plataforma de desarrollo de uso general de cuyo mantenimiento se encargan Microsoft y la comunidad .NET en [GitHub](https://github.com/dotnet/core). Es multiplataforma, admite Windows, macOS y Linux y puede usarse en escenarios de dispositivo, nube, IoT e incrustados. 

Las siguientes características definen mejor a .NET Core:

- **Implementación flexible:** se puede incluir en la aplicación o se puede instalar de forma paralela a nivel de usuario o de equipo.
- **Multiplataforma:** se ejecuta en Windows, macOS y Linux; se puede portar a otros sistemas operativos. Los [ sistemas operativos (SO)](https://github.com/dotnet/core/blob/master/roadmap.md), CPU y escenarios de aplicaciones admitidos proporcionados por Microsoft, otras empresas e individuos, crecerán con el tiempo
- **Herramientas de línea de comandos:** todos los escenarios de producto pueden ejecutarse en la línea de comandos. 
- **Compatible:** .NET Core es compatible con .NET Framework, Xamarin y Mono, mediante [.NET Standard](../standard/net-standard.md).
- **Código abierto:** la plataforma .NET Core es de código abierto, con licencias de MIT y Apache 2. Documentación con licencia de [CC-BY](https://creativecommons.org/licenses/by/4.0/). .NET Core es un proyecto de [.NET Foundation](https://dotnetfoundation.org/).
- **Compatible con Microsoft:** .NET Core incluye compatibilidad con Microsoft, como se indica en [.NET Core Support](https://www.microsoft.com/net/core/support/) (Compatibilidad de .NET Core).

## <a name="composition"></a>Composición

.NET Core consta de las siguientes partes:

- Un [entorno de ejecución .NET](https://github.com/dotnet/coreclr), que proporciona un sistema de tipos, la carga de ensamblados, un colector de elementos no utilizados, interoperabilidad nativa y otros servicios básicos. 
- Un conjunto de [bibliotecas de marco](https://github.com/dotnet/corefx), que proporciona tipos de datos primitivos, tipos de composición de aplicaciones y utilidades fundamentales. 
- Un [conjunto de herramientas de SDK](https://github.com/dotnet/cli) y [compiladores de lenguaje](https://github.com/dotnet/roslyn) que permiten la experiencia de desarrollo base, disponible en el [SDK de .NET Core](sdk.md).
- El host de aplicación 'dotnet', que se usa para iniciar aplicaciones .NET Core. Selecciona el entorno de tiempo de ejecución y lo hospeda, proporciona una directiva de carga de ensamblados e inicia la aplicación. El mismo host también se usa para iniciar las herramientas del SDK de la misma manera.

### <a name="languages"></a>Lenguajes

Los lenguajes C# y F # (y próximamente Visual Basic) pueden usarse para escribir aplicaciones y bibliotecas para .NET Core. Los compiladores se ejecutan en .NET Core, lo que permite desarrollar para .NET Core en cualquier lugar donde se ejecute. En general, no usará los compiladores directamente, sino de forma indirecta, mediante las herramientas del SDK.

Los compiladores de C# y F # y las herramientas de .NET Core están integradas o se pueden integrar en varios editores de texto e IDE, como Visual Studio, [Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp), Sublime Text y Vim, lo que convierte el desarrollo con .NET Core en una opción en su entorno de codificación y SO favoritos. Esta integración se proporciona, en parte, gracias a la buena gente del [proyecto OmniSharp](http://www.omnisharp.net/).

### <a name="net-apis-and-compatibility"></a>API y compatibilidad de .NET

.NET Core puede considerarse una versión multiplataforma de .NET Framework, en la capa de las bibliotecas de clases base (BCL) de .NET Framework. Implementa la especificación de [.NET Standard](../standard/net-standard.md). .NET Core proporciona un conjunto de las API que están disponibles en .NET Framework o Mono/Xamarin. En algunos casos, los tipos no están completamente implementados (algunos miembros no están disponibles o se han movido).

Consulte el [mapa de ruta de .NET Core](https://github.com/dotnet/core/blob/master/roadmap.md) para aprender más sobre la API de .NET Core.

### <a name="relationship-to-net-standard"></a>Relación con .NET Standard

[.NET Standard](../standard/net-standard.md) es una especificación de API que describe el conjunto coherente de API de .NET que los desarrolladores pueden esperar en cada implementación de .NET. Las implementaciones de .NET necesitan implementar esta especificación para ser consideradas compatibles con .NET Standard y para admitir las bibliotecas que tienen como destino .NET Standard. 

.NET Core implementa .NET Standard y, por tanto, admite las bibliotecas de .NET Standard.

### <a name="workloads"></a>Cargas de trabajo

Por sí mismo, .NET Core incluye un único modelo de aplicación, aplicaciones de consola, que resulta útil para herramientas, servicios locales y juegos basados en texto. Se han generado modelos de aplicación adicionales sobre .NET Core para ampliar su funcionalidad, como:

- [ASP.NET Core](/aspnet/core/)
- [Plataforma universal de Windows (UWP) de Windows 10](https://developer.microsoft.com/windows)
- [Xamarin.Forms cuando el destino es UWP](https://www.xamarin.com/forms)

### <a name="open-source"></a>Código abierto

[.NET Core](https://github.com/dotnet/core) es código abierto (licencia MIT) y fue presentado a [.NET Foundation](https://dotnetfoundation.org) por Microsoft en 2014. Ahora es uno de los proyectos más activos de .NET Foundation. Todos los individuos y organizaciones pueden adoptarlo libremente, con cualquier fin: personal, académico o comercial. Varias empresas usan .NET Core como parte de aplicaciones, herramientas, nuevas plataformas y servicios de hospedaje. Algunas de estas empresas realizan contribuciones significativas a .NET Core en GitHub y proporcionan una guía sobre la dirección del producto como parte del [Technical Steering Group de .NET Foundation](https://dotnetfoundation.org/blog/tsg-welcome).

## <a name="acquisition"></a>Adquisición

.NET Core se distribuye de dos formas: como paquetes en NuGet.org y como distribuciones independientes.

### <a name="distributions"></a>Distribuciones

Puede descargar .NET Core en la página [.NET Core Getting Started](https://www.microsoft.com/net/core) (Introducción a .NET Core).

- La distribución de *Microsoft .NET Core* incluye el entorno de tiempo de ejecución de CoreCLR, las bibliotecas asociadas, un host de aplicaciones de consola y el iniciador de aplicaciones `dotnet`. Se describe en el metapaquete [`Microsoft.NETCore.App`](https://www.nuget.org/packages/Microsoft.NETCore.App).
- La distribución del *SDK de Microsoft .NET Core* incluye .NET Core y un conjunto de herramientas para restaurar paquetes NuGet y compilar y crear aplicaciones. 

Normalmente primero se instala el SDK de .NET Core para comenzar con el desarrollo de .NET Core. Puede elegir instalar compilaciones adicionales de .NET Core (quizás versiones preliminares).

### <a name="packages"></a>Paquetes

- Los [paquetes de .NET Core](packages.md) contienen el entorno de tiempo de ejecución y las bibliotecas de .NET Core (ensamblados e implementaciones de referencia). Por ejemplo, [System.Net.Http](https://www.nuget.org/packages/System.Net.Http/).
- Los [metapaquetes de .NET Core](packages.md) describen diversas capas y modelos de aplicaciones mediante la referencia al conjunto adecuado de paquetes de bibliotecas con versiones.

## <a name="architecture"></a>Arquitectura

.NET Core es una implementación .NET multiplataforma. Las principales inquietudes específicas de la arquitectura .NET Core están relacionadas con la provisión de implementaciones específicas de la plataforma para plataformas compatibles.

### <a name="environments"></a>Entornos

Microsoft admite .NET Core en Windows, macOS y Linux. En Linux, Microsoft admite principalmente la ejecución de .NET Core en las familias de distribución Red Hat Enterprise Linux (RHEL) y Debian.

.NET Core admite actualmente CPU X64. En Windows, también se admite X86. ARM64 y ARM32 están en curso.

El [mapa de ruta de .NET Core](https://github.com/dotnet/core/blob/master/roadmap.md) proporciona información más detallada sobre la carga de trabajo y los planes y la compatibilidad del entorno de SO y CPU.

Otras empresas o grupos pueden admitir .NET Core en otros tipos de aplicaciones y entornos.

### <a name="designed-for-adaptability"></a>Diseñado para adaptabilidad

.NET Core se ha creado como un producto muy similar, pero único, en relación con otros productos .NET. Se ha diseñado para permitir una amplia adaptabilidad a nuevas plataformas, para nuevas cargas de trabajo y con nuevas cadenas de herramientas de compilador. Tiene varios puertos de CPU y SO en curso y se puede portar a muchos más. Por ejemplo, el proyecto [LLILC](https://github.com/dotnet/llilc), es uno de los primeros prototipos de compilación nativa para .NET Core mediante el compilador [LLVM](http://llvm.org/).

El producto se divide en varias partes, lo que permite que las distintas partes se adapten a nuevas plataformas en programaciones diferentes. El entorno de tiempo de ejecución y las bibliotecas fundamentales específicas de la plataforma se deben portar como una unidad. Las bibliotecas independientes de la plataforma deben funcionar, por diseño, en todas las plataformas, tal y como están. Hay una tendencia del proyecto a reducir las implementaciones específicas de la plataforma con el fin de aumentar la eficiencia del desarrollador, donde se prefiere el código C# independiente de la plataforma siempre que se pueda implementar un algoritmo o una API de esa forma completa o parcialmente.

Le gente se pregunta cómo se implementa .NET Core para que se admita en varios sistemas operativos. Normalmente preguntan si hay otras implementaciones o si se usa [compilación condicional](https://en.wikipedia.org/wiki/Conditional_compilation). Son las dos cosas, con una fuerte tendencia hacia la compilación condicional.

En el gráfico siguiente puede ver que la gran mayoría de [CoreFX](https://github.com/dotnet/corefx) es código independiente de la plataforma que se comparte en todas las plataformas. El código independiente de la plataforma se puede implementar como un solo ensamblado portátil que se usa en todas las plataformas.

![CoreFX: líneas de código por plataforma](../images/corefx-platforms-loc.png)

Las implementaciones de Windows y Unix son de tamaño similar. Windows tiene una implementación mayor ya que CoreFX implementa algunas características que son exclusivas de Windows, como [Microsoft.Win32.Registry](https://github.com/dotnet/corefx/tree/master/src/Microsoft.Win32.Registry) pero aún no implementa ningún concepto exclusivo de Unix. Verá que la mayoría de las implementaciones de Linux y macOS se comparten en una implementación de Unix, mientras que las implementaciones específicas de macOS y Linux son bastante similares en tamaño.


Hay una mezcla de bibliotecas específicas de la plataforma e independiente de la plataforma en .NET Core. Puede ver el patrón en algunos ejemplos:

- [CoreCLR](https://github.com/dotnet/coreclr) es específico de la plataforma. Se basa en C o C++, así que es específico de la plataforma por diseño.
- [System.IO](https://github.com/dotnet/corefx/tree/master/src/System.IO) y [System.Security.Cryptography.Algorithms](https://github.com/dotnet/corefx/tree/master/src/System.Security.Cryptography.Algorithms) son específicos de la plataforma, dado que las API de almacenamiento y criptografía difieren bastante en cada sistema operativo. 
- [System.Collections](https://github.com/dotnet/corefx/tree/master/src/System.Collections) y [System.Linq](https://github.com/dotnet/corefx/tree/master/src/System.Linq) son independientes de la plataforma, dado que crean estructuras de datos y funcionan sobre ellas.

## <a name="comparisons-to-other-net-implementations"></a>Comparación con otras implementaciones de .NET

Quizás es más fácil comprender la naturaleza de .NET Core si se compara con las implementaciones de .NET existentes. 

### <a name="comparison-with-net-framework"></a>Comparación con .NET Framework

Microsoft presentó la plataforma .NET en el año 2000, y a partir de ese momento ha ido evolucionando. .NET Framework ha sido la principal implementación de .NET producida por Microsoft durante ese lapso de 15 años. 

Las principales diferencias entre .NET Core y .NET Framework son: 

- **Modelos de aplicación**: .NET Core no admite todos los modelos de aplicación de .NET Framework, en parte porque muchos de ellos se basan en tecnologías de Windows, como WPF (basado en DirectX). La consola y los modelos de aplicación de ASP.NET Core se admiten tanto en .NET Core como en .NET Framework. 
- **API**: .NET Core contiene muchas de las mismas API, pero menos, que .NET Framework, y con una factorización diferente (los nombres de ensamblado son diferentes; la forma de los tipo difiere en casos principales). Estas diferencias actualmente suelen requerir cambios en el origen del puerto a .NET Core. .NET Core implementa la API de [.NET Standard](../standard/net-standard.md), que con el tiempo crecerá para incluir más de la API de BCL de .NET Framework.
- **Subsistemas**: .NET Core implementa un subconjunto de los subsistemas de .NET Framework, de cara a una implementación y un modelo de programación más sencillos. Por ejemplo, no se admite seguridad de acceso del código (CAS), aunque se admite la reflexión.
- **Plataformas**: .NET Framework admite Windows y Windows Server, mientras que .NET Core también es compatible con macOS y Linux.
- **Código abierto**: .NET Core es código abierto, mientras que un [subconjunto de .NET Framework de solo lectura](https://github.com/microsoft/referencesource) es código abierto.

Aunque .NET Core es única y tiene diferencias significativas con .NET Framework y otras implementaciones de .NET, permite compartir código fácilmente mediante técnicas de uso compartido de origen o binarias. 

### <a name="comparison-with-mono"></a>Comparación con Mono

[Mono](http://www.mono-project.com/) es la implementación .NET original multiplataforma y [de código abierto](https://github.com/mono/mono) implementación .NET, que se envió por primera vez en 2004. Se puede considerar un clon de la comunidad de .NET Framework. El equipo de proyecto de Mono se basó en los [estándares de .NET](https://github.com/dotnet/coreclr/blob/master/Documentation/project-docs/dotnet-standards.md) abiertos (en particular, ECMA 335) publicados por Microsoft para proporcionar una implementación compatible.

Las principales diferencias entre .NET Core y Mono:

- **Modelos de aplicación**: Mono admite un subconjunto de los modelos de aplicación de .NET Framework (por ejemplo, Windows Forms) y algunos adicionales (por ejemplo, [Xamarin.iOS](https://www.xamarin.com/platform)) mediante el producto de Xamarin. .NET Core no admite estos.
- **API**: Mono admite un [gran subconjunto](http://docs.go-mono.com/?link=root%3a%2fclasslib) de las API de .NET Framework, con los mismos nombres de ensamblado y factorización.
- **Plataformas**Mono admite muchas plataformas y CPU.
- **Código abierto**Mono y .NET Core usan la licencia MIT y son proyectos de .NET Foundation.
- **Enfoque**: el foco principal de Mono en los últimos años es plataformas móviles, aunque .NET Core se centra en las cargas de trabajo de la nube.

