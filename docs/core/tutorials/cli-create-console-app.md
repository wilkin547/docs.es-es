---
title: Introducción a .NET Core con la CLI
description: Un tutorial paso a paso que muestra cómo empezar a trabajar con .NET Core en Windows, Linux o macOS con la CLI de .NET Core.
author: thraka
ms.author: adegeo
ms.date: 12/05/2019
ms.technology: dotnet-cli
ms.custom: updateeachrelease
ms.openlocfilehash: 1a691ad0c1f8dbfadd642360d7f9629a136ff3ab
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156665"
---
# <a name="get-started-with-net-core-using-the-net-core-cli"></a><span data-ttu-id="442df-103">Introducción a .NET Core mediante la CLI de .NET Core</span><span class="sxs-lookup"><span data-stu-id="442df-103">Get started with .NET Core using the .NET Core CLI</span></span>

<span data-ttu-id="442df-104">En este artículo se muestra cómo empezar a desarrollar aplicaciones de .NET Core que funcionan en Windows, Linux y macOS mediante la CLI de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="442df-104">This article will show you how to start developing .NET Core apps that work on Windows, Linux, and macOS using the .NET Core CLI.</span></span>

<span data-ttu-id="442df-105">Si no está familiarizado con la CLI de .NET Core, consulte la [información general de la CLI de .NET Core](../tools/index.md).</span><span class="sxs-lookup"><span data-stu-id="442df-105">If you're unfamiliar with the .NET Core CLI, see the [.NET Core CLI overview](../tools/index.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="442df-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="442df-106">Prerequisites</span></span>

- <span data-ttu-id="442df-107">[SDK 3.1 de NET Core](https://dotnet.microsoft.com/download) o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="442df-107">[.NET Core SDK 3.1](https://dotnet.microsoft.com/download) or later versions.</span></span>
- <span data-ttu-id="442df-108">Un editor de texto o un editor de código de su elección.</span><span class="sxs-lookup"><span data-stu-id="442df-108">A text editor or code editor of your choice.</span></span>

## <a name="hello-console-app"></a><span data-ttu-id="442df-109">Hola, aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="442df-109">Hello, Console App!</span></span>

<span data-ttu-id="442df-110">Puede [ver o descargar el código de ejemplo](https://github.com/dotnet/samples/tree/master/core/console-apps/HelloMsBuild) del repositorio dotnet/samples de GitHub.</span><span class="sxs-lookup"><span data-stu-id="442df-110">You can [view or download the sample code](https://github.com/dotnet/samples/tree/master/core/console-apps/HelloMsBuild) from the dotnet/samples GitHub repository.</span></span> <span data-ttu-id="442df-111">Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="442df-111">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

<span data-ttu-id="442df-112">Abra un símbolo del sistema y cree una carpeta denominada *Hello*.</span><span class="sxs-lookup"><span data-stu-id="442df-112">Open a command prompt and create a folder named *Hello*.</span></span> <span data-ttu-id="442df-113">Vaya a la carpeta que ha creado y escriba lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="442df-113">Navigate to the folder you created and type the following.</span></span>

```dotnetcli
dotnet new console
dotnet run
```

<span data-ttu-id="442df-114">Veamos un tutorial rápido:</span><span class="sxs-lookup"><span data-stu-id="442df-114">Let's do a quick walkthrough:</span></span>

01. `dotnet new console`

    <span data-ttu-id="442df-115">[dotnet new](../tools/dotnet-new.md) crea un archivo de proyecto *Hello.csproj* actualizado con las dependencias necesarias para compilar una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="442df-115">[dotnet new](../tools/dotnet-new.md) creates an up-to-date *Hello.csproj* project file with the dependencies necessary to build a console app.</span></span> <span data-ttu-id="442df-116">Además, también crea *Program.cs*, un archivo básico que contiene el punto de entrada para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="442df-116">It also creates a *Program.cs*, a basic file containing the entry point for the application.</span></span>

    <span data-ttu-id="442df-117">*Hello.csproj*:</span><span class="sxs-lookup"><span data-stu-id="442df-117">*Hello.csproj*:</span></span>

    [!code-xml[Hello.csproj](~/samples/core/console-apps/HelloMsBuild/Hello.csproj)]

    <span data-ttu-id="442df-118">El archivo de proyecto especifica todo lo que es necesario para restaurar las dependencias y compilar el programa.</span><span class="sxs-lookup"><span data-stu-id="442df-118">The project file specifies everything that's needed to restore dependencies and build the program.</span></span>

    - <span data-ttu-id="442df-119">El elemento `<OutputType>` especifica que estamos creando un archivo ejecutable, es decir, una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="442df-119">The `<OutputType>` element specifies that we're building an executable, in other words a console application.</span></span>
    - <span data-ttu-id="442df-120">El elemento `<TargetFramework>` especifica el destino de la implementación de .NET.</span><span class="sxs-lookup"><span data-stu-id="442df-120">The `<TargetFramework>` element specifies what .NET implementation we're targeting.</span></span> <span data-ttu-id="442df-121">En un escenario avanzado, con una sola operación puede especificar varios marcos de destino y compilar en todos ellos.</span><span class="sxs-lookup"><span data-stu-id="442df-121">In an advanced scenario, you can specify multiple target frameworks and build to all those in a single operation.</span></span> <span data-ttu-id="442df-122">En este tutorial, nos centraremos en compilar únicamente para .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="442df-122">In this tutorial, we'll stick to building only for .NET Core 3.1.</span></span>

    <span data-ttu-id="442df-123">*Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="442df-123">*Program.cs*:</span></span>

    [!code-csharp[Program.cs](~/samples/core/console-apps/HelloMsBuild/Program.cs)]

    <span data-ttu-id="442df-124">El programa se inicia mediante `using System`, lo que significa "llevar cada cosa del espacio de nombres `System` al ámbito de este archivo".</span><span class="sxs-lookup"><span data-stu-id="442df-124">The program starts by `using System`, which means "bring everything in the `System` namespace into scope for this file".</span></span> <span data-ttu-id="442df-125">El espacio de nombres `System` incluye la clase `Console`.</span><span class="sxs-lookup"><span data-stu-id="442df-125">The `System` namespace includes the `Console` class.</span></span>

    <span data-ttu-id="442df-126">Después, definimos un espacio de nombres denominado `Hello`.</span><span class="sxs-lookup"><span data-stu-id="442df-126">We then define a namespace called `Hello`.</span></span> <span data-ttu-id="442df-127">Puede cambiar esto por cualquier cosa que desee.</span><span class="sxs-lookup"><span data-stu-id="442df-127">You can change this to anything you want.</span></span> <span data-ttu-id="442df-128">Se define una clase denominada `Program` dentro del espacio de nombres, con un método `Main` que toma una matriz de cadenas llamada `args`.</span><span class="sxs-lookup"><span data-stu-id="442df-128">A class named `Program` is defined within that namespace, with a `Main` method that takes an array of strings named `args`.</span></span> <span data-ttu-id="442df-129">Esta matriz contiene la lista de argumentos que se han pasado cuando se ejecuta el programa.</span><span class="sxs-lookup"><span data-stu-id="442df-129">This array contains the list of arguments passed in when the program is run.</span></span> <span data-ttu-id="442df-130">Esta matriz no se usa tal cual y el programa escribe simplemente el texto "¡Hola mundo!".</span><span class="sxs-lookup"><span data-stu-id="442df-130">As it is, this array is not used and the program simply writes the text "Hello World!"</span></span> <span data-ttu-id="442df-131">en la consola.</span><span class="sxs-lookup"><span data-stu-id="442df-131">to the console.</span></span> <span data-ttu-id="442df-132">Después, realizaremos cambios en el código que usará este argumento.</span><span class="sxs-lookup"><span data-stu-id="442df-132">Later, we'll make changes to the code that will make use of this argument.</span></span>

    <span data-ttu-id="442df-133">`dotnet new` llama a [dotnet restore](../tools/dotnet-restore.md) de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="442df-133">`dotnet new` calls [dotnet restore](../tools/dotnet-restore.md) implicitly.</span></span> <span data-ttu-id="442df-134">`dotnet restore` llama a [NuGet](https://www.nuget.org/) (el administrador de paquetes de .NET) para restaurar el árbol de dependencias.</span><span class="sxs-lookup"><span data-stu-id="442df-134">`dotnet restore` calls into [NuGet](https://www.nuget.org/) (.NET package manager) to restore the tree of dependencies.</span></span> <span data-ttu-id="442df-135">NuGet analiza el archivo *Hello.csproj*, descarga las dependencias descritas en el archivo (o las toma de la memoria caché del equipo) y escribe el archivo *obj/project.assets.json*, que es necesario para compilar y ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="442df-135">NuGet analyzes the *Hello.csproj* file, downloads the dependencies defined in the file (or grabs them from a cache on your machine), and writes the *obj/project.assets.json* file, which is necessary to compile and run the sample.</span></span>

02. `dotnet run`

    <span data-ttu-id="442df-136">[dotnet run](../tools/dotnet-run.md) llama a [dotnet build](../tools/dotnet-build.md) para garantizar que se han creado los destinos de compilación y, luego, llama a `dotnet <assembly.dll>` para ejecutar la aplicación de destino.</span><span class="sxs-lookup"><span data-stu-id="442df-136">[dotnet run](../tools/dotnet-run.md) calls [dotnet build](../tools/dotnet-build.md) to ensure that the build targets have been built, and then calls `dotnet <assembly.dll>` to run the target application.</span></span>

    ```dotnetcli
    dotnet run
    ```

    <span data-ttu-id="442df-137">Obtendrá la siguiente salida.</span><span class="sxs-lookup"><span data-stu-id="442df-137">You get the following output.</span></span>

    ```console
    Hello World!
    ```

    <span data-ttu-id="442df-138">También puede ejecutar `dotnet build` para compilar el código sin ejecutar las aplicaciones de consola de compilación.</span><span class="sxs-lookup"><span data-stu-id="442df-138">Alternatively, you can also run `dotnet build` to compile the code without running the build console applications.</span></span> <span data-ttu-id="442df-139">El resultado es una aplicación compilada, como un archivo DLL, basada en el nombre del proyecto.</span><span class="sxs-lookup"><span data-stu-id="442df-139">This results in a compiled application, as a DLL file, based on the name of the project.</span></span> <span data-ttu-id="442df-140">En este caso, el archivo creado se llama *Hello.dll*.</span><span class="sxs-lookup"><span data-stu-id="442df-140">In this case, the file created is named *Hello.dll*.</span></span> <span data-ttu-id="442df-141">Esta aplicación se puede ejecutar con `dotnet bin\Debug\netcoreapp3.1\Hello.dll` en Windows (use `/` con sistemas que no son Windows).</span><span class="sxs-lookup"><span data-stu-id="442df-141">This app can be run with `dotnet bin\Debug\netcoreapp3.1\Hello.dll` on Windows (use `/` for non-Windows systems).</span></span>

    ```dotnetcli
    dotnet bin\Debug\netcoreapp3.1\Hello.dll
    ```

    <span data-ttu-id="442df-142">Obtendrá la siguiente salida.</span><span class="sxs-lookup"><span data-stu-id="442df-142">You get the following output.</span></span>

    ```console
    Hello World!
    ```

    <span data-ttu-id="442df-143">Cuando se compila la aplicación, se crea un archivo ejecutable específico del sistema operativo junto con `Hello.dll`.</span><span class="sxs-lookup"><span data-stu-id="442df-143">When the app is compiled, an operating system-specific executable was created along with the `Hello.dll`.</span></span> <span data-ttu-id="442df-144">En Windows, sería `Hello.exe`; en Linux o macOS, sería `hello`.</span><span class="sxs-lookup"><span data-stu-id="442df-144">On Windows, this would be `Hello.exe`; on Linux or macOS, this would be `hello`.</span></span> <span data-ttu-id="442df-145">Con el ejemplo anterior, el archivo se designa con `Hello.exe` o `Hello`.</span><span class="sxs-lookup"><span data-stu-id="442df-145">With the example above, the file is named with `Hello.exe` or `Hello`.</span></span> <span data-ttu-id="442df-146">Puede ejecutar ese archivo ejecutable directamente.</span><span class="sxs-lookup"><span data-stu-id="442df-146">You can run that executable directly.</span></span>

    ```console
    .\bin\Debug\netcoreapp3.1\Hello.exe

    Hello World!
    ```

## <a name="modify-the-program"></a><span data-ttu-id="442df-147">Modificación del programa</span><span class="sxs-lookup"><span data-stu-id="442df-147">Modify the program</span></span>

<span data-ttu-id="442df-148">Cambiemos un poco el programa.</span><span class="sxs-lookup"><span data-stu-id="442df-148">Let's change the program a bit.</span></span> <span data-ttu-id="442df-149">Los números Fibonacci son divertidos, así que vamos a agregarlos y a usar además el argumento para saludar a la persona que ejecuta la aplicación.</span><span class="sxs-lookup"><span data-stu-id="442df-149">Fibonacci numbers are fun, so let's add that and also to use the argument to greet the person running the app.</span></span>

01. <span data-ttu-id="442df-150">Reemplace el contenido de su archivo *Program.cs* por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="442df-150">Replace the contents of your *Program.cs*  file with the following code:</span></span>

    [!code-csharp[Fibonacci](~/samples/core/console-apps/fibonacci-msbuild/Program.cs)]

02. <span data-ttu-id="442df-151">Ejecute [dotnet build](../tools/dotnet-build.md) para compilar los cambios.</span><span class="sxs-lookup"><span data-stu-id="442df-151">Run [dotnet build](../tools/dotnet-build.md) to compile the changes.</span></span>

03. <span data-ttu-id="442df-152">Para ejecutar el programa, pase un parámetro a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="442df-152">Run the program passing a parameter to the app.</span></span> <span data-ttu-id="442df-153">Cuando use el comando `dotnet` para ejecutar una aplicación, agregue `--` al final.</span><span class="sxs-lookup"><span data-stu-id="442df-153">When you use the `dotnet` command to run an app, add `--` to the end.</span></span> <span data-ttu-id="442df-154">Todo lo que quede a la derecha de `--` se pasará como un parámetro a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="442df-154">Anything to the right of `--` will be passed as a parameter to the app.</span></span> <span data-ttu-id="442df-155">En el ejemplo siguiente, el valor `John` se pasa a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="442df-155">In the following example, the value `John` is passed to the app.</span></span>

    ```dotnetcli
    dotnet run -- John
    ```

    <span data-ttu-id="442df-156">Obtendrá la siguiente salida.</span><span class="sxs-lookup"><span data-stu-id="442df-156">You get the following output.</span></span>

    ```console
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

<span data-ttu-id="442df-157">Y listo.</span><span class="sxs-lookup"><span data-stu-id="442df-157">And that's it!</span></span> <span data-ttu-id="442df-158">Puede modificar *Program.cs* como prefiera.</span><span class="sxs-lookup"><span data-stu-id="442df-158">You can modify *Program.cs* any way you like.</span></span>

## <a name="working-with-multiple-files"></a><span data-ttu-id="442df-159">Trabajar con varios archivos</span><span class="sxs-lookup"><span data-stu-id="442df-159">Working with multiple files</span></span>

<span data-ttu-id="442df-160">Los archivos únicos son adecuados para programas sencillos de uso único, pero, si va a crear una aplicación más compleja, probablemente llegue a tener varios archivos de código en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="442df-160">Single files are fine for simple one-off programs, but if you're building a more complex app, you're probably going to have multiple code files on your project.</span></span> <span data-ttu-id="442df-161">Se compilará sobre el ejemplo de Fibonacci anterior mediante el almacenamiento en caché de algunos valores de Fibonacci y la adición de varias características recursivas.</span><span class="sxs-lookup"><span data-stu-id="442df-161">Let's build off of the previous Fibonacci example by caching some Fibonacci values and add some recursive features.</span></span>

01. <span data-ttu-id="442df-162">Agregue un archivo nuevo dentro del directorio *Hello* denominado *FibonacciGenerator.cs* con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="442df-162">Add a new file inside the *Hello* directory named *FibonacciGenerator.cs* with the following code:</span></span>

    [!code-csharp[Fibonacci Generator](~/samples/core/console-apps/FibonacciBetterMsBuild/FibonacciGenerator.cs)]

02. <span data-ttu-id="442df-163">Cambie el método `Main` en su archivo *Program.cs* para crear una instancia de la nueva clase y llamar a su método como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="442df-163">Change the `Main` method in your *Program.cs* file to instantiate the new class and call its method as in the following example:</span></span>

    [!code-csharp[New Program.cs](~/samples/core/console-apps/FibonacciBetterMsBuild/Program.cs)]

03. <span data-ttu-id="442df-164">Ejecute [dotnet build](../tools/dotnet-build.md) para compilar los cambios.</span><span class="sxs-lookup"><span data-stu-id="442df-164">Run [dotnet build](../tools/dotnet-build.md) to compile the changes.</span></span>

04. <span data-ttu-id="442df-165">Ejecute su aplicación mediante la ejecución de [dotnet run](../tools/dotnet-run.md).</span><span class="sxs-lookup"><span data-stu-id="442df-165">Run your app by executing [dotnet run](../tools/dotnet-run.md).</span></span>

    ```dotnetcli
    dotnet run
    ```

    <span data-ttu-id="442df-166">Obtendrá la siguiente salida.</span><span class="sxs-lookup"><span data-stu-id="442df-166">You get the following output.</span></span>

    ```console
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

## <a name="publish-your-app"></a><span data-ttu-id="442df-167">Publicar la aplicación</span><span class="sxs-lookup"><span data-stu-id="442df-167">Publish your app</span></span>

<span data-ttu-id="442df-168">Cuando esté listo para distribuir la aplicación, use el comando [dotnet publish](../tools/dotnet-publish.md)_para generar la carpeta_publish _en \\bin\\debug\\netcoreapp3.1\\publish_`/` (para sistemas que no son Windows).</span><span class="sxs-lookup"><span data-stu-id="442df-168">Once you're ready to distribute your app, use the [dotnet publish](../tools/dotnet-publish.md) command to generate the _publish_ folder at _bin\\debug\\netcoreapp3.1\\publish\\_ (use `/` for non-Windows systems).</span></span> <span data-ttu-id="442df-169">Puede distribuir el contenido de la carpeta _publish_ en otras plataformas siempre y cuando ya haya instalado el entorno de ejecución de dotnet.</span><span class="sxs-lookup"><span data-stu-id="442df-169">You can distribute the contents of the _publish_ folder to other platforms as long as they've already installed the dotnet runtime.</span></span>

```dotnetcli
dotnet publish
```

<span data-ttu-id="442df-170">Verá un resultado similar al siguiente.</span><span class="sxs-lookup"><span data-stu-id="442df-170">You get output similar to the following.</span></span>

```console
Microsoft (R) Build Engine version 16.4.0+e901037fe for .NET Core
Copyright (C) Microsoft Corporation. All rights reserved.

  Restore completed in 20 ms for C:\Code\Temp\Hello\Hello.csproj.
  Hello -> C:\Code\Temp\Hello\bin\Debug\netcoreapp3.1\Hello.dll
  Hello -> C:\Code\Temp\Hello\bin\Debug\netcoreapp3.1\publish\
```

<span data-ttu-id="442df-171">Puede que la salida anterior no sea igual por la carpeta y el sistema operativo actuales, pero el resultado será parecido.</span><span class="sxs-lookup"><span data-stu-id="442df-171">The output above may differ based on your current folder and operating system, but the output should be similar.</span></span>

<span data-ttu-id="442df-172">Puede ejecutar la aplicación publicada con el comando [dotnet](../tools/dotnet.md):</span><span class="sxs-lookup"><span data-stu-id="442df-172">You can run your published app with the [dotnet](../tools/dotnet.md) command:</span></span>

```dotnetcli
dotnet bin\Debug\netcoreapp3.1\publish\Hello.dll
```

<span data-ttu-id="442df-173">Obtendrá la siguiente salida.</span><span class="sxs-lookup"><span data-stu-id="442df-173">You get the following output.</span></span>

```console
Hello World!
```

<span data-ttu-id="442df-174">Como se ha mencionado al comienzo de este artículo, se ha creado un archivo ejecutable específico del sistema operativo junto con `Hello.dll`.</span><span class="sxs-lookup"><span data-stu-id="442df-174">As mentioned at the start of this article, an operating system-specific executable was created along with the `Hello.dll`.</span></span> <span data-ttu-id="442df-175">En Windows, sería `Hello.exe`; en Linux o macOS, sería `hello`.</span><span class="sxs-lookup"><span data-stu-id="442df-175">On Windows, this would be `Hello.exe`; on Linux or macOS, this would be `hello`.</span></span> <span data-ttu-id="442df-176">Con el ejemplo anterior, el archivo se designa con `Hello.exe` o `Hello`.</span><span class="sxs-lookup"><span data-stu-id="442df-176">With the example above, the file is named with `Hello.exe` or `Hello`.</span></span> <span data-ttu-id="442df-177">Puede ejecutar este archivo ejecutable publicado directamente.</span><span class="sxs-lookup"><span data-stu-id="442df-177">You can run this published executable directly.</span></span>

```console
.\bin\Debug\netcoreapp3.1\publish\Hello.exe

Hello World!
```

## <a name="conclusion"></a><span data-ttu-id="442df-178">Conclusión</span><span class="sxs-lookup"><span data-stu-id="442df-178">Conclusion</span></span>

<span data-ttu-id="442df-179">Y listo.</span><span class="sxs-lookup"><span data-stu-id="442df-179">And that's it!</span></span> <span data-ttu-id="442df-180">Ahora, puede empezar a usar los conceptos básicos que ha aprendido aquí para crear sus propios programas.</span><span class="sxs-lookup"><span data-stu-id="442df-180">Now, you can start using the basic concepts learned here to create your own programs.</span></span>

## <a name="see-also"></a><span data-ttu-id="442df-181">Vea también</span><span class="sxs-lookup"><span data-stu-id="442df-181">See also</span></span>

- [<span data-ttu-id="442df-182">Organización y prueba de proyectos con la CLI de .NET Core</span><span class="sxs-lookup"><span data-stu-id="442df-182">Organizing and testing projects with the .NET Core CLI</span></span>](testing-with-cli.md)
- [<span data-ttu-id="442df-183">Publicación de aplicaciones .NET Core con la CLI de .NET Core</span><span class="sxs-lookup"><span data-stu-id="442df-183">Publish .NET Core apps with the .NET Core CLI</span></span>](../deploying/deploy-with-cli.md)
- [<span data-ttu-id="442df-184">Implementación de aplicaciones .NET Core</span><span class="sxs-lookup"><span data-stu-id="442df-184">.NET Core application deployment</span></span>](../deploying/index.md)
