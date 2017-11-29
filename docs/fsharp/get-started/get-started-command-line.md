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
# <a name="get-started-with-f-with-the-net-core-cli"></a><span data-ttu-id="9e25d-104">Empezar a trabajar con F # con la CLI de núcleo de .NET</span><span class="sxs-lookup"><span data-stu-id="9e25d-104">Get started with F# with the .NET Core CLI</span></span>

<span data-ttu-id="9e25d-105">Este artículo explican cómo puede empezar a usar F # en .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9e25d-105">This article covers how you can get started with using F# on .NET Core.</span></span> <span data-ttu-id="9e25d-106">Se desplazará por la creación de una solución de varios proyecto con una biblioteca de clases que se llama a una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="9e25d-106">It will go through building a multi-project solution with a Class Library that is called by a Console Application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9e25d-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="9e25d-107">Prerequisites</span></span>

<span data-ttu-id="9e25d-108">Para comenzar, primero debe instalar la [.NET Core SDK 1.0 o posterior](https://dot.net/core).</span><span class="sxs-lookup"><span data-stu-id="9e25d-108">To begin, you must install the [.NET Core SDK 1.0 or later](https://dot.net/core).</span></span> <span data-ttu-id="9e25d-109">No es necesario para desinstalar una versión anterior de .NET Core SDK, ya que admite instalaciones en paralelo.</span><span class="sxs-lookup"><span data-stu-id="9e25d-109">There is no need to uninstall a previous version of the .NET Core SDK, as it supports side-by-side installations.</span></span>

<span data-ttu-id="9e25d-110">En este artículo se supone que sabe cómo usar una línea de comandos y tiene un texto de preferencia editor.</span><span class="sxs-lookup"><span data-stu-id="9e25d-110">This article assumes that you know how to use a command line and have a preferred text editor.</span></span> <span data-ttu-id="9e25d-111">Si ya no utiliza, [código de Visual Studio](https://code.visualstudio.com) es una buena opción como un editor de texto para F #.</span><span class="sxs-lookup"><span data-stu-id="9e25d-111">If you don't already use it, [Visual Studio Code](https://code.visualstudio.com) is a great option as a text editor for F#.</span></span> <span data-ttu-id="9e25d-112">Para obtener maravillas características como IntelliSense, mejor resaltado de sintaxis y mucho más, puede descargar el [Ionide extensión](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span><span class="sxs-lookup"><span data-stu-id="9e25d-112">To get awesome features like IntelliSense, better syntax highlighting, and more, you can download the [Ionide Extension](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span></span>

## <a name="building-a-simple-multi-project-solution"></a><span data-ttu-id="9e25d-113">Crear una solución Simple de varios proyecto</span><span class="sxs-lookup"><span data-stu-id="9e25d-113">Building a Simple Multi-project Solution</span></span>

<span data-ttu-id="9e25d-114">Abra un símbolo del sistema o terminal y utilice la `dotnet new` comando para crear el nuevo archivo de solución denominado `FSNetCore`:</span><span class="sxs-lookup"><span data-stu-id="9e25d-114">Open a command prompt/terminal and use the `dotnet new` command to create new solution file called `FSNetCore`:</span></span>

```
dotnet new sln -o FSNetCore
```

<span data-ttu-id="9e25d-115">La estructura de directorios de lo siguiente es el resultado de la finalización de comando:</span><span class="sxs-lookup"><span data-stu-id="9e25d-115">The folowing directory structure is produced as a result of the command completing:</span></span>

```
FSNetCore
    ├── FSNetCore.sln
```

<span data-ttu-id="9e25d-116">Cambie los directorios a *FSNetCore* y empezar a agregar proyectos a la carpeta de soluciones.</span><span class="sxs-lookup"><span data-stu-id="9e25d-116">Change directories to *FSNetCore* and start adding projects to the solution folder.</span></span>
 
### <a name="writing-a-class-library"></a><span data-ttu-id="9e25d-117">Escribir una biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="9e25d-117">Writing a Class library</span></span>

<span data-ttu-id="9e25d-118">Use la `dotnet new` de comando, se crea un proyecto de biblioteca de clases en el **src** carpeta con el nombre de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="9e25d-118">Use the `dotnet new` command, create a Class Library project in the **src** folder named Library.</span></span> 

```bash
dotnet new lib -lang F# -o src/Library 
```

<span data-ttu-id="9e25d-119">La siguiente estructura de directorios es el resultado de la finalización de comando:</span><span class="sxs-lookup"><span data-stu-id="9e25d-119">The following directory structure is produced as a result of the command completing:</span></span>

```
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

<span data-ttu-id="9e25d-120">Reemplace el contenido de `Library.fs` con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9e25d-120">Replace the contents of `Library.fs` with the following:</span></span>

```fsharp
module Library

open Newtonsoft.Json

let getJsonNetJson value = 
    sprintf "I used to be %s but now I'm %s thanks to JSON.NET!" value  (JsonConvert.SerializeObject(value))
```

<span data-ttu-id="9e25d-121">Agregue el paquete Newtonsoft.Json NuGet al proyecto de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="9e25d-121">Add the Newtonsoft.Json NuGet package to the Library project.</span></span>

```bash
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

<span data-ttu-id="9e25d-122">Agregar el `Library` proyecto a la `FSNetCore` solución mediante la `dotnet sln add` comando:</span><span class="sxs-lookup"><span data-stu-id="9e25d-122">Add the `Library` project to the `FSNetCore` solution using the `dotnet sln add` command:</span></span>

```bash
dotnet sln add src/Library/Library.fsproj
```

<span data-ttu-id="9e25d-123">Restaurar las dependencias de NuGet, `dotnet restore` ([Véase la nota](#dotnet-restore-note)) y ejecute `dotnet build` para compilar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="9e25d-123">Restore the NuGet dependencies, `dotnet restore` ([see note](#dotnet-restore-note)) and run `dotnet build` to build the project.</span></span>

### <a name="writing-a-console-application-which-consumes-the-class-library"></a><span data-ttu-id="9e25d-124">Escribir una aplicación de consola que utiliza la biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="9e25d-124">Writing a Console Application which Consumes the Class Library</span></span>

<span data-ttu-id="9e25d-125">Use la `dotnet new` comando, cree una aplicación de consola en el **src** carpeta con el nombre de aplicación.</span><span class="sxs-lookup"><span data-stu-id="9e25d-125">Use the `dotnet new` command, create a Console app in the **src** folder named App.</span></span> 

```bash
dotnet new console -lang F# -o src/App 
```

<span data-ttu-id="9e25d-126">La siguiente estructura de directorios es el resultado de la finalización de comando:</span><span class="sxs-lookup"><span data-stu-id="9e25d-126">The following directory structure is produced as a result of the command completing:</span></span>

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

<span data-ttu-id="9e25d-127">Cambio `Program.fs` para:</span><span class="sxs-lookup"><span data-stu-id="9e25d-127">Change `Program.fs` to:</span></span>

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

<span data-ttu-id="9e25d-128">Agregue una referencia a la `Library` proyecto usando `dotnet add reference`.</span><span class="sxs-lookup"><span data-stu-id="9e25d-128">Add a reference to the `Library` project using `dotnet add reference`.</span></span>

```bash
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

<span data-ttu-id="9e25d-129">Agregar el `App` proyecto a la `FSNetCore` solución mediante la `dotnet sln add` comando:</span><span class="sxs-lookup"><span data-stu-id="9e25d-129">Add the `App` project to the `FSNetCore` solution using the `dotnet sln add` command:</span></span>

```bash
dotnet sln add src/App/App.fsproj
```

<span data-ttu-id="9e25d-130">Restaurar las dependencias de NuGet, `dotnet restore` ([Véase la nota](#dotnet-restore-note)) y ejecute `dotnet build` para compilar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="9e25d-130">Restore the NuGet dependencies, `dotnet restore` ([see note](#dotnet-restore-note)) and run `dotnet build` to build the project.</span></span>

<span data-ttu-id="9e25d-131">Cambie el directorio a la `src/App` proyecto de consola y ejecutar el proyecto pasar `Hello World` como argumentos.</span><span class="sxs-lookup"><span data-stu-id="9e25d-131">Change directory to the `src/App` console project and run the project passing `Hello World` as arguments.</span></span>

```bash
cd src/App
dotnet run Hello World
``` 

<span data-ttu-id="9e25d-132">Debería ver los siguientes resultados:</span><span class="sxs-lookup"><span data-stu-id="9e25d-132">You should see the following results:</span></span>

```
Nice command-line arguments! Here's what JSON.NET has to say about them:

I used to be Hello but now I'm ""Hello"" thanks to JSON.NET!
I used to be World but now I'm ""World"" thanks to JSON.NET!
```
<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]