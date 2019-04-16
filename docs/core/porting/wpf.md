---
title: Procedimiento para portar una aplicación WPF a .NET Core 3.0
description: Aprenderá a portar una aplicación de Windows Presentation Foundation de .NET Framework a .NET Core 3.0 para Windows.
author: Thraka
ms.author: adegeo
ms.date: 03/27/2019
ms.custom: ''
ms.openlocfilehash: 5c7e3aca0a473abb831693244d1b194985f2ef7f
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59342211"
---
# <a name="how-to-port-a-wpf-desktop-app-to-net-core"></a>Procedimiento Procedimiento para portar una aplicación de escritorio WPF a .NET Core

En este artículo se describe cómo portar la aplicación de escritorio basada en Windows Presentation Foundation (WPF) de .NET Framework a .NET Core 3.0. El SDK de .NET Core 3.0 incluye compatibilidad para las aplicaciones WPF. WPF sigue siendo un marco de solo Windows y únicamente se ejecuta en Windows. En este ejemplo se usa la CLI del SDK de .NET Core para crear y administrar un proyecto.

En este artículo, se usan diferentes nombres para identificar los tipos de archivos que se utilizan para la migración. Al migrar su proyecto, sus archivos se nombrarán de manera diferente, así que establezca una relación mental con los que se enumeran a continuación:

| Archivo | Descripción |
| ---- | ----------- |
| **MyApps.sln** | Nombre del archivo de la solución. |
| **MyWPF.csproj** | Nombre del proyecto de WPF de .NET Framework para portar. |
| **MyWPFCore.csproj** | Nombre del nuevo proyecto de .NET Core que crea. |
| **MyAppCore.exe** | Aplicación ejecutable WPF de .NET Core. |

## <a name="prerequisites"></a>Requisitos previos

- [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) para cualquier trabajo de diseñador que desee hacer.

  Instale las cargas de trabajo de Visual Studio siguientes:
  - Desarrollo de escritorio de .NET
  - Desarrollo multiplataforma de .NET

- Proyecto de WPF en funcionamiento en una solución que se compila y ejecuta sin problemas.
- El proyecto debe codificarse en C#. 
- Instale la versión preliminar de [.NET Core 3.0](https://aka.ms/netcore3download) más reciente.

>[!NOTE]
>**Visual Studio 2017** no es compatible con proyectos de .NET Core 3.0. **Visual Studio 2019** admite proyectos de .NET Core 3.0, pero todavía no admite el diseñador de objetos visuales para los proyectos WPF de .NET Core 3.0. Para usar el diseñador de objetos visuales, debe tener un proyecto WPF de .NET en la solución en el que se compartan los archivos con el proyecto de .NET Core.

### <a name="consider"></a>Tenga en cuenta que:

Al portar una aplicación WPF de .NET Framework, hay algunas cosas que debe tener en cuenta.

01. Compruebe que la aplicación cumple los requisitos para la migración.

    Use el [analizador de portabilidad de .NET](../../standard/analyzers/portability-analyzer.md) para determinar si el proyecto se migrará a .NET Core 3.0. Si el proyecto tiene problemas con .NET Core 3.0, el analizador le ayuda a identificar esos problemas.

01. Está usando otra versión de WPF.

    Cuando se publicó .NET Core 3.0 Preview 1, WPF se puso a disposición de los usuarios como código abierto en GitHub. El código para WPF de .NET Core es una bifurcación de la base de código de WPF de .NET Framework. Es posible que existan algunas diferencias y la aplicación no se migre.

01. El [paquete de compatibilidad de Windows][compat-pack] puede ayudarle con la migración.

    Algunas API que están disponibles en .NET Framework no están disponibles en .NET Core 3.0. El [paquete de compatibilidad de Windows][compat-pack] agrega muchas de estas API y puede ayudar a que la aplicación WPF sea compatible con .NET Core.

01. Actualice los paquetes de NuGet utilizados por el proyecto.

    Siempre se recomienda usar las últimas versiones de los paquetes de NuGet antes de cualquier migración. Si la aplicación hace referencia a cualquier paquete de NuGet, actualícelo a la versión más reciente. Asegúrese de que la aplicación se compila correctamente. Tras la actualización, si se han producido errores en el paquete, cambie el paquete a la versión más reciente que no rompa el código.

01. Visual Studio 2019 aún no admite WPF Designer para .NET Core 3.0

    En la actualidad, debe mantener el archivo de proyecto de WPF de .NET Framework existente si quiere usar WPF Designer de Visual Studio.

## <a name="create-a-new-sdk-project"></a>Creación de un nuevo proyecto de SDK

El nuevo proyecto .NET Core 3.0 que cree debe estar en un directorio diferente de su proyecto de .NET Framework. Si ambos están en el mismo directorio, es posible que tenga conflictos con los archivos que se generan en el directorio **obj**. En este ejemplo, se creará un directorio denominado **MyWPFAppCore** en el directorio **SolutionFolder**:

```
SolutionFolder
├───MyApps.sln
├───MyWPFApp
│   └───MyWPF.csproj
└───MyWPFAppCore      <--- New folder for core project
```

A continuación, tendrá que crear el proyecto **MyWPFCore.csproj** en el directorio **MyWPFAppCore**. Puede crear este archivo manualmente utilizando el editor de texto que prefiera. Pegue el siguiente XML:

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
    <UseWPF>true</UseWPF>
  </PropertyGroup>

</Project>
```

Si no desea crear manualmente el archivo de proyecto, puede usar Visual Studio o el SDK de .NET Core para generar el proyecto. Sin embargo, debe eliminar todos los demás archivos generados por la plantilla de proyecto, excepto el archivo de proyecto. Para usar el SDK, ejecute el siguiente comando desde el directorio **SolutionFolder**:

```cli
dotnet new wpf -o MyWPFAppCore -n MyWPFCore
```

Después de crear **MyWPFCore.csproj**, la estructura de directorios debe ser similar a la siguiente:

```
SolutionFolder
├───MyApps.sln
├───MyWPFApp
│   └───MyWPF.csproj
└───MyWPFAppCore
    └───MyWPFCore.csproj
```

Tendrá que agregar el proyecto **MyWPFCore.csproj** a **MyApps.sln** con Visual Studio o la CLI de .NET Core desde el directorio **SolutionFolder**:

```cli
dotnet sln add .\MyWPFAppCore\MyWPFCore.csproj
```

## <a name="fix-assembly-info-generation"></a>Corrección de la generación de información de ensamblado

Los proyectos de Windows Presentation Foundation que se han creado con .NET Framework incluyen un archivo `AssemblyInfo.cs`, que contiene los atributos de ensamblado, como la versión del ensamblado que se va a generar. Los proyectos de estilo SDK generan automáticamente esta información basándose en el archivo de proyecto de SDK. Tener ambos tipos de "información de ensamblado" crea un conflicto. Resuelva este problema deshabilitando la generación automática, lo que obliga al proyecto a usar su archivo `AssemblyInfo.cs` existente.

Hay tres opciones para agregar al nodo `<PropertyGroup>` principal. 

- **GenerateAssemblyInfo**\
Al establecer esta propiedad en `false`, no se generan los atributos del ensamblado. Esto evita el conflicto con el archivo `AssemblyInfo.cs` existente en el proyecto de .NET Framework.

- **AssemblyName**\
El valor de esta propiedad es el binario de salida que se crea al compilar. El nombre no necesita una extensión agregada. Por ejemplo, el uso de `MyCoreApp` genera `MyCoreApp.exe`.

- **RootNamespace**\
El espacio de nombres predeterminado que utiliza el proyecto. Debe coincidir con el espacio de nombres predeterminado del proyecto de .NET Framework.

Agregue estos tres elementos al nodo `<PropertyGroup>` en el archivo `MyWPFCore.csproj`:

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
    <UseWPF>true</UseWPF>

    <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
    <AssemblyName>MyCoreApp</AssemblyName>
    <RootNamespace>MyWPF</RootNamespace>
  </PropertyGroup>

</Project>
```

## <a name="add-source-code"></a>Adición de código fuente
Ahora, el proyecto **MyWPFCore.csproj** no compila ningún código. De forma predeterminada, los proyectos de .NET Core incluyen automáticamente todo el código fuente en el directorio actual y los directorios secundarios. Debe configurar el proyecto para incluir código del proyecto de .NET Framework con una ruta de acceso relativa. Si en el proyecto de .NET Framework se han usado archivos **.resx** para los iconos y los recursos de las ventanas y los controles, también tendrá que incluirlos. 

El primer nodo `<ItemGroup>` que tiene que agregar al proyecto incluye el archivo **App.xaml**, que representa la configuración de inicio y los recursos que usa la aplicación. El archivo **App.xaml** también tiene un archivo **App.xaml.cs** complementario, pero se incluirá de forma automática en otro elemento `<ItemGroup>`.

```xml
  <ItemGroup>
    <ApplicationDefinition Include="..\MyWPFApp\App.xaml">
      <Generator>MSBuild:Compile</Generator>
    </ApplicationDefinition>
  </ItemGroup>
```

A continuación, agregue el siguiente nodo `<ItemGroup>` al proyecto. Cada instrucción incluye un patrón global de archivo que incluye los directorios secundarios. Incluye el código fuente para el proyecto, los archivos de configuración y todos los recursos. El directorio **obj** se ha excluido de forma explícita.

```xml
  <ItemGroup>
    <Compile Include="..\MyWPFApp\**\*.cs" Exclude="..\MyWPFApp\obj\**" />
    <None Include="..\MyWPFApp\**\*.settings" />
    <EmbeddedResource Include="..\MyWPFApp\**\*.resx" />
  </ItemGroup>
```

A continuación, incluya otro nodo `<ItemGroup>` con una entrada `<Page>` para cada archivo **xaml**, del proyecto, excepto para el archivo **App.xaml**. Estos archivos contienen todas las ventanas, páginas y recursos que están en formato **xaml**. Aquí no se puede usar un patrón global y debe agregar una entrada para cada archivo e indicar el elemento `<Generator>` que se usa.

```xml
  <ItemGroup>
    <Page Include="..\MyWPFApp\MainWindow.xaml">
      <Generator>MSBuild:Compile</Generator>
    </Page>
  </ItemGroup>
```

## <a name="add-nuget-packages"></a>Adición de paquetes NuGet

Agregue cada paquete NuGet al que hace referencia el proyecto de .NET Framework al proyecto de .NET Core. 

Lo más probable es que la aplicación WPF de .NET Framework tenga un archivo **packages.config** en el que se incluya una lista de todos los paquetes NuGet a los que hace referencia su proyecto. Puede buscar en esta lista para determinar qué paquetes de NuGet se agregarán al proyecto de .NET Core. Por ejemplo, si el proyecto de .NET Framework hace referencia al paquete NuGet `MahApps.Metro`, agréguelo al proyecto con Visual Studio. También puede agregar la referencia del paquete con la CLI de .NET Core desde el directorio **SolutionFolder**:

```cli
dotnet add .\MyWPFAppCore\MyWPFCore.csproj package MahApps.Metro -v 2.0.0-alpha0262
```

El comando anterior agregaría las siguientes referencias de NuGet al proyecto **MyWPFCore.csproj**:

```xml
  <ItemGroup>
    <PackageReference Include="MahApps.Metro" Version="2.0.0-alpha0262" />
  </ItemGroup>
```

## <a name="problems-compiling"></a>Problemas de compilación

Si tiene problemas al compilar los proyectos, puede que esté usando algunas API solo de Windows que están disponibles en .NET Framework, pero no en .NET Core. Puede intentar agregar el paquete de NuGet del [paquete de compatibilidad de Windows][compat-pack] al proyecto. Este paquete solo se ejecuta en Windows y agrega aproximadamente 20 000 API de Windows a los proyectos de .NET Core y .NET Standard.

```cli
dotnet add .\MyWPFAppCore\MyWPFCore.csproj package Microsoft.Windows.Compatibility
```

El comando anterior agrega lo siguiente al proyecto **MyWPFCore.csproj**:

```xml
  <ItemGroup>
    <PackageReference Include="Microsoft.Windows.Compatibility" Version="2.0.1" />
  </ItemGroup>
```

## <a name="wpf-designer"></a>WPF Designer

Como se detalla en este artículo, Visual Studio 2019 solo admite WPF Designer en los proyectos de .NET Framework. Mediante la creación de un proyecto de .NET Core en paralelo, puede probar el proyecto con .NET Core mientras utiliza el proyecto de .NET Framework para diseñar formularios. El archivo de solución incluye proyectos de .NET Framework y .NET Core. Agregue y diseñe sus formularios y controles en el proyecto de .NET Framework, y en función de los patrones globales de archivos que agreguemos a los proyectos de .NET Core, cualquier archivo nuevo o modificado se incluirá automáticamente en los proyectos de .NET Core.

Una vez que Visual Studio 2019 sea compatible con WPF Designer, podrá copiar y pegar el contenido del archivo de proyecto de .NET Core en el archivo de proyecto de .NET Framework. A continuación, elimine los patrones globales de archivo agregados con los elementos `<Source>` y `<EmbeddedResource>`. Corrija las rutas a cualquier referencia de proyecto utilizada por su aplicación. Esto actualiza eficazmente el proyecto de .NET Framework a un proyecto de .NET Core.
 
## <a name="next-steps"></a>Pasos siguientes

* Obtenga más información sobre el [paquete de compatibilidad de Windows][compat-pack].
* Vea un [vídeo sobre cómo portar](https://www.youtube.com/watch?v=5MomsgkWkVw&list=PLS__JrkRveTMiWxG-Lv4cBwYfMQ6m2gmt) el proyecto de WPF de .NET Framework a .NET Core.

[compat-pack]: windows-compat-pack.md
