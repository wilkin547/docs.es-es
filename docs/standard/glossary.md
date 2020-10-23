---
title: Glosario de .NET
description: Descubra el significado de algunos de los términos usados en la documentación de .NET.
ms.date: 10/13/2020
ms.technology: dotnet-standard
ms.openlocfilehash: 1d9330b68f80da934777cb3aee6d2b3cb52c8256
ms.sourcegitcommit: 39b1d5f2978be15409c189a66ab30781d9082cd8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/14/2020
ms.locfileid: "92050349"
---
# <a name="net-glossary"></a>Glosario de .NET

El objetivo principal de este glosario es aclarar los significados de algunos de los términos y acrónimos que aparecen frecuentemente en la documentación de .NET sin definiciones.

## <a name="aot"></a>AOT

Compilador Ahead Of Time.

Similar a [JIT](#jit), este compilador también convierte [IL](#il) en código de máquina. A diferencia de la compilación JIT, la compilación AOT ocurre antes de que la aplicación se ejecute y, normalmente, se realiza en un equipo diferente. Dado que las cadenas de la herramienta de AOT no se compilan en tiempo de ejecución, no tienen que minimizar el tiempo dedicado a compilar. Esto significa que pueden dedicar más tiempo a la optimización. Puesto que el contexto de AOT es toda la aplicación, el compilador AOT también realiza vinculación entre módulos y el análisis de todo el programa, lo que significa que se siguen todas las referencias y se genera un archivo ejecutable único.

Vea [CoreRT](#corert) y [.NET Native](#net-native).

## <a name="app-model"></a>Modelo de aplicación

Una API específica de la [carga de trabajo](#workload). A continuación se muestran algunos ejemplos:

* ASP.NET
* ASP.NET Web API
* Entity Framework (EF)
* Windows Presentation Foundation (WPF)
* Windows Communication Foundation (WCF)
* Windows Workflow Foundation (WF)
* Windows Forms (WinForms)

## <a name="aspnet"></a>ASP.NET

La implementación original de ASP.NET que se distribuye con .NET Framework.

A veces, ASP.NET es un término genérico que hace referencia a ambas implementaciones de ASP.NET, incluido ASP.NET Core. El significado que lleva el término en una instancia específica se determina según el contexto. Haga referencia a ASP.NET 4.x cuando desee dejar claro que no usa ASP.NET para indicar ambas implementaciones.

Vea la [documentación de ASP.NET](/aspnet/#pivot=aspnet).

## <a name="aspnet-core"></a>ASP.NET Core

Implementación multiplataforma, de alto rendimiento y de código abierto de ASP.NET.

Vea la [documentación de ASP.NET Core](/aspnet/#pivot=core).

## <a name="assembly"></a>ensamblado

Un archivo *.dll*/ *.exe* que puede contener una colección de API a la que puede llamarse mediante aplicaciones u otros ensamblados.

Un ensamblado puede incluir tipos como interfaces, clases, estructuras, enumeraciones y delegados. A veces, se hace referencia a los ensamblados de la carpeta *bin* de un proyecto como *archivos binarios*. Vea también [biblioteca](#library).

## <a name="bcl"></a>BCL

Biblioteca de clases base. También se conoce como *biblioteca de marco*.

Un conjunto de bibliotecas que conforman los espacios de nombres de System.\* (y hasta cierto punto Microsoft.\*). BCL es un marco de nivel inferior de uso general donde se compilan marcos de trabajo de la aplicación de nivel superior, como ASP.NET Core.

El código fuente de la BCL para [.NET 5 (y .NET Core) y versiones posteriores](#net-5-and-later-versions) se encuentra en el [repositorio del entorno de ejecución de .NET](https://github.com/dotnet/runtime). La mayoría de las API de BCL para esta implementación más reciente de .NET también están disponibles en .NET Framework, por lo que puede considerar este código fuente como una bifurcación del código fuente de la BCL de .NET Framework.

## <a name="clr"></a>CLR

Common Language Runtime.

El significado exacto depende del contexto. Common Language Runtime normalmente hace referencia al entorno de ejecución de [.NET Framework](#net-framework) o de [.NET 5 (y .NET Core) y versiones posteriores](#net-5-and-later-versions).

CLR controla la asignación y administración de memoria. CLR es también una máquina virtual que no solo ejecuta aplicaciones, sino que también genera y compila código sobre la marcha mediante un compilador [JIT](#jit).

La implementación de CLR para .NET Framework es solo para Windows.

La implementación de CLR para .NET 5 y versiones posteriores (también conocida como CoreCLR) se crea a partir del mismo código base que el CLR de .NET Framework. Originalmente, CoreCLR era el entorno de ejecución de Silverlight y estaba diseñado para ejecutarse en varias plataformas, concretamente Windows y OS X. Sigue siendo un entorno de ejecución [multiplataforma](#cross-platform) y ahora incluye compatibilidad con muchas distribuciones de Linux.

Vea también [entorno de ejecución](#runtime).

## <a name="core-clr"></a>CoreCLR

Common Language Runtime para [.NET 5 (y .NET Core) y versiones posteriores](#net-5-and-later-versions).

Vea [CLR](#clr).

## <a name="corert"></a>CoreRT

A diferencia de [CLR](#clr), CoreRT no es una máquina virtual, lo que significa que no incluye las funciones para generar y ejecutar código sobre la marcha porque no incluye un compilador [JIT](#jit). En cambio, incluye [GC](#gc), reflexión y capacidad de identificación del tipo en tiempo de ejecución (RTTI). Con todo, su sistema de tipos está diseñado para que no sean necesarios los metadatos para la reflexión. No requerir los metadatos permite tener una cadena de herramientas de [AOT](#aot) que puede vincular metadatos superfluos y (más importante) identificar código que no usa la aplicación. CoreRT está en desarrollo.

Consulte [Introducción a .NET Native u CoreRT](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md).

## <a name="cross-platform"></a>multiplataforma

La capacidad para desarrollar y ejecutar una aplicación que se puede usar en varios sistemas operativos diferentes, como Linux, Windows e iOS, sin tener que volver a escribir específicamente para cada uno de ellos. Esto permite reutilizar el código y posibilita la coherencia entre aplicaciones en distintas plataformas.

## <a name="ecosystem"></a>ecosistema

Todo el software en tiempo de ejecución, las herramientas de desarrollo y los recursos de la comunidad que se usan para compilar y ejecutar aplicaciones de una tecnología determinada.

El término "ecosistema de .NET" se diferencia de términos parecidos como "pila de .NET" en que incluye bibliotecas y aplicaciones de terceros. Aquí se muestra un ejemplo en una frase:

- "La finalidad de [.NET Standard](#net-standard) es establecer una mayor uniformidad en el ecosistema de .NET".

## <a name="framework"></a>marco de trabajo

En general, una colección completa de API que facilita el desarrollo y la implementación de aplicaciones que se basan en una tecnología concreta. En este sentido general, ASP.NET Core y Windows Forms son ejemplos de marcos de trabajo de la aplicación. Vea también [biblioteca](#library).

Los siguientes términos tienen un significado diferente:

- [.NET Framework](#net-framework)
- [Plataforma de destino](#target-framework)
- [TFM (moniker de la plataforma de destino)](#tfm)
- [Aplicación dependiente de la plataforma](../core/deploying/index.md#publish-framework-dependent)

En la documentación de .NET heredada, "marco de trabajo" a veces hace referencia a una [implementación de .NET](#implementation-of-net). Por ejemplo, un artículo puede llamar marco de trabajo a .NET 5.

## <a name="gc"></a>GC

Recolector de elementos no utilizados.

El recolector de elementos no utilizados es una implementación de administración de memoria automática.  GC libera la memoria ocupada por objetos que ya no se usan.

Vea [Recolección de elementos no utilizados](garbage-collection/index.md).

## <a name="il"></a>IL

Lenguaje intermedio.

Los lenguajes .NET de nivel alto, como C#, compilan en un conjunto de instrucciones independiente del hardware, lo que se denomina lenguaje intermedio (IL). A veces, se hace referencia al IL como MSIL (IL de Microsoft) o CIL (Common IL).

## <a name="jit"></a>JIT

Compilador Just-In-Time.

Similar a [AOT](#aot), este compilador convierte el [IL](#il) en código de máquina que entienda el procesador. A diferencia de AOT, la compilación JIT se produce a petición y se lleva a cabo en el mismo equipo en que debe ejecutarse el código. Puesto que la compilación JIT tiene lugar durante la ejecución de la aplicación, el tiempo de compilación es parte del tiempo de ejecución. Por tanto, los compiladores JIT tienen que compensar el tiempo invertido en optimizar el código con el ahorro que puede generar el código resultante. Pero un JIT conoce el hardware real y puede liberar a los desarrolladores de tener que enviar diferentes implementaciones.

## <a name="implementation-of-net"></a>implementación de .NET

Una implementación de .NET incluye lo siguiente:

- Uno o varios entornos de ejecución. Ejemplos: [CLR](#clr) y [CoreRT](#corert).
- Una biblioteca de clases que implementa una versión de .NET Standard y puede incluir API adicionales. Ejemplos: [BCL](#bcl) para [.NET Framework](#net-framework) y para [.NET 5 (y .NET Core) y versiones posteriores](#net-5-and-later-versions).
- Opcionalmente, uno o varios marcos de trabajo de la aplicación. Ejemplos: [ASP.NET](#aspnet), Windows Forms y WPF se incluyen en .NET Framework y .NET 5.
- Opcionalmente, herramientas de desarrollo. Algunas herramientas de desarrollo se comparten entre varias implementaciones.

Ejemplos de implementaciones de .NET:

- [.NET Framework](#net-framework)
- [.NET 5 y versiones posteriores (incluido .NET Core 2.1-3.1](#net-5-and-later-versions)
- [Plataforma universal de Windows (UWP)](#uwp)
- [Mono](#mono)

## <a name="library"></a>biblioteca

Una colección de API que pueden llamarse mediante aplicaciones u otras bibliotecas. Una biblioteca de .NET se compone de uno o varios [ensamblados](#assembly).

Las palabras biblioteca y [marco de trabajo](#framework) se usan a menudo como sinónimos.

## <a name="mono"></a>Mono

Mono es una implementación de .NET [multiplataforma](#cross-platform) y de código abierto que se usa principalmente cuando se requiere un entorno de ejecución pequeño. Es el entorno de ejecución que activa las aplicaciones de Xamarin en Android, Mac, iOS, tvOS y watchOS, y se centra principalmente en aplicaciones que requieren una superficie pequeña.

Admite todas las versiones de .NET Standard publicadas actualmente.

Históricamente, Mono implementaba la API de .NET Framework más grande y emulaba algunas de las funciones más populares en Unix. A veces, se usa para ejecutar aplicaciones de .NET que se basan en estas capacidades en Unix.

Mono se suele usar con un [compilador Just-In-Time](#jit), pero también incluye un [compilador estático completo (compilación Ahead Of Time)](#aot) que se usa en plataformas como iOS.

Consulte la [documentación de Mono](https://www.mono-project.com/docs/).

## <a name="net"></a>.NET

El término que engloba [.NET Standard](#net-standard) y todas las cargas de trabajo e [implementaciones de .NET](#implementation-of-net). Siempre totalmente en mayúsculas, nunca ".Net".

Cuando se publique [.NET 5](#net-5-and-later-versions) (actualmente en versión preliminar), será la implementación de .NET recomendada para todo el nuevo desarrollo de .NET, por lo que en algunos contextos ".NET" implicará ".NET 5 y versiones posteriores".

Vea [Aspectos básicos de .NET](../fundamentals/index.yml).

## <a name="net-5-and-later-versions"></a>.NET 5 y versiones posteriores

Una implementación multiplataforma, de alto rendimiento y de código abierto de .NET. Incluye Common Language Runtime ([CLR](#clr)), un entorno de ejecución [AOT](#aot) ([CoreRT](#corert), en desarrollo), una biblioteca de clases base ([BCL](#bcl)) y el [SDK de .NET](#net-sdk).

Las versiones anteriores de esta implementación de .NET se conocen como .NET Core. .NET 5.0 es la siguiente versión después de .NET Core 3.1. La versión 4 se ha omitido para no confundir esta nueva implementación de .NET con la implementación anterior conocida como [.NET Framework](#net-framework). La versión actual de .NET Framework es 4.8.

Vea [Aspectos básicos de .NET](../fundamentals/index.yml).

## <a name="net-cli"></a>CLI de .NET

Una cadena de herramientas multiplataforma para desarrollar aplicaciones y bibliotecas para [.NET 5 (y .NET Core) y versiones posteriores](#net-5-and-later-versions). También conocida como la CLI de .NET Core.

Vea [CLI de .NET](../core/tools/index.md).

## <a name="net-core"></a>.NET Core

Vea [.NET 5 y versiones posteriores](#net-5-and-later-versions).

## <a name="net-framework"></a>.NET Framework

Una implementación de .NET que se ejecuta solo en Windows. Incluye Common Language Runtime ([CLR](#clr)), la biblioteca de clases base ([BCL](#bcl)) y las bibliotecas de marco de trabajo de la aplicación, como [ASP.NET](#aspnet), Windows Forms y WPF.

Vea [Guía de .NET Framework](../framework/index.yml).

## <a name="net-native"></a>.NET Native

Cadena de herramientas del compilador que genera código nativo Ahead Of Time ([AOT](#aot)), en lugar de Just-In-Time ([JIT](#jit)).

La compilación se produce en el equipo del desarrollador, de forma similar a cómo funcionan el compilador y el enlazador de C++. Quita el código que no se usa y emplea más tiempo en optimizarlo. Extrae código de bibliotecas y lo combina en el archivo ejecutable. El resultado es un módulo único que representa toda la aplicación.

UWP fue el primer marco de trabajo de la aplicación compatible con .NET Native. Ahora, se admite la compilación de aplicaciones de consola nativas para Windows, macOS y Linux.

Vea [Intro to .NET Native and CoreRT](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md) (Introducción a .NET Native y CoreRT).

## <a name="net-sdk"></a>.NET SDK

Conjunto de bibliotecas y herramientas que permiten a los desarrolladores crear aplicaciones y bibliotecas de .NET para [.NET 5 (y .NET Core) y versiones posteriores](#net-5-and-later-versions). También se conoce como el SDK de .NET Core.

Incluye la [CLI de .NET](#net-cli) para compilar aplicaciones, el entorno de ejecución, y las bibliotecas de .NET para compilar y ejecutar aplicaciones, y el ejecutable dotnet (*dotnet.exe*) que ejecuta comandos de la CLI y ejecuta aplicaciones.

Vea [Información general sobre el SDK de .NET](../core/sdk.md).

## <a name="net-standard"></a>.NET Standard

Una especificación formal de las API de .NET que están disponibles en cada implementación de .NET.

La especificación de .NET Standard a veces se denomina "biblioteca" en la documentación. Dado que una biblioteca incluye implementaciones de API, no solo especificaciones (interfaces), es confuso denominar "biblioteca" a .NET Standard.

Vea [.NET Standard](net-standard.md).

## <a name="ngen"></a>NGEN

Generación (de imágenes) nativas.

Esta tecnología se puede considerar como un compilador [JIT](#jit) persistente. Normalmente, compila código en el equipo en que se ejecuta el código, pero la compilación se suele producir durante la instalación.

## <a name="package"></a>paquete

Un paquete de NuGet &mdash; o simplemente un paquete &mdash; es un archivo *.zip* con uno o varios ensamblados del mismo nombre junto con metadatos adicionales, como el nombre del autor.

El archivo *.zip* tiene una extensión *.nupkg* y puede contener recursos (como archivos *.dll* y *.xml*) para usar con varios marcos de destino y versiones. Cuando se instala en una aplicación o biblioteca, se seleccionan los recursos adecuados en función de la plataforma de destino especificada por la aplicación o biblioteca. Los recursos que definen la interfaz se encuentran en la carpeta *ref* y los recursos que definen la implementación se encuentran en la carpeta *lib*.

## <a name="platform"></a>platform

Un sistema operativo y el hardware en que se ejecuta, como Windows, macOS, Linux, iOS y Android.

Aquí tiene ejemplos de uso en frases:

- ".NET Core es una implementación multiplataforma de .NET".
- "Los perfiles de PCL representan plataformas de Microsoft, mientras que .NET Standard es independiente de la plataforma".

La documentación heredada de .NET a veces usa el término "plataforma de .NET" para referirse a una [implementación de .NET](#implementation-of-net) o a [la pila de .NET](#stack) que incluyen todas las implementaciones. Estos dos usos tienden a confundirse con el significado principal (sistema operativo o hardware), por tanto, tratamos de evitar estos usos.

"Plataforma" tiene un significado diferente en "plataforma del desarrollador", ya que hace referencia al software que proporciona herramientas y bibliotecas para compilar y ejecutar aplicaciones. .NET es una plataforma para el desarrollo de contenido de código abierto multiplataforma que permite crear una gran variedad de tipos de aplicaciones.

## <a name="runtime"></a>motor en tiempo de ejecución

En términos generales, el entorno de ejecución de un programa administrado. El sistema operativo forma parte del entorno de ejecución, pero no del entorno de ejecución .NET. Estos son algunos ejemplos de los entornos de ejecución de .NET en este sentido de la palabra:

- Common Language Runtime ([CLR](#clr))
- .NET Native (para UWP)
- Entorno de ejecución Mono

El término "entorno de ejecución" tiene un significado diferente en los siguientes contextos:

* [Página de descarga de .NET](https://dotnet.microsoft.com/download).

  Aquí, "entorno de ejecución" se refiere a [CLR](#clr) y a [BCL](#bcl) (las bibliotecas de marco), que puede descargar e instalar en una máquina para ejecutar aplicaciones [dependientes de la plataforma](../core/deploying/index.md#publish-framework-dependent) en la máquina.

* [Identificador de entorno de ejecución (RID)](../core/rid-catalog.md) para [.NET 5 (y .NET Core) y versiones posteriores](#net-5-and-later-versions).

  Aquí, "entorno de ejecución" hace referencia a la plataforma del sistema operativo y a la arquitectura de la CPU en la que se ejecuta una aplicación .NET, por ejemplo, `linux-x64`.

A veces, la documentación heredada de .NET usa "entorno de ejecución" para indicar una [implementación de .NET](#implementation-of-net), como en los siguientes ejemplos:

- "Los diversos entornos de ejecución .NET implementan versiones concretas de .NET Standard".
- "Las bibliotecas diseñadas para ejecutarse en varios entornos de ejecución deben tener como destino este marco de trabajo". (Hace referencia a .NET Standard).
- "Los diversos entornos de ejecución .NET implementan versiones concretas de .NET Standard. … Cada versión del entorno de ejecución de .NET anuncia la última versión de .NET Standard que admite...".

## <a name="stack"></a>pila

Un conjunto de tecnologías de programación que se usan para compilar y ejecutar aplicaciones.

La "pila de .NET" hace referencia a .NET Standard y a todas las implementaciones de .NET. La frase "una pila de .NET" puede hacer referencia a una implementación de .NET.

## <a name="target-framework"></a>versión de .NET Framework de destino

La colección de API de las que depende una aplicación o biblioteca de .NET.

Una aplicación o biblioteca puede tener como destino una versión de .NET Standard (por ejemplo, .NET Standard 2.0), que es la especificación de un conjunto estándar de API de todas las implementaciones de .NET. Una aplicación o biblioteca también puede tener como destino una versión de una implementación específica de .NET; en este caso, obtiene acceso a las API específicas de la implementación. Por ejemplo, una aplicación que tenga como destino Xamarin.iOS obtiene acceso a contenedores de la API de iOS proporcionados por Xamarin.

Para algunas plataformas de destino (por ejemplo, .NET Framework), las API disponibles se definen mediante los ensamblados que una implementación de .NET instala en un sistema y pueden incluir las API del marco de trabajo de la aplicación (por ejemplo, ASP.NET o Windows Forms). Para plataformas de destino basadas en paquetes (por ejemplo, .NET Standard y .NET Core), las API se definen mediante los paquetes instalados en la aplicación o biblioteca. En ese caso, la plataforma de destino especifica implícitamente un paquete que hace referencia a todos los paquetes que forman el marco de trabajo.

Vea [Plataformas de destino](frameworks.md).

## <a name="tfm"></a>TFM

Moniker de la plataforma de destino.

Un formato de token normalizado para especificar la plataforma de destino de una aplicación o biblioteca de .NET. Se suele hacer referencia a las plataformas de destino mediante un nombre corto, como `net462`. Los TFM de formato largo (como .NETFramework,Version=4.6.2) existen, pero no se suelen usar para especificar una plataforma de destino.

Vea [Plataformas de destino](frameworks.md).

## <a name="uwp"></a>UWP

Plataforma universal de Windows.

Una implementación de .NET que se usa para compilar aplicaciones Windows modernas y táctiles y software para Internet de las cosas (IoT). Se ha diseñado para unificar los diferentes tipos de dispositivos de destino, incluidos equipos, tabletas, teléfonos e incluso la consola Xbox. UWP proporciona muchos servicios, como una tienda de aplicaciones centralizada, un entorno de ejecución (AppContainer) y un conjunto de API de Windows para usar en lugar de Win32 (WinRT). Pueden escribirse aplicaciones en C++, C#, Visual Basic y JavaScript. Al usar C# y Visual Basic, .NET 5 (y .NET Core), así como sus versiones posteriores, proporcionan las API de .NET.

## <a name="workload"></a>carga de trabajo

Un tipo de aplicación que alguien compila. Más genérico que [modelo de aplicación](#app-model). Por ejemplo, en la parte superior de todas las páginas de documentación de .NET, incluida esta, hay una lista desplegable para **Cargas de trabajo**, que permite cambiar a la documentación de **Web**, **Dispositivos móviles**, **Nube**, **Escritorio** y **Machine Learning y datos**.

En algunos contextos, *carga de trabajo* hace referencia a una colección de características de Visual Studio que puede elegir instalar para admitir un tipo determinado de aplicación. Para obtener un ejemplo, vea [Selección de una carga de trabajo](../core/install/windows.md#select-a-workload).

## <a name="see-also"></a>Vea también

- [Aspectos básicos de .NET](../fundamentals/index.yml)
- [Guía de .NET Framework](../framework/index.yml)
- [ASP.NET Overview](/aspnet/index#pivot=aspnet) (Información general de ASP.NET)
- [ASP.NET Core Overview](/aspnet/index#pivot=core) (Información general de ASP.NET Core)
