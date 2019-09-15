---
title: Introducción a .NET Core
description: Encuentre recursos para aprender a crear aplicaciones .NET Core en Windows, Linux y macOS.
author: thraka
ms.author: adegeo
ms.date: 06/27/2018
ms.openlocfilehash: 3c530c71d1cfa9d0c4cf09f38519970f6ef8da51
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2019
ms.locfileid: "70969897"
---
# <a name="get-started-with-net-core"></a><span data-ttu-id="ccd89-103">Introducción a .NET Core</span><span class="sxs-lookup"><span data-stu-id="ccd89-103">Get started with .NET Core</span></span>

<span data-ttu-id="ccd89-104">En este artículo se proporciona información sobre cómo comenzar con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ccd89-104">This article provides information on getting started with .NET Core.</span></span> <span data-ttu-id="ccd89-105">.NET Core se puede instalar en Windows, Linux y macOS.</span><span class="sxs-lookup"><span data-stu-id="ccd89-105">.NET Core can be installed on Windows, Linux, and macOS.</span></span> <span data-ttu-id="ccd89-106">Puede programar en su editor de texto preferido y crear aplicaciones y bibliotecas multiplataforma.</span><span class="sxs-lookup"><span data-stu-id="ccd89-106">You can code in your favorite text editor and produce cross-platform libraries and applications.</span></span> 

<span data-ttu-id="ccd89-107">Si no está seguro de qué es .NET Core o cómo se relaciona con otras tecnologías .NET, comience con la información general [¿Qué es .NET?](https://dotnet.microsoft.com/learn/dotnet/what-is-dotnet).</span><span class="sxs-lookup"><span data-stu-id="ccd89-107">If you're unsure what .NET Core is, or how it relates to other .NET technologies, start with the [What is .NET](https://dotnet.microsoft.com/learn/dotnet/what-is-dotnet) overview.</span></span> <span data-ttu-id="ccd89-108">En resumen, .NET Core es una implementación multiplataforma de código abierto de .NET.</span><span class="sxs-lookup"><span data-stu-id="ccd89-108">Put simply, .NET Core is an open-source, cross-platform implementation of .NET.</span></span>

## <a name="create-an-application"></a><span data-ttu-id="ccd89-109">Crear una aplicación</span><span class="sxs-lookup"><span data-stu-id="ccd89-109">Create an application</span></span>

<span data-ttu-id="ccd89-110">En primer lugar, descargue e instale el [SDK de .NET Core](https://dotnet.microsoft.com/download) en el equipo.</span><span class="sxs-lookup"><span data-stu-id="ccd89-110">First, download and install the [.NET Core SDK](https://dotnet.microsoft.com/download) on your computer.</span></span>

<span data-ttu-id="ccd89-111">A continuación, abra un terminal como **PowerShell**, **Símbolo del sistema** o **bash**.</span><span class="sxs-lookup"><span data-stu-id="ccd89-111">Next, open a terminal such as **PowerShell**, **Command Prompt**, or **bash**.</span></span> <span data-ttu-id="ccd89-112">Escriba los comandos `dotnet` siguientes para crear y ejecutar una aplicación de C#.</span><span class="sxs-lookup"><span data-stu-id="ccd89-112">Type the following `dotnet` commands to create and run a C# application.</span></span>

```console
dotnet new console --output sample1
dotnet run --project sample1
```

<span data-ttu-id="ccd89-113">Debería ver los siguientes resultados:</span><span class="sxs-lookup"><span data-stu-id="ccd89-113">You should see the following output:</span></span>

```console
Hello World!
```

<span data-ttu-id="ccd89-114">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="ccd89-114">Congratulations!</span></span> <span data-ttu-id="ccd89-115">Ha creado una sencilla aplicación .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ccd89-115">You've created a simple .NET Core application.</span></span> <span data-ttu-id="ccd89-116">También puede usar [Visual Studio Code](tutorials/with-visual-studio-code.md), [Visual Studio ](tutorials/with-visual-studio.md) (solo Windows) o [Visual Studio para Mac](tutorials/using-on-mac-vs.md) (solo macOS), para crear una aplicación .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ccd89-116">You can also use [Visual Studio Code](tutorials/with-visual-studio-code.md), [Visual Studio](tutorials/with-visual-studio.md) (Windows only), or [Visual Studio for Mac](tutorials/using-on-mac-vs.md) (macOS only), to create a .NET Core application.</span></span>

## <a name="tutorials"></a><span data-ttu-id="ccd89-117">Tutoriales</span><span class="sxs-lookup"><span data-stu-id="ccd89-117">Tutorials</span></span>

<span data-ttu-id="ccd89-118">Para comenzar a desarrollar aplicaciones .NET Core, puede seguir estos tutoriales paso a paso.</span><span class="sxs-lookup"><span data-stu-id="ccd89-118">You can get started developing .NET Core applications by following these step-by-step tutorials.</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="windowstabwindows"></a>[<span data-ttu-id="ccd89-119">Windows</span><span class="sxs-lookup"><span data-stu-id="ccd89-119">Windows</span></span>](#tab/windows)

* [<span data-ttu-id="ccd89-120">Compilación de una aplicación "Hola a todos" en C# con .NET Core en Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="ccd89-120">Build a C# "Hello World" Application with .NET Core in Visual Studio 2017.</span></span>](./tutorials/with-visual-studio.md)

* [<span data-ttu-id="ccd89-121">Creación de una biblioteca de clases de C# con .NET Core en Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="ccd89-121">Build a C# class library with .NET Core in Visual Studio 2017.</span></span>](./tutorials/library-with-visual-studio.md)

* [<span data-ttu-id="ccd89-122">Compilación de una aplicación "Hola a todos" en Visual Basic con .NET Core en Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="ccd89-122">Build a Visual Basic "Hello World" application with .NET Core in Visual Studio 2017.</span></span>](./tutorials/vb-with-visual-studio.md)

* [<span data-ttu-id="ccd89-123">Creación de una biblioteca de clases con Visual Basic y .NET Core en Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="ccd89-123">Build a class library with Visual Basic and .NET Core in Visual Studio 2017.</span></span>](./tutorials/vb-library-with-visual-studio.md)  

* <span data-ttu-id="ccd89-124">Vea un vídeo sobre [cómo instalar y usar Visual Studio Code y .NET Core](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core/).</span><span class="sxs-lookup"><span data-stu-id="ccd89-124">Watch a video on [how to install and use Visual Studio Code and .NET Core](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core/).</span></span>

* <span data-ttu-id="ccd89-125">Vea un vídeo sobre [cómo instalar y usar Visual Studio 2017 y .NET Core](https://channel9.msdn.com/Blogs/dotnet/Get-Started-NET-Core-Visual-Studio-2017/).</span><span class="sxs-lookup"><span data-stu-id="ccd89-125">Watch a video on [how to install and use Visual Studio 2017 and .NET Core](https://channel9.msdn.com/Blogs/dotnet/Get-Started-NET-Core-Visual-Studio-2017/).</span></span>

* [<span data-ttu-id="ccd89-126">Introducción a .NET Core con la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="ccd89-126">Getting started with .NET Core using the command-line.</span></span>](tutorials/using-with-xplat-cli.md)

<span data-ttu-id="ccd89-127">Vea el artículo [Requisitos previos para .NET Core en Windows](windows-prerequisites.md) para obtener una lista de las versiones de Windows admitidas.</span><span class="sxs-lookup"><span data-stu-id="ccd89-127">See the [Prerequisites for Windows development](windows-prerequisites.md) article for a list of the supported Windows versions.</span></span>

# <a name="linuxtablinux"></a>[<span data-ttu-id="ccd89-128">Linux</span><span class="sxs-lookup"><span data-stu-id="ccd89-128">Linux</span></span>](#tab/linux)

<span data-ttu-id="ccd89-129">Para comenzar a desarrollar aplicaciones .NET Core, puede seguir estos tutoriales paso a paso.</span><span class="sxs-lookup"><span data-stu-id="ccd89-129">You can get started developing .NET Core application by following these step-by-step tutorials.</span></span>

* [<span data-ttu-id="ccd89-130">Introducción a .NET Core con la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="ccd89-130">Getting started with .NET Core using the command-line.</span></span>](tutorials/using-with-xplat-cli.md)

* <span data-ttu-id="ccd89-131">Vea un vídeo de [introducción a Visual Studio Code mediante C# y .NET Core en Ubuntu](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).</span><span class="sxs-lookup"><span data-stu-id="ccd89-131">Watch a video on [getting started with Visual Studio Code using C# and .NET Core on Ubuntu](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).</span></span>

<span data-ttu-id="ccd89-132">Vea el artículo [Requisitos previos para .NET Core en Linux](linux-prerequisites.md) para obtener una lista de las versiones y distribuciones de Linux admitidas.</span><span class="sxs-lookup"><span data-stu-id="ccd89-132">See the [Prerequisites for Linux development](linux-prerequisites.md) article for a list of the supported Linux distros and versions.</span></span>

# <a name="macostabmacos"></a>[<span data-ttu-id="ccd89-133">macOS</span><span class="sxs-lookup"><span data-stu-id="ccd89-133">macOS</span></span>](#tab/macos)

<span data-ttu-id="ccd89-134">Para comenzar a desarrollar aplicaciones .NET Core, puede seguir estos tutoriales paso a paso.</span><span class="sxs-lookup"><span data-stu-id="ccd89-134">You can get started developing .NET Core application by following these step-by-step tutorials.</span></span>

* <span data-ttu-id="ccd89-135">Vea un vídeo de [introducción a Visual Studio Code mediante C# y .NET Core en macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-VSCode-NET-Core-Mac).</span><span class="sxs-lookup"><span data-stu-id="ccd89-135">Watch a video on [Getting started with Visual Studio Code using C# and .NET Core on macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-VSCode-NET-Core-Mac).</span></span>

* [<span data-ttu-id="ccd89-136">Introducción a .NET Core en macOS con Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="ccd89-136">Getting started with .NET Core on macOS, using Visual Studio Code.</span></span>](tutorials/using-on-macos.md)

* [<span data-ttu-id="ccd89-137">Introducción a .NET Core con la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="ccd89-137">Getting started with .NET Core using the command-line.</span></span>](tutorials/using-with-xplat-cli.md)

* [<span data-ttu-id="ccd89-138">Introducción a .NET Core en macOS con Visual Studio para Mac.</span><span class="sxs-lookup"><span data-stu-id="ccd89-138">Getting started with .NET Core on macOS using Visual Studio for Mac.</span></span>](tutorials/using-on-mac-vs.md)

* [<span data-ttu-id="ccd89-139">Creación de una solución completa de .NET Core en macOS con Visual Studio para Mac.</span><span class="sxs-lookup"><span data-stu-id="ccd89-139">Build a complete .NET Core solution on macOS using Visual Studio for Mac.</span></span>](tutorials/using-on-mac-vs-full-solution.md)

<span data-ttu-id="ccd89-140">Vea el artículo [Requisitos previos para .NET Core en macOS](macos-prerequisites.md) para obtener una lista de las versiones de OS X y macOS admitidas.</span><span class="sxs-lookup"><span data-stu-id="ccd89-140">See the [Prerequisites for macOS development](macos-prerequisites.md) article for a list of the supported OS X / macOS versions.</span></span>

---
