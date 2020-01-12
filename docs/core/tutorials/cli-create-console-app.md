---
title: 'Introducción a .NET Core con la CLI: CLI de .NET Core'
description: Un tutorial paso a paso que muestra cómo empezar a trabajar con .NET Core en Windows, Linux o macOS con la interfaz de la línea de comandos (CLI) de .NET Core.
author: thraka
ms.author: adegeo
ms.date: 12/05/2019
ms.technology: dotnet-cli
ms.custom: updateeachrelease
ms.openlocfilehash: 6c394ad2721bcdd91fb750fe93c03f16ca9f799f
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714074"
---
# <a name="get-started-with-net-core-on-windowslinuxmacos-using-the-command-line"></a><span data-ttu-id="73930-103">Introducción a .NET Core en Windows, Linux y macOS con la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="73930-103">Get started with .NET Core on Windows/Linux/macOS using the command line</span></span>

<span data-ttu-id="73930-104">En este artículo se muestra cómo empezar a desarrollar aplicaciones multiplataforma en su máquina con las herramientas de la CLI de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="73930-104">This article will show you how to start developing cross-platforms apps in your machine using the .NET Core CLI tools.</span></span>

<span data-ttu-id="73930-105">Si no está familiarizado con el conjunto de herramientas de la CLI de .NET Core, vea la [información general del SDK de .NET Core](../tools/index.md).</span><span class="sxs-lookup"><span data-stu-id="73930-105">If you're unfamiliar with the .NET Core CLI toolset, read the [.NET Core SDK overview](../tools/index.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="73930-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="73930-106">Prerequisites</span></span>

- <span data-ttu-id="73930-107">[SDK 3.1 de NET Core](https://dotnet.microsoft.com/download) o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="73930-107">[.NET Core SDK 3.1](https://dotnet.microsoft.com/download) or later versions.</span></span>
- <span data-ttu-id="73930-108">Un editor de texto o un editor de código de su elección.</span><span class="sxs-lookup"><span data-stu-id="73930-108">A text editor or code editor of your choice.</span></span>

## <a name="hello-console-app"></a><span data-ttu-id="73930-109">Hola, aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="73930-109">Hello, Console App!</span></span>

<span data-ttu-id="73930-110">Puede [ver o descargar el código de ejemplo](https://github.com/dotnet/samples/tree/master/core/console-apps/HelloMsBuild) del repositorio dotnet/samples de GitHub.</span><span class="sxs-lookup"><span data-stu-id="73930-110">You can [view or download the sample code](https://github.com/dotnet/samples/tree/master/core/console-apps/HelloMsBuild) from the dotnet/samples GitHub repository.</span></span> <span data-ttu-id="73930-111">Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="73930-111">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

<span data-ttu-id="73930-112">Abra un símbolo del sistema y cree una carpeta denominada *Hello*.</span><span class="sxs-lookup"><span data-stu-id="73930-112">Open a command prompt and create a folder named *Hello*.</span></span> <span data-ttu-id="73930-113">Vaya a la carpeta que ha creado y escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="73930-113">Navigate to the folder you created and type the following:</span></span>

```dotnetcli
dotnet new console
dotnet run
```

<span data-ttu-id="73930-114">Veamos un tutorial rápido:</span><span class="sxs-lookup"><span data-stu-id="73930-114">Let's do a quick walkthrough:</span></span>

01. `dotnet new console`

    <span data-ttu-id="73930-115">[dotnet new](../tools/dotnet-new.md) crea un archivo de proyecto *Hello.csproj* actualizado con las dependencias necesarias para compilar una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="73930-115">[dotnet new](../tools/dotnet-new.md) creates an up-to-date *Hello.csproj* project file with the dependencies necessary to build a console app.</span></span> <span data-ttu-id="73930-116">Además, también crea *Program.cs*, un archivo básico que contiene el punto de entrada para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="73930-116">It also creates a *Program.cs*, a basic file containing the entry point for the application.</span></span>
    
    <span data-ttu-id="73930-117">*Hello.csproj*:</span><span class="sxs-lookup"><span data-stu-id="73930-117">*Hello.csproj*:</span></span>
    
    [!code-xml[Hello.csproj](~/samples/core/console-apps/HelloMsBuild/Hello.csproj)]
    
    <span data-ttu-id="73930-118">El archivo de proyecto especifica todo lo que es necesario para restaurar las dependencias y compilar el programa.</span><span class="sxs-lookup"><span data-stu-id="73930-118">The project file specifies everything that's needed to restore dependencies and build the program.</span></span>
    
    - <span data-ttu-id="73930-119">El elemento `<OutputType>` especifica que estamos creando un archivo ejecutable, es decir, una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="73930-119">The `<OutputType>` element specifies that we're building an executable, in other words a console application.</span></span>
    - <span data-ttu-id="73930-120">El elemento `<TargetFramework>` especifica el destino de la implementación de .NET.</span><span class="sxs-lookup"><span data-stu-id="73930-120">The `<TargetFramework>` element specifies what .NET implementation we're targeting.</span></span> <span data-ttu-id="73930-121">En un escenario avanzado, con una sola operación puede especificar varios marcos de destino y compilar en todos ellos.</span><span class="sxs-lookup"><span data-stu-id="73930-121">In an advanced scenario, you can specify multiple target frameworks and build to all those in a single operation.</span></span> <span data-ttu-id="73930-122">En este tutorial, nos centraremos en compilar únicamente para .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="73930-122">In this tutorial, we'll stick to building only for .NET Core 3.1.</span></span>
    
    <span data-ttu-id="73930-123">*Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="73930-123">*Program.cs*:</span></span>
    
    [!code-csharp[Program.cs](~/samples/core/console-apps/HelloMsBuild/Program.cs)]
    
    <span data-ttu-id="73930-124">El programa se inicia mediante `using System`, lo que significa "llevar cada cosa del espacio de nombres `System` al ámbito de este archivo".</span><span class="sxs-lookup"><span data-stu-id="73930-124">The program starts by `using System`, which means "bring everything in the `System` namespace into scope for this file".</span></span> <span data-ttu-id="73930-125">El espacio de nombres `System` incluye la clase `Console`.</span><span class="sxs-lookup"><span data-stu-id="73930-125">The `System` namespace includes the `Console` class.</span></span>
    
    <span data-ttu-id="73930-126">Después, definimos un espacio de nombres denominado `Hello`.</span><span class="sxs-lookup"><span data-stu-id="73930-126">We then define a namespace called `Hello`.</span></span> <span data-ttu-id="73930-127">Puede cambiar esto por cualquier cosa que desee.</span><span class="sxs-lookup"><span data-stu-id="73930-127">You can change this to anything you want.</span></span> <span data-ttu-id="73930-128">Se define una clase denominada `Program` dentro del espacio de nombres, con un método `Main` que toma una matriz de cadenas llamada `args`.</span><span class="sxs-lookup"><span data-stu-id="73930-128">A class named `Program` is defined within that namespace, with a `Main` method that takes an array of strings named `args`.</span></span> <span data-ttu-id="73930-129">Esta matriz contiene la lista de argumentos que se han pasado cuando se ejecuta el programa.</span><span class="sxs-lookup"><span data-stu-id="73930-129">This array contains the list of arguments passed in when the program is run.</span></span> <span data-ttu-id="73930-130">Esta matriz no se usa tal cual y el programa escribe simplemente el texto "¡Hola mundo!".</span><span class="sxs-lookup"><span data-stu-id="73930-130">As it is, this array is not used and the program simply writes the text "Hello World!"</span></span> <span data-ttu-id="73930-131">en la consola.</span><span class="sxs-lookup"><span data-stu-id="73930-131">to the console.</span></span> <span data-ttu-id="73930-132">Después, realizaremos cambios en el código que usará este argumento.</span><span class="sxs-lookup"><span data-stu-id="73930-132">Later, we'll make changes to the code that will make use of this argument.</span></span>
    
    <span data-ttu-id="73930-133">`dotnet new` llama a [dotnet restore](../tools/dotnet-restore.md) de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="73930-133">`dotnet new` calls [dotnet restore](../tools/dotnet-restore.md) implicitly.</span></span> <span data-ttu-id="73930-134">`dotnet restore` llama a [NuGet](https://www.nuget.org/) (el administrador de paquetes de .NET) para restaurar el árbol de dependencias.</span><span class="sxs-lookup"><span data-stu-id="73930-134">`dotnet restore` calls into [NuGet](https://www.nuget.org/) (.NET package manager) to restore the tree of dependencies.</span></span> <span data-ttu-id="73930-135">NuGet analiza el archivo *Hello.csproj*, descarga las dependencias descritas en el archivo (o las toma de la memoria caché del equipo) y escribe el archivo *obj/project.assets.json*, que es necesario para compilar y ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="73930-135">NuGet analyzes the *Hello.csproj* file, downloads the dependencies defined in the file (or grabs them from a cache on your machine), and writes the *obj/project.assets.json* file, which is necessary to compile and run the sample.</span></span>

02. `dotnet run`

    <span data-ttu-id="73930-136">[dotnet run](../tools/dotnet-run.md) llama a [dotnet build](../tools/dotnet-build.md) para garantizar que se han creado los destinos de compilación y, luego, llama a `dotnet <assembly.dll>` para ejecutar la aplicación de destino.</span><span class="sxs-lookup"><span data-stu-id="73930-136">[dotnet run](../tools/dotnet-run.md) calls [dotnet build](../tools/dotnet-build.md) to ensure that the build targets have been built, and then calls `dotnet <assembly.dll>` to run the target application.</span></span>
    
    ```console
    dotnet run

    Hello World!
    ```
    
    <span data-ttu-id="73930-137">También puede ejecutar `dotnet build` para compilar el código sin ejecutar las aplicaciones de consola de compilación.</span><span class="sxs-lookup"><span data-stu-id="73930-137">Alternatively, you can also run `dotnet build` to compile the code without running the build console applications.</span></span> <span data-ttu-id="73930-138">El resultado es una aplicación compilada, como un archivo DLL, basada en el nombre del proyecto.</span><span class="sxs-lookup"><span data-stu-id="73930-138">This results in a compiled application, as a DLL file, based on the name of the project.</span></span> <span data-ttu-id="73930-139">En este caso, el archivo creado se llama *Hello.dll*.</span><span class="sxs-lookup"><span data-stu-id="73930-139">In this case, the file created is named *Hello.dll*.</span></span> <span data-ttu-id="73930-140">Esta aplicación se puede ejecutar con `dotnet bin\Debug\netcoreapp3.1\Hello.dll` en Windows (use `/` con sistemas que no son Windows).</span><span class="sxs-lookup"><span data-stu-id="73930-140">This app can be run with `dotnet bin\Debug\netcoreapp3.1\Hello.dll` on Windows (use `/` for non-Windows systems).</span></span>
    
    ```console
    dotnet bin\Debug\netcoreapp3.1\Hello.dll

    Hello World!
    ```
    
    <span data-ttu-id="73930-141">Cuando se compila la aplicación, se crea un archivo ejecutable específico del sistema operativo junto con `Hello.dll`.</span><span class="sxs-lookup"><span data-stu-id="73930-141">When the app is compiled, an operating system-specific executable was created along with the `Hello.dll`.</span></span> <span data-ttu-id="73930-142">En Windows, sería `Hello.exe`; en Linux o macOS, sería `hello`.</span><span class="sxs-lookup"><span data-stu-id="73930-142">On Windows, this would be `Hello.exe`; on Linux or macOS, this would be `hello`.</span></span> <span data-ttu-id="73930-143">Con el ejemplo anterior, el archivo se designa con `Hello.exe` o `Hello`.</span><span class="sxs-lookup"><span data-stu-id="73930-143">With the example above, the file is named with `Hello.exe` or `Hello`.</span></span> <span data-ttu-id="73930-144">Puede ejecutar ese archivo ejecutable directamente.</span><span class="sxs-lookup"><span data-stu-id="73930-144">You can run that executable directly.</span></span>

    ```console
    .\bin\Debug\netcoreapp3.1\Hello.exe

    Hello World!
    ```

## <a name="modify-the-program"></a><span data-ttu-id="73930-145">Modificación del programa</span><span class="sxs-lookup"><span data-stu-id="73930-145">Modify the program</span></span>

<span data-ttu-id="73930-146">Cambiemos un poco el programa.</span><span class="sxs-lookup"><span data-stu-id="73930-146">Let's change the program a bit.</span></span> <span data-ttu-id="73930-147">Los números Fibonacci son divertidos, así que vamos a agregarlos y a usar además el argumento para saludar a la persona que ejecuta la aplicación.</span><span class="sxs-lookup"><span data-stu-id="73930-147">Fibonacci numbers are fun, so let's add that and also to use the argument to greet the person running the app.</span></span>

01. <span data-ttu-id="73930-148">Reemplace el contenido de su archivo *Program.cs* por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="73930-148">Replace the contents of your *Program.cs*  file with the following code:</span></span>

    [!code-csharp[Fibonacci](~/samples/core/console-apps/fibonacci-msbuild/Program.cs)]

02. <span data-ttu-id="73930-149">Ejecute [dotnet build](../tools/dotnet-build.md) para compilar los cambios.</span><span class="sxs-lookup"><span data-stu-id="73930-149">Run [dotnet build](../tools/dotnet-build.md) to compile the changes.</span></span>

03. <span data-ttu-id="73930-150">Para ejecutar el programa, pase un parámetro a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="73930-150">Run the program passing a parameter to the app.</span></span> <span data-ttu-id="73930-151">Cuando use el comando `dotnet` para ejecutar una aplicación, agregue `--` al final.</span><span class="sxs-lookup"><span data-stu-id="73930-151">When you use the `dotnet` command to run an app, add `--` to the end.</span></span> <span data-ttu-id="73930-152">Todo lo que quede a la derecha de `--` se pasará como un parámetro a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="73930-152">Anything to the right of `--` will be passed as a parameter to the app.</span></span> <span data-ttu-id="73930-153">En el ejemplo siguiente, el valor `John` se pasa a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="73930-153">In the following example, the value `John` is passed to the app.</span></span>

    ```console
    $ dotnet run -- John
    Hello John!
    Fibonacci Numbers 1-15:
    1: 0
    2: 1
    3: 1
    4: 2
    5: 3
    6: 5
    7: 8
    8: 13
    9: 21
    10: 34
    11: 55
    12: 89
    13: 144
    14: 233
    15: 377
    ```

<span data-ttu-id="73930-154">Y listo.</span><span class="sxs-lookup"><span data-stu-id="73930-154">And that's it!</span></span> <span data-ttu-id="73930-155">Puede modificar *Program.cs* como prefiera.</span><span class="sxs-lookup"><span data-stu-id="73930-155">You can modify *Program.cs* any way you like.</span></span>

## <a name="working-with-multiple-files"></a><span data-ttu-id="73930-156">Trabajar con varios archivos</span><span class="sxs-lookup"><span data-stu-id="73930-156">Working with multiple files</span></span>

<span data-ttu-id="73930-157">Los archivos únicos son adecuados para programas sencillos de uso único, pero, si va a crear una aplicación más compleja, probablemente llegue a tener varios archivos de código en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="73930-157">Single files are fine for simple one-off programs, but if you're building a more complex app, you're probably going to have multiple code files on your project.</span></span> <span data-ttu-id="73930-158">Se compilará sobre el ejemplo de Fibonacci anterior mediante el almacenamiento en caché de algunos valores de Fibonacci y la adición de varias características recursivas.</span><span class="sxs-lookup"><span data-stu-id="73930-158">Let's build off of the previous Fibonacci example by caching some Fibonacci values and add some recursive features.</span></span>

01. <span data-ttu-id="73930-159">Agregue un archivo nuevo dentro del directorio *Hello* denominado *FibonacciGenerator.cs* con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="73930-159">Add a new file inside the *Hello* directory named *FibonacciGenerator.cs* with the following code:</span></span>

    [!code-csharp[Fibonacci Generator](~/samples/core/console-apps/FibonacciBetterMsBuild/FibonacciGenerator.cs)]

02. <span data-ttu-id="73930-160">Cambie el método `Main` en su archivo *Program.cs* para crear una instancia de la nueva clase y llamar a su método como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="73930-160">Change the `Main` method in your *Program.cs* file to instantiate the new class and call its method as in the following example:</span></span>

    [!code-csharp[New Program.cs](~/samples/core/console-apps/FibonacciBetterMsBuild/Program.cs)]

03. <span data-ttu-id="73930-161">Ejecute [dotnet build](../tools/dotnet-build.md) para compilar los cambios.</span><span class="sxs-lookup"><span data-stu-id="73930-161">Run [dotnet build](../tools/dotnet-build.md) to compile the changes.</span></span>

04. <span data-ttu-id="73930-162">Ejecute su aplicación mediante la ejecución de [dotnet run](../tools/dotnet-run.md).</span><span class="sxs-lookup"><span data-stu-id="73930-162">Run your app by executing [dotnet run](../tools/dotnet-run.md).</span></span> <span data-ttu-id="73930-163">A continuación se muestra el resultado del programa:</span><span class="sxs-lookup"><span data-stu-id="73930-163">The following shows the program output:</span></span>

    ```console
    $ dotnet run
    0
    1
    1
    2
    3
    5
    8
    13
    21
    34
    55
    89
    144
    233
    377
    ```

## <a name="publish-your-app"></a><span data-ttu-id="73930-164">Publicar la aplicación</span><span class="sxs-lookup"><span data-stu-id="73930-164">Publish your app</span></span>

<span data-ttu-id="73930-165">Cuando esté listo para distribuir la aplicación, use el comando [dotnet publish](../tools/dotnet-publish.md)_para generar la carpeta_publish _en \\bin\\debug\\netcoreapp3.1\\publish_`/` (para sistemas que no son Windows).</span><span class="sxs-lookup"><span data-stu-id="73930-165">Once you're ready to distribute your app, use the [dotnet publish](../tools/dotnet-publish.md) command to generate the _publish_ folder at _bin\\debug\\netcoreapp3.1\\publish\\_ (use `/` for non-Windows systems).</span></span> <span data-ttu-id="73930-166">Puede distribuir el contenido de la carpeta _publish_ en otras plataformas siempre y cuando ya haya instalado el entorno de ejecución de dotnet.</span><span class="sxs-lookup"><span data-stu-id="73930-166">You can distribute the contents of the _publish_ folder to other platforms as long as they've already installed the dotnet runtime.</span></span>

```console
dotnet publish
Microsoft (R) Build Engine version 16.4.0+e901037fe for .NET Core
Copyright (C) Microsoft Corporation. All rights reserved.

  Restore completed in 20 ms for C:\Code\Temp\Hello\Hello.csproj.
  Hello -> C:\Code\Temp\Hello\bin\Debug\netcoreapp3.1\Hello.dll
  Hello -> C:\Code\Temp\Hello\bin\Debug\netcoreapp3.1\publish\
```

<span data-ttu-id="73930-167">Puede que la salida anterior no sea igual por la carpeta y el sistema operativo actuales, pero el resultado será parecido.</span><span class="sxs-lookup"><span data-stu-id="73930-167">The output above may differ based on your current folder and operating system, but the output should be similar.</span></span>

<span data-ttu-id="73930-168">Puede ejecutar la aplicación publicada con el comando [dotnet](../tools/dotnet.md):</span><span class="sxs-lookup"><span data-stu-id="73930-168">You can run your published app with the [dotnet](../tools/dotnet.md) command:</span></span>

```console
dotnet bin\Debug\netcoreapp3.1\publish\Hello.dll

Hello World!
```

<span data-ttu-id="73930-169">Como se ha mencionado al comienzo de este artículo, se ha creado un archivo ejecutable específico del sistema operativo junto con `Hello.dll`.</span><span class="sxs-lookup"><span data-stu-id="73930-169">As mentioned at the start of this article, an operating system-specific executable was created along with the `Hello.dll`.</span></span> <span data-ttu-id="73930-170">En Windows, sería `Hello.exe`; en Linux o macOS, sería `hello`.</span><span class="sxs-lookup"><span data-stu-id="73930-170">On Windows, this would be `Hello.exe`; on Linux or macOS, this would be `hello`.</span></span> <span data-ttu-id="73930-171">Con el ejemplo anterior, el archivo se designa con `Hello.exe` o `Hello`.</span><span class="sxs-lookup"><span data-stu-id="73930-171">With the example above, the file is named with `Hello.exe` or `Hello`.</span></span> <span data-ttu-id="73930-172">Puede ejecutar este archivo ejecutable publicado directamente.</span><span class="sxs-lookup"><span data-stu-id="73930-172">You can run this published executable directly.</span></span>

```console
.\bin\Debug\netcoreapp3.1\Hello.exe

Hello World!
```

## <a name="conclusion"></a><span data-ttu-id="73930-173">Conclusión</span><span class="sxs-lookup"><span data-stu-id="73930-173">Conclusion</span></span>

<span data-ttu-id="73930-174">Y listo.</span><span class="sxs-lookup"><span data-stu-id="73930-174">And that's it!</span></span> <span data-ttu-id="73930-175">Ahora, puede empezar a usar los conceptos básicos que ha aprendido aquí para crear sus propios programas.</span><span class="sxs-lookup"><span data-stu-id="73930-175">Now, you can start using the basic concepts learned here to create your own programs.</span></span>

## <a name="see-also"></a><span data-ttu-id="73930-176">Vea también</span><span class="sxs-lookup"><span data-stu-id="73930-176">See also</span></span>

- [<span data-ttu-id="73930-177">Organización y prueba de proyectos con las herramientas de la CLI de .NET Core</span><span class="sxs-lookup"><span data-stu-id="73930-177">Organizing and testing projects with the .NET Core CLI tools</span></span>](testing-with-cli.md)
- [<span data-ttu-id="73930-178">Publicación de aplicaciones .NET Core con la CLI</span><span class="sxs-lookup"><span data-stu-id="73930-178">Publish .NET Core apps with the CLI</span></span>](../deploying/deploy-with-cli.md)
- [<span data-ttu-id="73930-179">Más información acerca de la implementación</span><span class="sxs-lookup"><span data-stu-id="73930-179">Learn more about app deployment</span></span>](../deploying/index.md)
