---
title: 'Comando dotnet-new: CLI de .NET Core | Microsoft Docs'
description: El comando dotnet-new crea nuevos proyectos de .NET Core en el directorio actual.
keywords: dotnet-new, CLI, comando de CLI, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: fcc3ed2e-9265-4d50-b59e-dc2e5c190b34
ms.translationtype: Human Translation
ms.sourcegitcommit: 68fbe2e9895825bbbb41cfe025bfdf1d4f9d3d04
ms.openlocfilehash: 14279ea6fdf4af52c0492f2dad1171d8150ac95b
ms.contentlocale: es-es
ms.lasthandoff: 05/05/2017

---

# <a name="dotnet-new"></a>dotnet-new

## <a name="name"></a>Name

`dotnet-new`: crea un nuevo proyecto, archivo de configuración o solución según la plantilla especificada.

## <a name="synopsis"></a>Sinopsis

```
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```

## <a name="description"></a>Descripción

El comando `dotnet new` proporciona una manera cómoda de inicializar un proyecto .NET Core válido. 

El comando llama al [motor de plantillas](https://github.com/dotnet/templating) para crear los artefactos en el disco basándose en las opciones y la plantilla especificadas.

## <a name="arguments"></a>Argumentos

`TEMPLATE`

La plantilla de la que se va a crear una instancia cuando se invoca el comando. Cada plantilla puede tener opciones específicas que puede pasar. Para obtener más información, vea [Opciones de plantilla](#template-options).

El comando contiene una lista predeterminada de plantillas. Use `dotnet new -all` para obtener una lista de las plantillas disponibles. En la siguiente tabla se muestran las plantillas que vienen preinstaladas con el SDK. El lenguaje predeterminado de la plantilla se muestra entre corchetes.

|Descripción de plantilla  | Nombre de plantilla  | Lenguajes |
|----------------------|----------------|-----------|
| Aplicación de consola  | consola        | [C#], F#  |
| Biblioteca de clases        | classlib       | [C#], F#  |
| Proyecto de prueba unitaria    | mstest         | [C#], F#  |
| Proyecto de prueba xUnit   | xunit          | [C#], F#  |
| Vacío de ASP.NET Core   | web            | [C#]      |
| Aplicación web de ASP.NET Core | mvc            | [C#], F#  |
| API web de ASP.NET Core | webapi         | [C#]      |
| Configuración de NuGet         | nugetconfig    |           |
| Configuración de la Web           | webconfig      |           |
| Archivo de solución        | sln            |           |

## <a name="options"></a>Opciones

`-h|--help`

Imprime la ayuda para el comando. Puede invocarse para el propio comando `dotnet new` o para cualquier plantilla, como `dotnet new mvc --help`.

`-l|--list`

Muestra las plantillas que contienen el nombre especificado. Si se invoca para el comando `dotnet new`, muestra las plantillas posibles disponibles para un directorio determinado. Por ejemplo, si el directorio ya contiene un proyecto, no mostrará todas las plantillas del proyecto.

`-lang|--language {C#|F#}`

El lenguaje de la plantilla que se va a crear. El lenguaje aceptado cambia según la plantilla (vea los valores predeterminados en la sección [argumentos](#arguments)). No es válido para algunas plantillas.

`-n|--name <OUTPUT_NAME>`

El nombre de la salida creada. Si no se especifica ningún nombre, se usa el nombre del directorio actual.

`-o|--output <OUTPUT_DIRECTORY>`

La ubicación para colocar la salida generada. El valor predeterminado es el directorio actual.

`-all|--show-all`

Muestra todas las plantillas de un tipo de proyecto específico cuando se ejecuta en el contexto del comando `dotnet new` por sí solo. Cuando se ejecuta en el contexto de una plantilla específica, como `dotnet new web -all`, `-all` se interpreta como una marca para forzar la creación. Esto es necesario cuando el directorio de salida ya contiene un proyecto.

## <a name="template-options"></a>Opciones de plantilla

Cada plantilla de proyecto puede tener opciones adicionales disponibles. Las plantillas principales tienen las siguientes opciones:

**console, xunit, mstest, web, webapi**

`-f|--framework`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino. Valores: `netcoreapp1.0` o `netcoreapp1.1` (valor predeterminado: `netcoreapp1.0`)

**mvc**

`-f|--framework`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino. Valores: `netcoreapp1.0` o `netcoreapp1.1` (`Default: netcoreapp1.0`)

`-au|--auth`: el tipo de autenticación que se va a usar. Valores: `None` o `Individual` (valor predeterminado: `None`)

`-uld|--use-local-db`: especifica si se va a usar o no LocalDB en lugar de SQLite. Valores: `true` o `false` (valor predeterminado: `false`)

**classlib**

`-f|--framework`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino. Valores: `netcoreapp1.0`, `netcoreapp1.1` o `netstandard1.0` para `netstandard1.6` (predeterminado: `netstandard1.4`)

## <a name="examples"></a>Ejemplos

Creación de un proyecto de aplicación de consola con F# en el directorio actual:

`dotnet new console -lang f#` 
   
Cree un nuevo proyecto de aplicación MVC de ASP.NET Core C# en el directorio actual sin autenticación destinado a .NET Core 1.0:  

`dotnet new mvc -au None -f netcoreapp1.0`
 
Cree una nueva aplicación de XUnit que tenga como destino .NET Core 1.1:

`dotnet new xunit --Framework netcoreapp1.1`

Enumere todas las plantillas disponibles para MVC:

`dotnet new mvc -l`

