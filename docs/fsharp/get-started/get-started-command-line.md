---
title: Introducción F# a las herramientas de línea de comandos
description: Obtenga información sobre cómo crear una solución sencilla de varios proyectos F# en el uso de la CLI de .net Core en cualquier sistema operativo (Windows, MacOS o Linux).
ms.date: 03/26/2018
ms.openlocfilehash: 6f67314f49150e20b18734f21f24daa3ce856922
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/20/2020
ms.locfileid: "77504148"
---
# <a name="get-started-with-f-with-the-net-core-cli"></a><span data-ttu-id="0f7be-103">Comience con F# el CLI de .net Core</span><span class="sxs-lookup"><span data-stu-id="0f7be-103">Get started with F# with the .NET Core CLI</span></span>

<span data-ttu-id="0f7be-104">En este artículo se explica cómo puede empezar a F# trabajar con en cualquier sistema operativo (Windows, MacOS o Linux) con el CLI de .net Core.</span><span class="sxs-lookup"><span data-stu-id="0f7be-104">This article covers how you can get started with F# on any operating system (Windows, macOS, or Linux) with the .NET Core CLI.</span></span> <span data-ttu-id="0f7be-105">Pasa por la creación de una solución de varios proyectos con una biblioteca de clases a la que llama una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="0f7be-105">It goes through building a multi-project solution with a class library that is called by a console application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0f7be-106">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="0f7be-106">Prerequisites</span></span>

<span data-ttu-id="0f7be-107">Para empezar, debe instalar la [SDK de .net Core](https://dotnet.microsoft.com/download)más reciente.</span><span class="sxs-lookup"><span data-stu-id="0f7be-107">To begin, you must install the latest [.NET Core SDK](https://dotnet.microsoft.com/download).</span></span>

<span data-ttu-id="0f7be-108">En este artículo se supone que sabe cómo usar una línea de comandos y tener un editor de texto preferido.</span><span class="sxs-lookup"><span data-stu-id="0f7be-108">This article assumes that you know how to use a command line and have a preferred text editor.</span></span> <span data-ttu-id="0f7be-109">Si aún no lo usa, [Visual Studio Code](get-started-vscode.md) es una excelente opción como editor de texto para F#.</span><span class="sxs-lookup"><span data-stu-id="0f7be-109">If you don't already use it, [Visual Studio Code](get-started-vscode.md) is a great option as a text editor for F#.</span></span>

## <a name="build-a-simple-multi-project-solution"></a><span data-ttu-id="0f7be-110">Compilar una solución sencilla de varios proyectos</span><span class="sxs-lookup"><span data-stu-id="0f7be-110">Build a simple multi-project solution</span></span>

<span data-ttu-id="0f7be-111">Abra un símbolo del sistema o terminal y use el comando [dotnet New](../../core/tools/dotnet-new.md) para crear un nuevo archivo de solución denominado `FSNetCore`:</span><span class="sxs-lookup"><span data-stu-id="0f7be-111">Open a command prompt/terminal and use the [dotnet new](../../core/tools/dotnet-new.md) command to create new solution file called `FSNetCore`:</span></span>

```dotnetcli
dotnet new sln -o FSNetCore
```

<span data-ttu-id="0f7be-112">Después de ejecutar el comando anterior, se genera la siguiente estructura de directorios:</span><span class="sxs-lookup"><span data-stu-id="0f7be-112">The following directory structure is produced after running the previous command:</span></span>

```console
FSNetCore
    ├── FSNetCore.sln
```

### <a name="write-a-class-library"></a><span data-ttu-id="0f7be-113">Escribir una biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="0f7be-113">Write a class library</span></span>

<span data-ttu-id="0f7be-114">Cambie los directorios a *FSNetCore*.</span><span class="sxs-lookup"><span data-stu-id="0f7be-114">Change directories to *FSNetCore*.</span></span>

<span data-ttu-id="0f7be-115">Use el comando `dotnet new`, cree un proyecto de biblioteca de clases en la carpeta **src** denominada Library.</span><span class="sxs-lookup"><span data-stu-id="0f7be-115">Use the `dotnet new` command, create a class library project in the **src** folder named Library.</span></span>

```dotnetcli
dotnet new classlib -lang "F#" -o src/Library
```

<span data-ttu-id="0f7be-116">Después de ejecutar el comando anterior, se genera la siguiente estructura de directorios:</span><span class="sxs-lookup"><span data-stu-id="0f7be-116">The following directory structure is produced after running the previous command:</span></span>

```console
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

<span data-ttu-id="0f7be-117">Reemplace el contenido de `Library.fs` por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="0f7be-117">Replace the contents of `Library.fs` with the following code:</span></span>

```fsharp
module Library

open Newtonsoft.Json

let getJsonNetJson value =
    sprintf "I used to be %s but now I'm %s thanks to JSON.NET!" value (JsonConvert.SerializeObject(value))
```

<span data-ttu-id="0f7be-118">Agregue el paquete NuGet Newtonsoft. JSON al proyecto de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="0f7be-118">Add the Newtonsoft.Json NuGet package to the Library project.</span></span>

```dotnetcli
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

<span data-ttu-id="0f7be-119">Agregue el proyecto `Library` a la solución de `FSNetCore` con el comando [dotnet sln Add](../../core/tools/dotnet-sln.md) :</span><span class="sxs-lookup"><span data-stu-id="0f7be-119">Add the `Library` project to the `FSNetCore` solution using the [dotnet sln add](../../core/tools/dotnet-sln.md) command:</span></span>

```dotnetcli
dotnet sln add src/Library/Library.fsproj
```

<span data-ttu-id="0f7be-120">Ejecute `dotnet build` para compilar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="0f7be-120">Run `dotnet build` to build the project.</span></span> <span data-ttu-id="0f7be-121">Las dependencias no resueltas se restaurarán al compilar.</span><span class="sxs-lookup"><span data-stu-id="0f7be-121">Unresolved dependencies will be restored when building.</span></span>

### <a name="write-a-console-application-that-consumes-the-class-library"></a><span data-ttu-id="0f7be-122">Escribir una aplicación de consola que consuma la biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="0f7be-122">Write a console application that consumes the class library</span></span>

<span data-ttu-id="0f7be-123">Use el comando `dotnet new`, cree una aplicación de consola en la carpeta **src** denominada app.</span><span class="sxs-lookup"><span data-stu-id="0f7be-123">Use the `dotnet new` command, create a console application in the **src** folder named App.</span></span>

```dotnetcli
dotnet new console -lang "F#" -o src/App
```

<span data-ttu-id="0f7be-124">Después de ejecutar el comando anterior, se genera la siguiente estructura de directorios:</span><span class="sxs-lookup"><span data-stu-id="0f7be-124">The following directory structure is produced after running the previous command:</span></span>

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

<span data-ttu-id="0f7be-125">Reemplace el contenido del archivo `Program.fs` por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="0f7be-125">Replace the contents of the `Program.fs` file with the following code:</span></span>

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

<span data-ttu-id="0f7be-126">Agregue una referencia al proyecto `Library` mediante [dotnet Add Reference](../../core/tools/dotnet-add-reference.md).</span><span class="sxs-lookup"><span data-stu-id="0f7be-126">Add a reference to the `Library` project using [dotnet add reference](../../core/tools/dotnet-add-reference.md).</span></span>

```dotnetcli
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

<span data-ttu-id="0f7be-127">Agregue el proyecto `App` a la solución de `FSNetCore` con el comando `dotnet sln add`:</span><span class="sxs-lookup"><span data-stu-id="0f7be-127">Add the `App` project to the `FSNetCore` solution using the `dotnet sln add` command:</span></span>

```dotnetcli
dotnet sln add src/App/App.fsproj
```

<span data-ttu-id="0f7be-128">Restaure las dependencias de NuGet, `dotnet restore` y ejecute `dotnet build` para compilar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="0f7be-128">Restore the NuGet dependencies, `dotnet restore` and run `dotnet build` to build the project.</span></span>

<span data-ttu-id="0f7be-129">Cambie el directorio al proyecto de consola de `src/App` y ejecute el proyecto pasando `Hello World` como argumentos:</span><span class="sxs-lookup"><span data-stu-id="0f7be-129">Change directory to the `src/App` console project and run the project passing `Hello World` as arguments:</span></span>

```dotnetcli
cd src/App
dotnet run Hello World
```

<span data-ttu-id="0f7be-130">Debería ver los siguientes resultados:</span><span class="sxs-lookup"><span data-stu-id="0f7be-130">You should see the following results:</span></span>

```console
Nice command-line arguments! Here's what JSON.NET has to say about them:

I used to be Hello but now I'm ""Hello"" thanks to JSON.NET!
I used to be World but now I'm ""World"" thanks to JSON.NET!
```

## <a name="next-steps"></a><span data-ttu-id="0f7be-131">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="0f7be-131">Next steps</span></span>

<span data-ttu-id="0f7be-132">A continuación, consulte el [paseo F# ](../tour.md) por para obtener más información sobre F# las distintas características.</span><span class="sxs-lookup"><span data-stu-id="0f7be-132">Next, check out the [Tour of F#](../tour.md) to learn more about different F# features.</span></span>
