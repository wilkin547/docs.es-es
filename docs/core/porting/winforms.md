---
title: Migración de una aplicación de Windows Forms a .NET Core
description: Se detalla cómo migrar una aplicación de Windows Forms de .NET Framework a .NET Core para Windows.
author: Thraka
ms.author: adegeo
ms.date: 03/01/2019
ms.openlocfilehash: dbd522851faa0a4fe435199914a034ee230d3455
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2020
ms.locfileid: "76116027"
---
# <a name="how-to-port-a-windows-forms-desktop-app-to-net-core"></a>Procedimiento para: Migrar una aplicación de escritorio de Windows Forms a .NET Core

En este artículo se explica cómo migrar una aplicación de escritorio basada en Windows Forms de .NET Framework a .NET Core 3.0 o una versión posterior. El SDK de .NET Core 3.0 incluye compatibilidad para las aplicaciones de Windows Forms. Windows Forms sigue siendo un marco de solo Windows y solo se ejecuta en Windows. En este ejemplo se usa la CLI del SDK de .NET Core para crear y administrar un proyecto.

En este artículo, se usan diferentes nombres para identificar los tipos de archivos que se utilizan para la migración. Al migrar su proyecto, sus archivos se nombrarán de manera diferente, así que establezca una relación mental con los que se enumeran a continuación:

| Archivo | Descripción |
| ---- | ----------- |
| **MyApps.sln** | Nombre del archivo de la solución. |
| **MyForms.csproj** | Nombre del proyecto de Windows Forms de .NET Framework para migrar. |
| **MyFormsCore.csproj** | Nombre del nuevo proyecto de .NET Core que crea. |
| **MyAppCore.exe** | Ejecutable de la aplicación de Windows Forms de .NET Core. |

## <a name="prerequisites"></a>Requisitos previos

- [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) para cualquier trabajo de diseñador que desee hacer.

  Instale las cargas de trabajo de Visual Studio siguientes:
  - Desarrollo de escritorio de .NET
  - Desarrollo multiplataforma de .NET Core

- Un proyecto de Windows Forms en funcionamiento en una solución que se construye y ejecuta sin problemas.
- Un proyecto codificado en C#.
- [.NET Core](https://dotnet.microsoft.com/download/dotnet-core) 3.0 o una versión posterior.

> [!NOTE]
> **Visual Studio 2017** no es compatible con proyectos de .NET Core 3.0. **Visual Studio 2019** admite proyectos de .NET Core 3.0, pero todavía no admite el diseñador visual para los proyectos de Windows Forms de .NET Core 3.0. Para usar el diseñador visual, debe tener un proyecto de Windows Forms de .NET en una solución que comparta los archivos de formularios con el proyecto de .NET Core.

### <a name="consider"></a>Tenga en cuenta que:

Al migrar una aplicación de Windows Forms de .NET Framework, hay algunas cosas que debe tener en cuenta.

01. Compruebe que la aplicación cumple los requisitos para la migración.

    Use el [analizador de portabilidad de .NET](../../standard/analyzers/portability-analyzer.md) para determinar si el proyecto se migrará a .NET Core 3.0. Si el proyecto tiene problemas con .NET Core 3.0, el analizador le ayuda a identificar esos problemas.

01. Está usando una versión diferente de Windows Forms.

    Cuando se publicó .NET Core 3.0 (versión preliminar 1), Windows Forms se puso a disposición de los usuarios en código abierto en GitHub. El código para Windows Forms de .NET Core es una bifurcación del código base de Windows Forms de .NET Framework. Es posible que existan algunas diferencias y la aplicación no se migre.

01. El [paquete de compatibilidad de Windows][compat-pack] puede ayudarle con la migración.

    Algunas API que están disponibles en .NET Framework no están disponibles en .NET Core 3.0. El [paquete de compatibilidad de Windows][compat-pack] agrega muchas de estas API y puede ayudar a que su aplicación de Windows Forms sea compatible con .NET Core.

01. Actualice los paquetes de NuGet utilizados por el proyecto.

    Siempre se recomienda usar las últimas versiones de los paquetes de NuGet antes de cualquier migración. Si la aplicación hace referencia a cualquier paquete de NuGet, actualícelo a la versión más reciente. Asegúrese de que la aplicación se compila correctamente. Tras la actualización, si se han producido errores en el paquete, cambie el paquete a la versión más reciente que no rompa el código.

01. Visual Studio 2019 aún no admite el Diseñador de Forms para .NET Core 3.0

    Actualmente, debe mantener el archivo de proyecto de Windows Forms de .NET Framework existente si desea utilizar el Diseñador de Forms de Visual Studio.

## <a name="create-a-new-sdk-project"></a>Creación de un nuevo proyecto de SDK

El nuevo proyecto .NET Core 3.0 que cree debe estar en un directorio diferente de su proyecto de .NET Framework. Si ambos están en el mismo directorio, es posible que tenga conflictos con los archivos que se generan en el directorio **obj**. En este ejemplo, vamos a crear un directorio denominado **MyFormsAppCore** en el directorio **SolutionFolder**:

```
SolutionFolder
├───MyApps.sln
├───MyFormsApp
│   └───MyForms.csproj
└───MyFormsAppCore      <--- New folder for core project
```

A continuación, deberá crear el proyecto **MyFormsCore.csproj** en el directorio **MyFormsAppCore**. Puede crear este archivo manualmente utilizando el editor de texto que prefiera. Pegue el siguiente XML:

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
    <UseWindowsForms>true</UseWindowsForms>
  </PropertyGroup>

</Project>
```

Si no desea crear manualmente el archivo de proyecto, puede usar Visual Studio o el SDK de .NET Core para generar el proyecto. Sin embargo, debe eliminar todos los demás archivos generados por la plantilla de proyecto, excepto el archivo de proyecto. Para usar el SDK, ejecute el siguiente comando desde el directorio **SolutionFolder**:

```dotnetcli
dotnet new winforms -o MyFormsAppCore -n MyFormsCore
```

Después de crear **MyFormsCore.csproj**, la estructura de directorios debe ser similar a la siguiente:

```
SolutionFolder
├───MyApps.sln
├───MyFormsApp
│   └───MyForms.csproj
└───MyFormsAppCore
    └───MyFormsCore.csproj
```

Agregue el proyecto **MyFormsCore.csproj** a **MyApps.sln** con Visual Studio o la CLI de .NET Core desde el directorio **SolutionFolder**:

```dotnetcli
dotnet sln add .\MyFormsAppCore\MyFormsCore.csproj
```

## <a name="fix-assembly-info-generation"></a>Corrección de la generación de información de ensamblado

Los proyectos de Windows Forms que se crearon con .NET Framework incluyen un archivo `AssemblyInfo.cs`, que contiene los atributos de ensamblado, como la versión del ensamblado que se generará. Los proyectos de estilo SDK generan automáticamente esta información basándose en el archivo de proyecto de SDK. Tener ambos tipos de "información de ensamblado" crea un conflicto. Resuelva este problema deshabilitando la generación automática, lo que obliga al proyecto a usar su archivo `AssemblyInfo.cs` existente.

Hay tres opciones para agregar al nodo `<PropertyGroup>` principal.

- **GenerateAssemblyInfo**\
Al establecer esta propiedad en `false`, no se generan los atributos del ensamblado. Esto evita el conflicto con el archivo `AssemblyInfo.cs` existente en el proyecto de .NET Framework.

- **AssemblyName**\
El valor de esta propiedad es el binario de salida que se crea al compilar. El nombre no necesita una extensión agregada. Por ejemplo, el uso de `MyCoreApp` genera `MyCoreApp.exe`.

- **RootNamespace**\
El espacio de nombres predeterminado que utiliza el proyecto. Debe coincidir con el espacio de nombres predeterminado del proyecto de .NET Framework.

Agregue estos tres elementos al nodo `<PropertyGroup>` en el archivo `MyFormsCore.csproj`:

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
    <UseWindowsForms>true</UseWindowsForms>

    <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
    <AssemblyName>MyCoreApp</AssemblyName>
    <RootNamespace>WindowsFormsApp1</RootNamespace>
  </PropertyGroup>

</Project>
```

## <a name="add-source-code"></a>Adición de código fuente

Ahora, el proyecto **MyFormsCore.csproj** no compila ningún código. De forma predeterminada, los proyectos de .NET Core incluyen automáticamente todo el código fuente en el directorio actual y los directorios secundarios. Debe configurar el proyecto para incluir código del proyecto de .NET Framework con una ruta de acceso relativa. Si el proyecto de .NET Framework usa archivos **.resx** para los iconos y los recursos de los formularios, deberá incluirlos también.

Agregue el siguiente nodo `<ItemGroup>` al proyecto. Cada instrucción incluye un patrón global de archivo que incluye los directorios secundarios.

```xml
  <ItemGroup>
    <Compile Include="..\MyFormsApp\**\*.cs" />
    <EmbeddedResource Include="..\MyFormsApp\**\*.resx" />
  </ItemGroup>
```

Como alternativa, puede crear una entrada `<Compile>` o `<EmbeddedResource>` para cada archivo en el proyecto de .NET Framework.

## <a name="add-nuget-packages"></a>Adición de paquetes NuGet

Agregue cada paquete NuGet al que hace referencia el proyecto de .NET Framework al proyecto de .NET Core.

Lo más probable es que su aplicación de Windows Forms de .NET Framework tenga un archivo **packages.config** que contenga una lista de todos los paquetes de NuGet a los que hace referencia su proyecto. Puede buscar en esta lista para determinar qué paquetes de NuGet se agregarán al proyecto de .NET Core. Por ejemplo, si el proyecto de .NET Framework hizo referencia a los paquetes de NuGet `MetroFramework`, `MetroFramework.Design` y `MetroFramework.Fonts`, agregue cada uno al proyecto con Visual Studio o la CLI de .NET Core del directorio **SolutionFolder**:

```dotnetcli
dotnet add .\MyFormsAppCore\MyFormsCore.csproj package MetroFramework
dotnet add .\MyFormsAppCore\MyFormsCore.csproj package MetroFramework.Design
dotnet add .\MyFormsAppCore\MyFormsCore.csproj package MetroFramework.Fonts
```

Los comandos anteriores podrían agregar las siguientes referencias de NuGet al proyecto **MyFormsCore.csproj**:

```xml
  <ItemGroup>
    <PackageReference Include="MetroFramework" Version="1.2.0.3" />
    <PackageReference Include="MetroFramework.Design" Version="1.2.0.3" />
    <PackageReference Include="MetroFramework.Fonts" Version="1.2.0.3" />
  </ItemGroup>
```

## <a name="port-control-libraries"></a>Migración de bibliotecas de controles

Si tiene un proyecto de biblioteca de controles de Windows Forms para migrar, las instrucciones son las mismas que para migrar un proyecto de aplicación de Windows Forms de .NET Framework, excepto algunas opciones de configuración. Y, en lugar de compilar en un archivo ejecutable, se compila en una biblioteca. La diferencia entre el proyecto ejecutable y el proyecto de biblioteca, además de las rutas de acceso para los patrones globales de archivo que incluyen el código fuente, es mínima.

Usando el ejemplo del paso anterior, vamos a expandir los proyectos y archivos con los que estamos trabajando.

| Archivo | Descripción |
| ---- | ----------- |
| **MyApps.sln** | Nombre del archivo de la solución. |
| **MyControls.csproj** | Nombre del proyecto de controles de Windows Forms de .NET Framework para migrar. |
| **MyControlsCore.csproj** | Nombre del nuevo proyecto de biblioteca de .NET Core que crea. |
| **MyCoreControls.dll** | La biblioteca de controles de Windows Forms de .NET Core. |

```
SolutionFolder
├───MyApps.sln
├───MyFormsApp
│   └───MyForms.csproj
├───MyFormsAppCore
│   └───MyFormsCore.csproj
│
├───MyFormsControls
│   └───MyControls.csproj
└───MyFormsControlsCore
    └───MyControlsCore.csproj   <--- New project for core controls
```

Tenga en cuenta las diferencias entre el proyecto `MyControlsCore.csproj` y el proyecto `MyFormsCore.csproj` creado anteriormente.

```diff
 <Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

   <PropertyGroup>
-    <OutputType>WinExe</OutputType>
     <TargetFramework>netcoreapp3.0</TargetFramework>
     <UseWindowsForms>true</UseWindowsForms>

     <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
-    <AssemblyName>MyCoreApp</AssemblyName>
-    <RootNamespace>WindowsFormsApp1</RootNamespace>
+    <AssemblyName>MyControlsCore</AssemblyName>
+    <RootNamespace>WindowsFormsControlLibrary1</RootNamespace>
   </PropertyGroup>

   <ItemGroup>
-    <Compile Include="..\MyFormsApp\**\*.cs" />
-    <EmbeddedResource Include="..\MyFormsApp\**\*.resx" />
+    <Compile Include="..\MyFormsControls\**\*.cs" />
+    <EmbeddedResource Include="..\MyFormsControls\**\*.resx" />
   </ItemGroup>

 </Project>
```

Este es un ejemplo del aspecto que podría tener el archivo de proyecto de biblioteca de controles de Windows Forms de .NET Core:

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>

    <TargetFramework>netcoreapp3.0</TargetFramework>
    <UseWindowsForms>true</UseWindowsForms>

    <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
    <AssemblyName>MyCoreControls</AssemblyName>
    <RootNamespace>WindowsFormsControlLibrary1</RootNamespace>
  </PropertyGroup>

  <ItemGroup>
    <Compile Include="..\MyFormsControls\**\*.cs" />
    <EmbeddedResource Include="..\MyFormsControls\**\*.resx" />
  </ItemGroup>

</Project>
```

Como puede ver, se quitó el nodo `<OutputType>`, que establece el compilador de forma predeterminada para generar una biblioteca en lugar de un archivo ejecutable. `<AssemblyName>` y `<RootNamespace>` se han cambiado. En concreto, `<RootNamespace>` debe coincidir con el espacio de nombres de la biblioteca de controles de Windows Forms que va a migrar. Y, finalmente, los nodos `<Compile>` y `<EmbeddedResource>` se ajustaron para apuntar a la carpeta de la biblioteca de controles de Windows Forms que está migrando.

A continuación, en el proyecto principal **MyFormsCore.csproj** de .NET Core, agregue una referencia a la nueva biblioteca de controles de Windows Forms de .NET Core. Agregue una referencia con Visual Studio o la CLI de .NET Core desde el directorio **SolutionFolder**:

```dotnetcli
dotnet add .\MyFormsAppCore\MyFormsCore.csproj reference .\MyFormsControlsCore\MyControlsCore.csproj
```

El comando anterior agrega lo siguiente al proyecto **MyFormsCore.csproj**:

```xml
  <ItemGroup>
    <ProjectReference Include="..\MyFormsControlsCore\MyControlsCore.csproj" />
  </ItemGroup>
```

## <a name="compilation-problems"></a>Problemas de compilación

Si tiene problemas al compilar los proyectos, puede que esté usando algunas API solo de Windows que están disponibles en .NET Framework, pero no en .NET Core. Puede intentar agregar el paquete de NuGet del [paquete de compatibilidad de Windows][compat-pack] al proyecto. Este paquete solo se ejecuta en Windows y agrega aproximadamente 20 000 API de Windows a los proyectos de .NET Core y .NET Standard.

```dotnetcli
dotnet add .\MyFormsAppCore\MyFormsCore.csproj package Microsoft.Windows.Compatibility
```

El comando anterior agrega lo siguiente al proyecto **MyFormsCore.csproj**:

```xml
  <ItemGroup>
    <PackageReference Include="Microsoft.Windows.Compatibility" Version="3.1.0" />
  </ItemGroup>
```

## <a name="windows-forms-designer"></a>Diseñador de Windows Forms

Como se detalla en este artículo, Visual Studio 2019 solo admite el Diseñador de Forms en los proyectos de .NET Framework. Mediante la creación de un proyecto de .NET Core en paralelo, puede probar el proyecto con .NET Core mientras utiliza el proyecto de .NET Framework para diseñar formularios. El archivo de solución incluye proyectos de .NET Framework y .NET Core. Agregue y diseñe sus formularios y controles en el proyecto de .NET Framework, y en función de los patrones globales de archivos que agreguemos a los proyectos de .NET Core, cualquier archivo nuevo o modificado se incluirá automáticamente en los proyectos de .NET Core.

Una vez que Visual Studio 2019 sea compatible con el Diseñador de Windows Forms, podrá copiar/pegar el contenido de su archivo de proyecto de .NET Core en el archivo de proyecto de .NET Framework. A continuación, elimine los patrones globales de archivo agregados con los elementos `<Source>` y `<EmbeddedResource>`. Corrija las rutas a cualquier referencia de proyecto utilizada por su aplicación. Esto actualiza eficazmente el proyecto de .NET Framework a un proyecto de .NET Core.

## <a name="next-steps"></a>Pasos siguientes

- Obtenga información sobre los [Cambios importantes para la migración de .NET Framework a .NET Core](../compatibility/fx-core.md).
- Obtenga más información sobre el [paquete de compatibilidad de Windows][compat-pack].
- Vea un [vídeo sobre cómo migrar](https://www.youtube.com/watch?v=upVQEUc_KwU) el proyecto de Windows Forms de .NET Framework a .NET Core.

[compat-pack]: windows-compat-pack.md
