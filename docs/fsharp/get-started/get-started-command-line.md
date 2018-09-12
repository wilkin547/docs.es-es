---
title: 'Introducción a F # con herramientas de línea de comandos'
description: 'Obtenga información sobre cómo compilar una solución sencilla de varios proyecto en F # mediante la CLI de .NET Core en cualquier sistema operativo (Windows, macOs o Linux).'
ms.date: 03/26/2018
ms.openlocfilehash: 8a82970f33c8bbe1b8cdd8fb6499b59b16d3cbf3
ms.sourcegitcommit: ba5c189bf44d44204a3e8838e59ec378a62d82f3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2018
ms.locfileid: "44706875"
---
# <a name="get-started-with-f-with-the-net-core-cli"></a>Introducción a F # con la CLI de .NET Core

Este artículo describe cómo puede empezar a trabajar con F # en cualquier sistema operativo (Windows, macOS o Linux) con la CLI de .NET Core. Pasa por crear una solución de varios proyecto con una biblioteca de clases que se llama a una aplicación de consola.

## <a name="prerequisites"></a>Requisitos previos

Para comenzar, primero debe instalar la versión más reciente [SDK de .NET Core](https://www.microsoft.com/net/download/).

En este artículo se supone que sabe cómo usar una línea de comandos y tiene un texto que prefiera editor. Si ya no usa, [Visual Studio Code](get-started-vscode.md) es una buena opción como un editor de texto para F #.

## <a name="build-a-simple-multi-project-solution"></a>Cree una solución sencilla de varios proyecto

Abra un símbolo del sistema o terminal y use la [dotnet nuevo](../../core/tools/dotnet-new.md) comando para crear el nuevo archivo de solución denominado `FSNetCore`:

```console
dotnet new sln -o FSNetCore
```

La siguiente estructura de directorios se produce después de ejecutar el comando anterior:

```console
FSNetCore
    ├── FSNetCore.sln
```

### <a name="write-a-class-library"></a>Escribir una biblioteca de clases

Cambie los directorios a *FSNetCore*.

Use la `dotnet new` de comandos, cree un proyecto de biblioteca de clases en el **src** carpeta con el nombre de biblioteca.

```console
dotnet new classlib -lang F# -o src/Library
```

La siguiente estructura de directorios se produce después de ejecutar el comando anterior:

```console
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

```console
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

Agregar el `Library` proyecto a la `FSNetCore` solución mediante la [agregar dotnet sln](../../core/tools/dotnet-sln.md) comando:

```console
dotnet sln add src/Library/Library.fsproj
```

Ejecute `dotnet build` para compilar el proyecto. Dependencias no resueltas se restaurará cuando se crea.

### <a name="write-a-console-application-that-consumes-the-class-library"></a>Escribir una aplicación de consola que utiliza la biblioteca de clases

Use la `dotnet new` de comandos, cree una aplicación de consola en el **src** carpeta con el nombre de aplicación.

```console
dotnet new console -lang F# -o src/App
```

La siguiente estructura de directorios se produce después de ejecutar el comando anterior:

```console
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

```console
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

Agregar el `App` proyecto a la `FSNetCore` solución mediante el `dotnet sln add` comando:

```console
dotnet sln add src/App/App.fsproj
```

Restaurar las dependencias de NuGet, `dotnet restore` ([vea la nota](#dotnet-restore-note)) y ejecute `dotnet build` para compilar el proyecto.

Cambie el directorio a la `src/App` proyecto de consola y ejecutar el proyecto pasando `Hello World` como argumentos:

```console
cd src/App
dotnet run Hello World
```

Debería ver los resultados siguientes:

```console
Nice command-line arguments! Here's what JSON.NET has to say about them:

I used to be Hello but now I'm ""Hello"" thanks to JSON.NET!
I used to be World but now I'm ""World"" thanks to JSON.NET!
```

## <a name="next-steps"></a>Pasos siguientes

A continuación, consulte el [paseo por F #](../tour.md) para obtener más información sobre las diferentes características de F #.
