---
title: Introducción a .NET Core en macOS con Visual Studio para Mac
description: Este tema le guía en la creación de una aplicación de consola sencilla con Visual Studio para Mac y .NET Core.
author: guardrex
ms.date: 06/12/2017
ms.custom: seodec18
ms.openlocfilehash: d99cabf15be63593b272474867359324a5892b04
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59300884"
---
# <a name="get-started-with-net-core-on-macos-using-visual-studio-for-mac"></a><span data-ttu-id="6b06c-103">Introducción a .NET Core en macOS con Visual Studio para Mac</span><span class="sxs-lookup"><span data-stu-id="6b06c-103">Get started with .NET Core on macOS using Visual Studio for Mac</span></span>

<span data-ttu-id="6b06c-104">Visual Studio para Mac proporciona un entorno de desarrollo integrado (IDE) completo para el desarrollo de aplicaciones .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6b06c-104">Visual Studio for Mac provides a full-featured Integrated Development Environment (IDE) for developing .NET Core applications.</span></span> <span data-ttu-id="6b06c-105">Este tema le guía en la creación de una aplicación de consola sencilla con Visual Studio para Mac y .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6b06c-105">This topic walks you through building a simple console application using Visual Studio for Mac and .NET Core.</span></span>

> [!NOTE]
> <span data-ttu-id="6b06c-106">Sus comentarios son muy importantes.</span><span class="sxs-lookup"><span data-stu-id="6b06c-106">Your feedback is highly valued.</span></span> <span data-ttu-id="6b06c-107">Hay dos maneras de proporcionar comentarios al equipo de desarrollo de Visual Studio para Mac:</span><span class="sxs-lookup"><span data-stu-id="6b06c-107">There are two ways you can provide feedback to the development team on Visual Studio for Mac:</span></span>
> * <span data-ttu-id="6b06c-108">En Visual Studio para Mac, seleccione **Ayuda** > **Notificar un problema** en el menú o **Notificar un problema** desde la pantalla de bienvenida, que abre una ventana para presentar un informe de errores.</span><span class="sxs-lookup"><span data-stu-id="6b06c-108">In Visual Studio for Mac, select **Help** > **Report a Problem** from the menu or **Report a Problem** from the Welcome screen, which will open a window for filing a bug report.</span></span> <span data-ttu-id="6b06c-109">Puede realizar un seguimiento de sus comentarios en el portal de la [Comunidad de desarrolladores](https://developercommunity.visualstudio.com/spaces/8/index.html).</span><span class="sxs-lookup"><span data-stu-id="6b06c-109">You can track your feedback in the [Developer Community](https://developercommunity.visualstudio.com/spaces/8/index.html) portal.</span></span>
> * <span data-ttu-id="6b06c-110">Para hacer una sugerencia, seleccione **Ayuda** > **Aportar una sugerencia** en el menú o **Aportar una sugerencia** desde la pantalla de bienvenida, que le lleva a la [página web de la Comunidad de desarrolladores de Visual Studio para Mac](https://developercommunity.visualstudio.com/content/idea/post.html?space=41).</span><span class="sxs-lookup"><span data-stu-id="6b06c-110">To make a suggestion, select **Help** > **Provide a Suggestion** from the menu or **Provide a Suggestion** from the Welcome screen, which will take you to the [Visual Studio for Mac Developer Community webpage](https://developercommunity.visualstudio.com/content/idea/post.html?space=41).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6b06c-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="6b06c-111">Prerequisites</span></span>

<span data-ttu-id="6b06c-112">Vea el tema [Requisitos previos para .NET Core en Mac](../../core/macos-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="6b06c-112">See the [Prerequisites for .NET Core on Mac](../../core/macos-prerequisites.md) topic.</span></span>

## <a name="get-started"></a><span data-ttu-id="6b06c-113">Primeros pasos</span><span class="sxs-lookup"><span data-stu-id="6b06c-113">Get started</span></span>

<span data-ttu-id="6b06c-114">Si ya ha instalado los requisitos previos y Visual Studio para Mac, omita esta sección y proceda con [Creación de un proyecto](#creating-a-project).</span><span class="sxs-lookup"><span data-stu-id="6b06c-114">If you've already installed the prerequisites and Visual Studio for Mac, skip this section and proceed to [Creating a project](#creating-a-project).</span></span> <span data-ttu-id="6b06c-115">Siga estos pasos para instalar los requisitos previos y Visual Studio para Mac:</span><span class="sxs-lookup"><span data-stu-id="6b06c-115">Follow these steps to install the prerequisites and Visual Studio for Mac:</span></span>

<span data-ttu-id="6b06c-116">Descargue el [instalador de Visual Studio para Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).</span><span class="sxs-lookup"><span data-stu-id="6b06c-116">Download the [Visual Studio for Mac installer](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).</span></span> <span data-ttu-id="6b06c-117">Ejecute el instalador.</span><span class="sxs-lookup"><span data-stu-id="6b06c-117">Run the installer.</span></span> <span data-ttu-id="6b06c-118">Lea y acepte el contrato de licencia.</span><span class="sxs-lookup"><span data-stu-id="6b06c-118">Read and accept the license agreement.</span></span> <span data-ttu-id="6b06c-119">Durante la instalación, se les proporciona la oportunidad de instalar Xamarin, una tecnología de desarrollo de aplicaciones móviles multiplataforma.</span><span class="sxs-lookup"><span data-stu-id="6b06c-119">During the install, you're provided the opportunity to install Xamarin, a cross-platform mobile app development technology.</span></span> <span data-ttu-id="6b06c-120">La instalación de Xamarin y sus componentes relacionados es opcional para el desarrollo de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6b06c-120">Installing Xamarin and its related components is optional for .NET Core development.</span></span> <span data-ttu-id="6b06c-121">Para ver un tutorial del proceso de instalación de Visual Studio para Mac, consulte la [documentación de Visual Studio para Mac](/visualstudio/mac/).</span><span class="sxs-lookup"><span data-stu-id="6b06c-121">For a walk-through of the Visual Studio for Mac install process, see [Visual Studio for Mac documentation](/visualstudio/mac/).</span></span> <span data-ttu-id="6b06c-122">Una vez completada la instalación, inicie el IDE de Visual Studio para Mac.</span><span class="sxs-lookup"><span data-stu-id="6b06c-122">When the install is complete, start the Visual Studio for Mac IDE.</span></span>

## <a name="creating-a-project"></a><span data-ttu-id="6b06c-123">Creación de un proyecto</span><span class="sxs-lookup"><span data-stu-id="6b06c-123">Creating a project</span></span>

1. <span data-ttu-id="6b06c-124">Seleccione **Nuevo proyecto** en la pantalla de bienvenida.</span><span class="sxs-lookup"><span data-stu-id="6b06c-124">Select **New Project** on the Welcome screen.</span></span>

   ![Botón Nuevo proyecto en la pantalla de bienvenida de Visual Studio para Mac](./media/using-on-mac-vs/visual-studio-mac-new-project.png)

1. <span data-ttu-id="6b06c-126">En el cuadro de diálogo **Nuevo proyecto**, seleccione **Aplicación** en el nodo **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="6b06c-126">In the **New Project** dialog, select **App** under the **.NET Core** node.</span></span> <span data-ttu-id="6b06c-127">Seleccione la plantilla **Aplicación de consola** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6b06c-127">Select the **Console Application** template followed by **Next**.</span></span>

   ![Lista de plantillas de Nuevo proyecto](./media/using-on-mac-vs/visual-studio-mac-new-dialog.png)

1. <span data-ttu-id="6b06c-129">Escriba "HelloWorld" en **Nombre de proyecto**.</span><span class="sxs-lookup"><span data-stu-id="6b06c-129">Type "HelloWorld" for the **Project Name**.</span></span> <span data-ttu-id="6b06c-130">Seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="6b06c-130">Select **Create**.</span></span>

   ![Configuración del cuadro de diálogo de nueva aplicación de consola](./media/using-on-mac-vs/visual-studio-mac-new-options.png)

1. <span data-ttu-id="6b06c-132">Espere mientras se restauran las dependencias del proyecto.</span><span class="sxs-lookup"><span data-stu-id="6b06c-132">Wait while the project's dependencies are restored.</span></span> <span data-ttu-id="6b06c-133">El proyecto tiene un único archivo de C#, *Program.cs*, que contiene una clase `Program` con un método `Main`.</span><span class="sxs-lookup"><span data-stu-id="6b06c-133">The project has a single C# file, *Program.cs*, containing a `Program` class with a `Main` method.</span></span> <span data-ttu-id="6b06c-134">La instrucción `Console.WriteLine` genera la salida "¡Hola a todos!"</span><span class="sxs-lookup"><span data-stu-id="6b06c-134">The `Console.WriteLine` statement will output "Hello World!"</span></span> <span data-ttu-id="6b06c-135">en la consola cuando se ejecuta la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6b06c-135">to the console when the app is run.</span></span>

   ![Ventana principal con el archivo Program.cs abierto](./media/using-on-mac-vs/visual-studio-mac-editor.png)

## <a name="run-the-application"></a><span data-ttu-id="6b06c-137">Ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="6b06c-137">Run the application</span></span>

<span data-ttu-id="6b06c-138">Ejecute la aplicación en modo de depuración mediante <kbd>F5</kbd> o en modo de versión mediante <kbd>CTRL</kbd>+<kbd>F5</kbd>.</span><span class="sxs-lookup"><span data-stu-id="6b06c-138">Run the app in Debug mode using <kbd>F5</kbd> or in Release mode using <kbd>CTRL</kbd>+<kbd>F5</kbd>.</span></span>

![El panel de salida de la aplicación muestra ¡Hola a todos!](./media/using-on-mac-vs/visual-studio-mac-output.png)

## <a name="next-step"></a><span data-ttu-id="6b06c-140">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="6b06c-140">Next step</span></span>

<span data-ttu-id="6b06c-141">El tema [Creación de una solución completa de .NET Core en macOS con Visual Studio para Mac](using-on-mac-vs-full-solution.md) le muestra cómo crear una solución completa de .NET Core que incluye una biblioteca reutilizable y pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="6b06c-141">The [Building a complete .NET Core solution on macOS using Visual Studio for Mac](using-on-mac-vs-full-solution.md) topic shows you how to build a complete .NET Core solution that includes a reusable library and unit testing.</span></span>
