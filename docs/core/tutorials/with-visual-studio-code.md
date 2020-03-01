---
title: Introducción a C# y Visual Studio Code
description: Obtenga información sobre cómo crear y depurar su primera aplicación .NET Core en C# mediante Visual Studio Code.
author: kendrahavens
ms.date: 12/05/2018
ms.openlocfilehash: ef7134e26c1ded3926faa51748c1b6d4a461008f
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156613"
---
# <a name="get-started-with-c-and-visual-studio-code"></a><span data-ttu-id="a94b5-103">Introducción a C# y Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="a94b5-103">Get started with C# and Visual Studio Code</span></span>

<span data-ttu-id="a94b5-104">.NET Core ofrece una plataforma modular y rápida para crear aplicaciones que se ejecutan en Windows, Linux y macOS.</span><span class="sxs-lookup"><span data-stu-id="a94b5-104">.NET Core gives you a fast and modular platform for creating applications that run on Windows, Linux, and macOS.</span></span> <span data-ttu-id="a94b5-105">Use Visual Studio Code con la extensión de C# para disfrutar de una sólida experiencia de edición con compatibilidad total para C# IntelliSense (completado de código inteligente) y para depuración.</span><span class="sxs-lookup"><span data-stu-id="a94b5-105">Use Visual Studio Code with the C# extension to get a powerful editing experience with full support for C# IntelliSense (smart code completion) and debugging.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a94b5-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a94b5-106">Prerequisites</span></span>

1. <span data-ttu-id="a94b5-107">Instale [Visual Studio Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="a94b5-107">Install [Visual Studio Code](https://code.visualstudio.com/).</span></span>
2. <span data-ttu-id="a94b5-108">Instale el [SDK de .NET Core](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="a94b5-108">Install the [.NET Core SDK](https://dotnet.microsoft.com/download).</span></span>
3. <span data-ttu-id="a94b5-109">Instale la [extensión de C#](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp) para Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="a94b5-109">Install the [C# extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp) for Visual Studio Code.</span></span> <span data-ttu-id="a94b5-110">Para más información sobre cómo instalar extensiones en Visual Studio Code, vea el [Marketplace de extensiones de VS Code](https://code.visualstudio.com/docs/editor/extension-gallery).</span><span class="sxs-lookup"><span data-stu-id="a94b5-110">For more information about how to install extensions on Visual Studio Code, see [VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery).</span></span>

## <a name="hello-world"></a><span data-ttu-id="a94b5-111">Hello World</span><span class="sxs-lookup"><span data-stu-id="a94b5-111">Hello World</span></span>

<span data-ttu-id="a94b5-112">Se va a empezar con un programa "Hola mundo" sencillo basado en .NET Core:</span><span class="sxs-lookup"><span data-stu-id="a94b5-112">Let's get started with a simple "Hello World" program on .NET Core:</span></span>

1. <span data-ttu-id="a94b5-113">Abrir un proyecto:</span><span class="sxs-lookup"><span data-stu-id="a94b5-113">Open a project:</span></span>

    - <span data-ttu-id="a94b5-114">Abra Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="a94b5-114">Open Visual Studio Code.</span></span>
    - <span data-ttu-id="a94b5-115">Haga clic en el icono del explorador en el menú de la izquierda y después haga clic en **Abrir carpeta**.</span><span class="sxs-lookup"><span data-stu-id="a94b5-115">Click on the Explorer icon on the left menu and then click **Open Folder**.</span></span>
    - <span data-ttu-id="a94b5-116">Seleccione **Archivo** > **Abrir carpeta** en el menú principal para abrir la carpeta en la que quiere que esté el proyecto de C# y haga clic en **Seleccionar carpeta**.</span><span class="sxs-lookup"><span data-stu-id="a94b5-116">Select **File** > **Open Folder** from the main menu to open the folder you want your C# project to be in and click **Select Folder**.</span></span> <span data-ttu-id="a94b5-117">En el ejemplo se va a crear una carpeta para el proyecto denominada *HelloWorld*.</span><span class="sxs-lookup"><span data-stu-id="a94b5-117">For our example, we're creating a folder for our project named *HelloWorld*.</span></span>

      ![Abrir carpeta de Visual Studio Code](media/with-visual-studio-code/vs-code-open-folder.png)

2. <span data-ttu-id="a94b5-119">Inicializar un proyecto de C#:</span><span class="sxs-lookup"><span data-stu-id="a94b5-119">Initialize a C# project:</span></span>

    - <span data-ttu-id="a94b5-120">Abra el terminal integrado de Visual Studio Code al seleccionar **Ver** > **Terminal integrado** en el menú principal.</span><span class="sxs-lookup"><span data-stu-id="a94b5-120">Open the Integrated Terminal from Visual Studio Code by selecting **View** > **Integrated Terminal** from the main menu.</span></span>
    - <span data-ttu-id="a94b5-121">En la ventana de terminal, escriba `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="a94b5-121">In the terminal window, type `dotnet new console`.</span></span>
    - <span data-ttu-id="a94b5-122">Este comando crea un archivo *Program.cs* en la carpeta con un programa "Hola mundo" sencillo ya escrito, junto con un archivo de proyecto de C# denominado *HelloWorld.csproj*.</span><span class="sxs-lookup"><span data-stu-id="a94b5-122">This command creates a *Program.cs* file in your folder with a simple "Hello World" program already written, along with a C# project file named *HelloWorld.csproj*.</span></span>

      ![El nuevo comando de dotnet](media/with-visual-studio-code/dotnet-new-command.png)

3. <span data-ttu-id="a94b5-124">Resolver los recursos de compilación:</span><span class="sxs-lookup"><span data-stu-id="a94b5-124">Resolve the build assets:</span></span>

    - <span data-ttu-id="a94b5-125">En **.NET Core 1.x**, escriba `dotnet restore`.</span><span class="sxs-lookup"><span data-stu-id="a94b5-125">For **.NET Core 1.x**, type `dotnet restore`.</span></span> <span data-ttu-id="a94b5-126">Al ejecutar `dotnet restore`, se concede acceso a los paquetes de .NET Core necesarios para compilar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="a94b5-126">Running `dotnet restore` gives you access to the  required .NET Core packages that are needed to build your project.</span></span>

      ![El comando de restauración de dotnet](media/with-visual-studio-code/dotnet-restore-command.png)

      [!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

4. <span data-ttu-id="a94b5-128">Ejecutar el programa "Hola mundo":</span><span class="sxs-lookup"><span data-stu-id="a94b5-128">Run the "Hello World" program:</span></span>

    - <span data-ttu-id="a94b5-129">Escriba `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="a94b5-129">Type `dotnet run`.</span></span>

      ![El comando de ejecución de dotnet](media/with-visual-studio-code/dotnet-run-command.png)

<span data-ttu-id="a94b5-131">También puede ver un breve tutorial de vídeo para obtener ayuda del programa de instalación en [Windows](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core), [macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core-on-MacOS) o [Linux](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).</span><span class="sxs-lookup"><span data-stu-id="a94b5-131">You can also watch a short video tutorial for further setup help on [Windows](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core), [macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core-on-MacOS), or [Linux](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).</span></span>

## <a name="debug"></a><span data-ttu-id="a94b5-132">Depuración</span><span class="sxs-lookup"><span data-stu-id="a94b5-132">Debug</span></span>

1. <span data-ttu-id="a94b5-133">Haga clic en el archivo *Program.cs* para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="a94b5-133">Open *Program.cs* by clicking on it.</span></span> <span data-ttu-id="a94b5-134">La primera vez que se abre un archivo de C# en Visual Studio Code, se carga [OmniSharp](https://www.omnisharp.net/) en el editor.</span><span class="sxs-lookup"><span data-stu-id="a94b5-134">The first time you open a C# file in Visual Studio Code, [OmniSharp](https://www.omnisharp.net/) loads in the editor.</span></span>

    ![Abrir el archivo Program.cs](media/with-visual-studio-code/open-program-cs.png)

2. <span data-ttu-id="a94b5-136">Visual Studio Code debe pedirle que agregue los recursos que faltan para compilar y depurar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a94b5-136">Visual Studio Code should prompt you to add the missing assets to build and debug your app.</span></span> <span data-ttu-id="a94b5-137">Seleccione **Sí**.</span><span class="sxs-lookup"><span data-stu-id="a94b5-137">Select **Yes**.</span></span>

    ![Solicitud de los recursos que faltan](media/with-visual-studio-code/missing-assets.png)

3. <span data-ttu-id="a94b5-139">Para abrir la vista Depurar, haga clic en el icono de depuración en el menú de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="a94b5-139">To open the Debug view, click on the Debugging icon on the left side menu.</span></span>

    ![Apertura de la pestaña Depurar en Visual Studio Code](media/with-visual-studio-code/open-debug-tab.png)

4. <span data-ttu-id="a94b5-141">Busque la flecha verde en la parte superior del panel.</span><span class="sxs-lookup"><span data-stu-id="a94b5-141">Locate the green arrow at the top of the pane.</span></span> <span data-ttu-id="a94b5-142">Asegúrese de que **.NET Core Launch (consola)** está seleccionado en el menú desplegable que está junto a la flecha.</span><span class="sxs-lookup"><span data-stu-id="a94b5-142">Make sure the drop-down next to it has **.NET Core Launch (console)** selected.</span></span>

    ![Selección de .NET Core en Visual Studio Code](media/with-visual-studio-code/select-net-core.png)

5. <span data-ttu-id="a94b5-144">Agregue un punto de interrupción al proyecto; para ello, haga clic en el **margen del editor**, que es el espacio a la izquierda de los números de línea del editor, junto a la línea 9 o mueva el cursor del texto de la línea 9 en el editor y presione <kbd>F9</kbd>.</span><span class="sxs-lookup"><span data-stu-id="a94b5-144">Add a breakpoint to your project by clicking on the **editor margin**, which is the space on the left of the line numbers in the editor, next to line 9, or move the text cursor onto line 9 in the editor and  press <kbd>F9</kbd>.</span></span>

    ![Establecer un punto de interrupción](media/with-visual-studio-code/set-breakpoint-vs-code.png)

6. <span data-ttu-id="a94b5-146">Para empezar a depurar, presione <kbd>F5</kbd> o seleccione la flecha verde.</span><span class="sxs-lookup"><span data-stu-id="a94b5-146">To start debugging, press <kbd>F5</kbd> or select the green arrow.</span></span> <span data-ttu-id="a94b5-147">El depurador detiene la ejecución del programa cuando alcanza el punto de interrupción establecido en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="a94b5-147">The debugger stops execution of your program when it reaches the breakpoint you set in the previous step.</span></span>
    - <span data-ttu-id="a94b5-148">Mientras depura, puede ver las variables locales en el panel superior izquierdo o usar la consola de depuración.</span><span class="sxs-lookup"><span data-stu-id="a94b5-148">While debugging, you can view your local variables in the top left pane or use the debug console.</span></span>

7. <span data-ttu-id="a94b5-149">Seleccione la flecha azul de la parte superior para continuar la depuración o seleccione el cuadrado rojo de la parte superior para detenerla.</span><span class="sxs-lookup"><span data-stu-id="a94b5-149">Select the blue arrow at the top to continue debugging, or select the red square at the top to stop.</span></span>

    ![Ejecución y depuración en Visual Studio Code](media/with-visual-studio-code/run-debug-vs-code.png)

> [!TIP]
> <span data-ttu-id="a94b5-151">Para obtener más información y sugerencias sobre solución de problemas en relación con la depuración de .NET Core con OmniSharp en Visual Studio Code, vea [Instructions for setting up the .NET Core debugger](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md) (Instrucciones para configurar el depurador de .NET Core).</span><span class="sxs-lookup"><span data-stu-id="a94b5-151">For more information and troubleshooting tips on .NET Core debugging with OmniSharp in Visual Studio Code, see [Instructions for setting up the .NET Core debugger](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).</span></span>

## <a name="add-a-class"></a><span data-ttu-id="a94b5-152">Agregar una clase</span><span class="sxs-lookup"><span data-stu-id="a94b5-152">Add a class</span></span>

1. <span data-ttu-id="a94b5-153">Para agregar una nueva clase, haga clic con el botón derecho en el Explorador de Visual Studio Code y seleccione **Nuevo archivo**.</span><span class="sxs-lookup"><span data-stu-id="a94b5-153">To add a new class, right click in the VSCode Explorer and select **New File**.</span></span> <span data-ttu-id="a94b5-154">Asé se agrega un nuevo archivo a la carpeta abierta en Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="a94b5-154">This adds a new file to the folder you have open in VSCode.</span></span>
2. <span data-ttu-id="a94b5-155">Asigne un nombre al archivo *MyClass.cs*.</span><span class="sxs-lookup"><span data-stu-id="a94b5-155">Name your file *MyClass.cs*.</span></span> <span data-ttu-id="a94b5-156">Debe guardarlo con una extensión `.cs` al final para que se reconozca como archivo csharp.</span><span class="sxs-lookup"><span data-stu-id="a94b5-156">You must save it with a `.cs` extension at the end for it to be recognized as a csharp file.</span></span>
3. <span data-ttu-id="a94b5-157">Agregue el código siguiente para crear la primera clase.</span><span class="sxs-lookup"><span data-stu-id="a94b5-157">Add the code below to create your first class.</span></span> <span data-ttu-id="a94b5-158">Asegúrese de incluir el espacio de nombres correcto para poder hacer referencia a él desde el archivo *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="a94b5-158">Make sure to include the correct namespace so you can reference it from your *Program.cs* file:</span></span>

    ``` csharp
    using System;

    namespace HelloWorld
    {
        public class MyClass
        {
            public string ReturnMessage()
            {
                return "Happy coding!";
            }
        }
    }
    ```

4. <span data-ttu-id="a94b5-159">Llame a la nueva clase con el método principal de *Program.cs* agregando el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="a94b5-159">Call your new class from your main method in *Program.cs* by adding the code below:</span></span>

    ```csharp
    using System;

    namespace HelloWorld
    {
        class Program
        {
            static void Main(string[] args)
            {
                var c1 = new MyClass();
                Console.WriteLine($"Hello World! {c1.ReturnMessage()}");
            }
        }
    }
    ```

5. <span data-ttu-id="a94b5-160">Guarde los cambios y vuelva a ejecutar el programa.</span><span class="sxs-lookup"><span data-stu-id="a94b5-160">Save your changes and run your program again.</span></span> <span data-ttu-id="a94b5-161">El nuevo mensaje debe aparecer con la cadena anexada.</span><span class="sxs-lookup"><span data-stu-id="a94b5-161">The new message should appear with the appended string.</span></span>

    ```dotnetcli
    dotnet run
    ```

    <span data-ttu-id="a94b5-162">Obtendrá la siguiente salida:</span><span class="sxs-lookup"><span data-stu-id="a94b5-162">You get the following output:</span></span>

    ```console
    Hello World! Happy coding!
    ```

## <a name="faq"></a><span data-ttu-id="a94b5-163">Preguntas más frecuentes</span><span class="sxs-lookup"><span data-stu-id="a94b5-163">FAQ</span></span>

### <a name="im-missing-required-assets-to-build-and-debug-c-in-visual-studio-code-my-debugger-says-no-configuration"></a><span data-ttu-id="a94b5-164">Me faltan los recursos necesarios para compilar y depurar C# en Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="a94b5-164">I'm missing required assets to build and debug C# in Visual Studio Code.</span></span> <span data-ttu-id="a94b5-165">Mi depurador dice "Sin configuración".</span><span class="sxs-lookup"><span data-stu-id="a94b5-165">My debugger says "No Configuration."</span></span>

<span data-ttu-id="a94b5-166">La extensión C# de Visual Studio Code puede generar recursos para compilar y depurar por usted.</span><span class="sxs-lookup"><span data-stu-id="a94b5-166">The Visual Studio Code C# extension can generate assets to build and debug for you.</span></span> <span data-ttu-id="a94b5-167">Visual Studio Code le pedirá que genere estos recursos al abrir un proyecto de C#.</span><span class="sxs-lookup"><span data-stu-id="a94b5-167">Visual Studio Code prompts you to generate these assets when you first open a C# project.</span></span> <span data-ttu-id="a94b5-168">Aunque no genere los recursos, podrá seguir ejecutando este comando si abre la paleta de comandos (**Vista > Paleta de comandos**) y escribe ">.NET: Generar recursos para la compilación y depuración".</span><span class="sxs-lookup"><span data-stu-id="a94b5-168">If you didn't generate assets then, you can still run this command by opening the Command Palette (**View > Command Palette**) and typing ">.NET: Generate Assets for Build and Debug".</span></span> <span data-ttu-id="a94b5-169">Al seleccionar esta opción se generan los archivos de configuración *.vscode*, *launch.json* y *tasks.json* que necesita.</span><span class="sxs-lookup"><span data-stu-id="a94b5-169">Selecting this generates the *.vscode*, *launch.json*, and *tasks.json* configuration files that you need.</span></span>

## <a name="see-also"></a><span data-ttu-id="a94b5-170">Vea también</span><span class="sxs-lookup"><span data-stu-id="a94b5-170">See also</span></span>

- <span data-ttu-id="a94b5-171">[Setting up Visual Studio Code](https://code.visualstudio.com/docs/setup/setup-overview) (Configuración de Visual Studio Code)</span><span class="sxs-lookup"><span data-stu-id="a94b5-171">[Setting up Visual Studio Code](https://code.visualstudio.com/docs/setup/setup-overview)</span></span>
- <span data-ttu-id="a94b5-172">[Debugging in Visual Studio Code](https://code.visualstudio.com/Docs/editor/debugging) (Depuración en Visual Studio Code)</span><span class="sxs-lookup"><span data-stu-id="a94b5-172">[Debugging in Visual Studio Code](https://code.visualstudio.com/Docs/editor/debugging)</span></span>
