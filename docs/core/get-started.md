---
title: Introducción a .NET Core
description: Encuentre recursos para aprender a crear aplicaciones .NET Core en Windows, Linux y macOS.
author: thraka
ms.author: adegeo
ms.date: 06/27/2018
ms.openlocfilehash: 2ec7f57250db8779552305b2ee69cbcf1db55d0c
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977184"
---
# <a name="get-started-with-net-core"></a><span data-ttu-id="0aed4-103">Introducción a .NET Core</span><span class="sxs-lookup"><span data-stu-id="0aed4-103">Get started with .NET Core</span></span>

<span data-ttu-id="0aed4-104">En este artículo se proporciona información sobre cómo comenzar con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="0aed4-104">This article provides information on getting started with .NET Core.</span></span> <span data-ttu-id="0aed4-105">.NET Core se puede instalar en Windows, Linux y macOS.</span><span class="sxs-lookup"><span data-stu-id="0aed4-105">.NET Core can be installed on Windows, Linux, and macOS.</span></span> <span data-ttu-id="0aed4-106">Puede programar en su editor de texto preferido y crear aplicaciones y bibliotecas multiplataforma.</span><span class="sxs-lookup"><span data-stu-id="0aed4-106">You can code in your favorite text editor and produce cross-platform libraries and applications.</span></span> 

<span data-ttu-id="0aed4-107">Si no está seguro de qué es .NET Core o cómo se relaciona con otras tecnologías .NET, comience con la información general [¿Qué es .NET?](https://www.microsoft.com/net/learn/dotnet/what-is-dotnet).</span><span class="sxs-lookup"><span data-stu-id="0aed4-107">If you're unsure what .NET Core is, or how it relates to other .NET technologies, start with the [What is .NET](https://www.microsoft.com/net/learn/dotnet/what-is-dotnet) overview.</span></span> <span data-ttu-id="0aed4-108">En resumen, .NET Core es una implementación multiplataforma de código abierto de .NET.</span><span class="sxs-lookup"><span data-stu-id="0aed4-108">Put simply, .NET Core is an open-source, cross-platform, implementation of .NET.</span></span>

## <a name="create-an-application"></a><span data-ttu-id="0aed4-109">Crear una aplicación</span><span class="sxs-lookup"><span data-stu-id="0aed4-109">Create an application</span></span>

<span data-ttu-id="0aed4-110">En primer lugar, descargue e instale el [SDK de .NET Core](https://www.microsoft.com/net/download/) en el equipo.</span><span class="sxs-lookup"><span data-stu-id="0aed4-110">First, download and install the [.NET Core SDK](https://www.microsoft.com/net/download/) on your computer.</span></span>

<span data-ttu-id="0aed4-111">A continuación, abra un terminal como **PowerShell**, **Símbolo del sistema** o **bash**.</span><span class="sxs-lookup"><span data-stu-id="0aed4-111">Next, open a terminal such as **PowerShell**, **Command Prompt**, or **bash**.</span></span> <span data-ttu-id="0aed4-112">Escriba los comandos `dotnet` siguientes para crear y ejecutar una aplicación de C#.</span><span class="sxs-lookup"><span data-stu-id="0aed4-112">Type the following `dotnet` commands to create and run a C# application.</span></span>

```console
dotnet new console --output sample1
dotnet run --project sample1
```

<span data-ttu-id="0aed4-113">Debería ver los siguientes resultados:</span><span class="sxs-lookup"><span data-stu-id="0aed4-113">You should see the following output:</span></span>

```console
Hello World!
```

<span data-ttu-id="0aed4-114">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="0aed4-114">Congratulations!</span></span> <span data-ttu-id="0aed4-115">Ha creado una sencilla aplicación .NET Core.</span><span class="sxs-lookup"><span data-stu-id="0aed4-115">You've created a simple .NET Core application.</span></span> <span data-ttu-id="0aed4-116">También puede usar [Visual Studio Code](tutorials/with-visual-studio-code.md), [Visual Studio 2017](tutorials/with-visual-studio.md) (solo Windows) o [Visual Studio para Mac](tutorials/using-on-mac-vs.md) (solo macOS), para crear una aplicación .NET Core.</span><span class="sxs-lookup"><span data-stu-id="0aed4-116">You can also use [Visual Studio Code](tutorials/with-visual-studio-code.md), [Visual Studio 2017](tutorials/with-visual-studio.md) (Windows only), or [Visual Studio for Mac](tutorials/using-on-mac-vs.md) (macOS only), to create a .NET Core application.</span></span>

## <a name="tutorials"></a><span data-ttu-id="0aed4-117">Tutoriales</span><span class="sxs-lookup"><span data-stu-id="0aed4-117">Tutorials</span></span>

<span data-ttu-id="0aed4-118">Para comenzar a desarrollar aplicaciones .NET Core, puede seguir estos tutoriales paso a paso.</span><span class="sxs-lookup"><span data-stu-id="0aed4-118">You can get started developing .NET Core applications by following these step-by-step tutorials.</span></span>

# <a name="windowstabwindows"></a>[<span data-ttu-id="0aed4-119">Windows</span><span class="sxs-lookup"><span data-stu-id="0aed4-119">Windows</span></span>](#tab/windows)

* [<span data-ttu-id="0aed4-120">Compilación de una aplicación "Hola a todos" en C# con .NET Core en Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="0aed4-120">Build a C# "Hello World" Application with .NET Core in Visual Studio 2017.</span></span>](./tutorials/with-visual-studio.md)

* [<span data-ttu-id="0aed4-121">Creación de una biblioteca de clases de C# con .NET Core en Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="0aed4-121">Build a C# class library with .NET Core in Visual Studio 2017.</span></span>](./tutorials/library-with-visual-studio.md)

* [<span data-ttu-id="0aed4-122">Compilación de una aplicación "Hola a todos" en Visual Basic con .NET Core en Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="0aed4-122">Build a Visual Basic "Hello World" application with .NET Core in Visual Studio 2017.</span></span>](./tutorials/vb-with-visual-studio.md)

* [<span data-ttu-id="0aed4-123">Creación de una biblioteca de clases con Visual Basic y .NET Core en Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="0aed4-123">Build a class library with Visual Basic and .NET Core in Visual Studio 2017.</span></span>](./tutorials/vb-library-with-visual-studio.md)  

* <span data-ttu-id="0aed4-124">Vea un vídeo sobre [cómo instalar y usar Visual Studio Code y .NET Core](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core/).</span><span class="sxs-lookup"><span data-stu-id="0aed4-124">Watch a video on [how to install and use Visual Studio Code and .NET Core](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core/).</span></span>

* <span data-ttu-id="0aed4-125">Vea un vídeo sobre [cómo instalar y usar Visual Studio 2017 y .NET Core](https://channel9.msdn.com/Blogs/dotnet/Get-Started-NET-Core-Visual-Studio-2017/).</span><span class="sxs-lookup"><span data-stu-id="0aed4-125">Watch a video on [how to install and use Visual Studio 2017 and .NET Core](https://channel9.msdn.com/Blogs/dotnet/Get-Started-NET-Core-Visual-Studio-2017/).</span></span>

* [<span data-ttu-id="0aed4-126">Introducción a .NET Core con la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="0aed4-126">Getting started with .NET Core using the command-line.</span></span>](tutorials/using-with-xplat-cli.md)

<span data-ttu-id="0aed4-127">Vea el artículo [Requisitos previos para .NET Core en Windows](windows-prerequisites.md) para obtener una lista de las versiones de Windows admitidas.</span><span class="sxs-lookup"><span data-stu-id="0aed4-127">See the [Prerequisites for Windows development](windows-prerequisites.md) article for a list of the supported Windows versions.</span></span>

# <a name="linuxtablinux"></a>[<span data-ttu-id="0aed4-128">Linux</span><span class="sxs-lookup"><span data-stu-id="0aed4-128">Linux</span></span>](#tab/linux)

<span data-ttu-id="0aed4-129">Para comenzar a desarrollar aplicaciones .NET Core, puede seguir estos tutoriales paso a paso.</span><span class="sxs-lookup"><span data-stu-id="0aed4-129">You can get started developing .NET Core application by following these step-by-step tutorials.</span></span>

* [<span data-ttu-id="0aed4-130">Introducción a .NET Core con la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="0aed4-130">Getting started with .NET Core using the command-line.</span></span>](tutorials/using-with-xplat-cli.md)

* <span data-ttu-id="0aed4-131">Vea un vídeo de [introducción a Visual Studio Code mediante C# y .NET Core en Ubuntu](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).</span><span class="sxs-lookup"><span data-stu-id="0aed4-131">Watch a video on [getting started with Visual Studio Code using C# and .NET Core on Ubuntu](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).</span></span>

<span data-ttu-id="0aed4-132">Vea el artículo [Requisitos previos para .NET Core en Linux](linux-prerequisites.md) para obtener una lista de las versiones y distribuciones de Linux admitidas.</span><span class="sxs-lookup"><span data-stu-id="0aed4-132">See the [Prerequisites for Linux development](linux-prerequisites.md) article for a list of the supported Linux distros and versions.</span></span>

# <a name="macostabmacos"></a>[<span data-ttu-id="0aed4-133">macOS</span><span class="sxs-lookup"><span data-stu-id="0aed4-133">macOS</span></span>](#tab/macos)

<span data-ttu-id="0aed4-134">Para comenzar a desarrollar aplicaciones .NET Core, puede seguir estos tutoriales paso a paso.</span><span class="sxs-lookup"><span data-stu-id="0aed4-134">You can get started developing .NET Core application by following these step-by-step tutorials.</span></span>

* <span data-ttu-id="0aed4-135">Vea un vídeo de [introducción a Visual Studio Code mediante C# y .NET Core en macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-VSCode-NET-Core-Mac).</span><span class="sxs-lookup"><span data-stu-id="0aed4-135">Watch a video on [Getting started with Visual Studio Code using C# and .NET Core on macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-VSCode-NET-Core-Mac).</span></span>

* [<span data-ttu-id="0aed4-136">Introducción a .NET Core en macOS con Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="0aed4-136">Getting started with .NET Core on macOS, using Visual Studio Code.</span></span>](tutorials/using-on-macos.md)

* [<span data-ttu-id="0aed4-137">Introducción a .NET Core con la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="0aed4-137">Getting started with .NET Core using the command-line.</span></span>](tutorials/using-with-xplat-cli.md)

* [<span data-ttu-id="0aed4-138">Introducción a .NET Core en macOS con Visual Studio para Mac.</span><span class="sxs-lookup"><span data-stu-id="0aed4-138">Getting started with .NET Core on macOS using Visual Studio for Mac.</span></span>](tutorials/using-on-mac-vs.md)

* [<span data-ttu-id="0aed4-139">Creación de una solución completa de .NET Core en macOS con Visual Studio para Mac.</span><span class="sxs-lookup"><span data-stu-id="0aed4-139">Build a complete .NET Core solution on macOS using Visual Studio for Mac.</span></span>](tutorials/using-on-mac-vs-full-solution.md)

<span data-ttu-id="0aed4-140">Vea el artículo [Requisitos previos para .NET Core en macOS](macos-prerequisites.md) para obtener una lista de las versiones de OS X y macOS admitidas.</span><span class="sxs-lookup"><span data-stu-id="0aed4-140">See the [Prerequisites for macOS development](macos-prerequisites.md) article for a list of the supported OS X / macOS versions.</span></span>

---
