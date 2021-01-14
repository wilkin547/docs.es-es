---
title: Introducción e información general de .NET
description: Obtenga información sobre .NET, una plataforma de desarrollo gratuita de código abierto para compilar muchos tipos de aplicaciones.
author: tdykstra
ms.date: 11/16/2020
ms.custom: updateeachrelease
ms.openlocfilehash: 0adc348c1fc340fe481d9987cdbe28c6cf8b065d
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938681"
---
# <a name="introduction-to-net"></a>Introducción a .NET

.NET es una plataforma de desarrollo gratuita de código abierto para compilar muchos tipos de aplicaciones, como las siguientes:

* [Aplicaciones web, API web y microservicios](/aspnet/core/introduction-to-aspnet-core#recommended-learning-path)
* [Funciones sin servidor en la nube](/azure/azure-functions/functions-create-first-function-vs-code?pivots=programming-language-csharp)
* [Aplicaciones nativas de la nube](../architecture/cloud-native/index.md)
* [Aplicaciones móviles](https://dotnet.microsoft.com/learn/xamarin/hello-world-tutorial/intro)
* Aplicaciones de escritorio
  * [Windows WPF](/dotnet/desktop/wpf/)
  * [Windows Forms](/dotnet/desktop/winforms/)
  * [Plataforma universal de Windows (UWP)](/windows/uwp/get-started/create-a-hello-world-app-xaml-universal)
* [Juegos](https://dotnet.microsoft.com/apps/games)
* [Internet de las cosas (IoT)](/dotnet/iot)
* [Aprendizaje automático](../machine-learning/index.yml)
* [Aplicaciones de consola](tutorials/with-visual-studio-code.md)
* [Servicios de Windows](/aspnet/core/host-and-deploy/windows-service)

Comparta la funcionalidad entre diferentes aplicaciones y tipos de aplicación mediante [bibliotecas de clases](../standard/class-libraries.md).

Con .NET, el código y los archivos del proyecto tienen el mismo aspecto, con independencia del tipo de aplicación que compile. Con cada aplicación tiene acceso a las mismas funcionalidades de tiempo de ejecución, API y lenguaje.

## <a name="cross-platform"></a>Multiplataforma

Puede crear aplicaciones .NET para muchos sistemas operativos, entre los que se incluyen los siguientes:

* Windows
* macOS
* Linux
* Android
* iOS
* tvOS
* watchOS

Las arquitecturas de procesador compatibles incluyen las siguientes:

* x64
* x86
* ARM32
* ARM64

.NET le permite usar funcionalidades específicas de la plataforma, como las API del sistema operativo. Algunos ejemplos son Windows Forms y WPF en Windows, y los enlaces nativos a cada plataforma móvil desde Xamarin.

Para obtener más información, vea [Directiva de ciclo de vida del sistema operativo compatible](https://github.com/dotnet/core/blob/master/os-lifecycle-policy.md) y [Catálogo de .NET RID](rid-catalog.md).

## <a name="open-source"></a>Código abierto

.NET es de código abierto y usa las licencias de [MIT y Apache 2](https://github.com/dotnet/runtime/blob/master/LICENSE.TXT). .NET es un proyecto de [.NET Foundation](https://dotnetfoundation.org/).

Para obtener más información, vea la [lista de repositorios de proyectos en GitHub.com](https://github.com/dotnet/core/blob/master/Documentation/core-repos.md).

## <a name="support"></a>Soporte técnico

Microsoft admite .NET en Windows, macOS y Linux. Se actualiza de forma periódica por motivos de seguridad y calidad, el segundo martes de cada mes.

Las distribuciones binarias de .NET de Microsoft se compilan y prueban en servidores mantenidos por Microsoft en Azure y siguen los procedimientos de seguridad e ingeniería de Microsoft.

[Red Hat admite .NET](https://developers.redhat.com/topics/dotnet/) en Red Hat Enterprise Linux (RHEL). Red Hat y Microsoft colaboran para asegurarse de que .NET Core funciona bien en RHEL.

[Tizen admite .NET ](https://developer.tizen.org/development/training/.net-application) en las plataformas Tizen.

Para obtener más información, vea [Versiones y compatibilidad con .NET Core y .NET 5](releases-and-support.md).

## <a name="tools-and-productivity"></a>Herramientas y productividad

.NET ofrece una selección de lenguajes, entornos de desarrollo integrados (IDE) y otras herramientas.

### <a name="programming-languages"></a>Lenguajes de programación

.NET admite tres lenguajes de programación:

* [C#](../csharp/index.yml)

  C# (pronunciado "si sharp" en inglés) es un lenguaje de programación moderno, basado en objetos y con seguridad de tipos. C# tiene sus raíces en la familia de lenguajes C, y a los programadores de C, C++, Java y JavaScript les resultará familiar inmediatamente.

* [F#](../fsharp/index.yml)

  El lenguaje F# admite los modelos de programación funcional, orientada a objetos e imperativa.

* [Visual Basic](../visual-basic/index.yml)

  Entre los lenguajes de .NET, la sintaxis de Visual Basic es la más parecida al lenguaje humano normal, lo que facilita su aprendizaje. A diferencia de C# y F#, para los que Microsoft desarrolla nuevas características de forma activa, el lenguaje Visual Basic es estable. Visual Basic no es compatible con las aplicaciones web, pero sí con las API web.

Estas son algunas de las funcionalidades que admiten los lenguajes de .NET:

* [Seguridad de tipos](../standard/base-types/common-type-system.md)
* Inferencia de tipos: [C#](../csharp/programming-guide/types/index.md#specifying-types-in-variable-declarations), [F#](../fsharp/language-reference/type-inference.md), [Visual Basic](../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
* [Tipos genéricos](../standard/generics.md)
* [Delegados](../standard/delegates-lambdas.md)
* [Expresiones lambda](../standard/delegates-lambdas.md)
* [Eventos](../standard/events/index.md)
* [Excepciones](../standard/exceptions/index.md)
* [Atributos](../standard/attributes/index.md)
* [Código asincrónico](../standard/async.md)
* [Programación en paralelo en .NET](../standard/parallel-programming/index.md)
* [Analizadores de código](../fundamentals/code-analysis/overview.md)

### <a name="ides"></a>IDE

Los entornos de desarrollo integrado para .NET incluyen los siguientes:

* [Visual Studio](https://visualstudio.microsoft.com/vs/)

  Solo se ejecuta en Windows. Dispone de una amplia funcionalidad integrada diseñada para trabajar con .NET. La edición Community es gratuita para estudiantes, colaboradores de código abierto y particulares.

* [Visual Studio Code](https://code.visualstudio.com/)

  Es compatible con Windows, macOS y Linux. De código abierto y gratuito. Hay extensiones disponibles para trabajar con lenguajes de .NET.

* [Visual Studio para Mac](https://visualstudio.microsoft.com/vs/mac/)

  Solo se ejecuta en macOS. Para desarrollar aplicaciones y juegos de .NET para iOS, Android y la web.

* [GitHub Codespaces](https://github.com/features/codespaces)

  Un entorno de Visual Studio Code en línea, actualmente en versión beta.

### <a name="sdk-and-runtimes"></a>SDK y entornos de ejecución

El [SDK de .NET](sdk.md) es un conjunto de bibliotecas y herramientas para desarrollar y ejecutar aplicaciones .NET.

Al [descargar .NET](https://dotnet.microsoft.com/download/dotnet-core/), puede elegir el SDK o un *entorno de ejecución*, como el de .NET o el de ASP.NET Core. Instale un entorno de ejecución en un equipo que quiera preparar para ejecutar aplicaciones .NET. Instale el SDK en un equipo que quiera usar para el desarrollo. Al descargar el SDK, obtiene automáticamente los entornos de ejecución.

La descarga del SDK incluye los componentes siguientes:

* La [CLI de .NET](tools/index.md). Herramientas de la línea de comandos que puede usar para scripts de desarrollo local e integración continua.
* El [controlador](tools/index.md#driver) `dotnet`. Un comando de la CLI que ejecuta aplicaciones dependientes del marco.
* Los compiladores de los lenguajes de programación [Roslyn](https://github.com/dotnet/roslyn) y [F#](https://github.com/microsoft/visualfsharp).
* El motor de compilación [MSBuild](/visualstudio/msbuild/msbuild).
* El [entorno de ejecución de .NET](#clr). Proporciona un sistema de tipos, la carga de ensamblados, un recolector de elementos no utilizados, interoperabilidad nativa y otros servicios básicos.
* [Bibliotecas tiempo de ejecución](#runtime-libraries). Proporciona tipos de datos primitivos y utilidades fundamentales.
* El entorno de ejecución de ASP.NET Core. Proporciona servicios básicos para las aplicaciones conectadas a Internet, como aplicaciones web, aplicaciones de IoT y back-ends para dispositivos móviles.
* El entorno de ejecución de escritorio. Proporciona servicios básicos para las aplicaciones de escritorio de Windows, como Windows Forms y WPF.

La descarga del entorno de ejecución incluye los componentes siguientes:

* Opcionalmente, el escritorio o el entorno de ejecución de ASP.NET Core.
* El [entorno de ejecución de .NET](#clr). Proporciona un sistema de tipos, la carga de ensamblados, un recolector de elementos no utilizados, interoperabilidad nativa y otros servicios básicos.
* [Bibliotecas tiempo de ejecución](#runtime-libraries). Proporciona tipos de datos primitivos y utilidades fundamentales.
* El [controlador](tools/index.md#driver) `dotnet`. Un comando de la CLI que ejecuta aplicaciones dependientes del marco.

Para obtener más información, vea los siguientes recursos:

* [Información general sobre el SDK de .NET](sdk.md)
* [Información general sobre la CLI de .NET](tools/index.md)
* [comando dotnet](tools/dotnet.md)

### <a name="project-system-and-msbuild"></a>Sistema del proyecto y MSBuild

Una aplicación .NET se crea a partir de código fuente mediante [MSBuild](/visualstudio/msbuild/msbuild). Un archivo del proyecto ( *.csproj*, *.fsproj* o *.vbproj*) especifica [destinos](/visualstudio/msbuild/msbuild-targets) y [tareas](/visualstudio/msbuild/msbuild-tasks) asociadas que se encargan de compilar, empaquetar y publicar código. Existen identificadores de SDK que hacen referencia a colecciones estándar de destinos y tareas. El uso de estos identificadores ayuda a reducir el tamaño de los archivos del proyecto y facilita el trabajo con ellos. Por ejemplo, este es un archivo del proyecto para una aplicación de consola:

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net5.0</TargetFramework>
  </PropertyGroup>
</Project>
```

Y este es otro para una aplicación web:

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">
  <PropertyGroup>
    <TargetFramework>net5.0</TargetFramework>
  </PropertyGroup>
</Project>
```

En estos ejemplos, el atributo `Sdk` del elemento `Project` especifica un conjunto de destinos y tareas de MSBuild que compilan el proyecto.  El elemento `TargetFramework` especifica la versión de .NET de la que depende la aplicación. Puede editar el archivo del proyecto para agregar destinos y tareas adicionales específicos del proyecto.

Para obtener más información, vea [Información general sobre el SDK de proyectos .NET](project-sdk/overview.md) y [Plataformas de destino](../standard/frameworks.md).

### <a name="cicd"></a>CI/CD

MSBuild y la CLI de .NET se pueden usar con diversas herramientas y entornos de integración continua, como:

* [Acciones de GitHub](https://github.com/features/actions)
* [Azure DevOps](/azure/devops/user-guide/what-is-azure-devops)
* [CAKE](https://cakebuild.net/)
* [FAKE](https://fake.build/)

Para obtener más información, vea [Uso del SDK de .NET y herramientas de integración continua (CI)](tools/using-ci-with-cli.md)

### <a name="nuget"></a>NuGet

[NuGet](/nuget/what-is-nuget) es un administrador de paquetes de código abierto diseñado para .NET. Un paquete NuGet es un archivo *.zip* con la extensión `.nupkg` que contiene código compilado (archivos DLL), otros archivos relacionados con ese código y un manifiesto descriptivo que incluye información como el número de versión del paquete. Los desarrolladores con código para compartir crean paquetes y los publican en [nuget.org](https://nuget.org) o un host privado. Los desarrolladores que quieren usar código compartido agregan un paquete a su proyecto y, después, pueden llamar a la API expuesta por el paquete en el código del proyecto.

Para obtener más información, vea la [documentación de NuGet](/nuget/).

### <a name="net-interactive"></a>Documentación interactiva de .NET

.NET Interactive es un grupo de API y herramientas de la CLI que permiten a los usuarios crear experiencias interactivas en la web, markdown y cuadernos.

Para obtener más información, vea los siguientes recursos:

* [Tutorial de .NET en el explorador](https://dotnet.microsoft.com/learn/dotnet/in-browser-tutorial/1)
* [Uso de cuadernos de .NET con Jupyter en el equipo](https://github.com/dotnet/interactive/blob/main/docs/NotebooksLocalExperience.md)
* [Documentación de .NET Interactive](https://github.com/dotnet/interactive/blob/main/docs/README.md)

## <a name="execution-models"></a>Modelos de ejecución

Las aplicaciones .NET ejecutan [código administrado](../standard/managed-code.md) en un entorno de tiempo de ejecución conocido como Common Language Runtime (CLR).

### <a name="clr"></a>CLR

El [CLR](../standard/clr.md) de .NET es un entorno de ejecución multiplataforma que incluye compatibilidad con Windows, macOS y Linux. CLR controla la asignación y administración de memoria. El CLR es además una máquina virtual que no solo ejecuta aplicaciones, sino que también genera y compila código mediante un compilador Just-In-Time (JIT).

Para obtener más información, vea [Información general de Common Language Runtime (CLR)](../standard/clr.md).

### <a name="jit-compiler-and-il"></a>Compilador JIT y lenguaje intermedio

Los lenguajes .NET de nivel alto, como C#, compilan en un conjunto de instrucciones independiente del hardware, lo que se denomina lenguaje intermedio (IL). Cuando se ejecuta una aplicación, el compilador JIT convierte el lenguaje intermedio en código máquina comprensible para el procesador. La compilación JIT se produce en el mismo equipo en el que se va a ejecutar el código.

Como la compilación JIT tiene lugar durante la ejecución de la aplicación, el tiempo de compilación es parte del tiempo de ejecución. Por tanto, los compiladores JIT tienen que compensar el tiempo invertido en optimizar el código con el ahorro que puede generar el código resultante. Pero un compilador JIT conoce el hardware real y puede liberar a los desarrolladores de tener que enviar diferentes implementaciones para distintas plataformas.

El compilador JIT de .NET puede realizar la *compilación en niveles*, lo que significa que puede volver a compilar métodos concretos en tiempo de ejecución. Esta característica le permite compilar rápidamente mientras todavía puede generar una versión muy optimizada del código para los métodos que se usan con frecuencia.

Para obtener más información, vea [Proceso de ejecución administrada](../standard/managed-execution-process.md) y [Compilación en niveles](whats-new/dotnet-core-3-0.md#tiered-compilation).

### <a name="aot-compiler"></a>Compilador AOT

La experiencia predeterminada para la mayoría de las cargas de trabajo de .NET es el compilador JIT, pero .NET ofrece dos formas de compilación anticipada (AOT):

* Algunos escenarios requieren una compilación AOT del 100 %. Un ejemplo es [iOS](/xamarin/ios/).
* En otros escenarios, la mayor parte del código de una aplicación se compilada mediante AOT, pero otra mediante JIT. Algunos patrones de código no son descriptivos para AOT (como los genéricos). Un ejemplo de este tipo de compilación AOT es la opción de publicación [listo para ejecutar](whats-new/dotnet-core-3-0.md#readytorun-images). Esta forma de AOT ofrece las ventajas de AOT sin sus inconvenientes.

### <a name="automatic-memory-management"></a>Administración de memoria automática

El *recolector de elementos no utilizados* (GC) administra la asignación y liberación de la memoria para las aplicaciones. Cada vez que el código crea un objeto, el CLR le asigna memoria del [montón administrado](../standard/garbage-collection/fundamentals.md#the-managed-heap). Siempre que haya espacio de direcciones disponible en el montón nativo, el motor en tiempo de ejecución continúa asignando espacio a los objetos nuevos. Cuando no queda suficiente espacio de direcciones libre, el GC comprueba los objetos del montón administrado que la aplicación ya no usa. Después, reclama esa memoria.

El recolector de elementos no utilizados es uno de los servicios del CLR que ayudan a garantizar la *protección de la memoria*. Un programa tiene protección de la memoria si tiene acceso solo a la memoria asignada. Por ejemplo, el entorno de ejecución garantiza que una aplicación no accede a memoria sin asignar más allá de los límites de una matriz.

Para obtener más información, vea [Administración de memoria automática](../standard/automatic-memory-management.md) y [Fundamentos de la recolección de elementos no utilizados](../standard/garbage-collection/fundamentals.md).

### <a name="working-with-unmanaged-resources"></a>Trabajar con recursos no administrados

En ocasiones el código debe hacer referencia a *recursos no administrados*. Los recursos no administrados son recursos que el entorno de ejecución .NET no mantiene de forma automática. Por ejemplo, un identificador de archivo es un recurso no administrado. Un objeto <xref:System.IO.FileStream> es un objeto administrado, pero hace referencia a un identificador de archivo, que es uno no administrado. Cuando haya acabado de usar <xref:System.IO.FileStream>, tiene que liberar de forma explícita el identificador de archivo.

En .NET, los objetos que hacen referencia a recursos no administrados implementan la interfaz de <xref:System.IDisposable>. Cuando haya acabado de usar el objeto, deberá llamar al método <xref:System.IDisposable.Dispose> del objeto, que es el responsable de liberar cualquier recurso no administrado. Los lenguajes de .NET proporcionan una práctica instrucción `using` ([C#](../csharp/language-reference/keywords/using.md), [F#](../fsharp/language-reference/resource-management-the-use-keyword.md), [VB](../visual-basic/language-reference/statements/using-statement.md)) que garantiza la llamada al método `Dispose`.

Para obtener más información, vea [Limpieza de recursos no administrados](../standard/garbage-collection/unmanaged.md).

## <a name="deployment-models"></a>Modelos de implementación

Las aplicaciones .NET se pueden publicar en dos modos diferentes:

* La publicación de una aplicación como *independiente* genera un archivo ejecutable que incluye el [entorno de ejecución](#sdk-and-runtimes) y las [bibliotecas](#runtime-libraries) de .NET, así como la aplicación y sus dependencias. Los usuarios de la aplicación pueden ejecutarla en un equipo que no tenga instalado el entorno de ejecución de .NET. Las aplicaciones independientes son específicas de la plataforma y, opcionalmente, se pueden publicar mediante una forma de [compilación AOT](#aot-compiler).

* La publicación de una aplicación como *dependiente del marco* genera un archivo ejecutable y archivos binarios (archivos *.dll*) que solo incluyen la propia aplicación y sus dependencias. Los usuarios de la aplicación tienen que instalar el [entorno de ejecución](#sdk-and-runtimes) de .NET por separado. El archivo ejecutable es específico de la plataforma, pero los archivos *.dll* de las aplicaciones dependientes del marco son multiplataforma.

  Puede instalar varias versiones del tiempo de ejecución en paralelo para ejecutar aplicaciones dependientes del marco destinadas a otras versiones del tiempo de ejecución. Para obtener más información, vea [Plataformas de destino](../standard/frameworks.md).

Los archivos ejecutables se generan para plataformas de destino concretas, que se especifican con un [ identificador en tiempo de ejecución (RID)](rid-catalog.md).

Para obtener más información, vea [Información general sobre la publicación de aplicaciones .NET](deploying/index.md) e [Introducción a .NET y Docker](docker/introduction.md).

## <a name="runtime-libraries"></a>Bibliotecas en tiempo de ejecución

.NET tiene un amplio conjunto estándar de bibliotecas de clases, conocidas como [bibliotecas en tiempo de ejecución](../standard/glossary.md#runtime), [bibliotecas de marco](../standard/glossary.md#framework-libraries) o la [biblioteca de clases base (BCL)](../standard/glossary.md#bcl). Estas bibliotecas proporcionan implementaciones para muchos tipos de propósito general y específicos de la carga de trabajo, y funcionalidad de la utilidad.

Estos son algunos ejemplos de los tipos definidos en las bibliotecas en tiempo de ejecución de .NET:

* Tipos primitivos, como <xref:System.Boolean?displayProperty=nameWithType> y <xref:System.Int32?displayProperty=nameWithType>.
* Colecciones, como <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> y <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType>.
* Tipos de datos, como <xref:System.Data.DataSet?displayProperty=nameWithType> y <xref:System.Data.DataTable?displayProperty=nameWithType>.
* Tipos de utilidad de red, como <xref:System.Net.Http.HttpClient?displayProperty=nameWithType>.
* Tipos de utilidad de [E/S de archivos y secuencias](../standard/io/index.md), como <xref:System.IO.FileStream?displayProperty=nameWithType> y <xref:System.IO.TextWriter?displayProperty=nameWithType>.
* Tipos de utilidad de [serialización](../standard/serialization/index.md), como <xref:System.Text.Json.JsonSerializer?displayProperty=nameWithType> y <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>.
* Tipos de alto rendimiento, como <xref:System.Span%601?displayProperty=nameWithType>, <xref:System.Numerics.Vector?displayProperty=nameWithType> y [Canalizaciones](../standard/io/pipelines.md).

Para obtener más información, vea [Introducción a las bibliotecas en tiempo de ejecución](../standard/runtime-libraries-overview.md). El código fuente de las bibliotecas está en [el repositorio dotnet/runtime de GitHub](https://github.com/dotnet/runtime/tree/master/src/libraries).

### <a name="extensions-to-the-runtime-libraries"></a>Extensiones de las bibliotecas en tiempo de ejecución

Las bibliotecas de algunas funcionalidades de aplicación de uso común no se incluyen en las bibliotecas en tiempo de ejecución, sino que están disponibles en paquetes NuGet como los siguientes:

| Paquete de NuGet | Documentación |
|---------|---------|
| [Microsoft.Extensions.Hosting](https://www.nuget.org/packages/Microsoft.Extensions.Hosting) | [Administración de la duración de la aplicación (host genérico)](extensions/generic-host.md) |
| [Microsoft.Extensions.DependencyInjection](https://www.nuget.org/packages/Microsoft.Extensions.DependencyInjection) | [Inserción de dependencias (ID)](extensions/dependency-injection.md)
| [Microsoft.Extensions.Configuration](https://www.nuget.org/packages/Microsoft.Extensions.Configuration) | [Configuración](extensions/configuration.md) |
| [Microsoft.Extensions.Logging](https://www.nuget.org/packages/Microsoft.Extensions.Logging) | [Logging](extensions/logging.md) |
| [Microsoft.Extensions.Options](https://www.nuget.org/packages/Microsoft.Extensions.Options) | [Patrón de opciones](extensions/options.md) |

Para obtener más información, vea [el repositorio dotnet/extensions en GitHub](https://github.com/dotnet/extensions).

## <a name="data-access"></a>Acceso a datos

.NET proporciona un asignador relacional/de objeto (ORM) y una manera de escribir consultas SQL en el código.

### <a name="entity-framework-core"></a>Entity Framework Core

Entity Framework (EF) Core es una tecnología de acceso a datos multiplataforma y de [código abierto](https://github.com/aspnet/EntityFrameworkCore) que puede servir como ORM. EF Core le permite trabajar con una base de datos si hace referencia a los objetos .NET en el código. Reduce la cantidad de código de acceso a datos que, de lo contrario, tendría que escribir y probar. EF Core es compatible con muchos motores de base de datos.

Para obtener más información, vea [Entity Framework Core](/ef/core/) y [Proveedores de base de datos](/ef/core/providers/).

### <a name="linq"></a>LINQ

Language Integrated Query (LINQ) permite escribir código declarativo para trabajar en los datos. Los datos pueden estar en muchos formatos (como objetos en memoria, una base de datos SQL o un documento XML), pero el código LINQ que escriba normalmente no es diferente según el origen de datos.

Para obtener más información, vea [Información general de LINQ (Language Integrated Query)](../standard/linq/index.md).

## <a name="net-terminology"></a>Terminología de .NET

Para entender la documentación de .NET, puede ser de ayuda saber cómo ha cambiado el uso de algunos términos con el tiempo.

### <a name="net-core-and-net-5"></a>.NET Core y .NET 5

En 2002, Microsoft publicó [.NET Framework](../framework/get-started/overview.md), una plataforma de desarrollo para la creación de aplicaciones Windows. En la actualidad, .NET Framework se encuentra en la versión 4.8 y [Microsoft todavía la admite](https://dotnet.microsoft.com/platform/support/policy/dotnet-framework).

En 2014, Microsoft comenzó a escribir un sucesor multiplataforma de código abierto para .NET Framework. Esta nueva implementación de .NET se denominó .NET Core hasta que alcanzó la versión 3.1. La siguiente versión después de .NET Core 3.1 es .NET 5.0, que actualmente se encuentra en versión preliminar. Se omitió el número de versión 4 para evitar la confusión entre esta implementación de .NET y .NET Framework 4.8. El nombre "Core" se quitó para aclarar que ahora esta es la implementación principal de .NET.

Este artículo trata sobre .NET 5, pero en gran parte de la documentación de .NET 5 todavía se incluyen referencias a ".NET Core" o ".NET Framework". Además, "Core" permanece en los nombres [ASP.NET Core](/aspnet/core/) y [Entity Framework Core](/ef/core/).

En la documentación también se hace referencia a .NET Standard. [.NET Standard](../standard/net-standard.md) es una especificación de API que permite desarrollar bibliotecas de clases para varias implementaciones de .NET.

Para obtener más información, vea [Componentes de la arquitectura de .NET](../standard/components.md).

### <a name="overloaded-terms"></a>Términos sobrecargados

Parte de la terminología de .NET puede resultar confusa porque la misma palabra se usa de maneras diferentes en contextos distintos. Estos son algunos de los casos más destacados:

* **motor en tiempo de ejecución**

  |Context  |Significado de "runtime" |
  |---------|---------|
  | [Common Language Runtime (CLR)](#clr)| El entorno de ejecución de un programa administrado. El sistema operativo forma parte del entorno de tiempo de ejecución, pero no del tiempo de ejecución de .NET. |
  | [Entorno de ejecución de .NET en la página de descarga de .NET](https://dotnet.microsoft.com/download/dotnet-core) | El [CLR](#clr) y las [bibliotecas en tiempo de ejecución](#runtime-libraries), que de manera conjunta proporcionan compatibilidad para ejecutar aplicaciones [dependientes del marco de trabajo](#deployment-models). En la página también se ofrecen opciones de tiempo de ejecución para aplicaciones de servidor de ASP.NET Core y aplicaciones de escritorio de Windows. |
  | [Identificador en tiempo de ejecución (RID)](rid-catalog.md) | La plataforma del sistema operativo y la arquitectura de la CPU en la que se ejecuta una aplicación .NET. Por ejemplo: Windows x64, Linux x64. |

* **marco de trabajo**

  |Context  | Significado de "marco" |
  |---------|---------------------|
  | .NET Framework | La implementación original de .NET, solo para Windows. La "F" de "Framework" está en mayúsculas. |
  | versión de .NET Framework de destino | La colección de API de las que depende una aplicación o biblioteca de .NET. Ejemplos: .NET Core 3.1, .NET Standard 2.0 |
  | Moniker de la plataforma de destino (TFM)  | TFM es un formato de token normalizado para especificar la plataforma de destino de una aplicación o biblioteca de .NET. Ejemplo: `net462` para .NET Framework 4.6.2. |
  | Aplicación dependiente de la plataforma | Una aplicación que solo se puede ejecutar en un equipo en el que se ha instalado el tiempo de ejecución desde la [página de descargas de .NET](https://dotnet.microsoft.com/download/dotnet-core). En este caso, "marco" es lo mismo que el "tiempo de ejecución" que se descarga de la página de descargas de .NET. |
  | Bibliotecas de marco | A veces se usa como sinónimo de las [bibliotecas en tiempo de ejecución](#runtime-libraries). |

* **SDK**

  |Context  | Significado de "SDK" |
  |---------|---------------|
  | [SDK en la página de descargas de .NET](#sdk-and-runtimes)  | Una colección de herramientas y bibliotecas que se descargan e instalan para desarrollar y ejecutar aplicaciones .NET. Incluye la CLI, MSBuild, el entorno de tiempo de ejecución de .NET y otros componentes.|
  | [Proyecto de estilo SDK](#project-system-and-msbuild) | Conjunto de destinos y tareas de MSBuild que especifica cómo compilar un proyecto para un tipo de aplicación concreto. En este sentido, el SDK se especifica mediante el atributo `Sdk` del elemento `Project` en un archivo del proyecto. |

* **platform**

  |Context  | Significado de "plataforma" |
  |---------|--------------------|
  | multiplataforma | En este término, "plataforma" significa un sistema operativo y el hardware en que se ejecuta, como Windows, macOS, Linux, iOS y Android. |
  | Plataforma .NET | El uso varía. La referencia puede ser una implementación de .NET (como .NET Framework o .NET 5), o bien un concepto general de .NET que incluye todas las implementaciones. |

Para obtener más información sobre la terminología de .NET, vea el [Glosario de .NET](../standard/glossary.md).

## <a name="advanced-scenarios"></a>Escenarios avanzados

En las secciones siguientes se explican algunas de las funciones de .NET que son útiles en escenarios avanzados.

### <a name="native-interop"></a>Interoperabilidad nativa

Cada sistema operativo incluye una interfaz de programación de aplicaciones (API) que proporciona servicios del sistema. .NET proporciona varias maneras de llamar a esas API.

La principal manera de interoperar con API nativas es a través de la "invocación de plataforma" (o P/Invoke para abreviar). P/Invoke se admite en las plataformas Windows y Linux. Una manera de interoperabilidad nativa exclusiva de Windows se denomina "Interoperabilidad COM", que se usa con [componentes COM](/cpp/atl/introduction-to-com) en código administrado. Se basa en la infraestructura de P/Invoke, pero funciona de forma ligeramente diferente.

Para obtener más información, vea [Interoperabilidad nativa](../standard/native-interop/index.md).

### <a name="unsafe-code"></a>Código no seguro

Según la compatibilidad con el lenguaje, CLR le permite tener acceso a memoria nativa y usar la aritmética de punteros a través de código `unsafe`. Estas operaciones son necesarias para determinados algoritmos y para la interoperabilidad del sistema. Aunque es eficaz, se desaconseja el uso de código no seguro a menos que sea necesario para la interoperabilidad con las API del sistema o para implementar el algoritmo más eficaz. Es posible que el código no seguro no se ejecute del mismo modo en entornos diferentes y que también pierda las ventajas de un recolector de elementos no utilizados y de la seguridad de tipos. Se recomienda limitar y centralizar el código no seguro lo máximo posible, y probar el código a conciencia.

Para obtener más información, vea [Código no seguro y punteros](../csharp/programming-guide/unsafe-code-pointers/index.md).

## <a name="next-steps"></a>Pasos siguientes

> [!div class="nextstepaction"]
> [Elección de un tutorial de .NET](tutorials/index.md)

> [!div class="nextstepaction"]
> [Prueba de .NET en el explorador](../csharp/tutorials/intro-to-csharp/numbers-in-csharp.yml)

> [!div class="nextstepaction"]
> [Un paseo por C#](../csharp/tour-of-csharp/index.md)

> [!div class="nextstepaction"]
> [Un paseo por F#](../fsharp/tour.md)
