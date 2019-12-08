---
title: Introducción a .NET Core
description: Encuentre recursos para aprender a crear aplicaciones .NET Core en Windows, Linux y macOS.
author: thraka
ms.author: adegeo
ms.date: 09/19/2019
ms.openlocfilehash: 89db6d79336c01315983133d9041904d88cba301
ms.sourcegitcommit: 68a4b28242da50e1d25aab597c632767713a6f81
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2019
ms.locfileid: "74884259"
---
# <a name="get-started-with-net-core"></a><span data-ttu-id="e6f70-103">Introducción a .NET Core</span><span class="sxs-lookup"><span data-stu-id="e6f70-103">Get started with .NET Core</span></span>

<span data-ttu-id="e6f70-104">En este artículo se proporciona información sobre cómo comenzar con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e6f70-104">This article provides information on getting started with .NET Core.</span></span> <span data-ttu-id="e6f70-105">.NET Core se puede instalar en Windows, Linux y macOS.</span><span class="sxs-lookup"><span data-stu-id="e6f70-105">.NET Core can be installed on Windows, Linux, and macOS.</span></span> <span data-ttu-id="e6f70-106">Puede programar en su editor de texto preferido y crear aplicaciones y bibliotecas multiplataforma.</span><span class="sxs-lookup"><span data-stu-id="e6f70-106">You can code in your favorite text editor and produce cross-platform libraries and applications.</span></span> 

<span data-ttu-id="e6f70-107">Si no está seguro de qué es .NET Core o cómo se relaciona con otras tecnologías .NET, comience con la información general [¿Qué es .NET?](https://dotnet.microsoft.com/learn/dotnet/what-is-dotnet).</span><span class="sxs-lookup"><span data-stu-id="e6f70-107">If you're unsure what .NET Core is, or how it relates to other .NET technologies, start with the [What is .NET](https://dotnet.microsoft.com/learn/dotnet/what-is-dotnet) overview.</span></span> <span data-ttu-id="e6f70-108">En resumen, .NET Core es una implementación multiplataforma de código abierto de .NET.</span><span class="sxs-lookup"><span data-stu-id="e6f70-108">Put simply, .NET Core is an open-source, cross-platform implementation of .NET.</span></span>

## <a name="create-an-application"></a><span data-ttu-id="e6f70-109">Crear una aplicación</span><span class="sxs-lookup"><span data-stu-id="e6f70-109">Create an application</span></span>

<span data-ttu-id="e6f70-110">En primer lugar, descargue e instale el [SDK de .NET Core](https://dotnet.microsoft.com/download) en el equipo.</span><span class="sxs-lookup"><span data-stu-id="e6f70-110">First, download and install the [.NET Core SDK](https://dotnet.microsoft.com/download) on your computer.</span></span>

<span data-ttu-id="e6f70-111">A continuación, abra un terminal como **PowerShell**, **Símbolo del sistema** o **bash**.</span><span class="sxs-lookup"><span data-stu-id="e6f70-111">Next, open a terminal such as **PowerShell**, **Command Prompt**, or **bash**.</span></span> <span data-ttu-id="e6f70-112">Escriba los comandos `dotnet` siguientes para crear y ejecutar una aplicación C#:</span><span class="sxs-lookup"><span data-stu-id="e6f70-112">Type the following `dotnet` commands to create and run a C# application:</span></span>

```dotnetcli
dotnet new console --output sample1
dotnet run --project sample1
```

<span data-ttu-id="e6f70-113">Debería ver los siguientes resultados:</span><span class="sxs-lookup"><span data-stu-id="e6f70-113">You should see the following output:</span></span>

```console
Hello World!
```

<span data-ttu-id="e6f70-114">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="e6f70-114">Congratulations!</span></span> <span data-ttu-id="e6f70-115">Ha creado una sencilla aplicación .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e6f70-115">You've created a simple .NET Core application.</span></span> <span data-ttu-id="e6f70-116">También puede usar [Visual Studio Code](tutorials/with-visual-studio-code.md), [Visual Studio ](tutorials/with-visual-studio.md) (solo Windows) o [Visual Studio para Mac](tutorials/using-on-mac-vs.md) (solo macOS), para crear una aplicación .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e6f70-116">You can also use [Visual Studio Code](tutorials/with-visual-studio-code.md), [Visual Studio](tutorials/with-visual-studio.md) (Windows only), or [Visual Studio for Mac](tutorials/using-on-mac-vs.md) (macOS only), to create a .NET Core application.</span></span>

## <a name="tutorials"></a><span data-ttu-id="e6f70-117">Tutoriales</span><span class="sxs-lookup"><span data-stu-id="e6f70-117">Tutorials</span></span>

<span data-ttu-id="e6f70-118">Para comenzar a desarrollar aplicaciones .NET Core, puede seguir estos tutoriales paso a paso.</span><span class="sxs-lookup"><span data-stu-id="e6f70-118">You can get started developing .NET Core applications by following these step-by-step tutorials.</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="windowstabwindows"></a>[<span data-ttu-id="e6f70-119">Windows</span><span class="sxs-lookup"><span data-stu-id="e6f70-119">Windows</span></span>](#tab/windows)

- [<span data-ttu-id="e6f70-120">Compilación de una aplicación "Hola a todos" en C# con .NET Core en Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="e6f70-120">Build a C# "Hello World" Application with .NET Core in Visual Studio 2017.</span></span>](./tutorials/with-visual-studio.md)
- [<span data-ttu-id="e6f70-121">Creación de una biblioteca de clases de C# con .NET Core en Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="e6f70-121">Build a C# class library with .NET Core in Visual Studio 2017.</span></span>](./tutorials/library-with-visual-studio.md)
- [<span data-ttu-id="e6f70-122">Compilación de una aplicación "Hola a todos" en Visual Basic con .NET Core en Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="e6f70-122">Build a Visual Basic "Hello World" application with .NET Core in Visual Studio 2017.</span></span>](./tutorials/vb-with-visual-studio.md)
- [<span data-ttu-id="e6f70-123">Creación de una biblioteca de clases con Visual Basic y .NET Core en Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="e6f70-123">Build a class library with Visual Basic and .NET Core in Visual Studio 2017.</span></span>](./tutorials/vb-library-with-visual-studio.md)  
- <span data-ttu-id="e6f70-124">Vea un vídeo sobre [cómo instalar y usar Visual Studio Code y .NET Core](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core/).</span><span class="sxs-lookup"><span data-stu-id="e6f70-124">Watch a video on [how to install and use Visual Studio Code and .NET Core](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core/).</span></span>
- <span data-ttu-id="e6f70-125">Vea un vídeo sobre [cómo instalar y usar Visual Studio 2017 y .NET Core](https://channel9.msdn.com/Blogs/dotnet/Get-Started-NET-Core-Visual-Studio-2017/).</span><span class="sxs-lookup"><span data-stu-id="e6f70-125">Watch a video on [how to install and use Visual Studio 2017 and .NET Core](https://channel9.msdn.com/Blogs/dotnet/Get-Started-NET-Core-Visual-Studio-2017/).</span></span>
- [<span data-ttu-id="e6f70-126">Introducción a .NET Core con la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="e6f70-126">Getting started with .NET Core using the command-line.</span></span>](tutorials/cli-create-console-app.md)

<span data-ttu-id="e6f70-127">Vea el artículo [Dependencias y requisitos de .NET Core](install/dependencies.md?tabs=netcore30&pivots=os-windows) para obtener una lista de las versiones de Windows admitidas.</span><span class="sxs-lookup"><span data-stu-id="e6f70-127">See the [.NET Core dependencies and requirements](install/dependencies.md?tabs=netcore30&pivots=os-windows) article for a list of the supported Windows versions.</span></span>

# <a name="linuxtablinux"></a>[<span data-ttu-id="e6f70-128">Linux</span><span class="sxs-lookup"><span data-stu-id="e6f70-128">Linux</span></span>](#tab/linux)

<span data-ttu-id="e6f70-129">Para empezar a desarrollar aplicaciones .NET Core, puede seguir estos tutoriales paso a paso:</span><span class="sxs-lookup"><span data-stu-id="e6f70-129">You can get started developing .NET Core application by following these step-by-step tutorials:</span></span>

- [<span data-ttu-id="e6f70-130">Introducción a .NET Core con la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="e6f70-130">Getting started with .NET Core using the command-line.</span></span>](tutorials/cli-create-console-app.md)
- <span data-ttu-id="e6f70-131">Vea un vídeo de [introducción a Visual Studio Code mediante C# y .NET Core en Ubuntu](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).</span><span class="sxs-lookup"><span data-stu-id="e6f70-131">Watch a video on [getting started with Visual Studio Code using C# and .NET Core on Ubuntu](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).</span></span>

<span data-ttu-id="e6f70-132">Vea el artículo [Dependencias y requisitos de .NET Core](install/dependencies.md?tabs=netcore30&pivots=os-linux) para obtener una lista de las distribuciones y las versiones de Linux admitidas.</span><span class="sxs-lookup"><span data-stu-id="e6f70-132">See the [.NET Core dependencies and requirements](install/dependencies.md?tabs=netcore30&pivots=os-linux) article for a list of the supported Linux distros and versions.</span></span>

# <a name="macostabmacos"></a>[<span data-ttu-id="e6f70-133">macOS</span><span class="sxs-lookup"><span data-stu-id="e6f70-133">macOS</span></span>](#tab/macos)

<span data-ttu-id="e6f70-134">Para empezar a desarrollar aplicaciones .NET Core, puede seguir estos tutoriales paso a paso:</span><span class="sxs-lookup"><span data-stu-id="e6f70-134">You can get started developing .NET Core application by following these step-by-step tutorials:</span></span>

- <span data-ttu-id="e6f70-135">Vea un vídeo de [introducción a Visual Studio Code mediante C# y .NET Core en macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-VSCode-NET-Core-Mac).</span><span class="sxs-lookup"><span data-stu-id="e6f70-135">Watch a video on [Getting started with Visual Studio Code using C# and .NET Core on macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-VSCode-NET-Core-Mac).</span></span>
- [<span data-ttu-id="e6f70-136">Introducción a .NET Core en macOS con Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="e6f70-136">Getting started with .NET Core on macOS, using Visual Studio Code.</span></span>](tutorials/using-on-macos.md)
- [<span data-ttu-id="e6f70-137">Introducción a .NET Core con la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="e6f70-137">Getting started with .NET Core using the command-line.</span></span>](tutorials/cli-create-console-app.md)
- [<span data-ttu-id="e6f70-138">Introducción a .NET Core en macOS con Visual Studio para Mac.</span><span class="sxs-lookup"><span data-stu-id="e6f70-138">Getting started with .NET Core on macOS using Visual Studio for Mac.</span></span>](tutorials/using-on-mac-vs.md)
- [<span data-ttu-id="e6f70-139">Creación de una solución completa de .NET Core en macOS con Visual Studio para Mac.</span><span class="sxs-lookup"><span data-stu-id="e6f70-139">Build a complete .NET Core solution on macOS using Visual Studio for Mac.</span></span>](tutorials/using-on-mac-vs-full-solution.md)

<span data-ttu-id="e6f70-140">Vea el artículo [Dependencias y requisitos de .NET Core](install/dependencies.md?tabs=netcore30&pivots=os-macos) para obtener una lista de las versiones de OS X / macOS admitidas.</span><span class="sxs-lookup"><span data-stu-id="e6f70-140">See the [.NET Core dependencies and requirements](install/dependencies.md?tabs=netcore30&pivots=os-macos) article for a list of the supported OS X / macOS versions.</span></span>

---
