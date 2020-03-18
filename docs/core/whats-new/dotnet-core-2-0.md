---
title: Novedades de .NET Core 2.0
description: Obtenga información sobre las características nuevas de .NET Core.
ms.date: 08/13/2017
ms.openlocfilehash: 115b3adc72b6798c6a7bac9cc18044a8822808a6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79397846"
---
# <a name="whats-new-in-net-core-20"></a>Novedades de .NET Core 2.0

.NET Core 2.0 incluye mejoras y características nuevas en las áreas siguientes:

- [Herramientas](#tooling)
- [Compatibilidad con lenguajes](#language-support)
- [Mejoras en la plataforma](#platform-improvements)
- [Cambios en la API](#api-changes-and-library-support)
- [Integración de Visual Studio](#visual-studio-integration)
- [Mejoras en la documentación](#documentation-improvements)

## <a name="tooling"></a>Tooling

### <a name="dotnet-restore-runs-implicitly"></a>dotnet restore se ejecuta de manera implícita

En las versiones anteriores de .NET Core, era necesario ejecutar el comando [dotnet restore](../tools/dotnet-restore.md) para descargar dependencias inmediatamente después de crear un proyecto nuevo con el comando [dotnet new](../tools/dotnet-new.md), así como también cada vez que se agregaba una dependencia nueva al proyecto.

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

También puede deshabilitar la invocación automática de `dotnet restore` si pasa el modificador `--no-restore` a los comandos `new`, `run`, `build`, `publish`, `pack` y `test`.

### <a name="retargeting-to-net-core-20"></a>Redestinación a .NET Core 2.0

Si el SDK de .NET Core 2.0 SDK está instalado, los proyectos que tienen .NET Core 1.x como destino se pueden redestinar a .NET Core 2.0.

Para redestinar a .NET Core 2.0, edite el archivo del proyecto cambiando el valor del elemento `<TargetFramework>` (o del elemento `<TargetFrameworks>`, si tiene más de un destino en el archivo del proyecto) de 1.x a 2.0:

```xml
<PropertyGroup>
    <TargetFramework>netcoreapp2.0</TargetFramework>
 </PropertyGroup>
```

También puede redestinar las bibliotecas de .NET Standard a .NET Standard 2.0 del mismo modo:

```xml
<PropertyGroup>
    <TargetFramework>netstandard2.0</TargetFramework>
 </PropertyGroup>
```

Para más información sobre cómo migrar el proyecto a .NET Core 2.0, consulte el artículo sobre [migración de ASP.NET Core 1.x a ASP.NET Core 2.0](/aspnet/core/migration/1x-to-2x/index).

## <a name="language-support"></a>Compatibilidad con lenguajes

Además de admitir C# y F#, .NET Core 2.0 también es compatible con Visual Basic.

### <a name="visual-basic"></a>Visual Basic

Con la versión 2.0, .NET Core ahora es compatible con Visual Basic 2017. Puede usar Visual Basic para crear los tipos de proyecto siguientes:

- Aplicaciones de consola .NET Core
- Bibliotecas de clases .NET Core
- Bibliotecas de clases .NET Standard
- Proyectos de prueba unitaria .NET Core
- Proyectos de prueba xUnit .NET Core

Por ejemplo, para crear una aplicación "Hola mundo" de Visual Basic, haga estos pasos en la línea de comandos:

1. En una ventana de la consola, cree un directorio para el proyecto y conviértalo en el directorio actual.

1. Escriba el comando `dotnet new console -lang vb`.

   El comando crea un archivo del proyecto con una extensión de archivo `.vbproj`, además de un archivo de código fuente de Visual Basic llamado *Program.vb*. Este archivo contiene el código fuente para escribir la cadena "Hola mundo" en la ventana de consola.

1. Escriba el comando `dotnet run`. La [CLI de .NET Core](../tools/index.md) compila y ejecuta automáticamente la aplicación, con lo que se muestra el mensaje "Hola mundo" en la ventana de la consola.

### <a name="support-for-c-71"></a>Compatibilidad con C# 7.1

.NET Core 2.0 es compatible con C# 7.1, que agrega varias características nuevas, entre las que se incluyen las siguientes:

- El método `Main`, el punto de entrada de la aplicación, se puede marcar con la palabra clave [async](../../csharp/language-reference/keywords/async.md).
- Nombres de tupla deducidos.
- Expresiones predeterminadas.

<!-- For more information see [link to C# what's new](url). -->

## <a name="platform-improvements"></a>Mejoras en la plataforma

.NET Core 2.0 incluye varias características que facilitan la instalación de .NET Core y su uso en sistemas operativos compatibles.

### <a name="net-core-for-linux-is-a-single-implementation"></a>.NET Core para Linux es una sola implementación

.NET Core 2.0 ofrece una sola implementación de Linux que funciona en varias distribuciones de Linux. .NET Core 1.x requería que descargara una implementación de Linux específica para la distribución.

También puede desarrollar aplicaciones que tienen Linux como destino como un solo sistema operativo. .NET Core 1.x requería que se tuviera cada distribución de Linux como destino de forma independiente.

### <a name="support-for-the-apple-cryptographic-libraries"></a>Compatibilidad con las bibliotecas de cifrado de Apple

.NET Core 1.x en macOS requería la biblioteca de cifrado del kit de herramientas OpenSSL. .NET Core 2.0 usa las bibliotecas de cifrado de Apple y no requiere OpenSSL, por lo que ya no es necesario instalarlo.

## <a name="api-changes-and-library-support"></a>Cambios en la API y compatibilidad con bibliotecas

### <a name="support-for-net-standard-20"></a>Compatibilidad con .NET Standard 2.0

.NET Standard define un conjunto de API con control de versiones que debe estar disponible en las implementaciones de .NET que cumplen con esa versión del estándar. .NET Standard está dirigido a los desarrolladores de bibliotecas. Pretende garantizar la funcionalidad que está disponible a una biblioteca que tiene como destino una versión de .NET Standard en cada implementación de .NET. .NET Core 1.x es compatible con la versión 1.6 de .NET Standard; .NET Core 2.0 es compatible con la versión más reciente, .NET Standard 2.0. Para más información, consulte [.NET Standard](../../standard/net-standard.md).

.NET Standard 2.0 incluye más de 20 000 API más que las disponibles en .NET Standard 1.6. Gran parte de esta área expuesta expandida es resultado de la incorporación de las API comunes de .NET Framework y Xamarin en .NET Standard.

Las bibliotecas de clases .NET Standard 2.0 también pueden hacer referencia a bibliotecas de clases .NET Framework siempre que llamen a las API que existen en .NET Standard 2.0. No es necesario realizar una nueva compilación de las bibliotecas .NET Framework.

Si desea ver una lista de las API que se agregaron a .NET Standard desde la última versión, .NET Standard 1.6, consulte el artículo de [comparación entre .NET Standard 2.0 y 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md).

### <a name="expanded-surface-area"></a>Área expuesta expandida

La cantidad total de API disponibles en .NET Core 2.0 aumentó más del doble en comparación con .NET Core 1.1.

Además, con el [paquete de compatibilidad de Windows](../porting/windows-compat-pack.md), la migración desde .NET Framework ahora es mucho más fácil.

### <a name="support-for-net-framework-libraries"></a>Compatibilidad con las bibliotecas .NET Framework

El código de .NET Core puede hacer referencia a bibliotecas .NET Framework existentes, incluidos paquetes NuGet existentes. Tenga en cuenta que las bibliotecas deben usar las API que se encuentran en .NET Standard.

## <a name="visual-studio-integration"></a>integración de Visual Studio

Visual Studio 2017 versión 15.3 y, en algunos casos, Visual Studio para Mac, ofrecen varias mejoras importantes para los desarrolladores de .NET Core.

### <a name="retargeting-net-core-apps-and-net-standard-libraries"></a>Redestinación de aplicaciones .NET Core y bibliotecas .NET Standard

Si el SDK de .NET Core 2.0 SDK está instalado, puede redestinar los proyectos de .NET Core 1.x a .NET Core 2.0 y las bibliotecas .NET Standard 1.x a .NET Standard 2.0.

Para redestinar el proyecto en Visual Studio, abra la pestaña **Aplicación** del cuadro de diálogo de propiedades del proyecto y cambie el valor de **plataforma de destino** a **.NET Core 2.0** o **.NET Standard 2.0**. También puede cambiarlo si hace clic con el botón derecho en el proyecto y selecciona la opción **Edit \*.csproj file** (Editar archivo .csproj). Para más información, consulte la sección [Herramientas](#tooling) anteriormente en este tema.

### <a name="live-unit-testing-support-for-net-core"></a>Compatibilidad con Live Unit Testing en .NET Core

Cada vez que modifique el código, Live Unit Testing ejecuta automáticamente y en segundo plano cualquier prueba unitaria afectada y presenta los resultados y la cobertura de código en vivo en el entorno de Visual Studio. .NET Core 2.0 ahora admite Live Unit Testing. Anteriormente, Live Unit Testing solo estaba disponible para aplicaciones .NET Framework.

Para obtener más información, consulte [Live Unit Testing con Visual Studio](/visualstudio/test/live-unit-testing) y las [preguntas más frecuentes de Live Unit Testing](/visualstudio/test/live-unit-testing-faq).

### <a name="better-support-for-multiple-target-frameworks"></a>Mejor compatibilidad con varias plataformas de destino

Si compila un proyecto para varias plataformas de destino, ahora puede seleccionar la plataforma de destino en el menú de nivel superior. En la figura siguiente, un proyecto llamado SCD1 tiene como destino macOS X 10.11 (`osx.10.11-x64`) de 64 bits y Windows 10/Windows Server 2016 (`win10-x64`) de 64 bits. Puede seleccionar la plataforma de destino antes de seleccionar el botón del proyecto, en este caso para ejecutar una compilación de depuración.

![Captura de pantalla en la que se muestra la selección de la plataforma de destino al crear un proyecto.](./media/dotnet-core-2-0/target-framework-selection.png)

### <a name="side-by-side-support-for-net-core-sdks"></a>Compatibilidad en paralelo con SDK de .NET Core

Ahora es posible instalar el SDK de .NET Core de manera independiente de Visual Studio. Esto permite que una versión única de Visual Studio compile proyectos que tienen como destino distintas versiones de .NET Core. Anteriormente, Visual Studio y el SDK de .NET Core estaban estrechamente relacionados; una versión específica del SDK acompañaba a una versión específica de Visual Studio.

## <a name="documentation-improvements"></a>Mejoras en la documentación

### <a name="net-application-architecture"></a>Arquitectura de aplicación de .NET

[Arquitectura de aplicación de .NET](https://dotnet.microsoft.com/learn/dotnet/architecture-guides) le permite acceder a un conjunto de libros electrónicos que ofrecen orientación, procedimientos recomendados y aplicaciones de ejemplo cuando use .NET para compilar:

- [Microservicios y contenedores Docker](../../architecture/microservices/index.md)
- [Aplicaciones web con ASP.NET](../../architecture/modern-web-apps-azure/index.md)
- [Aplicaciones móviles con Xamarin](/xamarin/xamarin-forms/enterprise-application-patterns/index)
- [Aplicaciones que se implementan en la nube con Azure](/azure/architecture/reference-architectures/index)

## <a name="see-also"></a>Vea también

- [Novedades de ASP.NET Core 2.0](/aspnet/core/aspnetcore-2.0)
