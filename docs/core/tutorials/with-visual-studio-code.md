---
title: "Introducción a C# y Visual Studio Code: Guía de C# | Microsoft Docs"
description: "Obtenga información sobre cómo crear y depurar su primera aplicación .NET Core en C# mediante Visual Studio Code."
keywords: "C#, Introducción, Adquisición, Instalación, Visual Studio Code, Multiplataforma"
author: kendrahavens
ms.author: mairaw
ms.date: 8/01/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 76c23597-4cf9-467e-8a47-0c3703ce37e7
ms.translationtype: HT
ms.sourcegitcommit: 3bd8800e7410ae4a3b89f5962af957789edd48b0
ms.openlocfilehash: a10fda5663f0a49069388ee8ee7a9ebb575cd549
ms.contentlocale: es-es
ms.lasthandoff: 08/03/2017

---

# <a name="get-started-with-c-and-visual-studio-code"></a><span data-ttu-id="1f6e0-104">Introducción a C# y Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="1f6e0-104">Get Started with C# and Visual Studio Code</span></span>

<span data-ttu-id="1f6e0-105">.NET Core ofrece una plataforma modular y rápida para crear aplicaciones que se ejecutan en Windows, Linux y macOS.</span><span class="sxs-lookup"><span data-stu-id="1f6e0-105">.NET Core gives you a fast and modular platform for creating applications that run on Windows, Linux, and macOS.</span></span> <span data-ttu-id="1f6e0-106">Use Visual Studio Code con la extensión de C# para disfrutar de una sólida experiencia de edición con compatibilidad total para C# IntelliSense (completado de código inteligente) y para depuración.</span><span class="sxs-lookup"><span data-stu-id="1f6e0-106">Use Visual Studio Code with the C# extension to get a powerful editing experience with full support for C# IntelliSense (smart code completion) and debugging.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1f6e0-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="1f6e0-107">Prerequisites</span></span>

1. <span data-ttu-id="1f6e0-108">Instale [Visual Studio Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="1f6e0-108">Install [Visual Studio Code](https://code.visualstudio.com/).</span></span>
2. <span data-ttu-id="1f6e0-109">Instale el [SDK de .NET Core](https://www.microsoft.com/net/download/core).</span><span class="sxs-lookup"><span data-stu-id="1f6e0-109">Install the [.NET Core SDK](https://www.microsoft.com/net/download/core).</span></span>
3. <span data-ttu-id="1f6e0-110">Instale la [extensión de C#](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp) desde Visual Studio Code Marketplace.</span><span class="sxs-lookup"><span data-stu-id="1f6e0-110">Install the [C# extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp) from the Visual Studio Code Marketplace.</span></span>

## <a name="hello-world"></a><span data-ttu-id="1f6e0-111">Hello World</span><span class="sxs-lookup"><span data-stu-id="1f6e0-111">Hello World</span></span>

<span data-ttu-id="1f6e0-112">Se va a empezar con un programa "Hola mundo" sencillo basado en .NET Core:</span><span class="sxs-lookup"><span data-stu-id="1f6e0-112">Let's get started with a simple "Hello World" program on .NET Core:</span></span>

1. <span data-ttu-id="1f6e0-113">Abrir un proyecto:</span><span class="sxs-lookup"><span data-stu-id="1f6e0-113">Open a project:</span></span>

    * <span data-ttu-id="1f6e0-114">Abra Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="1f6e0-114">Open Visual Studio Code.</span></span>
    * <span data-ttu-id="1f6e0-115">Haga clic en el icono del explorador en el menú de la izquierda y después haga clic en **Abrir carpeta**.</span><span class="sxs-lookup"><span data-stu-id="1f6e0-115">Click on the Explorer icon on the left menu and then click **Open Folder**.</span></span>
    * <span data-ttu-id="1f6e0-116">Seleccione la carpeta en que desea guardar el proyecto de C# y haga clic en **Seleccionar carpeta**.</span><span class="sxs-lookup"><span data-stu-id="1f6e0-116">Select the folder you want your C# project to be in and click **Select Folder**.</span></span> <span data-ttu-id="1f6e0-117">En el ejemplo, se va a crear una carpeta para el proyecto denominada "Hola mundo".</span><span class="sxs-lookup"><span data-stu-id="1f6e0-117">For our example, we'll create a folder for our project named 'HelloWorld'.</span></span> 

  ![VSCodeOpenFolder](media/with-visual-studio-code/vscodeopenfolder.png)

    * <span data-ttu-id="1f6e0-119">Como alternativa, puede seleccionar **Archivo** > **Abrir carpeta** desde el menú principal para abrir la carpeta del proyecto.</span><span class="sxs-lookup"><span data-stu-id="1f6e0-119">Alternatively, you can select **File** > **Open Folder** from the main menu to open your project folder.</span></span>

2. <span data-ttu-id="1f6e0-120">Inicializar un proyecto de C#:</span><span class="sxs-lookup"><span data-stu-id="1f6e0-120">Initialize a C# project:</span></span>
    * <span data-ttu-id="1f6e0-121">Abra el Terminal integrado de Visual Studio Code escribiendo <kbd>CTRL</kbd>+<kbd>\\`</kbd> (comilla simple).</span><span class="sxs-lookup"><span data-stu-id="1f6e0-121">Open the Integrated Terminal from Visual Studio Code by typing <kbd>CTRL</kbd>+<kbd>\\`</kbd> (backtick).</span></span> <span data-ttu-id="1f6e0-122">De manera alternativa, puede seleccionar **Ver** > **Integrated Terminal** (Terminal integrado) en el menú principal.</span><span class="sxs-lookup"><span data-stu-id="1f6e0-122">Alternatively, you can select **View** > **Integrated Terminal** from the main menu.</span></span>
    * <span data-ttu-id="1f6e0-123">En la ventana de terminal, escriba `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="1f6e0-123">In the terminal window, type `dotnet new console`.</span></span>
    * <span data-ttu-id="1f6e0-124">De esta forma, se crea un archivo `Program.cs` en la carpeta con un programa "Hola mundo" sencillo escrito previamente, junto con un nombre de proyecto de C# denominado `HelloWorld.csproj`.</span><span class="sxs-lookup"><span data-stu-id="1f6e0-124">This creates a `Program.cs` file in your folder with a simple "Hello World" program already written, along with a C# project file named `HelloWorld.csproj`.</span></span>

  ![El nuevo comando de dotnet](media/with-visual-studio-code/dotnetnew.png)

3. <span data-ttu-id="1f6e0-126">Resolver los recursos de compilación:</span><span class="sxs-lookup"><span data-stu-id="1f6e0-126">Resolve the build assets:</span></span>

    * <span data-ttu-id="1f6e0-127">En **.NET Core 1.1**, escriba `dotnet restore`.</span><span class="sxs-lookup"><span data-stu-id="1f6e0-127">For **.NET Core 1.1**, type `dotnet restore`.</span></span> <span data-ttu-id="1f6e0-128">Al ejecutar `dotnet restore`, se concede acceso a los paquetes de .NET Core necesarios para compilar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="1f6e0-128">Running `dotnet restore` gives you access to the  required .NET Core packages that are needed to build your project.</span></span>

   ![El comando de restauración de dotnet](media/with-visual-studio-code/dotnetrestore.png)

    * <span data-ttu-id="1f6e0-130">Este paso es opcional en **.NET Core 2.0**.</span><span class="sxs-lookup"><span data-stu-id="1f6e0-130">For **.NET Core 2.0**, this step is optional.</span></span> <span data-ttu-id="1f6e0-131">El comando `dotnet restore` se ejecuta automáticamente cuando se crea un proyecto nuevo.</span><span class="sxs-lookup"><span data-stu-id="1f6e0-131">The `dotnet restore` command executes automatically when a new project is created.</span></span>

4. <span data-ttu-id="1f6e0-132">Ejecutar el programa "Hola mundo":</span><span class="sxs-lookup"><span data-stu-id="1f6e0-132">Run the "Hello World" program:</span></span>

    * <span data-ttu-id="1f6e0-133">Escriba `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="1f6e0-133">Type `dotnet run`.</span></span> 

  ![El comando de ejecución de dotnet](media/with-visual-studio-code/dotnetrun.png)

<span data-ttu-id="1f6e0-135">También puede ver un breve tutorial de vídeo para obtener ayuda del programa de instalación en [Windows](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core), [macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core-on-MacOS) o [Linux](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).</span><span class="sxs-lookup"><span data-stu-id="1f6e0-135">You can also watch a short video tutorial for further setup help on [Windows](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core), [macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core-on-MacOS), or [Linux](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).</span></span>

## <a name="debug"></a><span data-ttu-id="1f6e0-136">Depuración</span><span class="sxs-lookup"><span data-stu-id="1f6e0-136">Debug</span></span>
1. <span data-ttu-id="1f6e0-137">Haga clic en el archivo *Program.cs* para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="1f6e0-137">Open *Program.cs* by clicking on it.</span></span> <span data-ttu-id="1f6e0-138">La primera vez que abra un archivo de C# en Visual Studio Code, [OmniSharp](http://www.omnisharp.net/) se cargará en el editor.</span><span class="sxs-lookup"><span data-stu-id="1f6e0-138">The first time you open a C# file in Visual Studio Code, [OmniSharp](http://www.omnisharp.net/) will load in the editor.</span></span>

  ![Abrir el archivo Program.cs](media/with-visual-studio-code/opencs.png)

2. <span data-ttu-id="1f6e0-140">Visual Studio Code le pedirá que agregue los recursos que faltan para compilar y depurar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1f6e0-140">Visual Studio Code will prompt you to add the missing assets to build and debug your app.</span></span> <span data-ttu-id="1f6e0-141">Seleccione **Sí**.</span><span class="sxs-lookup"><span data-stu-id="1f6e0-141">Select **Yes**.</span></span> 

  ![Solicitud de los recursos que faltan](media/with-visual-studio-code/missing-assets.png)

3. <span data-ttu-id="1f6e0-143">Para abrir la vista Depurar, haga clic en el icono de depuración en el menú de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="1f6e0-143">To open the Debug view, click on the Debugging icon on the left side menu.</span></span>

  ![Abrir la pestaña Depurar](media/with-visual-studio-code/opendebug.png)

4. <span data-ttu-id="1f6e0-145">Busque la flecha verde en la parte superior del panel.</span><span class="sxs-lookup"><span data-stu-id="1f6e0-145">Locate the green arrow at the top of the pane.</span></span> <span data-ttu-id="1f6e0-146">Asegúrese de que `.NET Core Launch (console)` está seleccionado en el menú desplegable que está junto a la flecha.</span><span class="sxs-lookup"><span data-stu-id="1f6e0-146">Make sure the drop-down next to it has `.NET Core Launch (console)` selected.</span></span>

  ![Selección de .NET Core](media/with-visual-studio-code/selectcore.png)

5. <span data-ttu-id="1f6e0-148">Agregue un punto de interrupción al proyecto; para ello, haga clic en el **margen del editor** (el espacio a la izquierda de los números de línea en el editor) junto a la línea 9.</span><span class="sxs-lookup"><span data-stu-id="1f6e0-148">Add a breakpoint to your project by clicking on the **editor margin** (the space on the left of the line numbers in the editor) next to line 9.</span></span>

  ![Establecer un punto de interrupción](media/with-visual-studio-code/setbreakpoint.png)

6. <span data-ttu-id="1f6e0-150">Seleccione <kbd>F5</kbd> o la flecha verde para iniciar la depuración.</span><span class="sxs-lookup"><span data-stu-id="1f6e0-150">Select <kbd>F5</kbd> or the green arrow to start debugging.</span></span> <span data-ttu-id="1f6e0-151">El depurador detiene la ejecución del programa cuando alcanza el punto de interrupción establecido en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="1f6e0-151">The debugger stops execution of your program when it reaches the breakpoint you set in the previous step.</span></span>
    * <span data-ttu-id="1f6e0-152">Mientras la depuración está en curso, puede ver las variables locales en el panel superior izquierdo o utilizar la consola de depuración.</span><span class="sxs-lookup"><span data-stu-id="1f6e0-152">While debugging you can view your local variables in the top left pane or use the debug console.</span></span>

  ![Ejecutar y depurar](media/with-visual-studio-code/rundebug.png)

7. <span data-ttu-id="1f6e0-154">Seleccione la flecha verde en la parte superior para continuar la depuración o seleccione el cuadrado rojo que se encuentra arriba para detenerla.</span><span class="sxs-lookup"><span data-stu-id="1f6e0-154">Select the green arrow at the top to continue debugging, or select the red square at the top to stop.</span></span>

> [!TIP] 
> <span data-ttu-id="1f6e0-155">Para obtener más información y sugerencias sobre solución de problemas en relación con la depuración de .NET Core con OmniSharp en Visual Studio Code, vea [Instructions for setting up the .NET Core debugger](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md) (Instrucciones para configurar el depurador de .NET Core).</span><span class="sxs-lookup"><span data-stu-id="1f6e0-155">For more information and troubleshooting tips on .NET Core debugging with OmniSharp in Visual Studio Code, see [Instructions for setting up the .NET Core debugger](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1f6e0-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="1f6e0-156">See also</span></span>
<span data-ttu-id="1f6e0-157">[Setting up Visual Studio Code](https://code.visualstudio.com/docs/setup/setup-overview)  (Configuración de Visual Studio Code)</span><span class="sxs-lookup"><span data-stu-id="1f6e0-157">[Setting up Visual Studio Code](https://code.visualstudio.com/docs/setup/setup-overview) </span></span>  
<span data-ttu-id="1f6e0-158">[Debugging in Visual Studio Code](https://code.visualstudio.com/Docs/editor/debugging) (Depuración en Visual Studio Code)</span><span class="sxs-lookup"><span data-stu-id="1f6e0-158">[Debugging in Visual Studio Code](https://code.visualstudio.com/Docs/editor/debugging)</span></span>

