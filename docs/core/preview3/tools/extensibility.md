---
title: Modelo de extensibilidad de la CLI de .NET Core
description: Modelo de extensibilidad de la CLI de .NET Core
keywords: CLI, extensibilidad, comandos personalizados, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 11/13/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 1bebd25a-120f-48d3-8c25-c89965afcbcd
translationtype: Human Translation
ms.sourcegitcommit: 1474b2869510d650b7ee69c88ec6b5a9d04a9b75
ms.openlocfilehash: c13349c34af944d5a55d57161246f865274cc888

---

# <a name="net-core-cli-extensibility-model"></a>Modelo de extensibilidad de la CLI de .NET Core 

## <a name="overview"></a>Información general
En este documento se tratan las principales formas de ampliar las herramientas de la CLI y se explican los escenarios que impulsan cada una. Se describe cómo consumir las herramientas y se proporcionan notas cortas sobre cómo compilar ambos tipos de herramientas. 

## <a name="how-to-extend-cli-tools"></a>Cómo extender las herramientas de la CLI
Las herramientas de la CLI de Preview 3 pueden extenderse de tres maneras principales:

1. A través de paquetes de NuGet por proyecto
2. A través de paquetes de NuGet con destinos personalizados  
3. Mediante la RUTA DE ACCESO del sistema

Los tres mecanismos de extensibilidad descritos anteriormente no son mutuamente excluyentes; puede usarlos todos, solo uno o combinarlos. La selección de uno u otro depende en gran medida de cuál sea el objetivo que intenta alcanzar con su extensión.

## <a name="per-project-based-extensibility"></a>Extensibilidad por proyecto
Las herramientas por proyecto son [implementaciones dependientes del marco](../deploying/index.md) que se distribuyen como paquetes de NuGet. Las herramientas solo están disponibles en el contexto del proyecto que hace referencia a ellas y para el que se restauran; la invocación fuera del contexto del proyecto (por ejemplo, fuera del directorio que contiene el proyecto) dará error ya que no se podrá encontrar el comando.

Estas herramientas son perfectas para servidores de compilación, dado que no se necesita nada fuera del archivo de proyecto. El proceso de compilación ejecuta la restauración para el proyecto que se compila y hay herramientas disponibles. Proyectos de lenguajes, como F #, también están en esta categoría; después de todo, cada proyecto solo se puede escribir en un lenguaje específico. 

Finalmente, este modelo de extensibilidad proporciona compatibilidad con la creación de herramientas que necesitan acceso a la salida compilada del proyecto. Por ejemplo, varias herramientas de vista de Razor de aplicaciones [ASP.NET](https://www.asp.net/) MVC se incluyen dentro de esta categoría. 

### <a name="consuming-per-project-tools"></a>Consumo de herramientas por proyecto
Para consumir estas herramientas es necesario agregar un elemento `<DotNetCliToolReference>` para cada herramienta que quiera usar para proteger su archivo. Dentro del elemento `<DotNetCliToolReference>`, se hace referencia el paquete en el que reside la herramienta y se especifica la versión necesaria. Después de ejecutar `dotnet restore`, se restauran la herramienta y sus dependencias. 

Para las herramientas que necesitan cargar la salida de compilación del proyecto para su ejecución, hay normalmente otra dependencia que aparece en las dependencias normales del archivo de proyecto. Como la versión Preview 3 de la CLI usa MSBuild como motor de compilación, se recomienda que estas partes de la herramienta se escriban como destinos y tareas de MSBuild personalizados puesto que pueden formar parte del proceso de compilación en general. Asimismo, pueden obtener fácilmente todos y cada uno de los datos que se producen mediante la compilación, por ejemplo, la ubicación de los archivos de salida, la configuración actual que se compila, etc. Toda esta información de Preview 3 se convierte en un conjunto de propiedades de MSBuild que se pueden leer desde cualquier destino. Más adelante en este documento veremos cómo agregar un destino personalizado mediante NuGet. 

Vamos a ver un ejemplo de cómo agregar una herramienta sencilla tools-only a un proyecto sencillo. Dado un comando de ejemplo llamado `dotnet-api-search` que le permite examinar los paquetes de NuGet hasta encontrar la API especificada, este es un archivo de proyecto de la aplicación de consola que usa esa herramienta:


```xml
<Project ToolsVersion="15.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" />
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp1.1/TargetFramework>
    <VersionPrefix>1.0.0</VersionPrefix>
  </PropertyGroup>
  <ItemGroup>
    <Compile Include="**\*.cs" />
    <EmbeddedResource Include="**\*.resx" />
  </ItemGroup>
  <ItemGroup>
    <PackageReference Include="Microsoft.NETCore.App">
      <Version>1.1.0</Version>
    </PackageReference>
    <PackageReference Include="Microsoft.NET.Sdk">
      <Version>1.0.0-alpha-20161102-2</Version>
      <PrivateAssets>All</PrivateAssets>
    </PackageReference>
  </ItemGroup>

  <!-- The tools reference -->
  <ItemGroup>
    <DotNetCliToolReference Include="dotnet-api-search">
      <Version></Version>
    </DotNetCliToolReference>
  </ItemGroup>

  <Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />
</Project>
```

El elemento `<DotNetCliToolReference>` está estructurado de forma similar al elemento `<PackageReference>`. Necesita como poco el identificador del paquete que contiene la herramienta y su versión. 

### <a name="building-tools"></a>Compilación de herramientas
Como se ha mencionado, las herramientas son simples aplicaciones de consola portátiles. Se compila lo mismo que cualquier aplicación de consola. Después de compilarla, puede usar el comando [`dotnet pack`](dotnet-pack.md) para crear un paquete de NuGet (nupkg) que contiene el código, información sobre sus dependencias. etc. El nombre del paquete puede ser lo que quiera el autor, pero la aplicación que contiene, el archivo binario de la herramienta real, debe respetar las convenciones de `dotnet-<command>` para que `dotnet` pueda invocarlo. 

En los bits de Preview 3, el comando `dotnet pack` no empaquetará el archivo `runtimeconfig.json` necesario para ejecutar la herramienta. Para empaquetar este archivo, tiene dos opciones:

1. Crear un archivo `nuspec` y usar el comando `dotnet nuget pack` disponible recientemente para la CLI de Preview 3 para incluir el archivo
2. Usar el nuevo elemento `<Content>` en un elemento `<ItemGroup>` en el archivo de proyecto para incluir el archivo manualmente

El trabajo con archivos nuspec queda fuera del ámbito de este artículo; sin embargo, puede encontrar mucha información útil en la [documentación oficial de NuGet](https://docs.nuget.org/ndocs/create-packages/creating-a-package#the-role-and-structure-of-the--nuspec-file). Si se decide por el segundo enfoque, puede ver a continuación el archivo `csproj` de ejemplo y cómo está configurado:

```xml
  <ItemGroup>
    <Content Include="$(OutputPath)\*.runtimeconfig.json">
      <Pack>true</Pack>
      <PackagePath>lib\$(TargetFramework)</PackagePath>
    </Content>
  </ItemGroup>
```

Este elemento `<ItemGroup>` indica al comando `dotnet pack` que empaquete cualquier archivo `runtimeconfig.json` del directorio de salida de compilación (designado por la variable `$(OutputPath)`) y que lo coloque en la carpeta `lib` del marco de destino compilado. Este marco de destino compilado está diseñado de forma parecida a la ruta de acceso de salida mediante una propiedad MSBuild. Una vez configurado, el archivo nupkg de herramienta resultante contendrá todo lo necesario para ejecutar la herramienta.

Como las herramientas son aplicaciones portátiles, el usuario que las consume tiene que tener la versión de las bibliotecas .NET Core con la que se compiló la herramienta para poder ejecutar esta. Cualquier otra dependencia que use la herramienta y que no esté contenida en las bibliotecas .NET Core se restauran y colocan en la caché de NuGet. Por lo tanto, la herramienta entera se ejecuta con los ensamblados de las bibliotecas .NET Core, así como los ensamblados de la caché de NuGet. 

Estas clases de herramientas tienen un gráfico de dependencias que es completamente independiente del gráfico de dependencias del proyecto que los usa. El proceso de restauración restaura primero las dependencias del proyecto y, a continuación, cada una de las herramientas y sus dependencias. 

Puede encontrar más ejemplos y diferentes combinaciones de esto en el [repositorio de la CLI de .NET Core](https://github.com/dotnet/cli/tree/rel/1.0.0-preview2/TestAssets/TestProjects). También puede ver las [herramientas de implementación usadas](https://github.com/dotnet/cli/tree/rel/1.0.0-preview2/TestAssets/TestPackages) en el mismo repositorio. 

### <a name="custom-targets"></a>Destinos personalizados
NuGet lleva tiempo con la funcionalidad para empaquetar archivos de destino y propiedades de MSBuild. La documentación oficial sobre ello se puede encontrar en el [sitio de documentación de NuGet](https://docs.nuget.org/ndocs/create-packages/creating-a-package#including-msbuild-props-and-targets-in-a-package). Con el paso en la CLI al uso de MSBuild, el mismo mecanismo de extensibilidad se aplica a proyectos de .NET Core. Este tipo de extensibilidad se usaría cuando quisiera extender el proceso de compilación o quisiera acceder a alguno de los artefactos de dicho proceso, como los archivos generados, inspeccionar la configuración bajo la que se invoca la compilación etc. 

El archivo de proyecto del destino de ejemplo se incluye a continuación como referencia. En él se muestra cómo usar la nueva sintaxis de `csproj` para indicar al comando `dotnet pack` qué empaquetar para colocar los archivos de destino y los ensamblados en la carpeta `build` dentro del paquete. Anote el elemento `<ItemGroup>` a continuación que tiene la propiedad `Label` establecida en "dotnet pack instructions". 

```xml
<Project ToolsVersion="15.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" />
  <PropertyGroup>
    <Description>Sample Packer</Description>
    <VersionPrefix>0.1.0-preview</VersionPrefix>
    <TargetFramework>netstandard1.3</TargetFramework>
    <DebugType>portable</DebugType>
    <AssemblyName>SampleTargets.PackerTarget</AssemblyName>
  </PropertyGroup>
  <ItemGroup>
    <Compile Include="**\*.cs" Exclude="bin\**;obj\**;**\*.xproj;packages\**" />
    <EmbeddedResource Include="**\*.resx" Exclude="bin\**;obj\**;**\*.xproj;packages\**" />
    <EmbeddedResource Include="Resources\Pkg\dist-template.xml;compiler\resources\**\*" Exclude="bin\**;obj\**;**\*.xproj;packages\**" />
  </ItemGroup>
  <ItemGroup>
    <None Include="build\SampleTargets.PackerTarget.targets" />
  </ItemGroup>
  <ItemGroup Label="dotent pack instructions">
    <Content Include="build\*.targets;$(OutputPath)\*.dll;$(OutputPath)\*.json">
      <Pack>true</Pack>
      <PackagePath>build\</PackagePath>
    </Content>
  </ItemGroup>
  <ItemGroup>
    <PackageReference Include="Microsoft.NET.Sdk">
      <Version>1.0.0-alpha-20161029-1</Version>
      <PrivateAssets>All</PrivateAssets>
    </PackageReference>
    <PackageReference Include="Microsoft.Extensions.DependencyModel">
      <Version>1.0.1-beta-000933</Version>
    </PackageReference>
    <PackageReference Include="Microsoft.Build.Framework">
      <Version>0.1.0-preview-00028-160627</Version>
    </PackageReference>
    <PackageReference Include="Microsoft.Build.Utilities.Core">
      <Version>0.1.0-preview-00028-160627</Version>
    </PackageReference>
    <PackageReference Include="Newtonsoft.Json">
      <Version>9.0.1</Version>
    </PackageReference>
  </ItemGroup>
  <ItemGroup Condition=" '$(TargetFramework)' == 'netstandard1.3' ">
    <PackageReference Include="NETStandard.Library">
      <Version>1.6.0</Version>
    </PackageReference>
  </ItemGroup>
  <ItemGroup />
  <PropertyGroup Condition=" '$(TargetFramework)' == 'netstandard1.3' ">
    <DefineConstants>$(DefineConstants);NETSTANDARD1_3</DefineConstants>
  </PropertyGroup>
  <PropertyGroup Condition=" '$(Configuration)' == 'Release' ">
    <DefineConstants>$(DefineConstants);RELEASE</DefineConstants>
  </PropertyGroup>
  <Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />
</Project>
```

Para consumir destinos personalizados se proporciona un elemento `<PackageReference>` que apunta al paquete y su versión dentro del proyecto que se extiende. A diferencia de las herramientas, el paquete de destinos personalizados se incluye en el cierre de dependencia del proyecto de consumo. 

El uso del destino personalizado depende exclusivamente de cómo se configure. Puesto que es el destino habitual de MSBuild, puede depender de un destino dado, ejecutarse después de otro destino e invocarse también manualmente mediante el comando `dotnet msbuild /t:<target-name>`. 

Sin embargo, si desea proporcionar una mejor experiencia de usuario, puede combinar las herramientas por proyecto y los destinos personalizados. En este escenario, la herramienta por proyecto básicamente solo aceptaría todos los parámetros necesarios y lo traduciría en la invocación de `dotnet msbuild` necesaria que ejecutaría el destino. Puede ver una muestra de esta clase de sinergia en el [repositorio de ejemplos de MVP Summit 2016 Hackathon](https://github.com/dotnet/MVPSummitHackathon2016) del proyecto [`dotnet-packer`](https://github.com/dotnet/MVPSummitHackathon2016/tree/master/dotnet-packer). 

### <a name="path-based-extensibility"></a>Extensibilidad basada en la RUTA DE ACCESO
La extensibilidad basada en la RUTA DE ACCESO se suele usar con equipos de desarrollo, donde necesita una herramienta que abarque conceptualmente más de un único proyecto. La principal desventaja de este mecanismo de extensiones es que está vinculado a la máquina donde existe la herramienta. Si lo necesita en otro equipo, tendría que implementarlo.

Este patrón de extensibilidad del conjunto de herramientas de la CLI es muy sencillo. Como se explica en la [información general de la CLI de .NET Core](index.md), el controlador `dotnet` puede ejecutar cualquier comando que se nombre según la convención `dotnet-<command>`. La lógica de resolución predeterminada sondeará primero varias ubicaciones y finalmente llegará a la RUTA DE ACCESO del sistema. Si el comando solicitado existe en la RUTA DE ACCESO del sistema y es un archivo binario que se puede invocar, el controlador `dotnet` lo invoca. 

El archivo binario puede ser casi cualquier cosa que el sistema operativo pueda ejecutar. En sistemas Unix, esto significa todo lo que tiene el bit de ejecución establecido mediante `chmod +x`. En Windows, significa todo lo que Windows sabe ejecutar. 

Por ejemplo, echemos un vistazo a una implementación muy sencilla de un comando `dotnet clean`. Usaremos `bash` para implementar este comando. El comando eliminará simplemente los directorios `bin/` y `obj/` del directorio actual. Si el argumento `--lock` se pasa a él, también se elimina el archivo `project.lock.json`. La totalidad del comando se proporciona a continuación. 

```bash
#!/bin/bash

# Delete the bin and obj dirs
rm -rf bin/ obj/

LOCK_FILE=$1
if [[ "$LOCK_FILE" = "--lock" ]]; then
    rm project.lock.json
fi


echo "Cleaning complete..."
```

En macOS, podemos guardar este script como `dotnet-clean` y establecer su bit ejecutable con `chmod +x dotnet-clean`. Luego, podemos crear un vínculo simbólico a él en `/usr/local/bin` con el comando `ln -s dotnet-clean /usr/local/bin/`. De esta manera se podrá invocar el comando de limpieza mediante la sintaxis `dotnet clean`. Para probar esto, cree una aplicación ejecutando `dotnet build` en él y, luego, ejecute `dotnet clean`. 

## <a name="conclusion"></a>Conclusión
Las herramientas de la CLI de .NET Core permiten tres puntos de extensibilidad principales. Las herramientas por proyecto están contenidas en el contexto del proyecto, pero permiten la instalación fácil mediante la restauración. Los destinos personalizados permiten extender fácilmente el proceso de compilación con tareas personalizadas. Las herramientas basadas en la RUTA DE ACCESO son buenas para herramientas entre proyectos generales que se pueden usar en una sola máquina. 




<!--HONumber=Jan17_HO3-->


