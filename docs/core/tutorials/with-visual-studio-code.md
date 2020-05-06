---
title: Introducción a C# y Visual Studio Code
description: Obtenga información sobre cómo crear y depurar su primera aplicación .NET Core en C# mediante Visual Studio Code.
author: kendrahavens
ms.date: 04/23/2020
ms.openlocfilehash: 3dd7c4602fbb27e29bad977f8d3df34b6061bc23
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2020
ms.locfileid: "82506919"
---
# <a name="get-started-with-c-and-visual-studio-code"></a><span data-ttu-id="4ee48-103">Introducción a C# y Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="4ee48-103">Get started with C# and Visual Studio Code</span></span>

<span data-ttu-id="4ee48-104">.NET Core ofrece una plataforma modular y rápida para crear aplicaciones que se ejecutan en Windows, Linux y macOS.</span><span class="sxs-lookup"><span data-stu-id="4ee48-104">.NET Core gives you a fast and modular platform for creating applications that run on Windows, Linux, and macOS.</span></span> <span data-ttu-id="4ee48-105">Use Visual Studio Code con la extensión de C# para disfrutar de una sólida experiencia de edición con compatibilidad total para C# IntelliSense (completado de código inteligente) y para depuración.</span><span class="sxs-lookup"><span data-stu-id="4ee48-105">Use Visual Studio Code with the C# extension to get a powerful editing experience with full support for C# IntelliSense (smart code completion) and debugging.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4ee48-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="4ee48-106">Prerequisites</span></span>

1. <span data-ttu-id="4ee48-107">Instale [Visual Studio Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="4ee48-107">Install [Visual Studio Code](https://code.visualstudio.com/).</span></span>
2. <span data-ttu-id="4ee48-108">Instale el [SDK de .NET Core](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="4ee48-108">Install the [.NET Core SDK](https://dotnet.microsoft.com/download).</span></span>
3. <span data-ttu-id="4ee48-109">Instale la [extensión de C#](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) para Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="4ee48-109">Install the [C# extension](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) for Visual Studio Code.</span></span> <span data-ttu-id="4ee48-110">Para más información sobre cómo instalar extensiones en Visual Studio Code, vea el [Marketplace de extensiones de VS Code](https://code.visualstudio.com/docs/editor/extension-gallery).</span><span class="sxs-lookup"><span data-stu-id="4ee48-110">For more information about how to install extensions on Visual Studio Code, see [VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery).</span></span>

## <a name="hello-world"></a><span data-ttu-id="4ee48-111">Hello World</span><span class="sxs-lookup"><span data-stu-id="4ee48-111">Hello World</span></span>

<span data-ttu-id="4ee48-112">Empiece con un sencillo programa "Hola mundo" basado en .NET Core:</span><span class="sxs-lookup"><span data-stu-id="4ee48-112">Get started with a simple "Hello World" program on .NET Core:</span></span>

1. <span data-ttu-id="4ee48-113">Abrir un proyecto:</span><span class="sxs-lookup"><span data-stu-id="4ee48-113">Open a project:</span></span>

    - <span data-ttu-id="4ee48-114">Abra Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="4ee48-114">Open Visual Studio Code.</span></span>
    - <span data-ttu-id="4ee48-115">Seleccione **Archivo** > **Abrir carpeta** en el menú principal.</span><span class="sxs-lookup"><span data-stu-id="4ee48-115">Select **File** > **Open Folder** from the main menu.</span></span>
    - <span data-ttu-id="4ee48-116">Cree una carpeta denominada *HelloWorld* y haga clic en **Seleccionar carpeta**.</span><span class="sxs-lookup"><span data-stu-id="4ee48-116">Create a folder named *HelloWorld*, and click **Select Folder**.</span></span> <span data-ttu-id="4ee48-117">De forma predeterminada, el nombre de la carpeta se convierte en el nombre del proyecto y del espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="4ee48-117">The folder name becomes the project name and the namespace name by default.</span></span> <span data-ttu-id="4ee48-118">Más adelante en el tutorial, agregará código que supone que el espacio de nombres del proyecto es `HelloWorld`.</span><span class="sxs-lookup"><span data-stu-id="4ee48-118">You'll add code later in the tutorial that assumes the project namespace is `HelloWorld`.</span></span>

1. <span data-ttu-id="4ee48-119">Inicializar un proyecto de C#:</span><span class="sxs-lookup"><span data-stu-id="4ee48-119">Initialize a C# project:</span></span>

    - <span data-ttu-id="4ee48-120">Abra el terminal de Visual Studio Code seleccionando **Ver** > **Terminal** en el menú principal.</span><span class="sxs-lookup"><span data-stu-id="4ee48-120">Open the Terminal from Visual Studio Code by selecting **View** > **Terminal** from the main menu.</span></span>
    - <span data-ttu-id="4ee48-121">En la ventana de terminal, escriba `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="4ee48-121">In the terminal window, enter `dotnet new console`.</span></span>

      <span data-ttu-id="4ee48-122">Este comando crea un archivo *Program.cs* en la carpeta con un programa "Hola mundo" sencillo ya escrito, junto con un archivo de proyecto de C# denominado *HelloWorld.csproj*.</span><span class="sxs-lookup"><span data-stu-id="4ee48-122">This command creates a *Program.cs* file in your folder with a simple "Hello World" program already written, along with a C# project file named *HelloWorld.csproj*.</span></span>

      ![El nuevo comando de dotnet](media/with-visual-studio-code/dotnet-new-command.png)

1. <span data-ttu-id="4ee48-124">Ejecutar el programa "Hola mundo":</span><span class="sxs-lookup"><span data-stu-id="4ee48-124">Run the "Hello World" program:</span></span>

    - <span data-ttu-id="4ee48-125">En la ventana de terminal, escriba `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="4ee48-125">In the terminal window, enter `dotnet run`.</span></span>

      ![El comando de ejecución de dotnet](media/with-visual-studio-code/dotnet-run-command.png)

## <a name="debug"></a><span data-ttu-id="4ee48-127">Depuración</span><span class="sxs-lookup"><span data-stu-id="4ee48-127">Debug</span></span>

1. <span data-ttu-id="4ee48-128">Haga clic en el archivo *Program.cs* para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="4ee48-128">Open *Program.cs* by clicking on it.</span></span> <span data-ttu-id="4ee48-129">La primera vez que se abre un archivo de C# en Visual Studio Code, se carga [OmniSharp](https://www.omnisharp.net/) en el editor.</span><span class="sxs-lookup"><span data-stu-id="4ee48-129">The first time you open a C# file in Visual Studio Code, [OmniSharp](https://www.omnisharp.net/) loads in the editor.</span></span>

    ![Abrir el archivo Program.cs](media/with-visual-studio-code/open-program-cs.png)

1. <span data-ttu-id="4ee48-131">Visual Studio Code le pedirá que agregue los recursos que faltan para compilar y depurar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4ee48-131">Visual Studio Code prompts you to add the missing assets to build and debug your app.</span></span> <span data-ttu-id="4ee48-132">Seleccione **Sí**.</span><span class="sxs-lookup"><span data-stu-id="4ee48-132">Select **Yes**.</span></span>

    ![Solicitud de los recursos que faltan](media/with-visual-studio-code/missing-assets.png)

1. <span data-ttu-id="4ee48-134">Para abrir la vista Depurar, haga clic en el icono de depuración en el menú de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="4ee48-134">To open the Debug view, click on the Debugging icon on the left side menu.</span></span>

    ![Apertura de la pestaña Depurar en Visual Studio Code](media/with-visual-studio-code/open-debug-tab.png)

1. <span data-ttu-id="4ee48-136">Busque la flecha verde en la parte superior del panel.</span><span class="sxs-lookup"><span data-stu-id="4ee48-136">Locate the green arrow at the top of the pane.</span></span> <span data-ttu-id="4ee48-137">Asegúrese de que **.NET Core Launch (consola)** está seleccionado en el menú desplegable que está junto a la flecha.</span><span class="sxs-lookup"><span data-stu-id="4ee48-137">Make sure the drop-down next to it has **.NET Core Launch (console)** selected.</span></span>

    ![Selección de .NET Core en Visual Studio Code](media/with-visual-studio-code/select-net-core.png)

1. <span data-ttu-id="4ee48-139">Agregue un punto de interrupción al proyecto; para ello, haga clic en el **margen del editor**, que es el espacio a la izquierda de los números de línea del editor, junto a la línea 9 o mueva el cursor del texto de la línea 9 en el editor y presione <kbd>F9</kbd>.</span><span class="sxs-lookup"><span data-stu-id="4ee48-139">Add a breakpoint to your project by clicking on the **editor margin**, which is the space on the left of the line numbers in the editor, next to line 9, or move the text cursor onto line 9 in the editor and  press <kbd>F9</kbd>.</span></span>

    ![Establecer un punto de interrupción](media/with-visual-studio-code/set-breakpoint-vs-code.png)

1. <span data-ttu-id="4ee48-141">Para empezar a depurar, presione <kbd>F5</kbd> o seleccione la flecha verde.</span><span class="sxs-lookup"><span data-stu-id="4ee48-141">To start debugging, press <kbd>F5</kbd> or select the green arrow.</span></span> <span data-ttu-id="4ee48-142">El depurador detiene la ejecución del programa cuando alcanza el punto de interrupción establecido en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="4ee48-142">The debugger stops execution of your program when it reaches the breakpoint you set in the previous step.</span></span>
    - <span data-ttu-id="4ee48-143">Mientras depura, puede ver las variables locales en el panel superior izquierdo o usar la consola de depuración.</span><span class="sxs-lookup"><span data-stu-id="4ee48-143">While debugging, you can view your local variables in the top-left pane or use the debug console.</span></span>

1. <span data-ttu-id="4ee48-144">Seleccione la flecha azul de la parte superior para continuar la depuración o seleccione el cuadrado rojo de la parte superior para detenerla.</span><span class="sxs-lookup"><span data-stu-id="4ee48-144">Select the blue arrow at the top to continue debugging, or select the red square at the top to stop.</span></span>

    ![Ejecución y depuración en Visual Studio Code](media/with-visual-studio-code/run-debug-vs-code.png)

> [!TIP]
> <span data-ttu-id="4ee48-146">Para obtener más información y sugerencias sobre solución de problemas en relación con la depuración de .NET Core con OmniSharp en Visual Studio Code, vea [Instructions for setting up the .NET Core debugger](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md) (Instrucciones para configurar el depurador de .NET Core).</span><span class="sxs-lookup"><span data-stu-id="4ee48-146">For more information and troubleshooting tips on .NET Core debugging with OmniSharp in Visual Studio Code, see [Instructions for setting up the .NET Core debugger](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).</span></span>

## <a name="add-a-class"></a><span data-ttu-id="4ee48-147">Agregar una clase</span><span class="sxs-lookup"><span data-stu-id="4ee48-147">Add a class</span></span>

1. <span data-ttu-id="4ee48-148">Para agregar una nueva clase, haga clic con el botón derecho en el Explorador de VSCode, debajo de *Program.cs*, y seleccione **Nuevo archivo**.</span><span class="sxs-lookup"><span data-stu-id="4ee48-148">To add a new class, right-click in the VSCode Explorer below *Program.cs* and select **New File**.</span></span> <span data-ttu-id="4ee48-149">Asé se agrega un nuevo archivo a la carpeta abierta en Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="4ee48-149">This adds a new file to the folder you have open in VSCode.</span></span>
1. <span data-ttu-id="4ee48-150">Asigne un nombre al archivo *MyClass.cs*.</span><span class="sxs-lookup"><span data-stu-id="4ee48-150">Name your file *MyClass.cs*.</span></span> <span data-ttu-id="4ee48-151">Debe guardarlo con una extensión `.cs` al final para que se reconozca como archivo csharp.</span><span class="sxs-lookup"><span data-stu-id="4ee48-151">You must save it with a `.cs` extension at the end for it to be recognized as a csharp file.</span></span>
1. <span data-ttu-id="4ee48-152">Agregue el código siguiente para crear la primera clase.</span><span class="sxs-lookup"><span data-stu-id="4ee48-152">Add the following code to create your first class.</span></span>

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

1. <span data-ttu-id="4ee48-153">Llame a la nueva clase desde el método `Main`. Para ello, reemplace el código en *Program.cs* por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="4ee48-153">Call your new class from your `Main` method by replacing the code in *Program.cs* with the following code:</span></span>

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

1. <span data-ttu-id="4ee48-154">Guarde los cambios.</span><span class="sxs-lookup"><span data-stu-id="4ee48-154">Save your changes.</span></span>

1. <span data-ttu-id="4ee48-155">Ejecute el programa otra vez.</span><span class="sxs-lookup"><span data-stu-id="4ee48-155">Run the program again.</span></span>

    ```dotnetcli
    dotnet run
    ```

    <span data-ttu-id="4ee48-156">El nuevo mensaje aparecerá con la cadena anexada.</span><span class="sxs-lookup"><span data-stu-id="4ee48-156">The new message appears with the appended string.</span></span>

    ```console
    Hello World! Happy coding!
    ```

## <a name="faq"></a><span data-ttu-id="4ee48-157">Preguntas más frecuentes</span><span class="sxs-lookup"><span data-stu-id="4ee48-157">FAQ</span></span>

### <a name="im-missing-required-assets-to-build-and-debug-c-in-visual-studio-code-my-debugger-says-no-configuration"></a><span data-ttu-id="4ee48-158">Me faltan los recursos necesarios para compilar y depurar C# en Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="4ee48-158">I'm missing required assets to build and debug C# in Visual Studio Code.</span></span> <span data-ttu-id="4ee48-159">Mi depurador dice "Sin configuración".</span><span class="sxs-lookup"><span data-stu-id="4ee48-159">My debugger says "No Configuration."</span></span>

<span data-ttu-id="4ee48-160">La extensión C# de Visual Studio Code puede generar recursos para compilar y depurar por usted.</span><span class="sxs-lookup"><span data-stu-id="4ee48-160">The Visual Studio Code C# extension can generate assets to build and debug for you.</span></span> <span data-ttu-id="4ee48-161">Visual Studio Code le pedirá que genere estos recursos al abrir un proyecto de C#.</span><span class="sxs-lookup"><span data-stu-id="4ee48-161">Visual Studio Code prompts you to generate these assets when you first open a C# project.</span></span> <span data-ttu-id="4ee48-162">Aunque no genere los recursos, podrá seguir ejecutando este comando si abre la paleta de comandos (**Vista > Paleta de comandos**) y escribe ">.NET: Generar recursos para la compilación y depuración".</span><span class="sxs-lookup"><span data-stu-id="4ee48-162">If you didn't generate assets then, you can still run this command by opening the Command Palette (**View > Command Palette**) and typing ">.NET: Generate Assets for Build and Debug".</span></span> <span data-ttu-id="4ee48-163">Al seleccionar esta opción se generan los archivos de configuración *.vscode*, *launch.json* y *tasks.json* que necesita.</span><span class="sxs-lookup"><span data-stu-id="4ee48-163">Selecting this generates the *.vscode*, *launch.json*, and *tasks.json* configuration files that you need.</span></span>

## <a name="see-also"></a><span data-ttu-id="4ee48-164">Vea también</span><span class="sxs-lookup"><span data-stu-id="4ee48-164">See also</span></span>

- <span data-ttu-id="4ee48-165">[Setting up Visual Studio Code](https://code.visualstudio.com/docs/setup/setup-overview) (Configuración de Visual Studio Code)</span><span class="sxs-lookup"><span data-stu-id="4ee48-165">[Setting up Visual Studio Code](https://code.visualstudio.com/docs/setup/setup-overview)</span></span>
- <span data-ttu-id="4ee48-166">[Debugging in Visual Studio Code](https://code.visualstudio.com/Docs/editor/debugging) (Depuración en Visual Studio Code)</span><span class="sxs-lookup"><span data-stu-id="4ee48-166">[Debugging in Visual Studio Code](https://code.visualstudio.com/Docs/editor/debugging)</span></span>
