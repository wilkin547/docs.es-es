---
title: Sobre .NET Core
description: Obtenga información sobre .NET Core.
ms.date: 09/17/2019
ms.openlocfilehash: 22530e861f6a13a6930b2fb35c91b4f7a95a17c7
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2019
ms.locfileid: "74801951"
---
# <a name="about-net-core"></a>Sobre .NET Core

.NET Core tiene las siguientes características:

- **Multiplataforma:** se ejecuta en los [sistemas operativos](https://github.com/dotnet/core/blob/master/os-lifecycle-policy.md) Windows, macOS y Linux.
- **Coherente entre arquitecturas:** el código se ejecuta con el mismo comportamiento en varias arquitecturas, como x64, x86 y ARM.
- **Herramientas de línea de comandos:**  incluye herramientas de línea de comandos sencillas que se pueden usar para el desarrollo local y en escenarios de integración continua.
- **Implementación flexible:** Se pueden incluir en la aplicación o se pueden instalar de forma paralela (instalaciones a nivel de usuario o de sistema). Se puede usar con [contenedores de Docker](docker/introduction.md).
- **Compatible:** .NET Core es compatible con .NET Framework, Xamarin y Mono mediante [.NET Standard](../standard/net-standard.md).
- **Código abierto:** la plataforma .NET Core es de código abierto, con licencias de MIT y Apache 2. .NET Core es un proyecto de [.NET Foundation](https://dotnetfoundation.org/).
- **Compatible con Microsoft:** .NET Core incluye compatibilidad con Microsoft, como se indica en [.NET Core Support](https://dotnet.microsoft.com/platform/support/policy) (Compatibilidad de .NET Core).

## <a name="languages"></a>Lenguajes

Los lenguajes C#, Visual Basic y F# pueden usarse para escribir aplicaciones y bibliotecas para .NET Core. Puede usar estos idiomas en su editor de texto o en su entorno de desarrollo integrado (IDE) favorito, incluidos:

- [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)
- [Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp)
- Sublime Text
- Vim

Esta integración la proporcionan, en parte, los colaboradores de los proyectos [OmniSharp](https://www.omnisharp.net/) e [Ionide](http://ionide.io).

## <a name="apis"></a>API

.NET Core expone las API de muchos escenarios. A continuación se muestran algunos de estos escenarios:

- Tipos primitivos, como <xref:System.Boolean?displayProperty=nameWithType> y <xref:System.Int32?displayProperty=nameWithType>.
- Colecciones, como <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> y <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType>.
- Tipos de utilidades, como <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> y <xref:System.IO.FileStream?displayProperty=nameWithType>.
- Tipos de datos, como <xref:System.Data.DataSet?displayProperty=nameWithType> y [DbSet](https://www.nuget.org/packages/Microsoft.EntityFrameworkCore/).
- Tipos de alto rendimiento, como <xref:System.Numerics.Vector?displayProperty=nameWithType> y [Canalizaciones](../standard/io/pipelines.md).

.NET Core proporciona compatibilidad con las API .NET Framework y Mono API implementando la especificación de [.NET Standard](../standard/net-standard.md).

## <a name="frameworks"></a>Marcos de trabajo

Se han creado varias plataformas en .NET Core:

- [ASP.NET Core](/aspnet/core/)
- [Plataforma universal de Windows (UWP) de Windows 10](https://developer.microsoft.com/windows)
- [Tizen](https://developer.tizen.org/development/training/.net-application)

## <a name="composition"></a>Composición

.NET Core consta de las siguientes partes:

- El [runtime de .NET Core](https://github.com/dotnet/runtime/tree/master/src/coreclr), que proporciona un sistema de tipos, la carga de ensamblados, un colector de elementos no usados, interoperabilidad nativa y otros servicios básicos. Las [bibliotecas de .NET Core Framework](https://github.com/dotnet/runtime/tree/master/src/libraries) proporcionan tipos de datos primitivos, tipos de composición de aplicaciones y utilidades fundamentales.
- El [runtime de ASP.NET](https://github.com/aspnet/home), el cual proporciona un marco para crear aplicaciones modernas conectadas a Internet y basadas en la nube, como aplicaciones web, aplicaciones de IoT y back-ends móviles.
- Las [herramientas de CLI de .NET Core](https://github.com/dotnet/cli) y compiladores de lenguaje ([Roslyn](https://github.com/dotnet/roslyn) y [F#](https://github.com/microsoft/visualfsharp)) que habilitan la experiencia de desarrollador de .NET Core.
- La [herramienta dotnet](https://github.com/dotnet/core-setup), que se usa para iniciar aplicaciones .NET Core y herramientas de CLI. Selecciona el runtime y lo hospeda, proporciona una directiva de carga de ensamblados e inicia aplicaciones y herramientas.

Estos componentes se distribuyen de las formas siguientes:

- [Runtime de .NET Core](https://dotnet.microsoft.com/download): incluye el runtime y las bibliotecas de la plataforma de .NET Core.
- [Runtime de ASP.NET Core](https://dotnet.microsoft.com/download): incluye el runtime y las bibliotecas de la plataforma de ASP.NET Core y .NET Core.
- [SDK de .NET Core](https://dotnet.microsoft.com/download): incluye las herramientas de CLI de .NET, el runtime de ASP.NET Core y el runtime y la plataforma de .NET Core.

### <a name="open-source"></a>Código Abierto

[.NET Core](https://github.com/dotnet/core) es código abierto ([licencia MIT](https://github.com/dotnet/core/blob/master/LICENSE.TXT)) y fue presentado a [.NET Foundation](https://dotnetfoundation.org) por Microsoft en 2014. Ahora es uno de los proyectos más activos de .NET Foundation. Pueden usarlo todos los individuos y organizaciones con fines personales, académicos o comerciales. Varias empresas usan .NET Core como parte de aplicaciones, herramientas, nuevas plataformas y servicios de hospedaje. Algunas de estas empresas realizan contribuciones significativas a .NET Core en GitHub y proporcionan una guía sobre la dirección del producto como parte del [Technical Steering Group de .NET Foundation](https://dotnetfoundation.org/blog/tsg-welcome).

### <a name="designed-for-adaptability"></a>Diseñado para adaptabilidad

.NET Core se ha creado como un producto muy similar, pero único, en comparación con otros productos .NET. Se ha diseñado para permitir una amplia adaptabilidad a nuevas plataformas y cargas de trabajo, y tiene varios puertos de CPU y sistemas operativos disponibles (y se puede portar a muchos más).

El producto se divide en varias partes, lo que permite que las distintas partes se adapten a nuevas plataformas en horas diferentes. El entorno de tiempo de ejecución y las bibliotecas fundamentales específicas de la plataforma se deben portar como una unidad. Las bibliotecas independientes de la plataforma deben funcionar, por diseño, en todas las plataformas, tal y como están. Hay una tendencia del proyecto a reducir las implementaciones específicas de la plataforma con el fin de aumentar la eficiencia del desarrollador, donde se prefiere el código C# independiente de la plataforma siempre que se pueda implementar completa o parcialmente un algoritmo o una API de esa forma.

Le gente se pregunta cómo se implementa .NET Core para que se admita en varios sistemas operativos. Normalmente preguntan si hay otras implementaciones o si se usa [compilación condicional](https://en.wikipedia.org/wiki/Conditional_compilation). Son las dos cosas, con una fuerte tendencia hacia la compilación condicional.

En el gráfico siguiente puede ver que la gran mayoría de [bibliotecas de .NET Core](https://github.com/dotnet/runtime/tree/master/src/libraries) es código independiente de la plataforma que se comparte en todas las plataformas. El código independiente de la plataforma se puede implementar como un solo ensamblado portátil que se usa en todas las plataformas.

![CoreFX: líneas de código por plataforma](../images/corefx-platforms-loc.png)

Las implementaciones de Windows y Unix son de tamaño similar. Windows tiene una implementación mayor, ya que las bibliotecas de .NET Core implementan algunas características que son exclusivas de Windows, como [Microsoft.Win32.Registry](https://github.com/dotnet/runtime/tree/master/src/libraries/Microsoft.Win32.Registry), pero aún no implementa muchos conceptos exclusivos de Unix. También verá que la mayoría de las implementaciones de Linux y macOS se comparten en una implementación de Unix, mientras que las implementaciones específicas de macOS y Linux son bastante similares en tamaño.

Hay una mezcla de bibliotecas específicas de la plataforma e independientes de la plataforma en .NET Core. Puede ver el patrón en algunos ejemplos:

- [CoreCLR](https://github.com/dotnet/runtime/tree/master/src/coreclr) es específico de la plataforma. Se compila en los subsistemas de SO, como el administrador de memoria y el programador de subprocesos.
- [System.IO](https://github.com/dotnet/runtime/tree/master/src/libraries/System.IO) y [System.Security.Cryptography.Algorithms](https://github.com/dotnet/runtime/tree/master/src/libraries/System.Security.Cryptography.Algorithms) son específicos de la plataforma, dado que las API de almacenamiento y criptografía difieren en cada sistema operativo.
- [System.Collections](https://github.com/dotnet/runtime/tree/master/src/libraries/System.Collections) y [System.Linq](https://github.com/dotnet/runtime/tree/master/src/libraries/System.Linq) son independientes de la plataforma, dado que crean estructuras de datos y funcionan sobre ellas.

## <a name="comparisons-to-other-net-implementations"></a>Comparación con otras implementaciones de .NET

Puede resultar más fácil comprender la naturaleza de .NET Core si se compara con las implementaciones de .NET existentes.

### <a name="comparison-with-net-framework"></a>Comparación con .NET Framework

Microsoft presentó la plataforma .NET en el año 2000, y a partir de ese momento ha ido evolucionando. .NET Framework ha sido la principal implementación de .NET producida por Microsoft durante ese periodo de casi dos décadas.

Las principales diferencias entre .NET Core y .NET Framework son:

- **Modelos de aplicación**: .NET Core no es compatible con todos los modelos de aplicación de .NET Framework. En concreto, no es compatible con los formularios Web Forms ASP.NET ni ASP.NET MVC, pero sí con ASP.NET Core MVC. Además, a partir de .NET Core 3.0, .NET Core también es compatible con WPF y Windows Forms (solo en Windows).
- **API**: .NET Core contiene un amplio subconjunto de bibliotecas de clases base de .NET Framework con una factorización distinta (los nombres de ensamblado son distintos y los miembros expuestos en los tipos difieren en los casos clave). En algunos casos, estas diferencias requieren cambios en el origen del puerto de .NET Core. Para obtener más información, vea [Analizador de portabilidad de .NET](../standard/analyzers/portability-analyzer.md). .NET Core implementa la especificación de la API [.NET Standard](../standard/net-standard.md).
- **Subsistemas**: .NET Core implementa un subconjunto de los subsistemas de .NET Framework, de cara a una implementación y un modelo de programación más sencillos. Por ejemplo, no se admite seguridad de acceso del código (CAS), aunque se admite la reflexión.
- **Plataformas**: .NET Framework admite Windows y Windows Server, mientras que .NET Core también es compatible con macOS y Linux.
- **Código abierto**: .NET Core es código abierto, mientras que un [subconjunto de .NET Framework de solo lectura](https://github.com/microsoft/referencesource) es código abierto.

Aunque .NET Core es única y tiene diferencias significativas con .NET Framework y otras implementaciones de .NET, permite compartir código fácilmente entre estas implementaciones mediante técnicas de uso compartido de origen o binarias.

Debido a que .NET Core admite la instalación en paralelo y el entorno de ejecución es completamente independiente de .NET Framework, puede instalarse en máquinas con .NET Framework instalado sin ningún problema.

### <a name="comparison-with-mono"></a>Comparación con Mono

[Mono](https://www.mono-project.com/) es la implementación multiplataforma original de .NET. Comenzó como una alternativa de [código abierto](https://github.com/mono/mono) para .NET Framework y pasó a tener como objetivo los dispositivos móviles cuando los dispositivos iOS y Android se popularizaron. Se puede considerar un clon de la comunidad de .NET Framework. El equipo de proyecto de Mono se basó en los [estándares de .NET](https://github.com/dotnet/coreclr/blob/master/Documentation/project-docs/dotnet-standards.md) abiertos (en particular, ECMA 335) publicados por Microsoft para proporcionar una implementación compatible.

Las principales diferencias entre .NET Core y Mono:

- **Modelos de aplicación**: Mono admite un subconjunto de los modelos de aplicación de .NET Framework (por ejemplo, Windows Forms) y algunos adicionales para el desarrollo móvil (por ejemplo, [Xamarin.iOS](https://www.xamarin.com/platform)) mediante el producto de Xamarin. .NET Core no es compatible con Xamarin.
- **API**: Mono admite un [gran subconjunto](http://docs.go-mono.com/?link=root%3a%2fclasslib) de las API de .NET Framework, con los mismos nombres de ensamblado y factorización.
- **Plataformas**Mono admite muchas plataformas y CPU.
- **Código abierto**Mono y .NET Core usan la licencia MIT y son proyectos de .NET Foundation.
- **Enfoque**: el foco principal de Mono en los últimos años es plataformas móviles, aunque .NET Core se centra en las cargas de trabajo de la nube y de escritorio.

## <a name="the-future"></a>El futuro

Se anunció que .NET 5 será la próxima versión de .NET Core y representa una unificación de la plataforma. El proyecto pretende mejorar .NET de varias maneras clave:

- Producir un único runtime y un marco de .NET que se pueda usar en todas partes y que tenga comportamientos de runtime y experiencias de desarrollador uniformes.
- Ampliar las funcionalidades de .NET con las mejores características de .NET Core, .NET Framework, Xamarin y Mono.
- Desarrollar el producto a partir de un solo código base que mejore todos los escenarios, que los desarrolladores (Microsoft y la comunidad) puedan expandir y en el que puedan trabajar juntos.

Para obtener más información sobre lo que está planeado para .NET 5, vea [Presentación de .NET 5](https://devblogs.microsoft.com/dotnet/introducing-net-5/).
