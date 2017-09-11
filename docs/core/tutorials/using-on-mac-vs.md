---
title: "Introducción a .NET Core en macOS con Visual Studio para Mac"
description: "Este tema le guía en la creación de una aplicación de consola sencilla con Visual Studio para Mac y .NET Core."
keywords: .NET, .NET Core, macOS, Mac
author: guardrex
ms.author: mairaw
ms.date: 06/12/2017
ms.topic: get-started-article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 8902e849-dd17-42c0-8264-cc7ae3927a0c
ms.translationtype: HT
ms.sourcegitcommit: fd165e8745e78c76dc233540575fac841eda37aa
ms.openlocfilehash: 893999f9abcc299da4fb0923fe47c371079f695c
ms.contentlocale: es-es
ms.lasthandoff: 08/24/2017

---

# <a name="getting-started-with-net-core-on-macos-using-visual-studio-for-mac"></a><span data-ttu-id="1f292-104">Introducción a .NET Core en macOS con Visual Studio para Mac</span><span class="sxs-lookup"><span data-stu-id="1f292-104">Getting started with .NET Core on macOS using Visual Studio for Mac</span></span>

<span data-ttu-id="1f292-105">Visual Studio para Mac proporciona un entorno de desarrollo integrado (IDE) completo para el desarrollo de aplicaciones .NET Core.</span><span class="sxs-lookup"><span data-stu-id="1f292-105">Visual Studio for Mac provides a full-featured Integrated Development Environment (IDE) for developing .NET Core applications.</span></span> <span data-ttu-id="1f292-106">Este tema le guía en la creación de una aplicación de consola sencilla con Visual Studio para Mac y .NET Core.</span><span class="sxs-lookup"><span data-stu-id="1f292-106">This topic walks you through building a simple console application using Visual Studio for Mac and .NET Core.</span></span>

> [!NOTE]
> <span data-ttu-id="1f292-107">Sus comentarios son muy importantes.</span><span class="sxs-lookup"><span data-stu-id="1f292-107">Your feedback is highly valued.</span></span> <span data-ttu-id="1f292-108">Hay dos maneras de proporcionar comentarios al equipo de desarrollo de Visual Studio para Mac:</span><span class="sxs-lookup"><span data-stu-id="1f292-108">There are a two ways you can provide feedback to the development team on Visual Studio for Mac:</span></span>
> * <span data-ttu-id="1f292-109">En Visual Studio para Mac, seleccione **Ayuda** > **Notificar un problema** en el menú o **Notificar un problema** desde la pantalla de bienvenida, que abre una ventana para presentar un informe de errores.</span><span class="sxs-lookup"><span data-stu-id="1f292-109">In Visual Studio for Mac, select **Help** > **Report a Problem** from the menu or **Report a Problem** from the Welcome screen, which will open a window for filing a bug report.</span></span> <span data-ttu-id="1f292-110">Puede realizar un seguimiento de sus comentarios en el portal de la [Comunidad de desarrolladores](https://developercommunity.visualstudio.com/spaces/8/index.html).</span><span class="sxs-lookup"><span data-stu-id="1f292-110">You can track your feedback in the [Developer Community](https://developercommunity.visualstudio.com/spaces/8/index.html) portal.</span></span>
> * <span data-ttu-id="1f292-111">Para hacer una sugerencia, seleccione **Ayuda** > **Aportar una sugerencia** en el menú o **Aportar una sugerencia** desde la pantalla de bienvenida, que le lleva a la [página web de UserVoice de Visual Studio para Mac](https://visualstudio.uservoice.com/forums/563332-visual-studio-for-mac).</span><span class="sxs-lookup"><span data-stu-id="1f292-111">To make a suggestion, select **Help** > **Provide a Suggestion** from the menu or **Provide a Suggestion** from the Welcome screen, which will take you to the [Visual Studio for Mac UserVoice webpage](https://visualstudio.uservoice.com/forums/563332-visual-studio-for-mac).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1f292-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="1f292-112">Prerequisites</span></span>

<span data-ttu-id="1f292-113">Vea el tema [Requisitos previos para .NET Core en Mac](../../core/macos-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="1f292-113">See the [Prerequisites for .NET Core on Mac](../../core/macos-prerequisites.md) topic.</span></span>

## <a name="getting-started"></a><span data-ttu-id="1f292-114">Introducción</span><span class="sxs-lookup"><span data-stu-id="1f292-114">Getting started</span></span>

<span data-ttu-id="1f292-115">Si ya ha instalado los requisitos previos y Visual Studio para Mac, omita esta sección y proceda con [Creación de un proyecto](#creating-a-project).</span><span class="sxs-lookup"><span data-stu-id="1f292-115">If you've already installed the prerequisites and Visual Studio for Mac, skip this section and proceed to [Creating a project](#creating-a-project).</span></span> <span data-ttu-id="1f292-116">Siga estos pasos para instalar los requisitos previos y Visual Studio para Mac:</span><span class="sxs-lookup"><span data-stu-id="1f292-116">Follow these steps to install the prerequisites and Visual Studio for Mac:</span></span>

<span data-ttu-id="1f292-117">Descargue el [instalador de Visual Studio para Mac](https://www.visualstudio.com/vs/visual-studio-mac/).</span><span class="sxs-lookup"><span data-stu-id="1f292-117">Download the [Visual Studio for Mac installer](https://www.visualstudio.com/vs/visual-studio-mac/).</span></span> <span data-ttu-id="1f292-118">Ejecute el instalador.</span><span class="sxs-lookup"><span data-stu-id="1f292-118">Run the installer.</span></span> <span data-ttu-id="1f292-119">Lea y acepte el contrato de licencia.</span><span class="sxs-lookup"><span data-stu-id="1f292-119">Read and accept the license agreement.</span></span> <span data-ttu-id="1f292-120">Durante la instalación, se les proporciona la oportunidad de instalar Xamarin, una tecnología de desarrollo de aplicaciones móviles multiplataforma.</span><span class="sxs-lookup"><span data-stu-id="1f292-120">During the install, you're provided the opportunity to install Xamarin, a cross-platform mobile app development technology.</span></span> <span data-ttu-id="1f292-121">La instalación de Xamarin y sus componentes relacionados es opcional para el desarrollo de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="1f292-121">Installing Xamarin and its related components is optional for .NET Core development.</span></span> <span data-ttu-id="1f292-122">Para ver un tutorial del proceso de instalación de Visual Studio para Mac, consulte [Introducing Visual Studio for Mac](https://developer.xamarin.com/guides/cross-platform/visual-studio-mac/) (Introducción a Visual Studio para Mac).</span><span class="sxs-lookup"><span data-stu-id="1f292-122">For a walk-through of the Visual Studio for Mac install process, see [Introducing Visual Studio for Mac](https://developer.xamarin.com/guides/cross-platform/visual-studio-mac/).</span></span> <span data-ttu-id="1f292-123">Una vez completada la instalación, inicie el IDE de Visual Studio para Mac.</span><span class="sxs-lookup"><span data-stu-id="1f292-123">When the install is complete, start the Visual Studio for Mac IDE.</span></span>

## <a name="creating-a-project"></a><span data-ttu-id="1f292-124">Creación de un proyecto</span><span class="sxs-lookup"><span data-stu-id="1f292-124">Creating a project</span></span>

1. <span data-ttu-id="1f292-125">Seleccione **Nuevo proyecto** en la pantalla de bienvenida.</span><span class="sxs-lookup"><span data-stu-id="1f292-125">Select **New Project** on the Welcome screen.</span></span>

   ![Botón Nuevo proyecto en la pantalla de bienvenida de Visual Studio para Mac](./media/using-on-mac-vs/vsmac1.png)

1. <span data-ttu-id="1f292-127">En el cuadro de diálogo **Nuevo proyecto**, seleccione **Aplicación** en el nodo **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="1f292-127">In the **New Project** dialog, select **App** under the **.NET Core** node.</span></span> <span data-ttu-id="1f292-128">Seleccione la plantilla **Aplicación de consola** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1f292-128">Select the **Console Application** template followed by **Next**.</span></span>

   ![Lista de plantillas de Nuevo proyecto](./media/using-on-mac-vs/vsmac2.png)

1. <span data-ttu-id="1f292-130">Escriba "HelloWorld" en **Nombre de proyecto**.</span><span class="sxs-lookup"><span data-stu-id="1f292-130">Type "HelloWorld" for the **Project Name**.</span></span> <span data-ttu-id="1f292-131">Seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="1f292-131">Select **Create**.</span></span>

   ![Configuración del cuadro de diálogo de nueva aplicación de consola](./media/using-on-mac-vs/vsmac3.png)

1. <span data-ttu-id="1f292-133">Espere mientras se restauran las dependencias del proyecto.</span><span class="sxs-lookup"><span data-stu-id="1f292-133">Wait while the project's dependencies are restored.</span></span> <span data-ttu-id="1f292-134">El proyecto tiene un único archivo de C#, *Program.cs*, que contiene una clase `Program` con un método `Main`.</span><span class="sxs-lookup"><span data-stu-id="1f292-134">The project has a single C# file, *Program.cs*, containing a `Program` class with a `Main` method.</span></span> <span data-ttu-id="1f292-135">La instrucción `Console.WriteLine` genera la salida "¡Hola a todos!"</span><span class="sxs-lookup"><span data-stu-id="1f292-135">The `Console.WriteLine` statement will output "Hello World!"</span></span> <span data-ttu-id="1f292-136">en la consola cuando se ejecuta la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1f292-136">to the console when the app is run.</span></span>

   ![Ventana principal con el archivo Program.cs abierto](./media/using-on-mac-vs/vsmac4.png)

## <a name="run-the-application"></a><span data-ttu-id="1f292-138">Ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="1f292-138">Run the application</span></span>

<span data-ttu-id="1f292-139">Ejecute la aplicación en modo de depuración mediante <kbd>F5</kbd> o en modo de versión mediante <kbd>CTRL</kbd>+<kbd>F5</kbd>.</span><span class="sxs-lookup"><span data-stu-id="1f292-139">Run the app in Debug mode using <kbd>F5</kbd> or in Release mode using <kbd>CTRL</kbd>+<kbd>F5</kbd>.</span></span>

![El panel de salida de la aplicación muestra ¡Hola a todos!](./media/using-on-mac-vs/vsmac5.png)

## <a name="next-step"></a><span data-ttu-id="1f292-141">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="1f292-141">Next step</span></span>

<span data-ttu-id="1f292-142">El tema [Creación de una solución completa de .NET Core en macOS con Visual Studio para Mac](using-on-mac-vs-full-solution.md) le muestra cómo crear una solución completa de .NET Core que incluye una biblioteca reutilizable y pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="1f292-142">The [Building a complete .NET Core solution on macOS using Visual Studio for Mac](using-on-mac-vs-full-solution.md) topic shows you how to build a complete .NET Core solution that includes a reusable library and unit testing.</span></span>

