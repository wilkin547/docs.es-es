---
title: 'Creación de una plantilla de elemento para dotnet new: CLI de .NET Core'
description: Obtenga información sobre cómo crear una plantilla de elemento para el comando dotnet new. Las plantillas de elemento pueden contener cualquier número de archivos.
author: adegeo
ms.date: 06/25/2019
ms.topic: tutorial
ms.author: adegeo
ms.openlocfilehash: 0b804d26b2f33d4d600c17de2f7f71101a0f9c98
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324375"
---
# <a name="tutorial-create-an-item-template"></a>Tutorial: Creación de una plantilla de elemento

Con .NET Core, puede crear e implementar plantillas que generan proyectos, archivos e inclusos recursos. Este tutorial es el primero de una serie que enseña a crear, instalar y desinstalar plantillas para usarlas con el comando `dotnet new`.

En esta parte de la serie, aprenderá a:

> [!div class="checklist"]
>
> * Crear una clase para una plantilla de elemento.
> * Crear el archivo y la carpeta de configuración de la plantilla.
> * Instalar una plantilla desde una ruta de acceso de archivo.
> * Probar una plantilla de elemento.
> * Desinstalar una plantilla de elemento.

## <a name="prerequisites"></a>Requisitos previos

* [SDK de .NET Core 2.2](https://dotnet.microsoft.com/download) o versiones posteriores.
* Leer el artículo de referencia [Plantillas personalizadas para dotnet new](../tools/custom-templates.md).

  En el artículo de referencia se explican los aspectos básicos de las plantillas y cómo se unen. Parte de esta información se repetirá en este tutorial.

* Abra un terminal y vaya a la carpeta _working\templates_.

## <a name="create-the-required-folders"></a>Creación de las carpetas necesarias

Esta serie usa una "carpeta de trabajo", donde se encuentra el origen de la plantilla, y una "carpeta de prueba" que se usa para probar las plantillas. La carpeta de trabajo y la carpeta de prueba deben estar en la misma carpeta.

En primer lugar, cree la carpeta principal, no importa con qué nombre. Luego, cree una subcarpeta denominada _working_ (trabajo). Dentro de la carpeta _working_, cree una subcarpeta con el nombre _templates_ (plantillas).

A continuación, cree una carpeta dentro de la carpeta principal con el nombre _test_ (prueba). La estructura de carpetas debe tener el siguiente aspecto.

```console
parent_folder
├───test
└───working
    └───templates
```

## <a name="create-an-item-template"></a>Creación de una plantilla de elemento

Una plantilla de elemento es un tipo de plantilla específico que contiene uno o varios archivos. Estos tipos de plantillas son útiles cuando se quiere generar algún contenido como un archivo de solución, código o configuración. En este ejemplo, creará una clase que agrega un método de extensión al tipo de cadena.

En el terminal, vaya a la carpeta _working\templates_ y cree una subcarpeta llamada _extensions_. Entre a la carpeta.

```console
working
└───templates
    └───extensions
```

Cree un archivo nuevo denominado _CommonExtensions.cs_ y ábralo con el editor de texto que prefiera. Esta clase proporcionará un método de extensión denominado `Reverse` que invierte el contenido de una cadena. Pegue el código siguiente y guarde el archivo:

```csharp
using System;

namespace System
{
    public static class StringExtensions
    {
        public static string Reverse(this string value)
        {
            var tempArray = value.ToCharArray();
            Array.Reverse(tempArray);
            return new string(tempArray);
        }
    }
}
```

Ahora que creó el contenido de la plantilla, debe crear su configuración en la carpeta raíz de la plantilla.

## <a name="create-the-template-config"></a>Creación de la configuración de una plantilla

En .NET Core, las plantillas se reconocen con una carpeta especial y un archivo de configuración que existen en la raíz de la plantilla. En este tutorial, la carpeta de la plantilla se encuentra en _working\templates\extensions_.

Cuando se crea una plantilla, todos los archivos y las carpetas de la carpeta de la plantilla se incluyen como parte de la plantilla, a excepción de la carpeta de configuración especial. Esta carpeta de configuración se denomina _.template.config_.

En primer lugar, cree una subcarpeta con el nombre _.template.config_ y entre en ella. Luego, cree un archivo denominado _template.json_. La estructura de la carpeta debe verse así:

```console
working
└───templates
    └───extensions
        └───.template.config
                template.json
```

Abra _template.json_ con el editor de texto que prefiera, pegue el código JSON siguiente y guárdelo.

```json
{
  "$schema": "http://json.schemastore.org/template",
  "author": "Me",
  "classifications": [ "Common", "Code" ],
  "identity": "ExampleTemplate.StringExtensions",
  "name": "Example templates: string extensions",
  "shortName": "stringext",
  "tags": {
    "language": "C#",
    "type": "item"
  }
}
```

Este archivo de configuración contiene todos los valores de la plantilla. Puede ver los valores básicos, como `name` y `shortName`, pero también hay un valor `tags/type` que está establecido en `item`. De este modo, la plantilla se clasifica como una plantilla de elemento. No hay ninguna restricción en el tipo de plantilla que crea. Los valores `item` y `project` son nombres comunes que .NET Core recomienda para que los usuarios puedan filtrar fácilmente el tipo de plantilla que buscan.

El elemento `classifications` representa la columna **tags** que ve cuando ejecuta `dotnet new` y obtiene una lista de plantillas. Los usuarios también pueden hacer una búsqueda según las etiquetas de clasificación. No confunda la propiedad `tags` del archivo \*.json con la lista de etiquetas `classifications`. Lamentablemente, son dos elementos que tienen nombres similares. El esquema completo del archivo *template.json* puede encontrarse en el [Almacenamiento del esquema JSON](http://json.schemastore.org/template). Para más información sobre el archivo *template.json*, consulte la [wiki de plantillas dotnet](https://github.com/dotnet/templating/wiki).

Ahora que tiene un archivo _.template.config/template.json_ válido, la plantilla está lista para instalarla. En el terminal, vaya a la carpeta _extensions_ y ejecute el comando siguiente para instalar la plantilla ubicada en la carpeta actual:

* **En Windows**: `dotnet new -i .\`
* **En Linux o macOS**: `dotnet new -i ./`

Este comando genera la lista de las plantillas instaladas, que debería incluir la suya.

```console
C:\working\templates\extensions> dotnet new -i .\
Usage: new [options]

Options:
  -h, --help          Displays help for this command.
  -l, --list          Lists templates containing the specified name. If no name is specified, lists all templates.

... cut to save space ...

Templates                                         Short Name            Language          Tags
-------------------------------------------------------------------------------------------------------------------------------
Example templates: string extensions              stringext             [C#]              Common/Code
Console Application                               console               [C#], F#, VB      Common/Console
Class library                                     classlib              [C#], F#, VB      Common/Library
WPF Application                                   wpf                   [C#], VB          Common/WPF
Windows Forms (WinForms) Application              winforms              [C#], VB          Common/WinForms
Worker Service                                    worker                [C#]              Common/Worker/Web
```

## <a name="test-the-item-template"></a>Prueba de la plantilla de elemento

Ahora que tiene instalada una plantilla de elemento, pruébela. Vaya a la carpeta _test/_ y cree una aplicación de consola con `dotnet new console`. Esto genera un proyecto de trabajo que puede probar fácilmente con el comando `dotnet run`.

```dotnetcli
dotnet new console
```

Verá un resultado similar al siguiente.

```console
The template "Console Application" was created successfully.

Processing post-creation actions...
Running 'dotnet restore' on C:\test\test.csproj...
  Restore completed in 54.82 ms for C:\test\test.csproj.

Restore succeeded.
```

Ejecute el proyecto.

```dotnetcli
dotnet run
```

Obtendrá la siguiente salida.

```console
Hello World!
```

Luego, ejecute `dotnet new stringext` para generar _CommonExtensions.cs_ desde la plantilla.

```dotnetcli
dotnet new stringext
```

Obtendrá la siguiente salida.

```console
The template "Example templates: string extensions" was created successfully.
```

Cambie el código en _Program.cs_ para invertir la cadena `"Hello World"` con el método de extensión que se proporciona en la plantilla.

```csharp
Console.WriteLine("Hello World!".Reverse());
```

Vuelva a ejecutar el programa y verá que el resultado se invirtió.

```dotnetcli
dotnet run
```

Obtendrá la siguiente salida.

```console
!dlroW olleH
```

¡Enhorabuena! Ha creado e implementado una plantilla de elemento con .NET Core. Como preparación para la próxima parte de esta serie de tutoriales, debe desinstalar la plantilla que creó. Asegúrese de eliminar también todos los archivos de la carpeta _test_. Esto le permitirá volver a un estado limpio listo para la próxima sección importante de este tutorial.

## <a name="uninstall-the-template"></a>Desinstalación de la plantilla

Como instaló la plantilla a través de la ruta de acceso de archivo, debe desinstalarla con la ruta de acceso de archivo **absoluta**. Ejecute el comando `dotnet new -u` para ver una lista de las plantillas instaladas. Su plantilla debe aparecer en último lugar. Use la ruta de acceso mostrada para desinstalar la plantilla con el comando `dotnet new -u <ABSOLUTE PATH TO TEMPLATE DIRECTORY>`.

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
  C:\working\templates\extensions
    Templates:
      Example templates: string extensions (stringext) C#
```

Para desinstalar una plantilla, ejecute el siguiente comando.

```dotnetcli
dotnet new -u C:\working\templates\extensions
```

## <a name="next-steps"></a>Pasos siguientes

En este tutorial, creó una plantilla de elemento. Para aprender a crear una plantilla de proyecto, siga con esta serie de tutoriales.

> [!div class="nextstepaction"]
> [Creación de una plantilla de proyecto](cli-templates-create-project-template.md)
