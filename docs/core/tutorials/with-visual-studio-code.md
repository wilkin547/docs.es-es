---
title: "Empezar a trabajar con código C# y Visual Studio - Guía de C#"
description: "Obtenga información sobre cómo crear y depurar su primera aplicación .NET Core en C# mediante Visual Studio Code."
keywords: "C#, Introducción, Adquisición, Instalación, Visual Studio Code, Multiplataforma"
author: kendrahavens
ms.author: mairaw
ms.date: 09/27/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 76c23597-4cf9-467e-8a47-0c3703ce37e7
ms.openlocfilehash: 3a9de689946507e4b6d89f684461d65049b3375a
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2017
---
# <a name="get-started-with-c-and-visual-studio-code"></a><span data-ttu-id="a2f9b-104">Introducción a C# y Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="a2f9b-104">Get Started with C# and Visual Studio Code</span></span>

<span data-ttu-id="a2f9b-105">.NET Core ofrece una plataforma modular y rápida para crear aplicaciones que se ejecutan en Windows, Linux y macOS.</span><span class="sxs-lookup"><span data-stu-id="a2f9b-105">.NET Core gives you a fast and modular platform for creating applications that run on Windows, Linux, and macOS.</span></span> <span data-ttu-id="a2f9b-106">Use Visual Studio Code con la extensión de C# para disfrutar de una sólida experiencia de edición con compatibilidad total para C# IntelliSense (completado de código inteligente) y para depuración.</span><span class="sxs-lookup"><span data-stu-id="a2f9b-106">Use Visual Studio Code with the C# extension to get a powerful editing experience with full support for C# IntelliSense (smart code completion) and debugging.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a2f9b-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a2f9b-107">Prerequisites</span></span>

1. <span data-ttu-id="a2f9b-108">Instale [Visual Studio Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="a2f9b-108">Install [Visual Studio Code](https://code.visualstudio.com/).</span></span>
2. <span data-ttu-id="a2f9b-109">Instale el [SDK de .NET Core](https://www.microsoft.com/net/download/core).</span><span class="sxs-lookup"><span data-stu-id="a2f9b-109">Install the [.NET Core SDK](https://www.microsoft.com/net/download/core).</span></span>
3. <span data-ttu-id="a2f9b-110">Instale la [extensión de C#](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp) desde Visual Studio Code Marketplace.</span><span class="sxs-lookup"><span data-stu-id="a2f9b-110">Install the [C# extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp) from the Visual Studio Code Marketplace.</span></span>

## <a name="hello-world"></a><span data-ttu-id="a2f9b-111">Hello World</span><span class="sxs-lookup"><span data-stu-id="a2f9b-111">Hello World</span></span>

<span data-ttu-id="a2f9b-112">Se va a empezar con un programa "Hola mundo" sencillo basado en .NET Core:</span><span class="sxs-lookup"><span data-stu-id="a2f9b-112">Let's get started with a simple "Hello World" program on .NET Core:</span></span>

1. <span data-ttu-id="a2f9b-113">Abrir un proyecto:</span><span class="sxs-lookup"><span data-stu-id="a2f9b-113">Open a project:</span></span>

    * <span data-ttu-id="a2f9b-114">Abra Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="a2f9b-114">Open Visual Studio Code.</span></span>
    * <span data-ttu-id="a2f9b-115">Haga clic en el icono del explorador en el menú de la izquierda y después haga clic en **Abrir carpeta**.</span><span class="sxs-lookup"><span data-stu-id="a2f9b-115">Click on the Explorer icon on the left menu and then click **Open Folder**.</span></span>
    * <span data-ttu-id="a2f9b-116">Seleccione **archivo** > **Abrir carpeta** en el menú principal para abrir la carpeta que desea que el proyecto de C# y haga clic en **seleccionar la carpeta**.</span><span class="sxs-lookup"><span data-stu-id="a2f9b-116">Select **File** > **Open Folder** from the main menu to open the folder you want your C# project to be in and click **Select Folder**.</span></span> <span data-ttu-id="a2f9b-117">En nuestro ejemplo, estamos creando una carpeta para nuestro proyecto denominado *HelloWorld*.</span><span class="sxs-lookup"><span data-stu-id="a2f9b-117">For our example, we're creating a folder for our project named *HelloWorld*.</span></span>

      ![VSCodeOpenFolder](media/with-visual-studio-code/vscodeopenfolder.png)

2. <span data-ttu-id="a2f9b-119">Inicializar un proyecto de C#:</span><span class="sxs-lookup"><span data-stu-id="a2f9b-119">Initialize a C# project:</span></span>
    * <span data-ttu-id="a2f9b-120">Para abrir el Terminal integrada desde código de Visual Studio, seleccione **vista** > **Terminal integrado** en el menú principal.</span><span class="sxs-lookup"><span data-stu-id="a2f9b-120">Open the Integrated Terminal from Visual Studio Code by selecting **View** > **Integrated Terminal** from the main menu.</span></span>
    * <span data-ttu-id="a2f9b-121">En la ventana de terminal, escriba `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="a2f9b-121">In the terminal window, type `dotnet new console`.</span></span>
    * <span data-ttu-id="a2f9b-122">Este comando crea un `Program.cs` archivo con un programa simple "Hola mundo" ya escrito, junto con un archivo de proyecto de C# con el nombre en la carpeta `HelloWorld.csproj`.</span><span class="sxs-lookup"><span data-stu-id="a2f9b-122">This command creates a `Program.cs` file in your folder with a simple "Hello World" program already written, along with a C# project file named `HelloWorld.csproj`.</span></span>

      ![El nuevo comando de dotnet](media/with-visual-studio-code/dotnetnew.png)

3. <span data-ttu-id="a2f9b-124">Resolver los recursos de compilación:</span><span class="sxs-lookup"><span data-stu-id="a2f9b-124">Resolve the build assets:</span></span>

    * <span data-ttu-id="a2f9b-125">Para **.NET Core 1.x**, tipo `dotnet restore`.</span><span class="sxs-lookup"><span data-stu-id="a2f9b-125">For **.NET Core 1.x**, type `dotnet restore`.</span></span> <span data-ttu-id="a2f9b-126">Al ejecutar `dotnet restore`, se concede acceso a los paquetes de .NET Core necesarios para compilar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="a2f9b-126">Running `dotnet restore` gives you access to the  required .NET Core packages that are needed to build your project.</span></span>

      ![El comando de restauración de dotnet](media/with-visual-studio-code/dotnetrestore.png)

      [!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

4. <span data-ttu-id="a2f9b-128">Ejecutar el programa "Hola mundo":</span><span class="sxs-lookup"><span data-stu-id="a2f9b-128">Run the "Hello World" program:</span></span>

    * <span data-ttu-id="a2f9b-129">Escriba `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="a2f9b-129">Type `dotnet run`.</span></span> 

      ![El comando de ejecución de dotnet](media/with-visual-studio-code/dotnetrun.png)

<span data-ttu-id="a2f9b-131">También puede ver un breve tutorial de vídeo para obtener ayuda del programa de instalación en [Windows](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core), [macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core-on-MacOS) o [Linux](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).</span><span class="sxs-lookup"><span data-stu-id="a2f9b-131">You can also watch a short video tutorial for further setup help on [Windows](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core), [macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core-on-MacOS), or [Linux](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).</span></span>

## <a name="debug"></a><span data-ttu-id="a2f9b-132">Depuración</span><span class="sxs-lookup"><span data-stu-id="a2f9b-132">Debug</span></span>

1. <span data-ttu-id="a2f9b-133">Haga clic en el archivo *Program.cs* para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="a2f9b-133">Open *Program.cs* by clicking on it.</span></span> <span data-ttu-id="a2f9b-134">La primera vez que abra un archivo de C# en Visual Studio Code, [OmniSharp](http://www.omnisharp.net/) se carga en el editor.</span><span class="sxs-lookup"><span data-stu-id="a2f9b-134">The first time you open a C# file in Visual Studio Code, [OmniSharp](http://www.omnisharp.net/) loads in the editor.</span></span>

    ![Abrir el archivo Program.cs](media/with-visual-studio-code/opencs.png)

2. <span data-ttu-id="a2f9b-136">Código de Visual Studio debe solicitarle que agregue los activos que faltan para compilar y depurar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a2f9b-136">Visual Studio Code should prompt you to add the missing assets to build and debug your app.</span></span> <span data-ttu-id="a2f9b-137">Seleccione **Sí**.</span><span class="sxs-lookup"><span data-stu-id="a2f9b-137">Select **Yes**.</span></span> 

    ![Solicitud de los recursos que faltan](media/with-visual-studio-code/missing-assets.png)

3. <span data-ttu-id="a2f9b-139">Para abrir la vista Depurar, haga clic en el icono de depuración en el menú de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="a2f9b-139">To open the Debug view, click on the Debugging icon on the left side menu.</span></span>

    ![Abrir la pestaña Depurar](media/with-visual-studio-code/opendebug.png)

4. <span data-ttu-id="a2f9b-141">Busque la flecha verde en la parte superior del panel.</span><span class="sxs-lookup"><span data-stu-id="a2f9b-141">Locate the green arrow at the top of the pane.</span></span> <span data-ttu-id="a2f9b-142">Asegúrese de que `.NET Core Launch (console)` está seleccionado en el menú desplegable que está junto a la flecha.</span><span class="sxs-lookup"><span data-stu-id="a2f9b-142">Make sure the drop-down next to it has `.NET Core Launch (console)` selected.</span></span>

    ![Selección de .NET Core](media/with-visual-studio-code/selectcore.png)

5. <span data-ttu-id="a2f9b-144">Agregar un punto de interrupción al proyecto haciendo clic en el **editor margen**, que es el espacio de la izquierda de los números de línea en el editor, junto a la línea 9.</span><span class="sxs-lookup"><span data-stu-id="a2f9b-144">Add a breakpoint to your project by clicking on the **editor margin**, which is the space on the left of the line numbers in the editor, next to line 9.</span></span>

    ![Establecer un punto de interrupción](media/with-visual-studio-code/setbreakpoint.png)

6. <span data-ttu-id="a2f9b-146">Para iniciar la depuración, seleccione <kbd>F5</kbd> o en la flecha verde.</span><span class="sxs-lookup"><span data-stu-id="a2f9b-146">To start debugging, select <kbd>F5</kbd> or the green arrow.</span></span> <span data-ttu-id="a2f9b-147">El depurador detiene la ejecución del programa cuando alcanza el punto de interrupción establecido en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="a2f9b-147">The debugger stops execution of your program when it reaches the breakpoint you set in the previous step.</span></span>
    * <span data-ttu-id="a2f9b-148">Durante la depuración, puede ver las variables locales en el panel superior izquierdo o utilizar la consola de depuración.</span><span class="sxs-lookup"><span data-stu-id="a2f9b-148">While debugging, you can view your local variables in the top left pane or use the debug console.</span></span>

    ![Ejecutar y depurar](media/with-visual-studio-code/rundebug.png)

7. <span data-ttu-id="a2f9b-150">Seleccione la flecha verde en la parte superior para continuar la depuración o seleccione el cuadrado rojo que se encuentra arriba para detenerla.</span><span class="sxs-lookup"><span data-stu-id="a2f9b-150">Select the green arrow at the top to continue debugging, or select the red square at the top to stop.</span></span>

> [!TIP] 
> <span data-ttu-id="a2f9b-151">Para obtener más información y sugerencias sobre solución de problemas en relación con la depuración de .NET Core con OmniSharp en Visual Studio Code, vea [Instructions for setting up the .NET Core debugger](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md) (Instrucciones para configurar el depurador de .NET Core).</span><span class="sxs-lookup"><span data-stu-id="a2f9b-151">For more information and troubleshooting tips on .NET Core debugging with OmniSharp in Visual Studio Code, see [Instructions for setting up the .NET Core debugger](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a2f9b-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="a2f9b-152">See also</span></span>
<span data-ttu-id="a2f9b-153">[Setting up Visual Studio Code](https://code.visualstudio.com/docs/setup/setup-overview)  (Configuración de Visual Studio Code)</span><span class="sxs-lookup"><span data-stu-id="a2f9b-153">[Setting up Visual Studio Code](https://code.visualstudio.com/docs/setup/setup-overview) </span></span>  
<span data-ttu-id="a2f9b-154">[Debugging in Visual Studio Code](https://code.visualstudio.com/Docs/editor/debugging) (Depuración en Visual Studio Code)</span><span class="sxs-lookup"><span data-stu-id="a2f9b-154">[Debugging in Visual Studio Code](https://code.visualstudio.com/Docs/editor/debugging)</span></span>
