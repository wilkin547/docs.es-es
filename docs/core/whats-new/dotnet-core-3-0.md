---
title: Novedades de .NET Core 3.0
description: Obtenga información sobre las características nuevas de .NET Core 3.0.
dev_langs:
- csharp
author: adegeo
ms.author: adegeo
ms.date: 01/27/2020
ms.openlocfilehash: 9f553e9af16be0891f208832c5daa444a1b736e2
ms.sourcegitcommit: 97ce5363efa88179dd76e09de0103a500ca9b659
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/13/2020
ms.locfileid: "86281516"
---
# <a name="whats-new-in-net-core-30"></a>Novedades de .NET Core 3.0

En este artículo se describen las novedades de .NET Core 3.0. Una de las mejoras más importantes es la compatibilidad con las aplicaciones de Escritorio de Windows (solo Windows). Mediante el componente Escritorio de Windows del SDK de .NET Core 3.0, puede portar sus aplicaciones de Windows Forms y Windows Presentation Foundation (WPF). Para ser más precisos, el componente Escritorio de Windows solo se admite e incluye en Windows. Para obtener más información, vea la sección [Escritorio de Windows](#windows-desktop) más adelante en este artículo.

.NET Core 3.0 agrega compatibilidad con C# 8.0. Se recomienda encarecidamente usar [Visual Studio 2019, versión 16.3](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) o una versión posterior, [Visual Studio para Mac 8.3](/visualstudio/mac/install-preview) o una versión posterior, o [Visual Studio Code](https://code.visualstudio.com/) con la última **extensión de C#** .

[Descargue .NET Core 3.0 y empiece a trabajar](https://aka.ms/netcore3download) ya en Windows, macOS o Linux.

Para obtener más información acerca de la versión, consulte el [anuncio de .NET Core 3.0](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-0/).

Microsoft considera .NET Core RC1 como listo para producción y es totalmente compatible. Si usa una versión preliminar, debe pasar a la versión RTM para obtener soporte técnico continuo.

## <a name="language-improvements-c-80"></a>Mejoras del lenguaje C# 8.0

C# 8.0 también forma parte de esta versión, que incluye la característica de [tipos de referencia que aceptan valores NULL](../../csharp/tutorials/nullable-reference-types.md), [flujos asincrónicos](../../csharp/tutorials/generate-consume-asynchronous-stream.md) y [más patrones](../../csharp/tutorials/pattern-matching.md). Para obtener más información sobre las características de C# 8.0, vea [Novedades de C# 8.0](../../csharp/whats-new/csharp-8.md).

Se han agregado mejoras del lenguaje para admitir las siguientes características de API que se detallan a continuación:

- [Rangos e índices](#ranges-and-indices)
- [Flujos asincrónicos](#async-streams)

## <a name="net-standard-21"></a>.NET Standard 2.1

.NET Core 3.0 implementa **.NET Standard 2.1**. Pero la plantilla predeterminada `dotnet new classlib` genera un proyecto que sigue destinado a **.NET Standard 2.0**. Para destinarlo a **.NET Standard 2.1**, edite el archivo de proyecto y cambie la propiedad `TargetFramework` a `netstandard2.1`:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFramework>netstandard2.1</TargetFramework>
  </PropertyGroup>

</Project>
```

Si usa Visual Studio, necesita [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019), ya que Visual Studio 2017 no admite **.NET Standard 2.1** ni **.NET Core 3.0**.

## <a name="compiledeploy"></a>Compilación e implementación

### <a name="default-executables"></a>Archivos ejecutables predeterminados

Ahora .NET Core compila [archivos ejecutables dependientes del entorno de ejecución](../deploying/index.md#publish-runtime-dependent) de forma predeterminada. Este comportamiento es nuevo en las aplicaciones que usan una versión de .NET Core instalada globalmente. Anteriormente, solo las [implementaciones independientes](../deploying/index.md#publish-self-contained) generarían un archivo ejecutable.

Durante `dotnet build` o `dotnet publish`, se crea un archivo ejecutable (conocido como **appHost**) que coincide con el entorno y la plataforma del SDK que se usa. Estos ejecutables funcionan de la misma forma que los ejecutables nativos:

- Haga doble clic en el archivo ejecutable.
- También puede iniciar la aplicación desde un símbolo del sistema directamente, como `myapp.exe` en Windows y `./myapp` en Linux y macOS.

### <a name="macos-apphost-and-notarization"></a>appHost y certificación de macOS

*Solo para macOS*

A partir del SDK de .NET Core 3.0 para macOS certificado, el valor para generar un archivo ejecutable predeterminado (conocido como appHost) está deshabilitado de forma predeterminada. Para obtener más información, vea [Certificación de macOS Catalina y el impacto en las descargas y proyectos de .NET Core](../install/macos-notarization-issues.md).

Cuando la configuración de appHost está habilitada, .NET Core genera un ejecutable Mach-O nativo al compilar o publicar. La aplicación se ejecuta en el contexto de appHost cuando se ejecuta desde el código fuente con el comando `dotnet run` o mediante el inicio directo del ejecutable Mach-O.

Sin appHost, la única manera en que un usuario puede iniciar una aplicación [dependiente del entorno de ejecución](../deploying/index.md#publish-runtime-dependent) es con el comando `dotnet <filename.dll>`. Siempre se crea un instancia de appHost al publicar la aplicación de manera [independiente](../deploying/index.md#publish-self-contained).

Puede configurar appHost en el nivel de proyecto, o bien cambiar la instancia de appHost de un comando `dotnet` específico con el parámetro `-p:UseAppHost`:

- Archivo del proyecto

  ```xml
  <PropertyGroup>
    <UseAppHost>true</UseAppHost>
  </PropertyGroup>
  ```

- Parámetro de línea de comandos

  ```dotnetcli
  dotnet run -p:UseAppHost=true
  ```

Para obtener más información sobre la configuración de `UseAppHost`, vea [Propiedades de MSBuild para Microsoft.NET.Sdk](../project-sdk/msbuild-props.md#useapphost).

### <a name="single-file-executables"></a>Archivos ejecutables de único archivo

El comando `dotnet publish` admite empaquetar la aplicación en un ejecutable de archivo único específico de la plataforma. El archivo ejecutable es autoextraíble y contiene todas las dependencias (incluidas las nativas) necesarias para ejecutar la aplicación. Cuando la aplicación se ejecuta por primera vez, se extrae en un directorio que se basa en el nombre de la aplicación y el identificador de compilación. El inicio es más rápido cuando se vuelve a ejecutar la aplicación. La aplicación no necesita extraerse por segunda vez a menos que se haya utilizado una nueva versión.

Para publicar un ejecutable de archivo único, establezca `PublishSingleFile` en el proyecto o en la línea de comandos con el comando `dotnet publish`:

```xml
<PropertyGroup>
  <RuntimeIdentifier>win10-x64</RuntimeIdentifier>
  <PublishSingleFile>true</PublishSingleFile>
</PropertyGroup>
```

o bien

```dotnetcli
dotnet publish -r win10-x64 -p:PublishSingleFile=true
```

Para obtener más información sobre la publicación de archivos únicos, vea el [documento de diseño del programa de instalación de conjunto de archivos únicos](https://github.com/dotnet/designs/blob/master/accepted/2020/single-file/design.md).

### <a name="assembly-linking"></a>Vinculación de ensamblados

El SDL de .NET Core 3.0 cuenta con una herramienta que puede reducir el tamaño de las aplicaciones mediante el análisis de IL y el recorte de los ensamblados no usados.

Las aplicaciones independientes incluyen todo lo necesario para ejecutar el código, sin necesidad de instalar .NET en el equipo host. Sin embargo, muchas veces, la aplicación solo requiere un pequeño subconjunto de marco para que funcione, y otras bibliotecas que no se utilizan podrían quitarse.

.NET Core incluye ahora un valor que usará la herramienta [Enlazador de IL](https://github.com/mono/linker) para examinar el nivel de integridad de la aplicación. Esta herramienta detecta el código que es necesario y, después, recorta las bibliotecas no utilizadas. Esta herramienta puede reducir significativamente el tamaño de implementación de algunas aplicaciones.

Para habilitar esta herramienta, agregue el valor `<PublishTrimmed>` en el proyecto y publique una aplicación independiente:

```xml
<PropertyGroup>
  <PublishTrimmed>true</PublishTrimmed>
</PropertyGroup>
```

```dotnetcli
dotnet publish -r <rid> -c Release
```

Por ejemplo, la nueva y básica plantilla de proyecto de consola "Hola mundo" que se incluye, cuando se publica, tiene un tamaño aproximado de 70 MB. Mediante el uso de `<PublishTrimmed>`, ese tamaño se reduce a unos 30 MB.

Es importante tener en cuenta que las aplicaciones o marcos (incluidos ASP.NET Core y WPF) que usan la reflexión o las características dinámicas relacionadas, se interrumpirán a menudo cuando se recorten. Esta interrupción se produce porque el enlazador no conoce este comportamiento dinámico y no puede determinar qué tipos de marco son necesarios para la reflexión. La herramienta Enlazador de IL puede configurarse para tener en cuenta este escenario.

Por encima de todo lo demás, no olvide probar la aplicación después del recorte.

Para más información sobre la herramienta Enlazador de IL, vea la [documentación](https://aka.ms/dotnet-illink) o visite el repositorio [mono/linker]( https://github.com/mono/linker).

### <a name="tiered-compilation"></a>Compilación en niveles

La [compilación en niveles](https://github.com/dotnet/runtime/blob/master/docs/design/features/tiered-compilation.md) (TC) está activada de forma predeterminada con .NET Core 3.0. Esta característica permite que el runtime use el compilador Just-In-Time (JIT) de forma más flexible para lograr un mejor rendimiento.

La principal ventaja de la compilación en niveles es que ofrece dos maneras de aplicar JIT a los métodos: con un nivel de menor calidad, pero más rápido, o un nivel de mayor calidad, pero más lento. La calidad se refiere al grado de optimización del método. La compilación en niveles contribuye a mejorar el rendimiento de una aplicación a medida que pasa por distintas fases de ejecución, desde el inicio hasta el estado estable. Cuando la compilación en niveles está deshabilitada, todos los métodos se compilan de una manera única que prima el rendimiento de estado estable sobre el rendimiento de inicio.

Cuando la compilación en niveles está habilitada, se aplica el comportamiento siguiente a la compilación de métodos al iniciar una aplicación:

- Si el método tiene código compilado mediante Ahead-Of-Time, o [ReadyToRun](#readytorun-images), se usa el código generado previamente.
- De lo contrario, el método se compila mediante JIT. Normalmente, estos métodos son genéricos con respecto a los tipos de valor.
  - *JIT rápido* produce código de menor calidad (o menos optimizado) más rápidamente. En .NET Core 3.0, JIT rápido está habilitado de forma predeterminada para los métodos que no contienen ningún bucle y tiene preferencia durante el inicio.
  - JIT de optimización completa produce código de mayor calidad (o más optimizado) más lentamente. En el caso de los métodos en los que no se use la compilación mediante JIT rápida (por ejemplo, si el método tiene el atributo <xref:System.Runtime.CompilerServices.MethodImplOptions.AggressiveOptimization?displayProperty=nameWithType>), se utilizará la compilación mediante JIT totalmente optimizada.

En el caso de los métodos a los que se llama con frecuencia, el compilador Just-in-Time al final crea código totalmente optimizado en segundo plano. Luego, el código optimizado reemplaza el código compilado previamente de ese método.

El código generado con compilación mediante JIT rápida puede ejecutarse más lentamente, asignar más memoria o usar más espacio de pila. Si hay problemas, puede deshabilitar JIT rápido con esta propiedad de MSBuild en el archivo de proyecto:

```xml
<PropertyGroup>
  <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
</PropertyGroup>
```

Para deshabilitar completamente la compilación en niveles, use esta propiedad de MSBuild en el archivo de proyecto:

```xml
<PropertyGroup>
  <TieredCompilation>false</TieredCompilation>
</PropertyGroup>
```

> [!TIP]
> Si cambia esta configuración en el archivo de proyecto, es posible que deba realizar una compilación limpia para que se refleje la nueva configuración (elimine los directorios `obj` y `bin` y vuelva a compilar).

Para obtener más información sobre la configuración de la compilación en tiempo de ejecución, vea [Opciones de configuración del entorno de ejecución para compilación](../run-time-config/compilation.md).

### <a name="readytorun-images"></a>Imágenes ReadyToRun

Puede mejorar el tiempo de inicio de la aplicación .NET Core mediante la compilación de los ensamblados de aplicación como el formato ReadyToRun (R2R). R2R es una forma de compilación Ahead Of Time (AOT).

Los binarios de R2R mejoran el rendimiento de inicio reduciendo la cantidad de trabajo que el compilador Just-In-Time (JIT) debe llevar a cabo cuando se carga la aplicación. Los binarios contienen código nativo similar en comparación con lo que generaría el compilador JIT. Sin embargo, los binarios de R2R son más grandes porque contienen tanto el código de lenguaje intermedio (IL), que sigue siendo necesario para algunos escenarios, como la versión nativa del mismo código. R2R solo está disponible cuando publica una aplicación independiente que tenga como destino entornos de tiempo de ejecución específicos (RID), como Linux x64 o Windows x64.

Para compilar el proyecto como ReadyToRun, haga lo siguiente:

01. Agregue el valor `<PublishReadyToRun>` al proyecto:

    ```xml
    <PropertyGroup>
      <PublishReadyToRun>true</PublishReadyToRun>
    </PropertyGroup>
    ```

01. Publique una aplicación independiente. Por ejemplo, este comando crea una aplicación independiente para la versión de 64 bits de Windows:

    ```dotnetcli
    dotnet publish -c Release -r win-x64 --self-contained
    ```

#### <a name="cross-platformarchitecture-restrictions"></a>Restricciones multiplataforma y de arquitectura

Actualmente, el compilador ReadyToRun no admite la compatibilidad cruzada. Debe compilar en un destino dado. Por ejemplo, si desea imágenes R2R para Windows x64, deberá ejecutar el comando de publicación en ese entorno.

Excepciones de la compatibilidad cruzada:

- Windows x64 se puede usar para compilar imágenes de Windows ARM32, ARM64 y x86.
- Windows x86 se puede usar para compilar imágenes de Windows ARM32.
- Linux x64 se puede usar para compilar imágenes de Linux ARM32 y ARM64.

## <a name="runtimesdk"></a>Runtime y SDK

### <a name="major-version-runtime-roll-forward"></a>Puesta al día del runtime de versiones principales

.NET Core 3.0 presenta una característica opcional que permite poner la aplicación al día con la versión principal más reciente de .NET Core. Además, se agregó una nueva configuración para controlar cómo se aplica la puesta al día a la aplicación. Esto se puede configurar de las maneras siguientes:

- Propiedad de archivo del proyecto: `RollForward`
- Propiedad de archivo de configuración en tiempo de ejecución: `rollForward`
- Variable de entorno: `DOTNET_ROLL_FORWARD`
- Argumento de línea de comandos: `--roll-forward`

Debe especificarse uno de los valores siguientes. Si se omite la configuración, **Minor** es el valor predeterminado.

- **LatestPatch**\
Se pone al día con la última versión de revisión. Se deshabilita la puesta al día de versiones secundarias.
- **Minor**\
Se pone al día con la versión secundaria mínima superior, si no se encuentra la versión secundaria solicitada. Si se encuentra la versión secundaria solicitada, se utiliza la directiva **LatestPatch**.
- **Major**\
Se pone al día con la versión secundaria mínima superior, y la versión secundaria mínima, si no se encuentra la versión secundaria solicitada. Si se encuentra la versión principal solicitada, se utiliza la directiva **Minor**.
- **LatestMinor**\
Se pone al día con la última versión secundaria, aunque la versión secundaria solicitada esté presente. Se destina a escenarios de hospedaje de componentes.
- **LatestMajor**\
Se pone al día con la última versión principal y la última versión secundaria, aunque la versión principal solicitada esté presente. Se destina a escenarios de hospedaje de componentes.
- **Disable**\
No se pone al día. Solo se enlaza a la versión especificada. No se recomienda esta directiva para uso general, ya que deshabilita la capacidad de puesta al día con las revisiones más recientes. Este valor solo se recomienda a efectos de pruebas.

Además del valor **Disable**, todos los valores usarán la última versión de revisión disponible.

De forma predeterminada, si la versión solicitada (como se especifica en `.runtimeconfig.json` para la aplicación) es una versión de lanzamiento, solo se tienen en cuenta las versiones de lanzamiento para la puesta al día. Se omiten las versiones preliminares. Si no hay ninguna versión de lanzamiento que coincida, se tienen en cuenta las versiones preliminares. Este comportamiento se puede cambiar estableciendo `DOTNET_ROLL_FORWARD_TO_PRERELEASE=1`, en cuyo caso siempre se tienen en cuenta todas las versiones.

### <a name="build-copies-dependencies"></a>Compilación de dependencias de copias

El comando `dotnet build` copia ahora las dependencias de NuGet para la aplicación de la caché de NuGet a la carpeta de salida de compilación. Anteriormente, las dependencias solo se copiaban como parte de `dotnet publish`.

Hay algunas operaciones, como la publicación de páginas Razor y la vinculación, que aún es necesario publicar.

### <a name="local-tools"></a>Herramientas locales

.NET Core 3.0 presenta herramientas locales. Las herramientas locales son similares a las [herramientas globales](../tools/global-tools.md) pero están asociadas a una ubicación concreta en el disco. Las herramientas locales no están disponibles globalmente y se distribuyen como paquetes NuGet.

> [!WARNING]
> Si ha probado herramientas locales en la versión preliminar 1 de .NET Core 3.0, tales como la ejecución de `dotnet tool restore` o de `dotnet tool install`, elimine la carpeta de caché de herramientas locales. En caso contrario, las herramientas locales no funcionan en las versiones más recientes. Esta carpeta se encuentra en:
>
> En macOS, Linux: `rm -r $HOME/.dotnet/toolResolverCache`
>
> En Windows: `rmdir /s %USERPROFILE%\.dotnet\toolResolverCache`

Las herramientas locales se basan en un nombre de archivo de manifiesto `dotnet-tools.json` del directorio actual. Este archivo de manifiesto define las herramientas que estarán disponibles en esa carpeta y a continuación. Puede distribuir el archivo de manifiesto con su código para asegurarse de que todo aquel que trabaje con su código pueda restaurar y utilizar las mismas herramientas.

Para las herramientas locales y globales, se requiere una versión compatible del entorno de ejecución. Actualmente, muchas herramientas de NuGet.org tienen como destino el entorno de ejecución de .NET Core 2.1. Para instalar estas herramientas local o globalmente, aún tendría que instalar [NET Core 2.1 Runtime](https://dotnet.microsoft.com/download/dotnet-core/2.1).

### <a name="new-globaljson-options"></a>Opciones nuevas de global.json

El archivo *global.json* tiene opciones nuevas que proporcionan más flexibilidad cuando se intenta definir qué versión de la SDK de .NET Core se usa. Las opciones nuevas son:

- `allowPrerelease`: Indica si la resolución del SDK debe tener en cuenta las versiones preliminares a la hora de seleccionar la versión del SDK que se va a usar.
- `rollForward`: indica la directiva de puesta al día que se va a usar al seleccionar una versión del SDK, ya sea como reserva si falta una versión específica del SDK o como una directiva para usar una versión superior.

Para más información sobre los cambios, incluidos los valores predeterminados, los valores admitidos y reglas de coincidencia nuevas, consulte la [información general de global.json](../tools/global-json.md).

### <a name="smaller-garbage-collection-heap-sizes"></a>Tamaños del montón de recolección de elementos no utilizados más pequeños

Se ha reducido el tamaño predeterminado del montón del recolector de elementos no utilizados, lo que se traduce en que .NET Core usa menos memoria. Este cambio se adapta mejor al presupuesto de asignación de generación 0 con tamaños de caché de procesador moderno.

### <a name="garbage-collection-large-page-support"></a>Compatibilidad con Large Pages de recolección de elementos no utilizados

Large Pages (también conocida como Huge Pages en Linux) es una característica en la que el sistema operativo es capaz de establecer regiones de memoria más grandes que el tamaño de página nativo (a menudo, 4 K) para mejorar el rendimiento de la aplicación que solicita estas páginas grandes.

Ahora, el recolector de elementos no utilizados puede configurarse con el valor **GCLargePages** como característica opcional para elegir la asignación de páginas grandes en Windows.

## <a name="windows-desktop--com"></a>Escritorio de Windows y COM

### <a name="net-core-sdk-windows-installer"></a>Windows Installer del SDK de .NET Core

El instalador MSI para Windows ha cambiado a partir de .NET Core 3.0. Los instaladores del SDK actualizarán ahora las versiones de la banda de características del SDK. Las bandas de características se definen en los grupos de *centenas* de la sección *revisión* del número de versión. Por ejemplo, **3.0._101_** y **3.0._201_** son versiones de dos bandas de características distintas mientras que **3.0._101_** y **3.0._199_** están en la misma banda de características. Y, cuando se instale el SDK **3.0._101_** de .NET Core, se quitará el SDK **3.0._100_** de .NET Core de la máquina si existe. Cuando se instale el SDK **3.0._200_** de .NET Core en la misma máquina, no se quitará el SDK **3.0._101_** de .NET Core.

Para obtener más información sobre las versiones, vea el artículo de [introducción a la creación de versiones de .NET Core](../versions/index.md).

### <a name="windows-desktop"></a>Escritorio de Windows

.NET Core 3.0 admite aplicaciones de escritorio de Windows con Windows Presentation Foundation (WPF) y Windows Forms. Estos marcos también admiten el uso de controles modernos y los estilos de Fluent de la biblioteca de XAML de la interfaz de usuario de Windows (WinUI) a través de [islas XAML](/windows/uwp/xaml-platform/xaml-host-controls).

El componente Escritorio de Windows forma parte del SDK de Windows .NET Core 3.0.

Puede crear una aplicación de Windows Forms o WPF con los siguientes comandos `dotnet`:

```dotnetcli
dotnet new wpf
dotnet new winforms
```

Visual Studio 2019 agrega plantillas de **nuevo proyecto** para WPF y Windows Forms de .NET Core 3.0.

Para obtener más información sobre cómo migrar una aplicación existente de .NET Framework, vea los artículos sobre [cómo portar proyectos de WPF](../../desktop-wpf/migration/convert-project-from-net-framework.md) y [cómo portar proyectos de Windows Forms](../porting/winforms.md).

#### <a name="winforms-high-dpi"></a>PPP alto de WinForms

En .NET Core, las aplicaciones de Windows Forms pueden establecer el modo de valores altos de PPP con <xref:System.Windows.Forms.Application.SetHighDpiMode(System.Windows.Forms.HighDpiMode)?displayProperty=nameWithType>. El método `SetHighDpiMode` establece el modo de valores altos de PPP correspondiente a menos que la opción se haya establecido por otros medios como `App.Manifest` o P/Invoke antes de `Application.Run`.

Los posibles valores de `highDpiMode`, expresados por la enumeración <xref:System.Windows.Forms.HighDpiMode?displayProperty=nameWithType> son:

- `DpiUnaware`
- `SystemAware`
- `PerMonitor`
- `PerMonitorV2`
- `DpiUnawareGdiScaled`

Para más información sobre los modos de valores altos de PPP, consulte el artículo sobre [desarrollo de aplicaciones de escritorio con valores altos de PPP en Windows](/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows).

### <a name="create-com-components"></a>Creación de componentes COM

En Windows, ahora puede crear componentes COM administrados invocables. Esta capacidad es fundamental para usar .NET Core con modelos de complemento COM, así como para ofrecer paridad con .NET Framework.

A diferencia de .NET Framework, donde se utilizó *mscoree.dll* como servidor COM, .NET Core agregará un archivo dll de inicio nativo al directorio *bin* al compilar el componente COM.

Para ver un ejemplo de cómo crear un componente COM y usarlo, consulte la [demostración de COM](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo).

### <a name="windows-native-interop"></a>Interoperabilidad nativa de Windows

Windows ofrece una API nativa enriquecida en forma de API de C sin formato, COM y WinRT. Mientras que .NET Core admite **P/Invoke**, .NET Core 3.0 agrega la capacidad de **API COM CoCreate** y **API WinRT Activate**. Para obtener un ejemplo de código, vea la [demostración de Excel](https://github.com/dotnet/samples/tree/master/core/extensions/ExcelDemo).

### <a name="msix-deployment"></a>Implementación de MSIX

[MSIX](https://docs.microsoft.com/windows/msix/) es un nuevo formato de paquete de aplicación de Windows. Se puede usar para implementar aplicaciones de escritorio de .NET Core 3.0 en Windows 10.

El [proyecto de paquete de aplicación de Windows](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-packaging-dot-net), disponible en Visual Studio 2019, le permite crear paquetes de MSIX con aplicaciones de .NET Core [independientes](../deploying/index.md#publish-self-contained).

El archivo del proyecto de .NET Core debe especificar los tiempos de ejecución admitidos en la propiedad `<RuntimeIdentifiers>`:

```xml
<RuntimeIdentifiers>win-x86;win-x64</RuntimeIdentifiers>
```

## <a name="linux-improvements"></a>Mejoras de Linux

### <a name="serialport-for-linux"></a>SerialPort para Linux

.Net Core 3.0 proporciona compatibilidad básica para <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType> en Linux.

Anteriormente, .NET Core solo admitía el uso de `SerialPort` en Windows.

Para obtener más información sobre la compatibilidad limitada para el puerto de serie en Linux, vea [Problema #33146 de GitHub](https://github.com/dotnet/corefx/issues/33146).

### <a name="docker-and-cgroup-memory-limits"></a>Docker y límites de memoria de cgroup

La ejecución de .NET Core 3.0 en Linux con Docker funciona mejor con límites de memoria de cgroup. La ejecución de un contenedor de Docker con límites de memoria, como con `docker run -m`, cambia el comportamiento de .NET Core.

- Tamaño predeterminado del montón del recolector de elementos no utilizados (GC): máximo de 20 MB o 75 % del límite de memoria en el contenedor.
- Puede establecerse el tamaño explícito como número absoluto o porcentaje del límite de cgroup.
- El tamaño mínimo del segmento reservado por el montón de GC es de 16 MB. Con este tamaño se reduce el número de montones que se crean en las máquinas.

### <a name="gpio-support-for-raspberry-pi"></a>Compatibilidad de GPIO con Raspberry Pi

Se han publicado dos paquetes en NuGet que puede usar para la programación de GPIO:

- [System.Device.Gpio](https://www.nuget.org/packages/System.Device.Gpio)
- [Iot.Device.Bindings](https://www.nuget.org/packages/Iot.Device.Bindings)

Los paquetes GPIO incluyen interfaces API para dispositivos *GPIO*, *SPI*, *I2C* y *PWM*. El paquete de enlaces de IoT incluye enlaces de dispositivos. Para obtener más información, vea el [repositorio de GitHub de los dispositivos](https://github.com/dotnet/iot/blob/master/src/devices/).

### <a name="arm64-linux-support"></a>Compatibilidad con ARM64 para Linux

.NET Core 3.0 agrega compatibilidad con ARM64 para Linux. El principal caso de uso de ARM64 son escenarios de IoT. Para obtener más información, vea el artículo sobre el [estado de ARM64 de .NET Core](https://github.com/dotnet/announcements/issues/82).

[Hay imágenes de docker para .NET Core en ARM64](https://hub.docker.com/r/microsoft/dotnet/) disponibles para Alpine, Debian y Ubuntu.

> [!NOTE]
> Windows aún no ofrece soporte técnico para **ARM64**.

## <a name="security"></a>Seguridad

### <a name="tls-13--openssl-111-on-linux"></a>TLS 1.3 y OpenSSL 1.1.1 en Linux

.NET Core aprovecha ahora la ventaja de la [compatibilidad con TLS 1.3 en OpenSSL 1.1.1](https://www.openssl.org/blog/blog/2018/09/11/release111/), cuando está disponible en un entorno determinado. Con TLS 1.3:

- Se han mejorado los tiempos de conexión con menores recorridos de ida y vuelta necesarios entre el cliente y servidor.
- Se ha mejorado la seguridad gracias a la eliminación de varios algoritmos criptográficos obsoletos y no seguros.

Cuando está disponible, .NET Core 3.0 utiliza **OpenSSL 1.1.1**, **OpenSSL 1.1.0** o **OpenSSL 1.0.2** en un sistema Linux. Si **OpenSSL 1.1.1** está disponible, los tipos <xref:System.Net.Security.SslStream?displayProperty=nameWithType> y <xref:System.Net.Http.HttpClient?displayProperty=nameWithType>, utilizarán **TLS 1.3** (suponiendo que el cliente y el servidor admitan **TLS 1.3**).

> [!IMPORTANT]
> Windows y macOS aún no admiten **TLS 1.3**. .NET Core 3.0 será compatible con **TLS 1.3** en estos sistemas operativos cuando haya disponible soporte técnico.

El siguiente ejemplo de C# 8.0 muestra .NET Core 3.0 en Ubuntu 18.10 al conectarse a <https://www.cloudflare.com>:

[!code-csharp[TLSExample](./snippets/dotnet-core-3-0/csharp/TLS.cs#TLS)]

### <a name="cryptography-ciphers"></a>Cifrados de criptografía

.NET 3.0 agrega compatibilidad con los cifrados **AES-GCM** y **AES-CCM**, que se implementan con <xref:System.Security.Cryptography.AesGcm?displayProperty=nameWithType> y <xref:System.Security.Cryptography.AesCcm?displayProperty=nameWithType> respectivamente. Estos dos algoritmos son [algoritmos AEAD (Authenticated Encryption with Associated Data)](https://en.wikipedia.org/wiki/Authenticated_encryption).

El código siguiente muestra cómo utilizar cifrado `AesGcm` para cifrar y descifrar datos aleatorios.

[!code-csharp[AesGcm](./snippets/dotnet-core-3-0/csharp/Cipher.cs#AesGcm)]

### <a name="cryptographic-key-importexport"></a>Importación y exportación de claves criptográfica

.NET Core 3.0 admite la importación y exportación de claves asimétricas públicas y privadas en formatos estándar. No es necesario utilizar un certificado X.509.

Todos los tipos de clave, como *RSA*, *DSA*, *ECDsa* y *ECDiffieHellman*, admiten los siguientes formatos:

- **Clave pública**
  - SubjectPublicKeyInfo X.509

- **Clave privada**
  - PrivateKeyInfo PKCS#8
  - EncryptedPrivateKeyInfo PKCS#8

Las claves RSA también admiten:

- **Clave pública**
  - RSAPublicKey PKCS#1

- **Clave privada**
  - RSAPrivateKey PKCS#1

Los métodos de exportación generan datos binarios con codificación DER y los métodos de importación esperan lo mismo. Si una clave se almacena en el formato PEM de texto descriptivo, el llamador debe descodificar en base64 el contenido antes de llamar a un método de importación.

[!code-csharp[RSA](./snippets/dotnet-core-3-0/csharp/RSA.cs#Rsa)]

Los archivos **PKCS#8** se pueden inspeccionar con <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo?displayProperty=nameWithType> y los archivos **PFX/PKCS#12** se pueden inspeccionar con <xref:System.Security.Cryptography.Pkcs.Pkcs12Info?displayProperty=nameWithType>. Los archivos **PFX/PKCS#12** se pueden manipular con <xref:System.Security.Cryptography.Pkcs.Pkcs12Builder?displayProperty=nameWithType>.

## <a name="net-core-30-api-changes"></a>Cambios de API en .NET Core 3.0

### <a name="ranges-and-indices"></a>Rangos e índices

El nuevo tipo <xref:System.Index?displayProperty=nameWithType> se puede utilizar para la indización. Puede crear uno desde un índice `int` que cuente desde el principio o con un operador `^` de prefijo (C#) que cuente desde el final:

```csharp
Index i1 = 3;  // number 3 from beginning
Index i2 = ^4; // number 4 from end
int[] a = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
Console.WriteLine($"{a[i1]}, {a[i2]}"); // "3, 6"
```

Existe también el tipo <xref:System.Range?displayProperty=nameWithType>, que consta de dos valores `Index`, uno para el inicio y otro para el final, y se puede escribir con una expresión de intervalo `x..y` (C#). Luego puede crear un índice con un `Range`, lo que genera un segmento:

```csharp
var slice = a[i1..i2]; // { 3, 4, 5 }
```

Para obtener más información, vea el [tutorial sobre intervalos e índices](../../csharp/tutorials/ranges-indexes.md).

### <a name="async-streams"></a>Flujos asincrónicos

El tipo <xref:System.Collections.Generic.IAsyncEnumerable%601> es una nueva versión asincrónica de <xref:System.Collections.Generic.IEnumerable%601>. El lenguaje permite ejecutar la instrucción `await foreach` en `IAsyncEnumerable<T>` para consumir sus elementos, y usar la instrucción `yield return` en ellos para generar los elementos.

En el ejemplo siguiente se muestra la producción y el consumo de flujos asincrónicos. La instrucción `foreach` es asincrónica y usa `yield return` para generar un flujo asincrónico para los llamadores. Este patrón (que usa `yield return`) es el modelo recomendado para generar flujos asincrónicos.

```csharp
async IAsyncEnumerable<int> GetBigResultsAsync()
{
    await foreach (var result in GetResultsAsync())
    {
        if (result > 20) yield return result;
    }
}
```

Además de poder ejecutar `await foreach`, también puede crear iteradores asincrónicos, por ejemplo, uno que devuelva un enumerador `IAsyncEnumerable/IAsyncEnumerator` en el que pueda ejecutar `await` y `yield`. Para los objetos que deban eliminarse, puede usar `IAsyncDisposable`, que implementan varios tipos BCL, como `Stream` y `Timer`.

Para obtener más información, vea el [tutorial sobre flujos asincrónicos](../../csharp/tutorials/generate-consume-asynchronous-stream.md).

### <a name="ieee-floating-point"></a>Punto flotante de IEEE

Las API de punto flotante se actualizan para cumplir con la [revisión IEEE 754-2008](https://en.wikipedia.org/wiki/IEEE_754-2008_revision). El objetivo de estos cambios es exponer todas operaciones **requeridas** y asegurarse de que cumplen con la especificación IEEE. Para obtener más información sobre las mejoras de punto flotante, vea la entrada de blog sobre [mejoras de formato y análisis de punto flotante en .NET Core 3.0](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/).

Entre las correcciones de análisis y formato se incluyen:

- Analice y redondee entradas de cualquier longitud correctamente.
- Analice y formatee el cero negativo correctamente.
- Análisis correcto de `Infinity` y `NaN` al hacer una comprobación que no distingue mayúsculas de minúsculas y permitir un `+` anterior opcional cuando corresponda.

Entre las nuevas API <xref:System.Math?displayProperty=nameWithType> se incluyen:

- <xref:System.Math.BitIncrement(System.Double)> y <xref:System.Math.BitDecrement(System.Double)>\
Corresponde a las operaciones IEEE `nextUp` y `nextDown`. Devuelven el número de punto flotante más pequeño que compara mayor o menor que la entrada (respectivamente). Por ejemplo, `Math.BitIncrement(0.0)` devolvería `double.Epsilon`.

- <xref:System.Math.MaxMagnitude(System.Double,System.Double)> y <xref:System.Math.MinMagnitude(System.Double,System.Double)>\
Corresponde a las operaciones IEEE `maxNumMag` y `minNumMag`, que devuelven el valor que es mayor o menor en magnitud de las dos entradas (respectivamente). Por ejemplo, `Math.MaxMagnitude(2.0, -3.0)` devolvería `-3.0`.

- <xref:System.Math.ILogB(System.Double)>\
Corresponde a la operación IEEE `logB` que devuelve un valor entero, devuelve el logaritmo en base 2 integral del parámetro de entrada. Este método es efectivamente el mismo que `floor(log2(x))`, pero con errores de redondeo mínimo.

- <xref:System.Math.ScaleB(System.Double,System.Int32)>\
Corresponde a la operación IEEE `scaleB` que toma un valor integral, devuelve eficazmente `x * pow(2, n)`, pero se realiza con errores de redondeo mínimo.

- <xref:System.Math.Log2(System.Double)>\
Corresponde a la operación IEEE `log2`. Devuelve el logaritmo de base 2. Minimiza el error de redondeo.

- <xref:System.Math.FusedMultiplyAdd(System.Double,System.Double,System.Double)>\
Corresponde a la operación IEEE `fma`. Realiza una multiplicación y suma fusionadas. Es decir, realiza `(x * y) + z` como operación única, de forma que se minimiza el error de redondeo. Un ejemplo es `FusedMultiplyAdd(1e308, 2.0, -1e308)`, que devuelve `1e308`. La operación `(1e308 * 2.0) - 1e308` regular devuelve `double.PositiveInfinity`.

- <xref:System.Math.CopySign(System.Double,System.Double)>\
Corresponde a la operación IEEE `copySign`. Devuelve el valor de `x`, pero con el signo de `y`.

### <a name="net-platform-dependent-intrinsics"></a>Elementos intrínsecos dependientes de la plataforma .NET

Se han agregado API que permiten el acceso a determinadas instrucciones CPU orientadas al rendimiento, como los conjuntos de **instrucciones de manipulación de bits** o **SIMD**. Estas instrucciones pueden ayudar a conseguir importantes mejoras de rendimiento en ciertos escenarios, como el procesamiento de datos con eficiencia en paralelo.

En su caso, las bibliotecas de .NET han comenzado a utilizar estas instrucciones para mejorar el rendimiento.

Para obtener más información, consulte el artículo sobre [elementos intrínsecos dependientes de la plataforma .NET](https://github.com/dotnet/designs/blob/master/accepted/2018/platform-intrinsics.md).

### <a name="improved-net-core-version-apis"></a>API de versión mejoradas de .NET Core

A partir de .NET Core 3.0, las API de versión incluidas con .NET Core ahora devuelven la información que se espera. Por ejemplo:

```csharp
System.Console.WriteLine($"Environment.Version: {System.Environment.Version}");

// Old result
//   Environment.Version: 4.0.30319.42000
//
// New result
//   Environment.Version: 3.0.0
```

```csharp
System.Console.WriteLine($"RuntimeInformation.FrameworkDescription: {System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription}");

// Old result
//   RuntimeInformation.FrameworkDescription: .NET Core 4.6.27415.71
//
// New result (notice the value includes any preview release information)
//   RuntimeInformation.FrameworkDescription: .NET Core 3.0.0-preview4-27615-11
```

> [!WARNING]
> Cambio importante. Se trata técnicamente de un cambio importante, porque ha cambiado el esquema de control de versiones.

### <a name="fast-built-in-json-support"></a>Compatibilidad con JSON integrada con rápido rendimiento

Los usuarios de .NET se han basado en gran medida en [Newtonsoft.Json](https://www.newtonsoft.com/json) y otras bibliotecas populares de JSON, que siguen siendo buenas opciones. `Newtonsoft.Json` usa cadenas de .NET como tipo de datos base, que, en esencia, es UTF-16.

La nueva compatibilidad integrada con JSON es de alto rendimiento, baja asignación y funciona con texto JSON codificado UTF-8. Para obtener más información sobre el espacio de nombres <xref:System.Text.Json> y los tipos, vea los artículos siguientes:

* [Serialización JSON en .NET: información general](../../standard/serialization/system-text-json-overview.md)
* En [Procedimiento para serializar y deserializar JSON en .NET](../../standard/serialization/system-text-json-how-to.md)
* [Migración desde Newtonsoft.json a System.Text.Json](../../standard/serialization/system-text-json-migrate-from-newtonsoft-how-to.md)

### <a name="http2-support"></a>Compatibilidad con HTTP/2

El tipo <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> es compatible con el protocolo HTTP/2. Si se habilita HTTP/2, la versión del protocolo HTTP se negocia a través de TLS/ALPN y HTTP/2 solo se usa si el servidor opta por usarlo.

El protocolo predeterminado sigue siendo HTTP/1.1, pero se puede habilitar HTTP/2 de dos maneras diferentes. En primer lugar, puede establecer el mensaje de solicitud HTTP para usar HTTP/2:

[!code-csharp[Http2Request](./snippets/dotnet-core-3-0/csharp/http.cs#Request)]

En segundo lugar, puede cambiar <xref:System.Net.Http.HttpClient> para usar HTTP/2 de forma predeterminada:

[!code-csharp[Http2Client](./snippets/dotnet-core-3-0/csharp/http.cs#Client)]

Muchas veces cuando está desarrollando una aplicación, desea utilizar una conexión no cifrada. Si sabe que el punto de conexión de destino utilizará HTTP/2, puede activar las conexiones no cifradas para HTTP/2. Puede activarlas estableciendo la variable de entorno `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT` en `1` o habilitándolas en el contexto de la aplicación:

[!code-csharp[Http2Context](./snippets/dotnet-core-3-0/csharp/http.cs#AppContext)]

## <a name="next-steps"></a>Pasos siguientes

- [Revise los cambios importantes entre .NET Core 2.2 y 3.0.](../compatibility/2.2-3.0.md)
- [Revise los cambios importantes de .NET Core 3.0 para aplicaciones de Windows Forms.](../compatibility/winforms.md#net-core-30)
