---
title: Creación de una plantilla de proyecto para dotnet new
description: Obtenga información sobre cómo crear una plantilla de proyecto para el comando dotnet new.
author: thraka
ms.date: 06/25/2019
ms.topic: tutorial
ms.author: adegeo
ms.openlocfilehash: f53f4037f832265a35f65bf2e5096c7e5a37bcf1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "77503534"
---
# <a name="tutorial-create-a-project-template"></a>Tutorial: Creación de una plantilla de proyecto

Con .NET Core, puede crear e implementar plantillas que generan proyectos, archivos e inclusos recursos. Este tutorial es el segundo de una serie que enseña a crear, instalar y desinstalar plantillas para usarlas con el comando `dotnet new`.

En esta parte de la serie, aprenderá a:

> [!div class="checklist"]
>
> * Crear los recursos de una plantilla de proyecto.
> * Crear el archivo y la carpeta de configuración de la plantilla.
> * Instalar una plantilla desde una ruta de acceso de archivo.
> * Probar una plantilla de elemento.
> * Desinstalar una plantilla de elemento.

## <a name="prerequisites"></a>Requisitos previos

* Complete la [parte 1](cli-templates-create-item-template.md) de esta serie de tutoriales.
* Abra un terminal y vaya a la carpeta _working\templates_.

## <a name="create-a-project-template"></a>Creación de una plantilla de proyecto

Las plantillas de proyecto generan proyectos listos para ejecutarse que facilita a los usuarios empezar a trabajar con un espacio de trabajo de código. .NET Core incluye algunas plantillas de proyecto, como una aplicación de consola o una biblioteca de clases. En este ejemplo, creará un proyecto de consola nuevo que habilita C# 8.0 y genera un punto de entrada `async main`.

En el terminal, vaya a la carpeta _working\templates_ y cree una subcarpeta denominada _consoleasync_. Entre a la subcarpeta y ejecute `dotnet new console` para generar la aplicación de consola estándar. Para crear una plantilla nueva, tendrá que editar los archivos que genere esta plantilla.

```console
working
└───templates
    └───consoleasync
            consoleasync.csproj
            Program.cs
```

## <a name="modify-programcs"></a>Modificación de Program.cs

Abra el archivo _program.cs_. El proyecto de la consola no usa un punto de entrada asincrónico, por lo que vamos a agregarlo. Cambie el código por lo siguiente y guarde el archivo.

```csharp
using System;
using System.Threading.Tasks;

namespace consoleasync
{
    class Program
    {
        static async Task Main(string[] args)
        {
            await Console.Out.WriteAsync("Hello World with C# 8.0!");
        }
    }
}
```

## <a name="modify-consoleasynccsproj"></a>Modificación de consoleasync.csproj

Actualicemos la versión del lenguaje C# que usa el proyecto a la versión 8.0. Edite el archivo _consoleasync.csproj_ y agregue el valor `<LangVersion>` a un nodo `<PropertyGroup>`.

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.2</TargetFramework>

    <LangVersion>8.0</LangVersion>

  </PropertyGroup>
  
</Project>
```

## <a name="build-the-project"></a>Compilar el proyecto

Antes de completar una plantilla de proyecto, debe probarla para asegurarse de que se compila y ejecuta correctamente.

En el terminal, ejecute el comando siguiente.

```dotnetcli
dotnet run
```

Obtendrá la siguiente salida.

```console
Hello World with C# 8.0!
```

Puede eliminar las carpetas _obj_ y _bin_ creadas si usa `dotnet run`. La eliminación de estos archivos garantizar que la plantilla solo incluya los archivos relacionados con la plantilla y no cualquier archivo que resulte de una acción de compilación.

Ahora que creó el contenido de la plantilla, debe crear su configuración en la carpeta raíz de la plantilla.

## <a name="create-the-template-config"></a>Creación de la configuración de una plantilla

En .NET Core, las plantillas se reconocen con una carpeta especial y un archivo de configuración que existen en la raíz de la plantilla. En este tutorial, la carpeta de la plantilla se encuentra en _working\templates\consoleasync_.

Cuando se crea una plantilla, todos los archivos y las carpetas de la carpeta de la plantilla se incluyen como parte de la plantilla, a excepción de la carpeta de configuración especial. Esta carpeta de configuración se denomina _.template.config_.

En primer lugar, cree una subcarpeta con el nombre _.template.config_ y entre en ella. Luego, cree un archivo denominado _template.json_. La estructura de carpetas debe tener este aspecto.

```console
working
└───templates
    └───consoleasync
        └───.template.config
                template.json
```

Abra _template.json_ con el editor de texto que prefiera, pegue el código JSON siguiente y guárdelo.

```json
{
  "$schema": "http://json.schemastore.org/template",
  "author": "Me",
  "classifications": [ "Common", "Console", "C#8" ],
  "identity": "ExampleTemplate.AsyncProject",
  "name": "Example templates: async project",
  "shortName": "consoleasync",
  "tags": {
    "language": "C#",
    "type": "project"
  }
}
```

Este archivo de configuración contiene todos los valores de la plantilla. Puede ver los valores básicos, como `name` y `shortName`, pero también hay un valor `tags/type` que está establecido en `project`. Esto diseña la plantilla como una plantilla de proyecto. No hay ninguna restricción en el tipo de plantilla que crea. Los valores `item` y `project` son nombres comunes que .NET Core recomienda para que los usuarios puedan filtrar fácilmente el tipo de plantilla que buscan.

El elemento `classifications` representa la columna **tags** que ve cuando ejecuta `dotnet new` y obtiene una lista de plantillas. Los usuarios también pueden hacer una búsqueda según las etiquetas de clasificación. No confunda la propiedad `tags` del archivo .json con la lista de etiquetas `classifications`. Lamentablemente, son dos elementos que tienen nombres similares. El esquema completo del archivo *template.json* puede encontrarse en el [Almacenamiento del esquema JSON](http://json.schemastore.org/template). Para más información sobre el archivo *template.json*, consulte la [wiki de plantillas dotnet](https://github.com/dotnet/templating/wiki).

Ahora que tiene un archivo _.template.config/template.json_ válido, la plantilla está lista para instalarla. Antes de instalar la plantilla, asegúrese de eliminar cualquier archivo o carpeta de archivos adicional que no quiere que se incluya en la plantilla, como las carpetas _bin_ o _obj_. En el terminal, vaya a la carpeta _consoleasync_ y ejecute `dotnet new -i .\` para instalar la plantilla ubicada en la carpeta actual. Si usa un sistema operativo Linux o macOS, use una barra diagonal: `dotnet new -i ./`.

Este comando genera la lista de las plantillas instaladas, que debería incluir la suya.

```dotnetcli
dotnet new -i .\
```

Verá un resultado similar al siguiente.

```console
Usage: new [options]

Options:
  -h, --help          Displays help for this command.
  -l, --list          Lists templates containing the specified name. If no name is specified, lists all templates.

... cut to save space ...

Templates                                         Short Name            Language          Tags
-------------------------------------------------------------------------------------------------------------------------------
Console Application                               console               [C#], F#, VB      Common/Console
Example templates: async project                  consoleasync          [C#]              Common/Console/C#8
Class library                                     classlib              [C#], F#, VB      Common/Library
WPF Application                                   wpf                   [C#], VB          Common/WPF
Windows Forms (WinForms) Application              winforms              [C#], VB          Common/WinForms
Worker Service                                    worker                [C#]              Common/Worker/Web
```

### <a name="test-the-project-template"></a>Prueba de la plantilla de proyecto

Ahora que tiene instalada una plantilla de elemento, pruébela.

1. Vaya a la carpeta _test_.

1. Cree una aplicación de consola con el siguiente comando que genera un proyecto de trabajo que puede probar fácilmente con el comando `dotnet run`.

    ```dotnetcli
    dotnet new consoleasync
    ```

    Obtendrá la siguiente salida.

    ```console
    The template "Example templates: async project" was created successfully.
    ```

1. Ejecute el proyecto con el comando siguiente.

    ```dotnetcli
    dotnet run
    ```

    Obtendrá la siguiente salida.

    ```console
    Hello World with C# 8.0!
    ```

¡Enhorabuena! Ha creado e implementado una plantilla de proyecto con .NET Core. Como preparación para la próxima parte de esta serie de tutoriales, debe desinstalar la plantilla que creó. Asegúrese de eliminar también todos los archivos de la carpeta _test_. Esto le permitirá volver a un estado limpio listo para la próxima sección importante de este tutorial.

### <a name="uninstall-the-template"></a>Desinstalación de la plantilla

Como instaló la plantilla a través de una ruta de acceso de archivo, debe desinstalarla con la ruta de acceso de archivo **absoluta**. Ejecute el comando `dotnet new -u` para ver una lista de las plantillas instaladas. Su plantilla debe aparecer en último lugar. Use la ruta de acceso mostrada para desinstalar la plantilla con el comando `dotnet new -u <ABSOLUTE PATH TO TEMPLATE DIRECTORY>`.

```dotnetcli
dotnet new -u
```

Verá un resultado similar al siguiente.

```console
Template Instantiation Commands for .NET Core CLI

Currently installed items:
  Microsoft.DotNet.Common.ItemTemplates
    Templates:
      dotnet gitignore file (gitignore)
      global.json file (globaljson)
      NuGet Config (nugetconfig)
      Solution File (sln)
      Dotnet local tool manifest file (tool-manifest)
      Web Config (webconfig)

... cut to save space ...

  NUnit3.DotNetNew.Template
    Templates:
      NUnit 3 Test Project (nunit) C#
      NUnit 3 Test Item (nunit-test) C#
      NUnit 3 Test Project (nunit) F#
      NUnit 3 Test Item (nunit-test) F#
      NUnit 3 Test Project (nunit) VB
      NUnit 3 Test Item (nunit-test) VB
  C:\working\templates\consoleasync
    Templates:
      Example templates: async project (consoleasync) C#
```

Para desinstalar una plantilla, ejecute el siguiente comando.

```dotnetcli
dotnet new -u C:\working\templates\consoleasync
```

## <a name="next-steps"></a>Pasos siguientes

En este tutorial creó una plantilla de proyecto. Para información sobre cómo empaquetar la plantilla de elemento y la de proyecto en un archivo fácil de usar, continúe con esta serie de tutoriales.

> [!div class="nextstepaction"]
> [Creación de un paquete de plantillas](cli-templates-create-template-pack.md)
