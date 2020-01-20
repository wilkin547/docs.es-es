---
title: Introducción a .NET Core con Visual Studio para Mac
description: Este tema le guía en la creación de una aplicación de consola sencilla con Visual Studio para Mac y .NET Core.
ms.date: 12/19/2019
ms.openlocfilehash: 4cd7e311411bce62698e291e763227496877ea39
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740495"
---
# <a name="get-started-with-net-core-on-macos-using-visual-studio-for-mac"></a><span data-ttu-id="991d0-103">Introducción a .NET Core en macOS con Visual Studio para Mac</span><span class="sxs-lookup"><span data-stu-id="991d0-103">Get started with .NET Core on macOS using Visual Studio for Mac</span></span>

<span data-ttu-id="991d0-104">Visual Studio para Mac proporciona un entorno de desarrollo integrado (IDE) completo para el desarrollo de aplicaciones .NET Core.</span><span class="sxs-lookup"><span data-stu-id="991d0-104">Visual Studio for Mac provides a full-featured Integrated Development Environment (IDE) for developing .NET Core applications.</span></span> <span data-ttu-id="991d0-105">Este artículo le guía en la creación de una aplicación de consola sencilla con Visual Studio para Mac y .NET Core.</span><span class="sxs-lookup"><span data-stu-id="991d0-105">This article walks you through building a simple console application using Visual Studio for Mac and .NET Core.</span></span>

> [!NOTE]
> <span data-ttu-id="991d0-106">Sus comentarios son muy importantes.</span><span class="sxs-lookup"><span data-stu-id="991d0-106">Your feedback is highly valued.</span></span> <span data-ttu-id="991d0-107">Hay dos maneras de proporcionar comentarios al equipo de desarrollo de Visual Studio para Mac:</span><span class="sxs-lookup"><span data-stu-id="991d0-107">There are two ways you can provide feedback to the development team on Visual Studio for Mac:</span></span>
>
> * <span data-ttu-id="991d0-108">En Visual Studio para Mac, seleccione **Ayuda** > **Notificar un problema** en el menú o **Notificar un problema** desde la pantalla de bienvenida, que abre una ventana para presentar un informe de errores.</span><span class="sxs-lookup"><span data-stu-id="991d0-108">In Visual Studio for Mac, select **Help** > **Report a Problem** from the menu or **Report a Problem** from the Welcome screen, which will open a window for filing a bug report.</span></span> <span data-ttu-id="991d0-109">Puede realizar un seguimiento de sus comentarios en el portal de la [Comunidad de desarrolladores](https://developercommunity.visualstudio.com/spaces/8/index.html).</span><span class="sxs-lookup"><span data-stu-id="991d0-109">You can track your feedback in the [Developer Community](https://developercommunity.visualstudio.com/spaces/8/index.html) portal.</span></span>
> * <span data-ttu-id="991d0-110">Para hacer una sugerencia, seleccione **Ayuda** > **Aportar una sugerencia** en el menú o **Aportar una sugerencia** desde la pantalla de bienvenida, que le lleva a la [página web de la Comunidad de desarrolladores de Visual Studio para Mac](https://developercommunity.visualstudio.com/content/idea/post.html?space=41).</span><span class="sxs-lookup"><span data-stu-id="991d0-110">To make a suggestion, select **Help** > **Provide a Suggestion** from the menu or **Provide a Suggestion** from the Welcome screen, which will take you to the [Visual Studio for Mac Developer Community webpage](https://developercommunity.visualstudio.com/content/idea/post.html?space=41).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="991d0-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="991d0-111">Prerequisites</span></span>

<span data-ttu-id="991d0-112">Consulte el artículo [Dependencias y requisitos de .NET Core](../install/dependencies.md?pivots=os-macos).</span><span class="sxs-lookup"><span data-stu-id="991d0-112">See the [.NET Core dependencies and requirements](../install/dependencies.md?pivots=os-macos) article.</span></span>

<span data-ttu-id="991d0-113">Consulte el artículo [Compatibilidad de .NET Core](/visualstudio/mac/net-core-support) para asegurarse de que usa una versión compatible de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="991d0-113">Check the [.NET Core Support](/visualstudio/mac/net-core-support) article to ensure you're using a supported version of .NET Core.</span></span>

## <a name="get-started"></a><span data-ttu-id="991d0-114">Primeros pasos</span><span class="sxs-lookup"><span data-stu-id="991d0-114">Get started</span></span>

<span data-ttu-id="991d0-115">Si ya ha instalado los requisitos previos y Visual Studio para Mac, omita esta sección y proceda con [Creación de un proyecto](#creating-a-project).</span><span class="sxs-lookup"><span data-stu-id="991d0-115">If you've already installed the prerequisites and Visual Studio for Mac, skip this section and proceed to [Creating a project](#creating-a-project).</span></span> <span data-ttu-id="991d0-116">Siga estos pasos para instalar los requisitos previos y Visual Studio para Mac:</span><span class="sxs-lookup"><span data-stu-id="991d0-116">Follow these steps to install the prerequisites and Visual Studio for Mac:</span></span>

<span data-ttu-id="991d0-117">Descargue el [instalador de Visual Studio para Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).</span><span class="sxs-lookup"><span data-stu-id="991d0-117">Download the [Visual Studio for Mac installer](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).</span></span> <span data-ttu-id="991d0-118">Ejecute el instalador.</span><span class="sxs-lookup"><span data-stu-id="991d0-118">Run the installer.</span></span> <span data-ttu-id="991d0-119">Lea y acepte el contrato de licencia.</span><span class="sxs-lookup"><span data-stu-id="991d0-119">Read and accept the license agreement.</span></span> <span data-ttu-id="991d0-120">Durante la instalación, seleccione la opción de instalar .NET Core.</span><span class="sxs-lookup"><span data-stu-id="991d0-120">During the install, select the option to install .NET Core.</span></span> <span data-ttu-id="991d0-121">Se le proporciona la oportunidad de instalar Xamarin, una tecnología de desarrollo de aplicaciones móviles multiplataforma.</span><span class="sxs-lookup"><span data-stu-id="991d0-121">You're provided the opportunity to install Xamarin, a cross-platform mobile app development technology.</span></span> <span data-ttu-id="991d0-122">La instalación de Xamarin y sus componentes relacionados es opcional para el desarrollo de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="991d0-122">Installing Xamarin and its related components is optional for .NET Core development.</span></span> <span data-ttu-id="991d0-123">Para ver un tutorial del proceso de instalación de Visual Studio para Mac, consulte la [documentación de Visual Studio para Mac](/visualstudio/mac/).</span><span class="sxs-lookup"><span data-stu-id="991d0-123">For a walk-through of the Visual Studio for Mac install process, see [Visual Studio for Mac documentation](/visualstudio/mac/).</span></span> <span data-ttu-id="991d0-124">Una vez completada la instalación, inicie el IDE de Visual Studio para Mac.</span><span class="sxs-lookup"><span data-stu-id="991d0-124">When the install is complete, start the Visual Studio for Mac IDE.</span></span>

## <a name="creating-a-project"></a><span data-ttu-id="991d0-125">Creación de un proyecto</span><span class="sxs-lookup"><span data-stu-id="991d0-125">Creating a project</span></span>

1. <span data-ttu-id="991d0-126">Seleccione **Nuevo** en la ventana de inicio.</span><span class="sxs-lookup"><span data-stu-id="991d0-126">Select **New** on the start window.</span></span>

   ![Botón Nuevo en la pantalla Inicio de Visual Studio para Mac](./media/using-on-mac-vs/visual-studio-mac-new-project.png)

1. <span data-ttu-id="991d0-128">En el cuadro de diálogo **Nuevo proyecto**, seleccione **Aplicación** en el nodo **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="991d0-128">In the **New Project** dialog, select **App** under the **.NET Core** node.</span></span> <span data-ttu-id="991d0-129">Seleccione la plantilla **Aplicación de consola** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="991d0-129">Select the **Console Application** template followed by **Next**.</span></span>

   ![Lista de plantillas de Nuevo proyecto](./media/using-on-mac-vs/visual-studio-mac-new-dialog.png)

1. <span data-ttu-id="991d0-131">Si tiene instalada más de una versión de .NET Core, seleccione el marco de destino del proyecto.</span><span class="sxs-lookup"><span data-stu-id="991d0-131">If you have more than one version of .NET Core installed, select the target framework for your project.</span></span>

1. <span data-ttu-id="991d0-132">Escriba "HelloWorld" en **Nombre de proyecto**.</span><span class="sxs-lookup"><span data-stu-id="991d0-132">Type "HelloWorld" for the **Project Name**.</span></span> <span data-ttu-id="991d0-133">Seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="991d0-133">Select **Create**.</span></span>

   ![Configuración del cuadro de diálogo de nueva aplicación de consola](./media/using-on-mac-vs/visual-studio-mac-new-options.png)

1. <span data-ttu-id="991d0-135">Espere mientras se restauran las dependencias del proyecto.</span><span class="sxs-lookup"><span data-stu-id="991d0-135">Wait while the project's dependencies are restored.</span></span> <span data-ttu-id="991d0-136">El proyecto tiene un único archivo de C#, *Program.cs*, que contiene una clase `Program` con un método `Main`.</span><span class="sxs-lookup"><span data-stu-id="991d0-136">The project has a single C# file, *Program.cs*, containing a `Program` class with a `Main` method.</span></span> <span data-ttu-id="991d0-137">La instrucción `Console.WriteLine` genera la salida "¡Hola a todos!"</span><span class="sxs-lookup"><span data-stu-id="991d0-137">The `Console.WriteLine` statement will output "Hello World!"</span></span> <span data-ttu-id="991d0-138">en la consola cuando se ejecuta la aplicación.</span><span class="sxs-lookup"><span data-stu-id="991d0-138">to the console when the app is run.</span></span>

   ![Ventana principal con el archivo Program.cs abierto](./media/using-on-mac-vs/visual-studio-mac-editor.png)

## <a name="run-the-application"></a><span data-ttu-id="991d0-140">Ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="991d0-140">Run the application</span></span>

<span data-ttu-id="991d0-141">Ejecute la aplicación en modo de depuración con ⌘ ↵ (comando + ENTRAR) o en modo de versión ⌥ ⌘ ↵ (opción + comando + ENTRAR).</span><span class="sxs-lookup"><span data-stu-id="991d0-141">Run the app in Debug mode using ⌘ ↵ (command + enter) or in Release mode using ⌥ ⌘ ↵ (option + command + enter).</span></span>

![El panel de salida de la aplicación muestra ¡Hola a todos!](./media/using-on-mac-vs/visual-studio-mac-output.png)

## <a name="next-step"></a><span data-ttu-id="991d0-143">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="991d0-143">Next step</span></span>

<span data-ttu-id="991d0-144">El tema [Creación de una solución completa de .NET Core en macOS con Visual Studio para Mac](using-on-mac-vs-full-solution.md) le muestra cómo crear una solución completa de .NET Core que incluye una biblioteca reutilizable y pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="991d0-144">The [Building a complete .NET Core solution on macOS using Visual Studio for Mac](using-on-mac-vs-full-solution.md) topic shows you how to build a complete .NET Core solution that includes a reusable library and unit testing.</span></span>
