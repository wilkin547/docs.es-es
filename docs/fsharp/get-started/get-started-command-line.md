---
title: Introducción a F# con herramientas de línea de comandos
description: Aprenda a crear una sencilla solución de varios proyectos F# mediante la CLI de .NET Core en cualquier sistema operativo (Windows, macOs o Linux).
ms.date: 03/26/2018
ms.openlocfilehash: bc9b223fcf133ffe8b19d5284dcbd3c14a426235
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54152104"
---
# <a name="get-started-with-f-with-the-net-core-cli"></a><span data-ttu-id="89376-103">Introducción a F# con la CLI de .NET Core</span><span class="sxs-lookup"><span data-stu-id="89376-103">Get started with F# with the .NET Core CLI</span></span>

<span data-ttu-id="89376-104">Este artículo describe cómo puede comenzar con F# en cualquier sistema operativo (Windows, macOS o Linux) con la CLI de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="89376-104">This article covers how you can get started with F# on any operating system (Windows, macOS, or Linux) with the .NET Core CLI.</span></span> <span data-ttu-id="89376-105">Pasa por crear una solución de varios proyecto con una biblioteca de clases que se llama a una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="89376-105">It goes through building a multi-project solution with a class library that is called by a console application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="89376-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="89376-106">Prerequisites</span></span>

<span data-ttu-id="89376-107">Para comenzar, primero debe instalar la versión más reciente [SDK de .NET Core](https://www.microsoft.com/net/download/).</span><span class="sxs-lookup"><span data-stu-id="89376-107">To begin, you must install the latest [.NET Core SDK](https://www.microsoft.com/net/download/).</span></span>

<span data-ttu-id="89376-108">En este artículo se supone que sabe cómo usar una línea de comandos y tiene un texto que prefiera editor.</span><span class="sxs-lookup"><span data-stu-id="89376-108">This article assumes that you know how to use a command line and have a preferred text editor.</span></span> <span data-ttu-id="89376-109">Si ya no usa, [Visual Studio Code](get-started-vscode.md) es una buena opción como un editor de texto para F#.</span><span class="sxs-lookup"><span data-stu-id="89376-109">If you don't already use it, [Visual Studio Code](get-started-vscode.md) is a great option as a text editor for F#.</span></span>

## <a name="build-a-simple-multi-project-solution"></a><span data-ttu-id="89376-110">Cree una solución sencilla de varios proyecto</span><span class="sxs-lookup"><span data-stu-id="89376-110">Build a simple multi-project solution</span></span>

<span data-ttu-id="89376-111">Abra un símbolo del sistema o terminal y use la [dotnet nuevo](../../core/tools/dotnet-new.md) comando para crear el nuevo archivo de solución denominado `FSNetCore`:</span><span class="sxs-lookup"><span data-stu-id="89376-111">Open a command prompt/terminal and use the [dotnet new](../../core/tools/dotnet-new.md) command to create new solution file called `FSNetCore`:</span></span>

```console
dotnet new sln -o FSNetCore
```

<span data-ttu-id="89376-112">La siguiente estructura de directorios se produce después de ejecutar el comando anterior:</span><span class="sxs-lookup"><span data-stu-id="89376-112">The following directory structure is produced after running the previous command:</span></span>

```console
FSNetCore
    ├── FSNetCore.sln
```

### <a name="write-a-class-library"></a><span data-ttu-id="89376-113">Escribir una biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="89376-113">Write a class library</span></span>

<span data-ttu-id="89376-114">Cambie los directorios a *FSNetCore*.</span><span class="sxs-lookup"><span data-stu-id="89376-114">Change directories to *FSNetCore*.</span></span>

<span data-ttu-id="89376-115">Use la `dotnet new` de comandos, cree un proyecto de biblioteca de clases en el **src** carpeta con el nombre de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="89376-115">Use the `dotnet new` command, create a class library project in the **src** folder named Library.</span></span>

```console
dotnet new classlib -lang F# -o src/Library
```

<span data-ttu-id="89376-116">La siguiente estructura de directorios se produce después de ejecutar el comando anterior:</span><span class="sxs-lookup"><span data-stu-id="89376-116">The following directory structure is produced after running the previous command:</span></span>

```console
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

<span data-ttu-id="89376-117">Reemplace el contenido de `Library.fs` con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="89376-117">Replace the contents of `Library.fs` with the following code:</span></span>

```fsharp
module Library

open Newtonsoft.Json

let getJsonNetJson value =
    sprintf "I used to be %s but now I'm %s thanks to JSON.NET!" value (JsonConvert.SerializeObject(value))
```

<span data-ttu-id="89376-118">Agregue el paquete Newtonsoft.Json NuGet al proyecto de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="89376-118">Add the Newtonsoft.Json NuGet package to the Library project.</span></span>

```console
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

<span data-ttu-id="89376-119">Agregar el `Library` proyecto a la `FSNetCore` solución mediante la [agregar dotnet sln](../../core/tools/dotnet-sln.md) comando:</span><span class="sxs-lookup"><span data-stu-id="89376-119">Add the `Library` project to the `FSNetCore` solution using the [dotnet sln add](../../core/tools/dotnet-sln.md) command:</span></span>

```console
dotnet sln add src/Library/Library.fsproj
```

<span data-ttu-id="89376-120">Ejecute `dotnet build` para compilar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="89376-120">Run `dotnet build` to build the project.</span></span> <span data-ttu-id="89376-121">Dependencias no resueltas se restaurará cuando se crea.</span><span class="sxs-lookup"><span data-stu-id="89376-121">Unresolved dependencies will be restored when building.</span></span>

### <a name="write-a-console-application-that-consumes-the-class-library"></a><span data-ttu-id="89376-122">Escribir una aplicación de consola que utiliza la biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="89376-122">Write a console application that consumes the class library</span></span>

<span data-ttu-id="89376-123">Use la `dotnet new` de comandos, cree una aplicación de consola en el **src** carpeta con el nombre de aplicación.</span><span class="sxs-lookup"><span data-stu-id="89376-123">Use the `dotnet new` command, create a console application in the **src** folder named App.</span></span>

```console
dotnet new console -lang F# -o src/App
```

<span data-ttu-id="89376-124">La siguiente estructura de directorios se produce después de ejecutar el comando anterior:</span><span class="sxs-lookup"><span data-stu-id="89376-124">The following directory structure is produced after running the previous command:</span></span>

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

<span data-ttu-id="89376-125">Reemplace el contenido de la `Program.fs` archivo con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="89376-125">Replace the contents of the `Program.fs` file with the following code:</span></span>

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

<span data-ttu-id="89376-126">Agregue una referencia a la `Library` proyecto usando [dotnet Agregar referencia](../../core/tools/dotnet-add-reference.md).</span><span class="sxs-lookup"><span data-stu-id="89376-126">Add a reference to the `Library` project using [dotnet add reference](../../core/tools/dotnet-add-reference.md).</span></span>

```console
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

<span data-ttu-id="89376-127">Agregar el `App` proyecto a la `FSNetCore` solución mediante el `dotnet sln add` comando:</span><span class="sxs-lookup"><span data-stu-id="89376-127">Add the `App` project to the `FSNetCore` solution using the `dotnet sln add` command:</span></span>

```console
dotnet sln add src/App/App.fsproj
```

<span data-ttu-id="89376-128">Restaurar las dependencias de NuGet, `dotnet restore` y ejecute `dotnet build` para compilar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="89376-128">Restore the NuGet dependencies, `dotnet restore` and run `dotnet build` to build the project.</span></span>

<span data-ttu-id="89376-129">Cambie el directorio a la `src/App` proyecto de consola y ejecutar el proyecto pasando `Hello World` como argumentos:</span><span class="sxs-lookup"><span data-stu-id="89376-129">Change directory to the `src/App` console project and run the project passing `Hello World` as arguments:</span></span>

```console
cd src/App
dotnet run Hello World
```

<span data-ttu-id="89376-130">Debería ver los resultados siguientes:</span><span class="sxs-lookup"><span data-stu-id="89376-130">You should see the following results:</span></span>

```console
Nice command-line arguments! Here's what JSON.NET has to say about them:

I used to be Hello but now I'm ""Hello"" thanks to JSON.NET!
I used to be World but now I'm ""World"" thanks to JSON.NET!
```

## <a name="next-steps"></a><span data-ttu-id="89376-131">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="89376-131">Next steps</span></span>

<span data-ttu-id="89376-132">A continuación, consulte el [paseo F# ](../tour.md) para obtener más información sobre diferentes F# características.</span><span class="sxs-lookup"><span data-stu-id="89376-132">Next, check out the [Tour of F#](../tour.md) to learn more about different F# features.</span></span>
