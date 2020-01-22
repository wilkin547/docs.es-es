---
title: Migración de proyectos de C++/CLI a .NET Core
description: Obtenga información sobre la migración de proyectos de C++/CLI a .NET Core.
author: mjrousos
ms.date: 01/10/2020
ms.openlocfilehash: eb03f2a5ff42e8279fd3ebd6ee6fb6d955f6798d
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964864"
---
# <a name="how-to-port-a-ccli-project-to-net-core"></a>Migración de un proyecto de C++/CLI a .NET Core

A partir de .NET Core 3.1 y Visual Studio 2019 versión 16.4, los [proyectos de C++/CLI](/cpp/dotnet/dotnet-programming-with-cpp-cli-visual-cpp) pueden tener como destino .NET Core. Esta compatibilidad permite migrar aplicaciones de escritorio de Windows con capas de interoperabilidad de C++/CLI a .NET Core. En este artículo se explica cómo migrar proyectos de C++/CLI desde .NET Framework a .NET Core 3.1.

## <a name="ccli-net-core-limitations"></a>Limitaciones de .NET Core respecto a C++/CLI

Hay algunas limitaciones importantes en cuanto a la migración de proyectos de C++/CLI a .NET Core en comparación con otros lenguajes:

* La compatibilidad de C++/CLI con .NET Core es solo en Windows.
* Los proyectos de C++/CLI no pueden tener como destino .NET Standard, solo .NET Core (o .NET Framework).
* Los proyectos de C++/CLI no admiten el nuevo formato de archivo de proyecto de estilo SDK. En su lugar, aun cuando el destino sea .NET Core, los proyectos de C++/CLI usan el formato de archivo vcxproj existente.
* Los proyectos de C++/CLI no pueden tener como destino varias plataformas de .NET. Si necesita compilar un proyecto de C++/CLI para .NET Framework y .NET Core, use archivos de proyecto independientes.
* .NET Core no admite la compilación `-clr:pure` o `-clr:safe`, solo la nueva opción `-clr:netcore` (que es equivalente a `-clr` para .NET Framework).

## <a name="port-a-ccli-project"></a>Migración de un proyecto de C++/CLI

Para migrar un proyecto de C++/CLI a .NET Core, realice los cambios siguientes en el archivo vcxproj. Estos pasos de migración difieren de los necesarios para otros tipos de proyectos, ya que los proyectos de C++/CLI no usan archivos de proyecto de estilo SDK.

1. Reemplace las propiedades de `<CLRSupport>true</CLRSupport>` por `<CLRSupport>NetCore</CLRSupport>`. Esta propiedad suele estar en grupos de propiedades específicas de la configuración, por lo que puede que tenga que reemplazarla en varios lugares.
2. Reemplace las propiedades de `<TargetFrameworkVersion>` por `<TargetFramework>netcoreapp3.1</TargetFramework>`.
3. Quite todas las referencias de .NET Framework (como `<Reference Include="System" />`). Cuando se usa `<CLRSupport>NetCore</CLRSupport>`, se hace referencia automáticamente a los ensamblados del SDK de .NET Core.
4. Actualice el uso de API en los archivos cpp, según sea necesario, para quitar las API que no están disponibles en .NET Core. Dado que los proyectos de C++/CLI tienden a ser capas de interoperabilidad bastante finas, no se suelen necesitar muchos cambios. Se puede usar el [Analizador de portabilidad de .NET](../../standard/analyzers/portability-analyzer.md) para identificar las API de .NET no compatibles que usan los binarios de C++/CLI, como con los binarios puramente administrados. Las instrucciones para determinar la portabilidad del código y para actualizar los proyectos de modo que funcionen con las API de .NET Core están disponibles en la [guía de portabilidad de bibliotecas](./libraries.md#determine-portability).

### <a name="wpf-and-windows-forms-usage"></a>Uso de WPF y Windows Forms

Los proyectos de C++/CLI de .NET Core pueden usar las API de Windows Forms y WPF. Para usar estas API de escritorio de Windows, debe agregar referencias de marco de trabajo explícitas a las bibliotecas de interfaces de usuario. Los proyectos de estilo SDK que usan las API de escritorio de Windows hacen referencia a las bibliotecas de marcos de trabajo necesarias de forma automática mediante el SDK de `Microsoft.NET.Sdk.WindowsDesktop`. Dado que los proyectos de C++/CLI no usan el formato de proyecto de estilo SDK, necesitan agregar referencias de marco de trabajo explícitas si el destino es .NET Core.

Para usar API de Windows Forms, agregue esta referencia al archivo vcxproj:

```xml
<!-- Reference all of Windows Forms -->
<FrameworkReference Include="Microsoft.WindowsDesktop.App.WindowsForms" />
```

Para usar API de WPF, agregue esta referencia al archivo vcxproj:

```xml
<!-- Reference all of WPF -->
<FrameworkReference Include="Microsoft.WindowsDesktop.App.WPF" />
```

Para usar API de Windows Forms y WPF, agregue esta referencia al archivo vcxproj:

```xml
<!-- Reference the entirety of the Windows desktop framework:
     Windows Forms, WPF, and the types that provide integration between them -->
<FrameworkReference Include="Microsoft.WindowsDesktop.App" />
```

De momento no es posible agregar estas referencias mediante el administrador de referencias de Visual Studio. En su lugar, actualice el archivo de proyecto de forma manual. Esta actualización se puede realizar en Visual Studio si se descarga el proyecto y luego se edita el archivo de proyecto. También puede usar otro editor, como VS Code.

## <a name="build-without-msbuild"></a>Compilación sin MSBuild

También es posible compilar proyectos de C++/CLI sin usar MSBuild. Siga estos pasos para compilar un proyecto de C++/CLI para .NET Core directamente con *cl.exe* y *link.exe*:

1. Al compilar, pase `-clr:netcore` a *cl.exe*.
2. Haga referencia a los ensamblados de referencia de .NET Core necesarios.
3. Al vincular, proporcione el directorio de host de la aplicación .NET Core como `LibPath` (de modo que se pueda encontrar *ijwhost.lib*).
4. Copie *ijwhost.dll* (desde el directorio de host de la aplicación .NET Core) en el directorio de salida del proyecto.
5. Asegúrese de que exista un archivo [runtimeconfig.json](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) para el primer componente de la aplicación que va a ejecutar el código administrado. Si la aplicación tiene un punto de entrada administrado, se crea un archivo `runtime.config` y se copia automáticamente. Pero si la aplicación tiene un punto de entrada nativo, debe crear un archivo `runtimeconfig.json` para que la primera biblioteca de C++/CLI use el runtime de .NET Core.

## <a name="known-issues"></a>Problemas conocidos

Hay un par de problemas conocidos que se deben tener en cuentan a la hora de trabajar con proyectos de C++/CLI cuyo destino es .NET Core.

* Una referencia de marco de trabajo de WPF en proyectos de C++/CLI de .NET Core actualmente provoca algunas advertencias superfluas sobre la imposibilidad de importar símbolos. Estas advertencias se pueden pasar por alto sin problemas y se deberían corregir en breve.
* Si la aplicación tiene un punto de entrada nativo, la biblioteca de C++/CLI que primero ejecuta el código administrado necesita un archivo [runtimeconfig.json](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md). Este archivo de configuración se usa cuando se inicia el runtime de .NET Core. Los proyectos de C++/CLI aún no crean archivos `runtimeconfig.json` automáticamente en tiempo de compilación, por lo que el archivo debe generarse manualmente. Si se llama a una biblioteca de C++/CLI desde un punto de entrada administrado, esta no necesita un archivo `runtimeconfig.json` (puesto que el ensamblado del punto de entrada tiene uno que se usa al iniciar el runtime). A continuación se muestra un archivo `runtimeconfig.json` de ejemplo sencillo. Para obtener más información, vea la [especificación en GitHub](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).

    ```json
    {
          "runtimeOptions": {
             "tfm": "netcoreapp3.1",
             "framework": {
                "name": "Microsoft.NETCore.App",
                "version": "3.1.0"
             }
          }
    }
    ```
