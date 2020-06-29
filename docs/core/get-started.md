---
title: Introducción a .NET Core
description: Encuentre recursos para aprender a crear aplicaciones .NET Core en Windows, Linux y macOS.
author: adegeo
ms.author: adegeo
ms.date: 12/03/2019
ms.custom: vs-dotnet
ms.openlocfilehash: 5cfd9925f4ee93ef4ebe15ebf16febdfb98aaa9a
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325009"
---
# <a name="get-started-with-net-core"></a><span data-ttu-id="f3d0c-103">Introducción a .NET Core</span><span class="sxs-lookup"><span data-stu-id="f3d0c-103">Get started with .NET Core</span></span>

<span data-ttu-id="f3d0c-104">En este artículo se proporciona información sobre cómo comenzar con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f3d0c-104">This article provides information on getting started with .NET Core.</span></span> <span data-ttu-id="f3d0c-105">.NET Core se puede instalar en Windows, Linux y macOS.</span><span class="sxs-lookup"><span data-stu-id="f3d0c-105">.NET Core can be installed on Windows, Linux, and macOS.</span></span> <span data-ttu-id="f3d0c-106">Puede programar en su editor de texto preferido y crear aplicaciones y bibliotecas multiplataforma.</span><span class="sxs-lookup"><span data-stu-id="f3d0c-106">You can code in your favorite text editor and produce cross-platform libraries and applications.</span></span>

<span data-ttu-id="f3d0c-107">Si no está seguro de qué es .NET Core o cómo se relaciona con otras tecnologías .NET, comience con la información general [¿Qué es .NET?](https://dotnet.microsoft.com/learn/dotnet/what-is-dotnet).</span><span class="sxs-lookup"><span data-stu-id="f3d0c-107">If you're unsure what .NET Core is, or how it relates to other .NET technologies, start with the [What is .NET](https://dotnet.microsoft.com/learn/dotnet/what-is-dotnet) overview.</span></span> <span data-ttu-id="f3d0c-108">En resumen, .NET Core es una implementación multiplataforma de código abierto de .NET.</span><span class="sxs-lookup"><span data-stu-id="f3d0c-108">Put simply, .NET Core is an open-source, cross-platform implementation of .NET.</span></span>

## <a name="create-an-application"></a><span data-ttu-id="f3d0c-109">Crear una aplicación</span><span class="sxs-lookup"><span data-stu-id="f3d0c-109">Create an application</span></span>

<span data-ttu-id="f3d0c-110">En primer lugar, descargue e instale el [SDK de .NET Core](https://dotnet.microsoft.com/download) en el equipo.</span><span class="sxs-lookup"><span data-stu-id="f3d0c-110">First, download and install the [.NET Core SDK](https://dotnet.microsoft.com/download) on your computer.</span></span>

<span data-ttu-id="f3d0c-111">A continuación, abra un terminal como **PowerShell**, **Símbolo del sistema** o **bash**.</span><span class="sxs-lookup"><span data-stu-id="f3d0c-111">Next, open a terminal such as **PowerShell**, **Command Prompt**, or **bash**.</span></span> <span data-ttu-id="f3d0c-112">Escriba los comandos `dotnet` siguientes para crear y ejecutar una aplicación C#:</span><span class="sxs-lookup"><span data-stu-id="f3d0c-112">Type the following `dotnet` commands to create and run a C# application:</span></span>

```dotnetcli
dotnet new console --output sample1
dotnet run --project sample1
```

<span data-ttu-id="f3d0c-113">Debería ver los siguientes resultados:</span><span class="sxs-lookup"><span data-stu-id="f3d0c-113">You should see the following output:</span></span>

```console
Hello World!
```

<span data-ttu-id="f3d0c-114">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="f3d0c-114">Congratulations!</span></span> <span data-ttu-id="f3d0c-115">Ha creado una sencilla aplicación .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f3d0c-115">You've created a simple .NET Core application.</span></span> <span data-ttu-id="f3d0c-116">También puede usar [Visual Studio Code](./tutorials/with-visual-studio-code.md), [Visual Studio ](./tutorials/with-visual-studio.md) (solo Windows) o [Visual Studio para Mac](./tutorials/using-on-mac-vs.md) (solo macOS), para crear una aplicación .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f3d0c-116">You can also use [Visual Studio Code](./tutorials/with-visual-studio-code.md), [Visual Studio](./tutorials/with-visual-studio.md) (Windows only), or [Visual Studio for Mac](./tutorials/using-on-mac-vs.md) (macOS only), to create a .NET Core application.</span></span>

## <a name="tutorials"></a><span data-ttu-id="f3d0c-117">Tutoriales</span><span class="sxs-lookup"><span data-stu-id="f3d0c-117">Tutorials</span></span>

<span data-ttu-id="f3d0c-118">Para comenzar a desarrollar aplicaciones .NET Core, puede seguir estos tutoriales paso a paso:</span><span class="sxs-lookup"><span data-stu-id="f3d0c-118">Get started developing .NET Core applications by following these step-by-step tutorials:</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="windows"></a>[<span data-ttu-id="f3d0c-119">Windows</span><span class="sxs-lookup"><span data-stu-id="f3d0c-119">Windows</span></span>](#tab/windows)

- [<span data-ttu-id="f3d0c-120">Creación de su primera aplicación de consola con .NET Core en Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="f3d0c-120">Create your first .NET Core console application in Visual Studio 2019</span></span>](./tutorials/with-visual-studio.md)
- [<span data-ttu-id="f3d0c-121">Compilación de una biblioteca de clases con .NET Standard en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f3d0c-121">Build a class library with .NET Standard in Visual Studio</span></span>](./tutorials/library-with-visual-studio.md)
- [<span data-ttu-id="f3d0c-122">Introducción a .NET Core mediante la CLI de .NET Core</span><span class="sxs-lookup"><span data-stu-id="f3d0c-122">Get started with .NET Core using the .NET Core CLI</span></span>](./tutorials/cli-create-console-app.md)

|   |   |
|---|---|
| <span data-ttu-id="f3d0c-123">![icono de cámara de cine para vídeo](./media/video-icon.png "Ver un vídeo")</span><span class="sxs-lookup"><span data-stu-id="f3d0c-123">![movie camera icon for video](./media/video-icon.png "Watch a video")</span></span> | <span data-ttu-id="f3d0c-124">Vea el vídeo de Channel 9 sobre [cómo instalar y usar Visual Studio Code y .NET Core](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core/).</span><span class="sxs-lookup"><span data-stu-id="f3d0c-124">Watch the [how to install and use Visual Studio Code and .NET Core](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core/) video on Channel 9.</span></span> |
| <span data-ttu-id="f3d0c-125">![icono de cámara de cine para vídeo](./media/video-icon.png "Ver un vídeo")</span><span class="sxs-lookup"><span data-stu-id="f3d0c-125">![movie camera icon for video](./media/video-icon.png "Watch a video")</span></span> | <span data-ttu-id="f3d0c-126">Vea los vídeos [.NET Core 101](https://www.youtube.com/playlist?list=PLdo4fOcmZ0oWoazjhXQzBKMrFuArxpW80) en YouTube.</span><span class="sxs-lookup"><span data-stu-id="f3d0c-126">Watch the [.NET Core 101](https://www.youtube.com/playlist?list=PLdo4fOcmZ0oWoazjhXQzBKMrFuArxpW80) videos on YouTube.</span></span> |

<span data-ttu-id="f3d0c-127">Vea el artículo [Dependencias y requisitos de .NET Core](install/dependencies.md?pivots=os-windows) para obtener una lista de las versiones de Windows admitidas.</span><span class="sxs-lookup"><span data-stu-id="f3d0c-127">See the [.NET Core dependencies and requirements](install/dependencies.md?pivots=os-windows) article for a list of the supported Windows versions.</span></span>

# <a name="linux"></a>[<span data-ttu-id="f3d0c-128">Linux</span><span class="sxs-lookup"><span data-stu-id="f3d0c-128">Linux</span></span>](#tab/linux)

<span data-ttu-id="f3d0c-129">Para comenzar a desarrollar aplicaciones .NET Core, puede seguir estos tutoriales paso a paso:</span><span class="sxs-lookup"><span data-stu-id="f3d0c-129">Get started developing .NET Core applications by following these step-by-step tutorials:</span></span>

- [<span data-ttu-id="f3d0c-130">Introducción a .NET Core con la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="f3d0c-130">Get started with .NET Core using the command line</span></span>](./tutorials/cli-create-console-app.md)

|   |   |
|---|---|
| <span data-ttu-id="f3d0c-131">![icono de cámara de cine para vídeo](./media/video-icon.png "Ver un vídeo")</span><span class="sxs-lookup"><span data-stu-id="f3d0c-131">![movie camera icon for video](./media/video-icon.png "Watch a video")</span></span> | <span data-ttu-id="f3d0c-132">Vea un vídeo de [introducción a Visual Studio Code mediante C# y .NET Core en Ubuntu](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).</span><span class="sxs-lookup"><span data-stu-id="f3d0c-132">Watch a video on [getting started with Visual Studio Code using C# and .NET Core on Ubuntu](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).</span></span> |

<span data-ttu-id="f3d0c-133">Vea el artículo [Dependencias y requisitos de .NET Core](install/dependencies.md?pivots=os-linux) para obtener una lista de las distribuciones y las versiones de Linux admitidas.</span><span class="sxs-lookup"><span data-stu-id="f3d0c-133">See the [.NET Core dependencies and requirements](install/dependencies.md?pivots=os-linux) article for a list of the supported Linux distros and versions.</span></span>

# <a name="macos"></a>[<span data-ttu-id="f3d0c-134">macOS</span><span class="sxs-lookup"><span data-stu-id="f3d0c-134">macOS</span></span>](#tab/macos)

<span data-ttu-id="f3d0c-135">Para comenzar a desarrollar aplicaciones .NET Core, puede seguir estos tutoriales paso a paso:</span><span class="sxs-lookup"><span data-stu-id="f3d0c-135">Get started developing .NET Core applications by following these step-by-step tutorials:</span></span>

- [<span data-ttu-id="f3d0c-136">Introducción a .NET Core en macOS con Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="f3d0c-136">Get started with .NET Core on macOS using Visual Studio Code</span></span>](./tutorials/using-on-macos.md)
- [<span data-ttu-id="f3d0c-137">Introducción a .NET Core con la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="f3d0c-137">Get started with .NET Core using the command-line</span></span>](./tutorials/cli-create-console-app.md)
- [<span data-ttu-id="f3d0c-138">Introducción a .NET Core en macOS con Visual Studio para Mac</span><span class="sxs-lookup"><span data-stu-id="f3d0c-138">Get started with .NET Core on macOS using Visual Studio for Mac</span></span>](./tutorials/using-on-mac-vs.md)
- [<span data-ttu-id="f3d0c-139">Creación de una solución completa de .NET Core en macOS con Visual Studio para Mac</span><span class="sxs-lookup"><span data-stu-id="f3d0c-139">Build a complete .NET Core solution on macOS using Visual Studio for Mac</span></span>](./tutorials/using-on-mac-vs-full-solution.md)

|   |   |
|---|---|
| <span data-ttu-id="f3d0c-140">![icono de cámara de cine para vídeo](media/video-icon.png "Ver un vídeo")</span><span class="sxs-lookup"><span data-stu-id="f3d0c-140">![movie camera icon for video](media/video-icon.png "Watch a video")</span></span> | <span data-ttu-id="f3d0c-141">Vea un vídeo de [introducción a Visual Studio Code mediante C# y .NET Core en macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-VSCode-NET-Core-Mac).</span><span class="sxs-lookup"><span data-stu-id="f3d0c-141">Watch a video on [getting started with Visual Studio Code using C# and .NET Core on macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-VSCode-NET-Core-Mac).</span></span> |

<span data-ttu-id="f3d0c-142">Vea el artículo [Dependencias y requisitos de .NET Core](install/dependencies.md?pivots=os-macos) para obtener una lista de las versiones de OS X / macOS admitidas.</span><span class="sxs-lookup"><span data-stu-id="f3d0c-142">See the [.NET Core dependencies and requirements](install/dependencies.md?pivots=os-macos) article for a list of the supported OS X / macOS versions.</span></span>

---
