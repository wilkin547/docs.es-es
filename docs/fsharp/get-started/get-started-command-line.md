---
title: 'Introducción a F # con las herramientas de línea de comandos'
description: 'Obtenga información sobre cómo crear una solución sencilla de varios proyectos en F # mediante el CLI de .NET Core en cualquier sistema operativo (Windows, macOS o Linux).'
ms.date: 08/15/2020
ms.openlocfilehash: e652b66337a3122de8e6bd4d62d86fb6082b759d
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/25/2020
ms.locfileid: "88811995"
---
# <a name="get-started-with-f-with-the-net-core-cli"></a>Introducción a F # con el CLI de .NET Core

En este artículo se explica cómo puede empezar a trabajar con F # en cualquier sistema operativo (Windows, macOS o Linux) con el CLI de .NET Core. Pasa por la creación de una solución de varios proyectos con una biblioteca de clases a la que llama una aplicación de consola.

## <a name="prerequisites"></a>Requisitos previos

Para empezar, debe instalar la [SDK de .net Core](https://dotnet.microsoft.com/download)más reciente.

En este artículo se supone que sabe cómo usar una línea de comandos y tener un editor de texto preferido. Si aún no lo usa, [Visual Studio Code](get-started-vscode.md) es una opción excelente como editor de texto de F #.

## <a name="build-a-simple-multi-project-solution"></a>Compilar una solución sencilla de varios proyectos

Abra un símbolo del sistema o terminal y use el comando [dotnet New](../../core/tools/dotnet-new.md) para crear un nuevo archivo de solución denominado `FSNetCore` :

```dotnetcli
dotnet new sln -o FSNetCore
```

Después de ejecutar el comando anterior, se genera la siguiente estructura de directorios:

```console
FSNetCore
    ├── FSNetCore.sln
```

### <a name="write-a-class-library"></a>Escribir una biblioteca de clases

Cambie los directorios a *FSNetCore*.

Use el `dotnet new` comando, cree un proyecto de biblioteca de clases en la carpeta **src** denominada Library.

```dotnetcli
dotnet new classlib -lang "F#" -o src/Library
```

Después de ejecutar el comando anterior, se genera la siguiente estructura de directorios:

```console
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

Reemplace el contenido de `Library.fs` por el código siguiente:

```fsharp
module Library

open Newtonsoft.Json

let getJsonNetJson value =
    let json = JsonConvert.SerializeObject(value)
    sprintf "I used to be %s but now I'm %s thanks to JSON.NET!" value json
```

Agregue el Newtonsoft.Jsen el paquete NuGet al proyecto de biblioteca.

```dotnetcli
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

Agregue el `Library` proyecto a la `FSNetCore` solución mediante el comando [dotnet sln Add](../../core/tools/dotnet-sln.md) :

```dotnetcli
dotnet sln add src/Library/Library.fsproj
```

Ejecute `dotnet build` para compilar el proyecto. Las dependencias no resueltas se restaurarán al compilar.

### <a name="write-a-console-application-that-consumes-the-class-library"></a>Escribir una aplicación de consola que consuma la biblioteca de clases

Use el `dotnet new` comando para crear una aplicación de consola en la carpeta **src** denominada app.

```dotnetcli
dotnet new console -lang "F#" -o src/App
```

Después de ejecutar el comando anterior, se genera la siguiente estructura de directorios:

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

Reemplace el contenido del archivo `Program.fs` por el código siguiente:

```fsharp
open System
open Library

[<EntryPoint>]
let main argv =
    printfn "Nice command-line arguments! Here's what JSON.NET has to say about them:"

    for arg in argv do
        let value = getJsonNetJson arg
        printfn "%s" value

    0 // return an integer exit code
```

Agregue una referencia al `Library` proyecto mediante [dotnet Add Reference](../../core/tools/dotnet-add-reference.md).

```dotnetcli
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

Agregue el `App` proyecto a la `FSNetCore` solución mediante el `dotnet sln add` comando:

```dotnetcli
dotnet sln add src/App/App.fsproj
```

Restaure las dependencias de NuGet `dotnet restore` y ejecute `dotnet build` para compilar el proyecto.

Cambie el directorio al `src/App` proyecto de consola y ejecute el proyecto pasando `Hello World` como argumentos:

```dotnetcli
cd src/App
dotnet run Hello World
```

Debería ver los siguientes resultados:

```console
Nice command-line arguments! Here's what JSON.NET has to say about them:

I used to be Hello but now I'm ""Hello"" thanks to JSON.NET!
I used to be World but now I'm ""World"" thanks to JSON.NET!
```

## <a name="next-steps"></a>Pasos siguientes

A continuación, consulte el [paseo por f #](../tour.md) para obtener más información sobre las diferentes características de f #.
