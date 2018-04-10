---
title: 'Empezar a trabajar con F # con herramientas de línea de comandos'
description: 'Obtenga información acerca de cómo crear una solución sencilla de varios proyecto en F # mediante la CLI de núcleo de .NET en cualquier sistema operativo (Windows, Mac OS o Linux).'
author: cartermp
ms.author: phcart
ms.date: 03/26/2018
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.openlocfilehash: e48e1291bbe91da0d9ca2adbb08662bd106c8fb4
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2018
---
# <a name="get-started-with-f-with-the-net-core-cli"></a>Empezar a trabajar con F # con la CLI de núcleo de .NET

Este artículo explican cómo puede empezar a trabajar con F # en cualquier sistema operativo (Windows, Mac OS o Linux) con la CLI de .NET Core. Lleva a cabo la creación de una solución de varios proyecto con una biblioteca de clases que se llama a una aplicación de consola.

## <a name="prerequisites"></a>Requisitos previos

Para comenzar, primero debe instalar la [.NET Core SDK 1.0 o posterior](https://www.microsoft.com/net/download/). No es necesario para desinstalar una versión anterior de .NET Core SDK, ya que admite instalaciones en paralelo.

En este artículo se supone que sabe cómo usar una línea de comandos y tiene un texto de preferencia editor. Si ya no utiliza, [código de Visual Studio](https://code.visualstudio.com) es una buena opción como un editor de texto para F #. Para obtener maravillas características como IntelliSense, mejor resaltado de sintaxis y mucho más, puede descargar el [Ionide extensión](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).

## <a name="build-a-simple-multi-project-solution"></a>Crear una solución sencilla de varios proyecto

Abra un símbolo del sistema o terminal y utilice la [dotnet nueva](../../core/tools/dotnet-new.md) comando para crear el nuevo archivo de solución denominado `FSNetCore`:

```
dotnet new sln -o FSNetCore
```

La siguiente estructura de directorios se produce después de ejecutar el comando anterior:

```
FSNetCore
    ├── FSNetCore.sln
```

### <a name="write-a-class-library"></a>Escribir una biblioteca de clases

Cambie los directorios a *FSNetCore*.

Use la `dotnet new` comando, cree un proyecto de biblioteca de clases en el **src** carpeta con el nombre de biblioteca.

```
dotnet new lib -lang F# -o src/Library
```

La siguiente estructura de directorios se produce después de ejecutar el comando anterior:

```
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

Reemplace el contenido de `Library.fs` con el código siguiente:

```fsharp
module Library

open Newtonsoft.Json

let getJsonNetJson value =
    sprintf "I used to be %s but now I'm %s thanks to JSON.NET!" value (JsonConvert.SerializeObject(value))
```

Agregue el paquete Newtonsoft.Json NuGet al proyecto de biblioteca.

```
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

Agregar el `Library` proyecto a la `FSNetCore` solución mediante la [dotnet sln agregar](../../core/tools/dotnet-sln.md) comando:

```
dotnet sln add src/Library/Library.fsproj
```

Restaurar las dependencias de NuGet utilizando el `dotnet restore` comando ([Véase la nota](#dotnet-restore-note)) y ejecute `dotnet build` para compilar el proyecto.

### <a name="write-a-console-application-that-consumes-the-class-library"></a>Escribir una aplicación de consola que utiliza la biblioteca de clases

Use la `dotnet new` comando, cree una aplicación de consola en el **src** carpeta con el nombre de aplicación.

```
dotnet new console -lang F# -o src/App
```

La siguiente estructura de directorios se produce después de ejecutar el comando anterior:

```
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        ├── App
        │   ├── App.fsproj
        │   ├── Program.fs
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

Reemplace el contenido de la `Program.fs` archivo con el código siguiente:

```fsharp
open System
open Library

[<EntryPoint>]
let main argv =
    printfn "Nice command-line arguments! Here's what JSON.NET has to say about them:"

    argv
    |> Array.map getJsonNetJson
    |> Array.iter (printfn "%s")

    0 // return an integer exit code
```

Agregue una referencia a la `Library` proyecto usando [dotnet Agregar referencia](../../core/tools/dotnet-add-reference.md).

```
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

Agregar el `App` proyecto a la `FSNetCore` solución mediante la `dotnet sln add` comando:

```
dotnet sln add src/App/App.fsproj
```

Restaurar las dependencias de NuGet, `dotnet restore` ([Véase la nota](#dotnet-restore-note)) y ejecute `dotnet build` para compilar el proyecto.

Cambie el directorio a la `src/App` proyecto de consola y ejecutar el proyecto pasar `Hello World` como argumentos:

```
cd src/App
dotnet run Hello World
```

Debería ver los siguientes resultados:

```
Nice command-line arguments! Here's what JSON.NET has to say about them:

I used to be Hello but now I'm ""Hello"" thanks to JSON.NET!
I used to be World but now I'm ""World"" thanks to JSON.NET!
```

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]