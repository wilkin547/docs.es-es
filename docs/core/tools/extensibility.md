---
title: Modelo de extensibilidad de la CLI de .NET Core
description: Obtenga información sobre cómo puede ampliar las herramientas de la interfaz de la línea de comandos (CLI).
ms.date: 04/12/2017
ms.openlocfilehash: 4f49735fa94b2a7ee32e0d80590f9e680edeff16
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714179"
---
# <a name="net-core-cli-tools-extensibility-model"></a>Modelo de extensibilidad de las herramientas de la CLI de .NET Core

En este documento se tratan las maneras diferentes en las que puede ampliar las herramientas de la interfaz de la línea de comandos (CLI) de .NET Core y se explican los escenarios que impulsan cada una de ellas.
Verá cómo usar las herramientas así como la manera de crear los diferentes tipos de herramientas.

## <a name="how-to-extend-cli-tools"></a>Cómo extender las herramientas de la CLI
Las herramientas de la CLI pueden extenderse de tres maneras principales:

1. [A través de paquetes NuGet por proyecto](#per-project-based-extensibility)

   Las herramientas por proyecto se incluyen en el contexto del proyecto, pero permiten la instalación fácil mediante la restauración.

2. [A través de paquetes NuGet con destinos personalizados](#custom-targets)

   Los destinos personalizados permiten extender fácilmente el proceso de compilación con tareas personalizadas.

3. [A través de la RUTA DE ACCESO del sistema](#path-based-extensibility)

   Las herramientas basadas en la RUTA DE ACCESO son buenas para herramientas entre proyectos generales que se pueden usar en una sola máquina.

Los tres mecanismos de extensibilidad descritos anteriormente no son exclusivos. Puede usar uno, o todos, o una combinación de ellos. La selección de uno u otro depende en gran medida del objetivo que intenta alcanzar con su extensión.

## <a name="per-project-based-extensibility"></a>Extensibilidad por proyecto
Las herramientas por proyecto son [implementaciones dependientes del marco](../deploying/index.md#framework-dependent-deployments-fdd) que se distribuyen como paquetes NuGet. Las herramientas solo están disponibles en el contexto del proyecto que les hace referencia y para el que se restauran. La invocación fuera del contexto del proyecto (por ejemplo, fuera del directorio que contiene el proyecto) producirá un error porque el comando no puede encontrarse.

Estas herramientas son perfectas para servidores de compilación, dado que no se necesita nada fuera del archivo de proyecto. El proceso de compilación ejecuta la restauración para el proyecto que se compila y hay herramientas disponibles. Los proyectos de lenguajes, como F#, también están en esta categoría ya que cada proyecto solo se puede escribir en un lenguaje específico.

Finalmente, este modelo de extensibilidad proporciona compatibilidad con la creación de herramientas que necesitan acceso a la salida compilada del proyecto. Por ejemplo, varias herramientas de vista de Razor de aplicaciones [ASP.NET](https://www.asp.net/) MVC se incluyen dentro de esta categoría.

### <a name="consuming-per-project-tools"></a>Consumo de herramientas por proyecto
Para consumir estas herramientas es necesario agregar un elemento `<DotNetCliToolReference>` a su archivo del proyecto para cada herramienta que quiera usar. Dentro del elemento `<DotNetCliToolReference>`, se hace referencia al paquete en el que reside la herramienta y se especifica la versión necesaria. Después de ejecutar [`dotnet restore`](dotnet-restore.md), se restauran la herramienta y sus dependencias.

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

Para las herramientas que necesitan cargar la salida de compilación del proyecto para su ejecución, hay normalmente otra dependencia que aparece en las dependencias normales del archivo de proyecto. Como la CLI usa MSBuild como motor de compilación, recomendamos que estas partes de la herramienta se escriban como [destinos](/visualstudio/msbuild/msbuild-targets) y [tareas](/visualstudio/msbuild/msbuild-tasks) de MSBuild personalizados, ya que pueden formar parte del proceso de compilación general. Además, pueden obtener fácilmente todos y cada uno de los datos que se producen mediante la compilación, como la ubicación de los archivos de salida, la configuración actual que se compila, etc. Toda esta información se convierte en un conjunto de propiedades de MSBuild que se puede leer desde cualquier destino. Más adelante en este documento puede ver cómo agregar un destino personalizado mediante NuGet.

Vamos a ver un ejemplo de cómo agregar una herramienta sencilla tools-only a un proyecto sencillo. Dado un comando de ejemplo llamado `dotnet-api-search` que le permite examinar los paquetes de NuGet hasta encontrar la API especificada, este es un archivo de proyecto de la aplicación de consola que usa esa herramienta:

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.1</TargetFramework>
  </PropertyGroup>

  <!-- The tools reference -->
  <ItemGroup>
    <DotNetCliToolReference Include="dotnet-api-search" Version="1.0.0" />
  </ItemGroup>
</Project>
```

El elemento `<DotNetCliToolReference>` está estructurado de forma similar al elemento `<PackageReference>`. Necesita el identificador del paquete que contiene la herramienta y su versión para que pueda realizarse la restauración.

### <a name="building-tools"></a>Compilación de herramientas
Como se ha mencionado, las herramientas son simples aplicaciones de consola portátiles. Compila herramientas como lo haría en cualquier otra aplicación de consola.
Después de compilarla, puede usar el comando [`dotnet pack`](dotnet-pack.md) para crear un paquete de NuGet (archivo .nupkg) que contiene el código e información sobre sus dependencias, entre otros. Puede proporcionar cualquier nombre al paquete, pero la aplicación que contiene, el archivo binario de la herramienta real, debe respetar las convenciones de `dotnet-<command>` para que `dotnet` pueda invocarlo.

> [!NOTE]
> En las versiones anteriores a RC3 de las herramientas de línea de comandos de .NET Core, el comando `dotnet pack` tenía un error que provocaba que *.runtimeconfig.json* no se empaquetase con la herramienta. La falta de dicho archivo provoca errores en tiempo de ejecución. Si se produce este comportamiento, asegúrese de actualizar a las últimas herramientas y pruebe `dotnet pack` nuevo.

Como las herramientas son aplicaciones portátiles, el usuario que las consume debe tener la versión de las bibliotecas .NET Core con la que se ha compilado la herramienta para poder ejecutar esta. Cualquier otra dependencia que use la herramienta y que no esté contenida en las bibliotecas .NET Core se restauran y colocan en la caché de NuGet. Por lo tanto, la herramienta entera se ejecuta con los ensamblados de las bibliotecas .NET Core, así como los ensamblados de la caché de NuGet.

Estas clases de herramientas tienen un gráfico de dependencias que es completamente independiente del gráfico de dependencias del proyecto que los usa. El proceso de restauración restaura primero las dependencias del proyecto y, después, cada una de las herramientas y sus dependencias.

Puede encontrar más ejemplos y diferentes combinaciones de esto en el [repositorio de la CLI de .NET Core](https://github.com/dotnet/cli/tree/release/2.1/TestAssets/TestProjects).
También puede ver las [herramientas de implementación usadas](https://github.com/dotnet/cli/tree/release/2.1/TestAssets/TestPackages) en el mismo repositorio.

## <a name="custom-targets"></a>Destinos personalizados

NuGet tiene la capacidad de [empaquetar archivos de propiedades y destinos de MSBuild personalizados](/nuget/create-packages/creating-a-package#include-msbuild-props-and-targets-in-a-package). Con el paso de las herramientas de la CLI de .NET Core para usar MSBuild, el mismo mecanismo de extensibilidad se aplica ahora en proyectos de .NET Core. Este tipo de extensibilidad se usaría cuando quisiera extender el proceso de compilación o quisiera acceder a alguno de los artefactos de dicho proceso, como los archivos generados, o si quiere inspeccionar la configuración bajo la que se invoca la compilación, etc.

En el ejemplo siguiente, puede ver el archivo del proyecto de destino con la sintaxis `csproj`. Esto indica al comando [`dotnet pack`](dotnet-pack.md) qué empaquetar, colocando los archivos de destinos así como los ensamblados en la carpeta *build* dentro del paquete. Observe el elemento `<ItemGroup>` que tiene la propiedad `Label` establecida en `dotnet pack instructions`, y el destino que se define por debajo.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <Description>Sample Packer</Description>
    <VersionPrefix>0.1.0-preview</VersionPrefix>
    <TargetFramework>netstandard1.3</TargetFramework>
    <DebugType>portable</DebugType>
    <AssemblyName>SampleTargets.PackerTarget</AssemblyName>
  </PropertyGroup>
  <ItemGroup>
    <EmbeddedResource Include="Resources\Pkg\dist-template.xml;compiler\resources\**\*" Exclude="bin\**;obj\**;**\*.xproj;packages\**" />
    <None Include="build\SampleTargets.PackerTarget.targets" />
  </ItemGroup>
  <ItemGroup Label="dotnet pack instructions">
    <Content Include="build\*.targets">
      <Pack>true</Pack>
      <PackagePath>build\</PackagePath>
    </Content>
  </ItemGroup>
  <Target Name="CollectRuntimeOutputs" BeforeTargets="_GetPackageFiles">
    <!-- Collect these items inside a target that runs after build but before packaging. -->
    <ItemGroup>
      <Content Include="$(OutputPath)\*.dll;$(OutputPath)\*.json">
        <Pack>true</Pack>
        <PackagePath>build\</PackagePath>
      </Content>
    </ItemGroup>
  </Target>
  <ItemGroup>
    <PackageReference Include="Microsoft.Extensions.DependencyModel" Version="1.0.1-beta-000933"/>
    <PackageReference Include="Microsoft.Build.Framework" Version="0.1.0-preview-00028-160627" />
    <PackageReference Include="Microsoft.Build.Utilities.Core" Version="0.1.0-preview-00028-160627" />
    <PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
  </ItemGroup>
  <ItemGroup />
  <PropertyGroup Label="Globals">
    <ProjectGuid>463c66f0-921d-4d34-8bde-7c9d0bffaf7b</ProjectGuid>
  </PropertyGroup>
  <PropertyGroup Condition=" '$(TargetFramework)' == 'netstandard1.3' ">
    <DefineConstants>$(DefineConstants);NETSTANDARD1_3</DefineConstants>
  </PropertyGroup>
  <PropertyGroup Condition=" '$(Configuration)' == 'Release' ">
    <DefineConstants>$(DefineConstants);RELEASE</DefineConstants>
  </PropertyGroup>
</Project>
```

Para consumir destinos personalizados se proporciona un elemento `<PackageReference>` que apunta al paquete y su versión dentro del proyecto que se extiende. A diferencia de las herramientas, el paquete de destinos personalizados se incluye en el cierre de dependencia del proyecto de consumo.

El uso del destino personalizado depende exclusivamente de cómo se configure. Como es un destino de MSBuild, puede depender de un destino dado, ejecutarse después de otro destino e invocarse también manualmente mediante el comando `dotnet msbuild -t:<target-name>`.

En cambio, si quiere proporcionar una mejor experiencia de usuario, puede combinar las herramientas por proyecto y los destinos personalizados. En este escenario, la herramienta por proyecto básicamente solo aceptaría todos los parámetros necesarios y lo traduciría en la invocación de [`dotnet msbuild`](dotnet-msbuild.md) necesaria que ejecutaría el destino. Puede ver una muestra de esta clase de sinergia en el [repositorio de ejemplos de MVP Summit 2016 Hackathon](https://github.com/dotnet/MVPSummitHackathon2016) del proyecto [`dotnet-packer`](https://github.com/dotnet/MVPSummitHackathon2016/tree/master/dotnet-packer).

## <a name="path-based-extensibility"></a>Extensibilidad basada en la RUTA DE ACCESO
La extensibilidad basada en la RUTA DE ACCESO se suele usar con equipos de desarrollo, donde necesita una herramienta que abarque conceptualmente más de un único proyecto. La principal desventaja de este mecanismo de extensión es que está vinculado a la máquina donde existe la herramienta. Si lo necesita en otro equipo, tendría que implementarlo.

Este patrón de extensibilidad del conjunto de herramientas de la CLI es muy sencillo. Como se explica en la [información general de la CLI de .NET Core](index.md), el controlador `dotnet` puede ejecutar cualquier comando que se nombre según la convención `dotnet-<command>`. La lógica de resolución predeterminada sondea primero varias ubicaciones y finalmente vuelve a la RUTA DE ACCESO del sistema. Si el comando solicitado existe en la RUTA DE ACCESO del sistema y es un archivo binario que se puede invocar, el controlador `dotnet` lo invoca.

El archivo debe ser ejecutable. En sistemas Unix, esto significa todo lo que tiene el bit de ejecución establecido mediante `chmod +x`. En Windows, puede usar archivos *cmd*.

Echemos un vistazo a una implementación muy sencilla de una herramienta "Hola mundo". Usaremos `bash` y `cmd` en Windows.
En el siguiente comando simplemente reflejaremos "Hola mundo" en la consola.

```bash
#!/bin/bash

echo "Hello World!"
```

```cmd
echo "Hello World"
```

En macOS, podemos guardar este script como `dotnet-hello` y establecer su bit ejecutable con `chmod +x dotnet-hello`. Luego, podemos crear un vínculo simbólico a él en `/usr/local/bin` con el comando `ln -s <full_path>/dotnet-hello /usr/local/bin/`. De esta manera se podrá invocar el comando mediante la sintaxis `dotnet hello`.

En Windows, podemos guardar este script como `dotnet-hello.cmd` y colocarlo en una ubicación que esté en una ruta de acceso del sistema (o puede agregarlo en una carpeta que ya se encuentre en la ruta de acceso). Después de esto, simplemente puede usar `dotnet hello` para ejecutar este ejemplo.
