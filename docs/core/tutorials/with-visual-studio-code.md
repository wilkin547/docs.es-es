---
title: 'Introducción a C# y Visual Studio Code: Guía de C#'
description: Obtenga información sobre cómo crear y depurar su primera aplicación .NET Core en C# mediante Visual Studio Code.
author: kendrahavens
ms.author: mairaw
ms.date: 09/27/2017
ms.openlocfilehash: 8958c39ba16cadbfab95e35fa36e8e85ce0a4ab8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33213622"
---
# <a name="get-started-with-c-and-visual-studio-code"></a><span data-ttu-id="202dd-103">Introducción a C# y Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="202dd-103">Get Started with C# and Visual Studio Code</span></span>

<span data-ttu-id="202dd-104">.NET Core ofrece una plataforma modular y rápida para crear aplicaciones que se ejecutan en Windows, Linux y macOS.</span><span class="sxs-lookup"><span data-stu-id="202dd-104">.NET Core gives you a fast and modular platform for creating applications that run on Windows, Linux, and macOS.</span></span> <span data-ttu-id="202dd-105">Use Visual Studio Code con la extensión de C# para disfrutar de una sólida experiencia de edición con compatibilidad total para C# IntelliSense (completado de código inteligente) y para depuración.</span><span class="sxs-lookup"><span data-stu-id="202dd-105">Use Visual Studio Code with the C# extension to get a powerful editing experience with full support for C# IntelliSense (smart code completion) and debugging.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="202dd-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="202dd-106">Prerequisites</span></span>

1. <span data-ttu-id="202dd-107">Instale [Visual Studio Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="202dd-107">Install [Visual Studio Code](https://code.visualstudio.com/).</span></span>
2. <span data-ttu-id="202dd-108">Instale el [SDK de .NET Core](https://www.microsoft.com/net/download/core).</span><span class="sxs-lookup"><span data-stu-id="202dd-108">Install the [.NET Core SDK](https://www.microsoft.com/net/download/core).</span></span>
3. <span data-ttu-id="202dd-109">Instale la [extensión de C#](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp) para Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="202dd-109">Install the [C# extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp) for Visual Studio Code.</span></span> <span data-ttu-id="202dd-110">Para más información sobre cómo instalar extensiones en Visual Studio Code, vea el [Marketplace de extensiones de VS Code](https://code.visualstudio.com/docs/editor/extension-gallery).</span><span class="sxs-lookup"><span data-stu-id="202dd-110">For more information about how to install extensions on Visual Studio Code, see [VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery).</span></span>

## <a name="hello-world"></a><span data-ttu-id="202dd-111">Hello World</span><span class="sxs-lookup"><span data-stu-id="202dd-111">Hello World</span></span>

<span data-ttu-id="202dd-112">Se va a empezar con un programa "Hola mundo" sencillo basado en .NET Core:</span><span class="sxs-lookup"><span data-stu-id="202dd-112">Let's get started with a simple "Hello World" program on .NET Core:</span></span>

1. <span data-ttu-id="202dd-113">Abrir un proyecto:</span><span class="sxs-lookup"><span data-stu-id="202dd-113">Open a project:</span></span>

    * <span data-ttu-id="202dd-114">Abra Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="202dd-114">Open Visual Studio Code.</span></span>
    * <span data-ttu-id="202dd-115">Haga clic en el icono del explorador en el menú de la izquierda y después haga clic en **Abrir carpeta**.</span><span class="sxs-lookup"><span data-stu-id="202dd-115">Click on the Explorer icon on the left menu and then click **Open Folder**.</span></span>
    * <span data-ttu-id="202dd-116">Seleccione **Archivo** > **Abrir carpeta** en el menú principal para abrir la carpeta en la que quiere que esté el proyecto de C# y haga clic en **Seleccionar carpeta**.</span><span class="sxs-lookup"><span data-stu-id="202dd-116">Select **File** > **Open Folder** from the main menu to open the folder you want your C# project to be in and click **Select Folder**.</span></span> <span data-ttu-id="202dd-117">En el ejemplo se va a crear una carpeta para el proyecto denominada *HelloWorld*.</span><span class="sxs-lookup"><span data-stu-id="202dd-117">For our example, we're creating a folder for our project named *HelloWorld*.</span></span>

      ![VSCodeOpenFolder](media/with-visual-studio-code/vscodeopenfolder.png)

2. <span data-ttu-id="202dd-119">Inicializar un proyecto de C#:</span><span class="sxs-lookup"><span data-stu-id="202dd-119">Initialize a C# project:</span></span>
    * <span data-ttu-id="202dd-120">Abra el terminal integrado de Visual Studio Code al seleccionar **Ver** > **Terminal integrado** en el menú principal.</span><span class="sxs-lookup"><span data-stu-id="202dd-120">Open the Integrated Terminal from Visual Studio Code by selecting **View** > **Integrated Terminal** from the main menu.</span></span>
    * <span data-ttu-id="202dd-121">En la ventana de terminal, escriba `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="202dd-121">In the terminal window, type `dotnet new console`.</span></span>
    * <span data-ttu-id="202dd-122">Este comando crea un archivo `Program.cs` en la carpeta con un programa "Hello World" sencillo ya escrito, junto con un archivo de proyecto de C# denominado `HelloWorld.csproj`.</span><span class="sxs-lookup"><span data-stu-id="202dd-122">This command creates a `Program.cs` file in your folder with a simple "Hello World" program already written, along with a C# project file named `HelloWorld.csproj`.</span></span>

      ![El nuevo comando de dotnet](media/with-visual-studio-code/dotnetnew.png)

3. <span data-ttu-id="202dd-124">Resolver los recursos de compilación:</span><span class="sxs-lookup"><span data-stu-id="202dd-124">Resolve the build assets:</span></span>

    * <span data-ttu-id="202dd-125">En **.NET Core 1.x**, escriba `dotnet restore`.</span><span class="sxs-lookup"><span data-stu-id="202dd-125">For **.NET Core 1.x**, type `dotnet restore`.</span></span> <span data-ttu-id="202dd-126">Al ejecutar `dotnet restore`, se concede acceso a los paquetes de .NET Core necesarios para compilar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="202dd-126">Running `dotnet restore` gives you access to the  required .NET Core packages that are needed to build your project.</span></span>

      ![El comando de restauración de dotnet](media/with-visual-studio-code/dotnetrestore.png)

      [!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

4. <span data-ttu-id="202dd-128">Ejecutar el programa "Hola mundo":</span><span class="sxs-lookup"><span data-stu-id="202dd-128">Run the "Hello World" program:</span></span>

    * <span data-ttu-id="202dd-129">Escriba `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="202dd-129">Type `dotnet run`.</span></span> 

      ![El comando de ejecución de dotnet](media/with-visual-studio-code/dotnetrun.png)

<span data-ttu-id="202dd-131">También puede ver un breve tutorial de vídeo para obtener ayuda del programa de instalación en [Windows](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core), [macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core-on-MacOS) o [Linux](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).</span><span class="sxs-lookup"><span data-stu-id="202dd-131">You can also watch a short video tutorial for further setup help on [Windows](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core), [macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core-on-MacOS), or [Linux](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).</span></span>

## <a name="debug"></a><span data-ttu-id="202dd-132">Depuración</span><span class="sxs-lookup"><span data-stu-id="202dd-132">Debug</span></span>

1. <span data-ttu-id="202dd-133">Haga clic en el archivo *Program.cs* para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="202dd-133">Open *Program.cs* by clicking on it.</span></span> <span data-ttu-id="202dd-134">La primera vez que se abre un archivo de C# en Visual Studio Code, se carga [OmniSharp](http://www.omnisharp.net/) en el editor.</span><span class="sxs-lookup"><span data-stu-id="202dd-134">The first time you open a C# file in Visual Studio Code, [OmniSharp](http://www.omnisharp.net/) loads in the editor.</span></span>

    ![Abrir el archivo Program.cs](media/with-visual-studio-code/opencs.png)

2. <span data-ttu-id="202dd-136">Visual Studio Code debe pedirle que agregue los recursos que faltan para compilar y depurar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="202dd-136">Visual Studio Code should prompt you to add the missing assets to build and debug your app.</span></span> <span data-ttu-id="202dd-137">Seleccione **Sí**.</span><span class="sxs-lookup"><span data-stu-id="202dd-137">Select **Yes**.</span></span> 

    ![Solicitud de los recursos que faltan](media/with-visual-studio-code/missing-assets.png)

3. <span data-ttu-id="202dd-139">Para abrir la vista Depurar, haga clic en el icono de depuración en el menú de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="202dd-139">To open the Debug view, click on the Debugging icon on the left side menu.</span></span>

    ![Abrir la pestaña Depurar](media/with-visual-studio-code/opendebug.png)

4. <span data-ttu-id="202dd-141">Busque la flecha verde en la parte superior del panel.</span><span class="sxs-lookup"><span data-stu-id="202dd-141">Locate the green arrow at the top of the pane.</span></span> <span data-ttu-id="202dd-142">Asegúrese de que `.NET Core Launch (console)` está seleccionado en el menú desplegable que está junto a la flecha.</span><span class="sxs-lookup"><span data-stu-id="202dd-142">Make sure the drop-down next to it has `.NET Core Launch (console)` selected.</span></span>

    ![Selección de .NET Core](media/with-visual-studio-code/selectcore.png)

5. <span data-ttu-id="202dd-144">Agregue un punto de interrupción al proyecto; para ello, haga clic en el **margen del editor**, que es el espacio a la izquierda de los números de línea del editor, junto a la línea 9.</span><span class="sxs-lookup"><span data-stu-id="202dd-144">Add a breakpoint to your project by clicking on the **editor margin**, which is the space on the left of the line numbers in the editor, next to line 9.</span></span>

    ![Establecer un punto de interrupción](media/with-visual-studio-code/setbreakpoint.png)

6. <span data-ttu-id="202dd-146">Para comenzar a depurar, seleccione <kbd>F5</kbd> o la flecha verde.</span><span class="sxs-lookup"><span data-stu-id="202dd-146">To start debugging, select <kbd>F5</kbd> or the green arrow.</span></span> <span data-ttu-id="202dd-147">El depurador detiene la ejecución del programa cuando alcanza el punto de interrupción establecido en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="202dd-147">The debugger stops execution of your program when it reaches the breakpoint you set in the previous step.</span></span>
    * <span data-ttu-id="202dd-148">Mientras depura, puede ver las variables locales en el panel superior izquierdo o usar la consola de depuración.</span><span class="sxs-lookup"><span data-stu-id="202dd-148">While debugging, you can view your local variables in the top left pane or use the debug console.</span></span>

    ![Ejecutar y depurar](media/with-visual-studio-code/rundebug.png)

7. <span data-ttu-id="202dd-150">Seleccione la flecha verde en la parte superior para continuar la depuración o seleccione el cuadrado rojo que se encuentra arriba para detenerla.</span><span class="sxs-lookup"><span data-stu-id="202dd-150">Select the green arrow at the top to continue debugging, or select the red square at the top to stop.</span></span>

> [!TIP] 
> <span data-ttu-id="202dd-151">Para obtener más información y sugerencias sobre solución de problemas en relación con la depuración de .NET Core con OmniSharp en Visual Studio Code, vea [Instructions for setting up the .NET Core debugger](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md) (Instrucciones para configurar el depurador de .NET Core).</span><span class="sxs-lookup"><span data-stu-id="202dd-151">For more information and troubleshooting tips on .NET Core debugging with OmniSharp in Visual Studio Code, see [Instructions for setting up the .NET Core debugger](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="202dd-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="202dd-152">See also</span></span>
<span data-ttu-id="202dd-153">[Setting up Visual Studio Code](https://code.visualstudio.com/docs/setup/setup-overview)  (Configuración de Visual Studio Code)</span><span class="sxs-lookup"><span data-stu-id="202dd-153">[Setting up Visual Studio Code](https://code.visualstudio.com/docs/setup/setup-overview) </span></span>  
<span data-ttu-id="202dd-154">[Debugging in Visual Studio Code](https://code.visualstudio.com/Docs/editor/debugging) (Depuración en Visual Studio Code)</span><span class="sxs-lookup"><span data-stu-id="202dd-154">[Debugging in Visual Studio Code](https://code.visualstudio.com/Docs/editor/debugging)</span></span>
