---
title: Uso de MSBuild para compilar proyectos .NET Core
description: Uso de MSBuild para compilar proyectos .NET Core
keywords: .NET, .NET Core
author: dsplaisted
manager: wpickett
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 13c66464-4f14-4db6-aa8b-06f25e7ba894
translationtype: Human Translation
ms.sourcegitcommit: a04755da6417bb28bad5f28a18ead9feeba2d957
ms.openlocfilehash: 5d37e78be88828d6c82777f96b6334903aecbe53

---

# <a name="using-msbuild-to-build-net-core-projects"></a>Uso de MSBuild para compilar proyectos .NET Core

Las herramientas de .NET Core [migrarán de project.json a proyectos basados en MSBuild](https://blogs.msdn.microsoft.com/dotnet/2016/05/23/changes-to-project-json/).
Se espera que la primera versión de las herramientas de .NET Core que usen MSBuild se incluyan en la versión siguiente de Visual Studio.  Sin embargo, actualmente es posible usar MSBuild para los proyectos .NET Core. En esta página aprenderá a hacerlo.

Se recomienda que la mayor parte de las personas que tienen como destino .NET Core en proyectos *nuevos* usen la experiencia de herramientas predeterminada con project.json debido a las razones siguientes:

- MSBuild todavía admite una gran cantidad de las ventajas de project.json.
- Gran parte de las herramientas basadas en ASP.NET actualmente no funciona con los proyectos de MSBuild.
- Cuando finalmente lancemos las herramientas de .NET Core que usen MSBuild, se podrá convertir directamente de project.json a proyectos de MSBuild. 

Es posible que desee usar MSBuild para establecer a .NET Core como destino para los proyectos existentes que ya usan MSBuild al que desea trasladar a .NET Core, o bien si usa la extensibilidad de MSBuild en la compilación para los escenarios que no adecuados para los proyectos de project.json.

## <a name="prerequisites"></a>Requisitos previos

- [Visual Studio 2015 Update 3](https://www.visualstudio.com/en-us/news/releasenotes/vs2015-update3-vs) o superior
- [Herramientas de .NET Core para Visual Studio 2015](https://www.visualstudio.com/downloads/download-visual-studio-vs)
- Extensión de Visual Studio para NuGet [v3.5.0-beta](https://dist.nuget.org/visualstudio-2015-vsix/v3.5.0-beta/NuGet.Tools.vsix) o posterior

## <a name="creating-a-library-targeting-net-core"></a>Creación de una biblioteca con .NET Core como destino

1. En la barra de menús de Visual Studio, elija **Archivo** | **Nuevo** | **Proyecto** y seleccione **Biblioteca de clases (portable)**.

  ![Nuevo proyecto](./media/target-dotnetcore-with-msbuild/new-project-dialog-class-library-portable.png)

2. Elija un nombre y una ubicación para el proyecto y, luego, haga clic en **Aceptar**.

3. Aparecerá el cuadro de diálogo "Agregar Biblioteca de clases portable".  Seleccione **.NET Framework 4.6** y **ASP.NET Core 1.0** como destinos y haga clic en **Aceptar**.

  ![Cuadro de diálogo de destinos portátiles](./media/target-dotnetcore-with-msbuild/pcl-targets-dialog-net46-aspnetcore10.png)

4. En el Explorador de soluciones, haga clic con el botón derecho en el proyecto y, luego, elija **Propiedades**.
5. En la pestaña **Biblioteca** de las propiedades del proyecto, haga clic en el vínculo **Usar como destino la plataforma del estándar .NET** y haga clic en **Sí** en el cuadro de diálogo que aparece.
6. Abra el archivo `project.json` en el proyecto y haga los cambios siguientes:
    - Cambie el número de versión del paquete `NETStandard.Library` a `1.6.0` (esta es la versión .NET Core 1.0 del paquete).
    - Agregue la definición de `imports` que aparece a continuación dentro de la definición del marco de trabajo `netstandard1.6`.  Esto permitirá que el proyecto haga referencia a paquetes NuGet compatibles con .NET Core que no se actualizaron para tener como destino el estándar .NET.

        ```json
        "netstandard1.6": {
            "imports": [ "dnxcore50", "portable-net452" ]
        }
        ```

## <a name="creating-a-net-core-console-application"></a>Creación de una aplicación de consola .NET Core
Crear una aplicación de consola para .NET Core requiere cierta personalización del proceso de compilación de MSBuild.  Puede encontrar un proyecto de ejemplo para una aplicación de consola .NET Core llamada [CoreApp](https://github.com/dotnet/corefxlab/tree/master/samples/NetCoreSample/CoreApp) en el repositorio [corefxlab](https://github.com/dotnet/corefxlab).  Otra buena opción es comenzar con [coretemplate](https://github.com/mellinoe/coretemplate), que usa archivos de destinos de MSBuild independientes para establecer como destino a .NET Core en lugar de colocar los cambios directamente en el archivo del proyecto.  

También se puede comenzar a través de la creación de un proyecto en Visual Studio y su modificación para que establezca .NET Core como destino.  Las instrucciones que aparecen a continuación muestran los pasos mínimos que debe realizar para que esto funcione.  A diferencia de [CoreApp](https://github.com/dotnet/corefxlab/tree/master/samples/NetCoreSample/CoreApp) o [coretemplate](https://github.com/mellinoe/coretemplate), un proyecto que se crea de esta manera no incluirá configuraciones para tener a Linux y macOS como destinos.

1. En la barra de menús de Visual Studio, elija **Archivo** | **Nuevo** | **Proyecto** y seleccione **Aplicación de consola**.
2. Elija un nombre y una ubicación para el proyecto y, luego, haga clic en **Aceptar**.
3. En el Explorador de soluciones, haga clic con el botón derecho en el proyecto, elija **Propiedades** y, luego, vaya a la pestaña **Compilación**.
4. En el menú desplegable **Configuración** (que se encuentra en la parte superior de la página de propiedades), seleccione **Todas las configuraciones** y, luego, cambie **Destino de la plataforma** a **x64**.
5. Elimine el archivo `app.config` del proyecto.
6. Agregue un archivo `project.json` al proyecto con el contenido siguiente:

    ```json
    {
        "dependencies": {
            "Microsoft.NETCore.App": "1.0.0-rc2-3002702"
        },
        "runtimes": {
            "win7-x64": { },
            "ubuntu.14.04-x64": { },
            "osx.10.10-x64": { }
        },
        "frameworks": {
            "netcoreapp1.0": {
                "imports": [ "dnxcore50", "portable-net452" ]
            }
        }
    }
    ```

7. En el Explorador de soluciones, haga clic con el botón derecho en el proyecto, elija **Descargar proyecto**, vuelva a hacer clic con el botón derecho y, luego, elija **Editar _MyProj.csproj_** y haga los cambios siguientes.
    - Quite todos los elementos `Reference` predeterminados (a `System`, `System.Core`, etc.).
    - Agregue las propiedades siguientes al primer `PropertyGroup` del proyecto:

        ```xml
        <TargetFrameworkIdentifier>.NETCoreApp</TargetFrameworkIdentifier>
        <TargetFrameworkVersion>v1.0</TargetFrameworkVersion>
        <BaseNuGetRuntimeIdentifier>win7</BaseNuGetRuntimeIdentifier>
        <NoStdLib>true</NoStdLib>
        <NoWarn>$(NoWarn);1701</NoWarn>
        ```

    - Agregue lo siguiente al final del archivo (después de la importación de `Microsoft.CSharp.Targets`):

        ```xml
        <PropertyGroup>
            <!-- We don't use any of MSBuild's resolution logic for resolving the framework, so just set these two
                    properties to any folder that exists to skip the GetReferenceAssemblyPaths task (not target) and
                    to prevent it from outputting a warning (MSB3644).
                -->
            <_TargetFrameworkDirectories>$(MSBuildThisFileDirectory)</_TargetFrameworkDirectories>
            <_FullFrameworkReferenceAssemblyPaths>$(MSBuildThisFileDirectory)</_FullFrameworkReferenceAssemblyPaths>

            <!-- MSBuild thinks all EXEs need binding redirects, not so for CoreCLR! -->
            <AutoUnifyAssemblyReferences>true</AutoUnifyAssemblyReferences>
            <AutoGenerateBindingRedirects>false</AutoGenerateBindingRedirects>

            <!-- Set up debug options to run with host, and to use the CoreCLR debug engine -->
            <StartAction>Program</StartAction>
            <StartProgram>$(TargetDir)dotnet.exe</StartProgram>
            <StartArguments>$(TargetPath)</StartArguments>
            <DebugEngines>{2E36F1D4-B23C-435D-AB41-18E608940038}</DebugEngines>
        </PropertyGroup>
        ```

    - Cierre el archivo .csproj y recargue el proyecto en Visual Studio.

8. Debería poder ejecutar el programa con F5 en Visual Studio, o bien desde la línea de comandos en la carpeta de salida con`dotnet MyApp.exe` 



<!--HONumber=Nov16_HO1-->


