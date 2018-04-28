---
title: 'Empezar a trabajar con F # con herramientas de línea de comandos'
description: 'Obtenga información acerca de cómo crear una solución sencilla de varios proyecto en F # mediante la CLI de núcleo de .NET en cualquier sistema operativo (Windows, Mac OS o Linux).'
author: cartermp
ms.author: phcart
ms.date: 03/26/2018
ms.topic: conceptual
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 767385be605d863644db563a2e86a41ca80527c4
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="get-started-with-f-with-the-net-core-cli"></a><span data-ttu-id="ce81b-103">Empezar a trabajar con F # con la CLI de núcleo de .NET</span><span class="sxs-lookup"><span data-stu-id="ce81b-103">Get started with F# with the .NET Core CLI</span></span>

<span data-ttu-id="ce81b-104">Este artículo explican cómo puede empezar a trabajar con F # en cualquier sistema operativo (Windows, Mac OS o Linux) con la CLI de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ce81b-104">This article covers how you can get started with F# on any operating system (Windows, macOS, or Linux) with the .NET Core CLI.</span></span> <span data-ttu-id="ce81b-105">Lleva a cabo la creación de una solución de varios proyecto con una biblioteca de clases que se llama a una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="ce81b-105">It goes through building a multi-project solution with a class library that is called by a console application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ce81b-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="ce81b-106">Prerequisites</span></span>

<span data-ttu-id="ce81b-107">Para comenzar, primero debe instalar la [.NET Core SDK 1.0 o posterior](https://www.microsoft.com/net/download/).</span><span class="sxs-lookup"><span data-stu-id="ce81b-107">To begin, you must install the [.NET Core SDK 1.0 or later](https://www.microsoft.com/net/download/).</span></span> <span data-ttu-id="ce81b-108">No es necesario para desinstalar una versión anterior de .NET Core SDK, ya que admite instalaciones en paralelo.</span><span class="sxs-lookup"><span data-stu-id="ce81b-108">There is no need to uninstall a previous version of the .NET Core SDK, as it supports side-by-side installations.</span></span>

<span data-ttu-id="ce81b-109">En este artículo se supone que sabe cómo usar una línea de comandos y tiene un texto de preferencia editor.</span><span class="sxs-lookup"><span data-stu-id="ce81b-109">This article assumes that you know how to use a command line and have a preferred text editor.</span></span> <span data-ttu-id="ce81b-110">Si ya no utiliza, [código de Visual Studio](https://code.visualstudio.com) es una buena opción como un editor de texto para F #.</span><span class="sxs-lookup"><span data-stu-id="ce81b-110">If you don't already use it, [Visual Studio Code](https://code.visualstudio.com) is a great option as a text editor for F#.</span></span> <span data-ttu-id="ce81b-111">Para obtener maravillas características como IntelliSense, mejor resaltado de sintaxis y mucho más, puede descargar el [Ionide extensión](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span><span class="sxs-lookup"><span data-stu-id="ce81b-111">To get awesome features like IntelliSense, better syntax highlighting, and more, you can download the [Ionide Extension](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span></span>

## <a name="build-a-simple-multi-project-solution"></a><span data-ttu-id="ce81b-112">Crear una solución sencilla de varios proyecto</span><span class="sxs-lookup"><span data-stu-id="ce81b-112">Build a simple multi-project solution</span></span>

<span data-ttu-id="ce81b-113">Abra un símbolo del sistema o terminal y utilice la [dotnet nueva](../../core/tools/dotnet-new.md) comando para crear el nuevo archivo de solución denominado `FSNetCore`:</span><span class="sxs-lookup"><span data-stu-id="ce81b-113">Open a command prompt/terminal and use the [dotnet new](../../core/tools/dotnet-new.md) command to create new solution file called `FSNetCore`:</span></span>

```
dotnet new sln -o FSNetCore
```

<span data-ttu-id="ce81b-114">La siguiente estructura de directorios se produce después de ejecutar el comando anterior:</span><span class="sxs-lookup"><span data-stu-id="ce81b-114">The following directory structure is produced after running the previous command:</span></span>

```
FSNetCore
    ├── FSNetCore.sln
```

### <a name="write-a-class-library"></a><span data-ttu-id="ce81b-115">Escribir una biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="ce81b-115">Write a class library</span></span>

<span data-ttu-id="ce81b-116">Cambie los directorios a *FSNetCore*.</span><span class="sxs-lookup"><span data-stu-id="ce81b-116">Change directories to *FSNetCore*.</span></span>

<span data-ttu-id="ce81b-117">Use la `dotnet new` comando, cree un proyecto de biblioteca de clases en el **src** carpeta con el nombre de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="ce81b-117">Use the `dotnet new` command, create a class library project in the **src** folder named Library.</span></span>

```
dotnet new lib -lang F# -o src/Library
```

<span data-ttu-id="ce81b-118">La siguiente estructura de directorios se produce después de ejecutar el comando anterior:</span><span class="sxs-lookup"><span data-stu-id="ce81b-118">The following directory structure is produced after running the previous command:</span></span>

```
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

<span data-ttu-id="ce81b-119">Reemplace el contenido de `Library.fs` con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="ce81b-119">Replace the contents of `Library.fs` with the following code:</span></span>

```fsharp
module Library

open Newtonsoft.Json

let getJsonNetJson value =
    sprintf "I used to be %s but now I'm %s thanks to JSON.NET!" value (JsonConvert.SerializeObject(value))
```

<span data-ttu-id="ce81b-120">Agregue el paquete Newtonsoft.Json NuGet al proyecto de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="ce81b-120">Add the Newtonsoft.Json NuGet package to the Library project.</span></span>

```
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

<span data-ttu-id="ce81b-121">Agregar el `Library` proyecto a la `FSNetCore` solución mediante la [dotnet sln agregar](../../core/tools/dotnet-sln.md) comando:</span><span class="sxs-lookup"><span data-stu-id="ce81b-121">Add the `Library` project to the `FSNetCore` solution using the [dotnet sln add](../../core/tools/dotnet-sln.md) command:</span></span>

```
dotnet sln add src/Library/Library.fsproj
```

<span data-ttu-id="ce81b-122">Restaurar las dependencias de NuGet utilizando el `dotnet restore` comando ([Véase la nota](#dotnet-restore-note)) y ejecute `dotnet build` para compilar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="ce81b-122">Restore the NuGet dependencies using the `dotnet restore` command ([see note](#dotnet-restore-note)) and run `dotnet build` to build the project.</span></span>

### <a name="write-a-console-application-that-consumes-the-class-library"></a><span data-ttu-id="ce81b-123">Escribir una aplicación de consola que utiliza la biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="ce81b-123">Write a console application that consumes the class library</span></span>

<span data-ttu-id="ce81b-124">Use la `dotnet new` comando, cree una aplicación de consola en el **src** carpeta con el nombre de aplicación.</span><span class="sxs-lookup"><span data-stu-id="ce81b-124">Use the `dotnet new` command, create a console application in the **src** folder named App.</span></span>

```
dotnet new console -lang F# -o src/App
```

<span data-ttu-id="ce81b-125">La siguiente estructura de directorios se produce después de ejecutar el comando anterior:</span><span class="sxs-lookup"><span data-stu-id="ce81b-125">The following directory structure is produced after running the previous command:</span></span>

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

<span data-ttu-id="ce81b-126">Reemplace el contenido de la `Program.fs` archivo con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="ce81b-126">Replace the contents of the `Program.fs` file with the following code:</span></span>

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

<span data-ttu-id="ce81b-127">Agregue una referencia a la `Library` proyecto usando [dotnet Agregar referencia](../../core/tools/dotnet-add-reference.md).</span><span class="sxs-lookup"><span data-stu-id="ce81b-127">Add a reference to the `Library` project using [dotnet add reference](../../core/tools/dotnet-add-reference.md).</span></span>

```
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

<span data-ttu-id="ce81b-128">Agregar el `App` proyecto a la `FSNetCore` solución mediante la `dotnet sln add` comando:</span><span class="sxs-lookup"><span data-stu-id="ce81b-128">Add the `App` project to the `FSNetCore` solution using the `dotnet sln add` command:</span></span>

```
dotnet sln add src/App/App.fsproj
```

<span data-ttu-id="ce81b-129">Restaurar las dependencias de NuGet, `dotnet restore` ([Véase la nota](#dotnet-restore-note)) y ejecute `dotnet build` para compilar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="ce81b-129">Restore the NuGet dependencies, `dotnet restore` ([see note](#dotnet-restore-note)) and run `dotnet build` to build the project.</span></span>

<span data-ttu-id="ce81b-130">Cambie el directorio a la `src/App` proyecto de consola y ejecutar el proyecto pasar `Hello World` como argumentos:</span><span class="sxs-lookup"><span data-stu-id="ce81b-130">Change directory to the `src/App` console project and run the project passing `Hello World` as arguments:</span></span>

```
cd src/App
dotnet run Hello World
```

<span data-ttu-id="ce81b-131">Debería ver los siguientes resultados:</span><span class="sxs-lookup"><span data-stu-id="ce81b-131">You should see the following results:</span></span>

```
Nice command-line arguments! Here's what JSON.NET has to say about them:

I used to be Hello but now I'm ""Hello"" thanks to JSON.NET!
I used to be World but now I'm ""World"" thanks to JSON.NET!
```

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]