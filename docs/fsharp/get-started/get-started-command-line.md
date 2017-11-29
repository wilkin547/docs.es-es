---
title: "Empezar a trabajar con F # con herramientas de línea de comandos"
description: "Obtenga información acerca de cómo usar F # con la CLI de núcleo de .NET de multiplataforma."
keywords: "visual f#, f#, programación funcional, .NET, .NET Core"
author: cartermp
ms.author: phcart
ms.date: 06/14/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 615db1ec-6ef3-4de2-bae6-4586affa9771
ms.openlocfilehash: a23d4861ce599f20f37ecd0564a0187e7b9b739f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="get-started-with-f-with-the-net-core-cli"></a>Empezar a trabajar con F # con la CLI de núcleo de .NET

Este artículo explican cómo puede empezar a usar F # en .NET Core. Se desplazará por la creación de una solución de varios proyecto con una biblioteca de clases que se llama a una aplicación de consola.

## <a name="prerequisites"></a>Requisitos previos

Para comenzar, primero debe instalar la [.NET Core SDK 1.0 o posterior](https://dot.net/core). No es necesario para desinstalar una versión anterior de .NET Core SDK, ya que admite instalaciones en paralelo.

En este artículo se supone que sabe cómo usar una línea de comandos y tiene un texto de preferencia editor. Si ya no utiliza, [código de Visual Studio](https://code.visualstudio.com) es una buena opción como un editor de texto para F #. Para obtener maravillas características como IntelliSense, mejor resaltado de sintaxis y mucho más, puede descargar el [Ionide extensión](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).

## <a name="building-a-simple-multi-project-solution"></a>Crear una solución Simple de varios proyecto

Abra un símbolo del sistema o terminal y utilice la `dotnet new` comando para crear el nuevo archivo de solución denominado `FSNetCore`:

```
dotnet new sln -o FSNetCore
```

La estructura de directorios de lo siguiente es el resultado de la finalización de comando:

```
FSNetCore
    ├── FSNetCore.sln
```

Cambie los directorios a *FSNetCore* y empezar a agregar proyectos a la carpeta de soluciones.
 
### <a name="writing-a-class-library"></a>Escribir una biblioteca de clases

Use la `dotnet new` de comando, se crea un proyecto de biblioteca de clases en el **src** carpeta con el nombre de biblioteca. 

```bash
dotnet new lib -lang F# -o src/Library 
```

La siguiente estructura de directorios es el resultado de la finalización de comando:

```
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

Reemplace el contenido de `Library.fs` con lo siguiente:

```fsharp
module Library

open Newtonsoft.Json

let getJsonNetJson value = 
    sprintf "I used to be %s but now I'm %s thanks to JSON.NET!" value  (JsonConvert.SerializeObject(value))
```

Agregue el paquete Newtonsoft.Json NuGet al proyecto de biblioteca.

```bash
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

Agregar el `Library` proyecto a la `FSNetCore` solución mediante la `dotnet sln add` comando:

```bash
dotnet sln add src/Library/Library.fsproj
```

Restaurar las dependencias de NuGet, `dotnet restore` ([Véase la nota](#dotnet-restore-note)) y ejecute `dotnet build` para compilar el proyecto.

### <a name="writing-a-console-application-which-consumes-the-class-library"></a>Escribir una aplicación de consola que utiliza la biblioteca de clases

Use la `dotnet new` comando, cree una aplicación de consola en el **src** carpeta con el nombre de aplicación. 

```bash
dotnet new console -lang F# -o src/App 
```

La siguiente estructura de directorios es el resultado de la finalización de comando:

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

Cambio `Program.fs` para:

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

Agregue una referencia a la `Library` proyecto usando `dotnet add reference`.

```bash
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

Agregar el `App` proyecto a la `FSNetCore` solución mediante la `dotnet sln add` comando:

```bash
dotnet sln add src/App/App.fsproj
```

Restaurar las dependencias de NuGet, `dotnet restore` ([Véase la nota](#dotnet-restore-note)) y ejecute `dotnet build` para compilar el proyecto.

Cambie el directorio a la `src/App` proyecto de consola y ejecutar el proyecto pasar `Hello World` como argumentos.

```bash
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