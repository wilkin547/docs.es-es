---
title: Introducción a .NET Core en macOS con Visual Studio para Mac
description: Este tema le guía en la creación de una aplicación de consola sencilla con Visual Studio para Mac y .NET Core.
author: guardrex
ms.author: mairaw
ms.date: 06/12/2017
ms.openlocfilehash: dd8262a7d2fa03ab06f9f85e91c298f52e3c0849
ms.sourcegitcommit: c217b067985905cb21eafc5dd9a83568d7ff4e45
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/22/2018
ms.locfileid: "36315152"
---
# <a name="getting-started-with-net-core-on-macos-using-visual-studio-for-mac"></a><span data-ttu-id="acad7-103">Introducción a .NET Core en macOS con Visual Studio para Mac</span><span class="sxs-lookup"><span data-stu-id="acad7-103">Getting started with .NET Core on macOS using Visual Studio for Mac</span></span>

<span data-ttu-id="acad7-104">Visual Studio para Mac proporciona un entorno de desarrollo integrado (IDE) completo para el desarrollo de aplicaciones .NET Core.</span><span class="sxs-lookup"><span data-stu-id="acad7-104">Visual Studio for Mac provides a full-featured Integrated Development Environment (IDE) for developing .NET Core applications.</span></span> <span data-ttu-id="acad7-105">Este tema le guía en la creación de una aplicación de consola sencilla con Visual Studio para Mac y .NET Core.</span><span class="sxs-lookup"><span data-stu-id="acad7-105">This topic walks you through building a simple console application using Visual Studio for Mac and .NET Core.</span></span>

> [!NOTE]
> <span data-ttu-id="acad7-106">Sus comentarios son muy importantes.</span><span class="sxs-lookup"><span data-stu-id="acad7-106">Your feedback is highly valued.</span></span> <span data-ttu-id="acad7-107">Hay dos maneras de proporcionar comentarios al equipo de desarrollo de Visual Studio para Mac:</span><span class="sxs-lookup"><span data-stu-id="acad7-107">There are a two ways you can provide feedback to the development team on Visual Studio for Mac:</span></span>
> * <span data-ttu-id="acad7-108">En Visual Studio para Mac, seleccione **Ayuda** > **Notificar un problema** en el menú o **Notificar un problema** desde la pantalla de bienvenida, que abre una ventana para presentar un informe de errores.</span><span class="sxs-lookup"><span data-stu-id="acad7-108">In Visual Studio for Mac, select **Help** > **Report a Problem** from the menu or **Report a Problem** from the Welcome screen, which will open a window for filing a bug report.</span></span> <span data-ttu-id="acad7-109">Puede realizar un seguimiento de sus comentarios en el portal de la [Comunidad de desarrolladores](https://developercommunity.visualstudio.com/spaces/8/index.html).</span><span class="sxs-lookup"><span data-stu-id="acad7-109">You can track your feedback in the [Developer Community](https://developercommunity.visualstudio.com/spaces/8/index.html) portal.</span></span>
> * <span data-ttu-id="acad7-110">Para hacer una sugerencia, seleccione **Ayuda** > **Aportar una sugerencia** en el menú o **Aportar una sugerencia** desde la pantalla de bienvenida, que le lleva a la [página web de UserVoice de Visual Studio para Mac](https://visualstudio.uservoice.com/forums/563332-visual-studio-for-mac).</span><span class="sxs-lookup"><span data-stu-id="acad7-110">To make a suggestion, select **Help** > **Provide a Suggestion** from the menu or **Provide a Suggestion** from the Welcome screen, which will take you to the [Visual Studio for Mac UserVoice webpage](https://visualstudio.uservoice.com/forums/563332-visual-studio-for-mac).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="acad7-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="acad7-111">Prerequisites</span></span>

<span data-ttu-id="acad7-112">Vea el tema [Requisitos previos para .NET Core en Mac](../../core/macos-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="acad7-112">See the [Prerequisites for .NET Core on Mac](../../core/macos-prerequisites.md) topic.</span></span>

## <a name="getting-started"></a><span data-ttu-id="acad7-113">Introducción</span><span class="sxs-lookup"><span data-stu-id="acad7-113">Getting started</span></span>

<span data-ttu-id="acad7-114">Si ya ha instalado los requisitos previos y Visual Studio para Mac, omita esta sección y proceda con [Creación de un proyecto](#creating-a-project).</span><span class="sxs-lookup"><span data-stu-id="acad7-114">If you've already installed the prerequisites and Visual Studio for Mac, skip this section and proceed to [Creating a project](#creating-a-project).</span></span> <span data-ttu-id="acad7-115">Siga estos pasos para instalar los requisitos previos y Visual Studio para Mac:</span><span class="sxs-lookup"><span data-stu-id="acad7-115">Follow these steps to install the prerequisites and Visual Studio for Mac:</span></span>

<span data-ttu-id="acad7-116">Descargue el [instalador de Visual Studio para Mac](https://visualstudio.microsoft.com/vs/visual-studio-mac/).</span><span class="sxs-lookup"><span data-stu-id="acad7-116">Download the [Visual Studio for Mac installer](https://visualstudio.microsoft.com/vs/visual-studio-mac/).</span></span> <span data-ttu-id="acad7-117">Ejecute el instalador.</span><span class="sxs-lookup"><span data-stu-id="acad7-117">Run the installer.</span></span> <span data-ttu-id="acad7-118">Lea y acepte el contrato de licencia.</span><span class="sxs-lookup"><span data-stu-id="acad7-118">Read and accept the license agreement.</span></span> <span data-ttu-id="acad7-119">Durante la instalación, se les proporciona la oportunidad de instalar Xamarin, una tecnología de desarrollo de aplicaciones móviles multiplataforma.</span><span class="sxs-lookup"><span data-stu-id="acad7-119">During the install, you're provided the opportunity to install Xamarin, a cross-platform mobile app development technology.</span></span> <span data-ttu-id="acad7-120">La instalación de Xamarin y sus componentes relacionados es opcional para el desarrollo de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="acad7-120">Installing Xamarin and its related components is optional for .NET Core development.</span></span> <span data-ttu-id="acad7-121">Para ver un tutorial del proceso de instalación de Visual Studio para Mac, consulte [Introducing Visual Studio for Mac](https://developer.xamarin.com/guides/cross-platform/visual-studio-mac/) (Introducción a Visual Studio para Mac).</span><span class="sxs-lookup"><span data-stu-id="acad7-121">For a walk-through of the Visual Studio for Mac install process, see [Introducing Visual Studio for Mac](https://developer.xamarin.com/guides/cross-platform/visual-studio-mac/).</span></span> <span data-ttu-id="acad7-122">Una vez completada la instalación, inicie el IDE de Visual Studio para Mac.</span><span class="sxs-lookup"><span data-stu-id="acad7-122">When the install is complete, start the Visual Studio for Mac IDE.</span></span>

## <a name="creating-a-project"></a><span data-ttu-id="acad7-123">Creación de un proyecto</span><span class="sxs-lookup"><span data-stu-id="acad7-123">Creating a project</span></span>

1. <span data-ttu-id="acad7-124">Seleccione **Nuevo proyecto** en la pantalla de bienvenida.</span><span class="sxs-lookup"><span data-stu-id="acad7-124">Select **New Project** on the Welcome screen.</span></span>

   ![Botón Nuevo proyecto en la pantalla de bienvenida de Visual Studio para Mac](./media/using-on-mac-vs/vsmac1.png)

1. <span data-ttu-id="acad7-126">En el cuadro de diálogo **Nuevo proyecto**, seleccione **Aplicación** en el nodo **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="acad7-126">In the **New Project** dialog, select **App** under the **.NET Core** node.</span></span> <span data-ttu-id="acad7-127">Seleccione la plantilla **Aplicación de consola** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="acad7-127">Select the **Console Application** template followed by **Next**.</span></span>

   ![Lista de plantillas de Nuevo proyecto](./media/using-on-mac-vs/vsmac2.png)

1. <span data-ttu-id="acad7-129">Escriba "HelloWorld" en **Nombre de proyecto**.</span><span class="sxs-lookup"><span data-stu-id="acad7-129">Type "HelloWorld" for the **Project Name**.</span></span> <span data-ttu-id="acad7-130">Seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="acad7-130">Select **Create**.</span></span>

   ![Configuración del cuadro de diálogo de nueva aplicación de consola](./media/using-on-mac-vs/vsmac3.png)

1. <span data-ttu-id="acad7-132">Espere mientras se restauran las dependencias del proyecto.</span><span class="sxs-lookup"><span data-stu-id="acad7-132">Wait while the project's dependencies are restored.</span></span> <span data-ttu-id="acad7-133">El proyecto tiene un único archivo de C#, *Program.cs*, que contiene una clase `Program` con un método `Main`.</span><span class="sxs-lookup"><span data-stu-id="acad7-133">The project has a single C# file, *Program.cs*, containing a `Program` class with a `Main` method.</span></span> <span data-ttu-id="acad7-134">La instrucción `Console.WriteLine` genera la salida "¡Hola a todos!"</span><span class="sxs-lookup"><span data-stu-id="acad7-134">The `Console.WriteLine` statement will output "Hello World!"</span></span> <span data-ttu-id="acad7-135">en la consola cuando se ejecuta la aplicación.</span><span class="sxs-lookup"><span data-stu-id="acad7-135">to the console when the app is run.</span></span>

   ![Ventana principal con el archivo Program.cs abierto](./media/using-on-mac-vs/vsmac4.png)

## <a name="run-the-application"></a><span data-ttu-id="acad7-137">Ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="acad7-137">Run the application</span></span>

<span data-ttu-id="acad7-138">Ejecute la aplicación en modo de depuración mediante <kbd>F5</kbd> o en modo de versión mediante <kbd>CTRL</kbd>+<kbd>F5</kbd>.</span><span class="sxs-lookup"><span data-stu-id="acad7-138">Run the app in Debug mode using <kbd>F5</kbd> or in Release mode using <kbd>CTRL</kbd>+<kbd>F5</kbd>.</span></span>

![El panel de salida de la aplicación muestra ¡Hola a todos!](./media/using-on-mac-vs/vsmac5.png)

## <a name="next-step"></a><span data-ttu-id="acad7-140">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="acad7-140">Next step</span></span>

<span data-ttu-id="acad7-141">El tema [Creación de una solución completa de .NET Core en macOS con Visual Studio para Mac](using-on-mac-vs-full-solution.md) le muestra cómo crear una solución completa de .NET Core que incluye una biblioteca reutilizable y pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="acad7-141">The [Building a complete .NET Core solution on macOS using Visual Studio for Mac](using-on-mac-vs-full-solution.md) topic shows you how to build a complete .NET Core solution that includes a reusable library and unit testing.</span></span>
