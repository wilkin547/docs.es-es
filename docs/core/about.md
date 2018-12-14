---
title: Sobre .NET Core
description: Obtenga información sobre .NET Core.
author: richlander
ms.author: mairaw
ms.date: 08/01/2018
ms.openlocfilehash: 93619fce58a3b3aa94e6c14fc7cfeb1b0bf48272
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53126983"
---
# <a name="about-net-core"></a>Sobre .NET Core

.NET Core tiene las siguientes características:

- **Multiplataforma:** se ejecuta en los [sistemas operativos](https://github.com/dotnet/core/blob/master/os-lifecycle-policy.md) Windows, macOS y Linux.
- **Coherente en todas las arquitecturas:** se ejecuta el código con el mismo comportamiento en varias arquitecturas, como x64, x86 y ARM.
- **Herramientas de línea de comandos:** incluye herramientas de línea de comandos fáciles de usar que pueden utilizarse para el desarrollo local y en escenarios de integración continua.
- **Implementación flexible:** se puede incluir en la aplicación o se puede instalar de forma paralela a nivel de usuario o de equipo. Se puede usar con [contenedores de Docker](docker/index.md).
- **Compatible:** .NET Core es compatible con .NET Framework, Xamarin y Mono, mediante [.NET Standard](../standard/net-standard.md).
- **Código abierto:** la plataforma .NET Core es de código abierto, con licencias de MIT y Apache 2. .NET Core es un proyecto de [.NET Foundation](https://dotnetfoundation.org/).
- **Compatible con Microsoft:** .NET Core incluye compatibilidad con Microsoft, como se indica en [.NET Core Support](https://www.microsoft.com/net/core/support/) (Compatibilidad de .NET Core).

## <a name="languages"></a>Lenguajes

Los lenguajes C#, Visual Basic y F# pueden usarse para escribir aplicaciones y bibliotecas para .NET Core. Estos lenguajes se integran o se pueden integrar en los editores de texto y entornos de desarrollo integrado que se prefieran, como [Visual Studio](https://visualstudio.microsoft.com/vs/), [Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp), Sublime Text y Vim. Esta integración se proporciona, en parte, gracias a la buena gente de los proyectos [OmniSharp](https://www.omnisharp.net/) e [Ionide](http://ionide.io).

## <a name="apis"></a>API

.NET Core expone las API de muchos escenarios. A continuación se muestran algunos de estos escenarios:

- Tipos primitivos como [bool](../csharp/language-reference/keywords/bool.md) e [int](../csharp/language-reference/keywords/int.md).
- Colecciones, como <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> y <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType>.
- Tipos de utilidades, como <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> y <xref:System.IO.FileStream?displayProperty=nameWithType>.
- Tipos de datos, como <xref:System.Data.DataSet?displayProperty=nameWithType> y [DbSet](https://www.nuget.org/packages/Microsoft.EntityFrameworkCore/).
- Tipos de alto rendimiento, como <xref:System.Numerics.Vector?displayProperty=nameWithType> y [Canalizaciones](https://blogs.msdn.microsoft.com/dotnet/2018/07/09/system-io-pipelines-high-performance-io-in-net/).

.NET Core proporciona compatibilidad con las API .NET Framework y Mono API implementando la especificación de [.NET Standard](../standard/net-standard.md).

## <a name="frameworks"></a>Marcos de trabajo

Se han creado varias plataformas en .NET Core:

- [ASP.NET Core](/aspnet/core/)
- [Plataforma universal de Windows (UWP) de Windows 10](https://developer.microsoft.com/windows)
- [Tizen](https://developer.tizen.org/development/training/.net-application)

## <a name="composition"></a>Composición

.NET Core consta de las siguientes partes:

- El [runtime de .NET Core](https://github.com/dotnet/coreclr), que proporciona un sistema de tipos, la carga de ensamblados, un colector de elementos no utilizados, interoperabilidad nativa y otros servicios básicos. Las [bibliotecas de .NET Core Framework](https://github.com/dotnet/corefx), que proporcionan tipos de datos primitivos, tipos de composición de aplicaciones y utilidades fundamentales.
- El [runtime de ASP.NET](https://github.com/aspnet/home), que proporciona una plataforma en la que se pueden crear modernas aplicaciones conectadas a Internet y basadas en la nube, como aplicaciones web, aplicaciones de IoT y back-end móviles.
- Las [herramientas de CLI de .NET Core](https://github.com/dotnet/cli) y compiladores de lenguaje ([Roslyn](https://github.com/dotnet/roslyn) y [F#](https://github.com/microsoft/visualfsharp)) que habilitan la experiencia de desarrollador de .NET Core.
- La [herramienta dotnet](https://github.com/dotnet/core-setup), que se usa para iniciar aplicaciones .NET Core y herramientas de CLI. Selecciona el entorno de tiempo de ejecución y lo hospeda, proporciona una directiva de carga de ensamblados e inicia aplicaciones y herramientas.

Estos componentes se distribuyen de las formas siguientes:

- [Runtime de .NET Core](https://www.microsoft.com/net/download/dotnet-core/2.1): incluye el runtime y las bibliotecas de la plataforma de .NET Core.
- [Runtime de ASP.NET Core](https://www.microsoft.com/net/download/dotnet-core/2.1): incluye el runtime y las bibliotecas de la plataforma de ASP.NET Core y .NET Core.
- [SDK de .NET Core](https://www.microsoft.com/net/download/dotnet-core/2.1): incluye las herramientas de CLI de .NET, el runtime de ASP.NET Core y el runtime y la plataforma de .NET Core.

### <a name="open-source"></a>Código abierto

[.NET Core](https://github.com/dotnet/core) es código abierto ([licencia MIT](https://github.com/dotnet/core/blob/master/LICENSE.TXT)) y fue presentado a [.NET Foundation](https://dotnetfoundation.org) por Microsoft en 2014. Ahora es uno de los proyectos más activos de .NET Foundation. Todos los individuos y organizaciones pueden adoptarlo libremente, con cualquier fin: personal, académico o comercial. Varias empresas usan .NET Core como parte de aplicaciones, herramientas, nuevas plataformas y servicios de hospedaje. Algunas de estas empresas realizan contribuciones significativas a .NET Core en GitHub y proporcionan una guía sobre la dirección del producto como parte del [Technical Steering Group de .NET Foundation](https://dotnetfoundation.org/blog/tsg-welcome).

### <a name="designed-for-adaptability"></a>Diseñado para adaptabilidad

.NET Core se ha creado como un producto muy similar, pero único, en relación con otros productos .NET. Se ha diseñado para permitir una amplia adaptabilidad a nuevas plataformas y cargas de trabajo. Tiene varios puertos de CPU y SO disponibles y se puede portar a muchos más.

El producto se divide en varias partes, lo que permite que las distintas partes se adapten a nuevas plataformas en horas diferentes. El entorno de tiempo de ejecución y las bibliotecas fundamentales específicas de la plataforma se deben portar como una unidad. Las bibliotecas independientes de la plataforma deben funcionar, por diseño, en todas las plataformas, tal y como están. Hay una tendencia del proyecto a reducir las implementaciones específicas de la plataforma con el fin de aumentar la eficiencia del desarrollador, donde se prefiere el código C# independiente de la plataforma siempre que se pueda implementar un algoritmo o una API de esa forma completa o parcialmente.

Le gente se pregunta cómo se implementa .NET Core para que se admita en varios sistemas operativos. Normalmente preguntan si hay otras implementaciones o si se usa [compilación condicional](https://en.wikipedia.org/wiki/Conditional_compilation). Son las dos cosas, con una fuerte tendencia hacia la compilación condicional.

En el gráfico siguiente puede ver que la gran mayoría de [CoreFX](https://github.com/dotnet/corefx) es código independiente de la plataforma que se comparte en todas las plataformas. El código independiente de la plataforma se puede implementar como un solo ensamblado portátil que se usa en todas las plataformas.

![CoreFX: líneas de código por plataforma](../images/corefx-platforms-loc.png)

Las implementaciones de Windows y Unix son de tamaño similar. Windows tiene una implementación mayor ya que CoreFX implementa algunas características que son exclusivas de Windows, como [Microsoft.Win32.Registry](https://github.com/dotnet/corefx/tree/master/src/Microsoft.Win32.Registry) pero aún no implementa muchos conceptos exclusivos de Unix. Verá que la mayoría de las implementaciones de Linux y macOS se comparten en una implementación de Unix, mientras que las implementaciones específicas de macOS y Linux son bastante similares en tamaño.

Hay una mezcla de bibliotecas específicas de la plataforma e independiente de la plataforma en .NET Core. Puede ver el patrón en algunos ejemplos:

- [CoreCLR](https://github.com/dotnet/coreclr) es específico de la plataforma. Se compila en los subsistemas de SO, como el administrador de memoria y el programador de subprocesos.
- [System.IO](https://github.com/dotnet/corefx/tree/master/src/System.IO) y [System.Security.Cryptography.Algorithms](https://github.com/dotnet/corefx/tree/master/src/System.Security.Cryptography.Algorithms) son específicos de la plataforma, dado que las API de almacenamiento y criptografía difieren en cada sistema operativo.
- [System.Collections](https://github.com/dotnet/corefx/tree/master/src/System.Collections) y [System.Linq](https://github.com/dotnet/corefx/tree/master/src/System.Linq) son independientes de la plataforma, dado que crean estructuras de datos y funcionan sobre ellas.

## <a name="comparisons-to-other-net-implementations"></a>Comparación con otras implementaciones de .NET

Quizás es más fácil comprender la naturaleza de .NET Core si se compara con las implementaciones de .NET existentes.

### <a name="comparison-with-net-framework"></a>Comparación con .NET Framework

Microsoft presentó la plataforma .NET en el año 2000, y a partir de ese momento ha ido evolucionando. .NET Framework ha sido la principal implementación de .NET producida por Microsoft durante ese periodo de casi dos décadas.

Las principales diferencias entre .NET Core y .NET Framework son:

- **Modelos de aplicación**: .NET Core no es compatible con todos los modelos de aplicación de .NET Framework. En concreto, no es compatible con los formularios Web Forms de ASP.NET ni MVC. Se anunció que [.NET Core 3 será compatible con WPF y Windows Forms](https://blogs.msdn.microsoft.com/dotnet/2018/05/07/net-core-3-and-support-for-windows-desktop-applications/).
- **API**: .NET Core contiene un amplio subconjunto de bibliotecas de clases base de .NET Framework con una factorización distinta (los nombres de ensamblado son distintos y los miembros expuestos en los tipos difieren en los casos clave). Estas diferencias requieren cambios en el origen del puerto de .NET Core en algunos casos (vea [microsoft/dotnet-apiport](https://github.com/microsoft/dotnet-apiport)). .NET Core implementa la especificación de la API [.NET Standard](../standard/net-standard.md).
- **Subsistemas**: .NET Core implementa un subconjunto de los subsistemas de .NET Framework, de cara a una implementación y un modelo de programación más sencillos. Por ejemplo, no se admite seguridad de acceso del código (CAS), aunque se admite la reflexión.
- **Plataformas**: .NET Framework admite Windows y Windows Server, mientras que .NET Core también es compatible con macOS y Linux.
- **Código abierto**: .NET Core es código abierto, mientras que un [subconjunto de .NET Framework de solo lectura](https://github.com/microsoft/referencesource) es código abierto.

Aunque .NET Core es única y tiene diferencias significativas con .NET Framework y otras implementaciones de .NET, permite compartir código fácilmente entre estas implementaciones mediante técnicas de uso compartido de origen o binarias.

### <a name="comparison-with-mono"></a>Comparación con Mono

[Mono](https://www.mono-project.com/) es la implementación .NET original multiplataforma y [de código abierto](https://github.com/mono/mono) implementación .NET, que se envió por primera vez en 2004. Se puede considerar un clon de la comunidad de .NET Framework. El equipo de proyecto de Mono se basó en los [estándares de .NET](https://github.com/dotnet/coreclr/blob/master/Documentation/project-docs/dotnet-standards.md) abiertos (en particular, ECMA 335) publicados por Microsoft para proporcionar una implementación compatible.

Las principales diferencias entre .NET Core y Mono:

- **Modelos de aplicación**: Mono admite un subconjunto de los modelos de aplicación de .NET Framework (por ejemplo, Windows Forms) y algunos adicionales (por ejemplo, [Xamarin.iOS](https://www.xamarin.com/platform)) mediante el producto de Xamarin. .NET Core no admite estos.
- **API**: Mono admite un [gran subconjunto](http://docs.go-mono.com/?link=root%3a%2fclasslib) de las API de .NET Framework, con los mismos nombres de ensamblado y factorización.
- **Plataformas**Mono admite muchas plataformas y CPU.
- **Código abierto**Mono y .NET Core usan la licencia MIT y son proyectos de .NET Foundation.
- **Enfoque**: el foco principal de Mono en los últimos años es plataformas móviles, aunque .NET Core se centra en las cargas de trabajo de la nube y de escritorio.
