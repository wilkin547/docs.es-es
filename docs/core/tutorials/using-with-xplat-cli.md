---
title: Introducción a .NET Core con la CLI
description: Un tutorial paso a paso que muestra cómo empezar a trabajar con .NET Core en Windows, Linux o macOS con la interfaz de la línea de comandos (CLI) de .NET Core.
author: thraka
ms.author: adegeo
ms.date: 08/07/2019
ms.technology: dotnet-cli
ms.custom: seodec18
ms.openlocfilehash: 88e9501a776a026a311c5002674c15acf2324f2b
ms.sourcegitcommit: 9ee6cd851b6e176a5811ea28ed0d5935c71950f9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/09/2019
ms.locfileid: "68868588"
---
# <a name="get-started-with-net-core-on-windowslinuxmacos-using-the-command-line"></a><span data-ttu-id="3a4ca-103">Introducción a .NET Core en Windows, Linux y macOS con la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="3a4ca-103">Get started with .NET Core on Windows/Linux/macOS using the command line</span></span>

<span data-ttu-id="3a4ca-104">Este tema le mostrará cómo empezar a desarrollar aplicaciones multiplataforma en su equipo con las herramientas de la CLI de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3a4ca-104">This topic will show you how to start developing cross-platforms apps in your machine using the .NET Core CLI tools.</span></span>

<span data-ttu-id="3a4ca-105">Si no está familiarizado con el conjunto de herramientas de la CLI de .NET Core, vea la [información general del SDK de .NET Core](../tools/index.md).</span><span class="sxs-lookup"><span data-stu-id="3a4ca-105">If you're unfamiliar with the .NET Core CLI toolset, read the [.NET Core SDK overview](../tools/index.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3a4ca-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="3a4ca-106">Prerequisites</span></span>

- <span data-ttu-id="3a4ca-107">[SDK de .NET Core 2.1](https://www.microsoft.com/net/download/core).</span><span class="sxs-lookup"><span data-stu-id="3a4ca-107">[.NET Core SDK 2.1](https://www.microsoft.com/net/download/core).</span></span>
- <span data-ttu-id="3a4ca-108">Un editor de texto o un editor de código de su elección.</span><span class="sxs-lookup"><span data-stu-id="3a4ca-108">A text editor or code editor of your choice.</span></span>

## <a name="hello-console-app"></a><span data-ttu-id="3a4ca-109">Hola, aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="3a4ca-109">Hello, Console App!</span></span>

<span data-ttu-id="3a4ca-110">Puede [ver o descargar el código de ejemplo](https://github.com/dotnet/samples/tree/master/core/console-apps/HelloMsBuild) del repositorio dotnet/samples de GitHub.</span><span class="sxs-lookup"><span data-stu-id="3a4ca-110">You can [view or download the sample code](https://github.com/dotnet/samples/tree/master/core/console-apps/HelloMsBuild) from the dotnet/samples GitHub repository.</span></span> <span data-ttu-id="3a4ca-111">Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="3a4ca-111">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

<span data-ttu-id="3a4ca-112">Abra un símbolo del sistema y cree una carpeta denominada *Hello*.</span><span class="sxs-lookup"><span data-stu-id="3a4ca-112">Open a command prompt and create a folder named *Hello*.</span></span> <span data-ttu-id="3a4ca-113">Vaya a la carpeta que ha creado y escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3a4ca-113">Navigate to the folder you created and type the following:</span></span>

```console
dotnet new console
dotnet run
```

<span data-ttu-id="3a4ca-114">Veamos un tutorial rápido:</span><span class="sxs-lookup"><span data-stu-id="3a4ca-114">Let's do a quick walkthrough:</span></span>

1. `dotnet new console`

   <span data-ttu-id="3a4ca-115">[`dotnet new`](../tools/dotnet-new.md) crea un archivo de proyecto `Hello.csproj` actualizado con las dependencias necesarias para compilar una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="3a4ca-115">[`dotnet new`](../tools/dotnet-new.md) creates an up-to-date `Hello.csproj` project file with the dependencies necessary to build a console app.</span></span>  <span data-ttu-id="3a4ca-116">Además, se crea un archivo `Program.cs`, un archivo básico que contiene el punto de entrada para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3a4ca-116">It also creates a `Program.cs`, a basic file containing the entry point for the application.</span></span>

   <span data-ttu-id="3a4ca-117">`Hello.csproj`:</span><span class="sxs-lookup"><span data-stu-id="3a4ca-117">`Hello.csproj`:</span></span>

   [!code[Hello.csproj](../../../samples/core/console-apps/HelloMsBuild/Hello.csproj)]

   <span data-ttu-id="3a4ca-118">El archivo de proyecto especifica todo lo que es necesario para restaurar las dependencias y compilar el programa.</span><span class="sxs-lookup"><span data-stu-id="3a4ca-118">The project file specifies everything that's needed to restore dependencies and build the program.</span></span>

   * <span data-ttu-id="3a4ca-119">La etiqueta `OutputType` especifica que estamos creando un archivo ejecutable, es decir, una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="3a4ca-119">The `OutputType` tag specifies that we're building an executable, in other words a console application.</span></span>
   * <span data-ttu-id="3a4ca-120">La etiqueta `TargetFramework` especifica la implementación .NET a la que nos dirigimos.</span><span class="sxs-lookup"><span data-stu-id="3a4ca-120">The `TargetFramework` tag specifies what .NET implementation we're targeting.</span></span> <span data-ttu-id="3a4ca-121">En un escenario avanzado, con una sola operación puede especificar varios marcos de destino y compilar en todos ellos.</span><span class="sxs-lookup"><span data-stu-id="3a4ca-121">In an advanced scenario, you can specify multiple target frameworks and build to all those in a single operation.</span></span> <span data-ttu-id="3a4ca-122">En este tutorial, nos centraremos en compilar únicamente para .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="3a4ca-122">In this tutorial, we'll stick to building only for .NET Core 2.1.</span></span>

   <span data-ttu-id="3a4ca-123">`Program.cs`:</span><span class="sxs-lookup"><span data-stu-id="3a4ca-123">`Program.cs`:</span></span>

   [!code-csharp[Program.cs](../../../samples/core/console-apps/HelloMsBuild/Program.cs)]

   <span data-ttu-id="3a4ca-124">El programa se inicia mediante `using System`, lo que significa "llevar cada cosa del espacio de nombres `System` al ámbito de este archivo".</span><span class="sxs-lookup"><span data-stu-id="3a4ca-124">The program starts by `using System`, which means "bring everything in the `System` namespace into scope for this file".</span></span> <span data-ttu-id="3a4ca-125">El espacio de nombres `System` incluye construcciones básicas, como `string` o tipos numéricos.</span><span class="sxs-lookup"><span data-stu-id="3a4ca-125">The `System` namespace includes basic constructs such as `string`, or numeric types.</span></span>

   <span data-ttu-id="3a4ca-126">Después, definimos un espacio de nombres denominado `Hello`.</span><span class="sxs-lookup"><span data-stu-id="3a4ca-126">We then define a namespace called `Hello`.</span></span> <span data-ttu-id="3a4ca-127">Puede cambiar esto por cualquier cosa que desee.</span><span class="sxs-lookup"><span data-stu-id="3a4ca-127">You can change this to anything you want.</span></span> <span data-ttu-id="3a4ca-128">Se define una clase denominada `Program` dentro del espacio de nombres, con un método `Main` que toma una matriz de cadenas como argumento.</span><span class="sxs-lookup"><span data-stu-id="3a4ca-128">A class named `Program` is defined within that namespace, with a `Main` method that takes an array of strings as its argument.</span></span> <span data-ttu-id="3a4ca-129">Esta matriz contiene la lista de argumentos que se ha pasado cuando se llama al programa compilado.</span><span class="sxs-lookup"><span data-stu-id="3a4ca-129">This array contains the list of arguments passed in when the compiled program is called.</span></span> <span data-ttu-id="3a4ca-130">Tal y como está, esta matriz no se usa: todo lo que hace el programa es escribir "¡Hola a todos!"</span><span class="sxs-lookup"><span data-stu-id="3a4ca-130">As it is, this array is not used: all the program is doing is to write "Hello World!"</span></span> <span data-ttu-id="3a4ca-131">en la consola.</span><span class="sxs-lookup"><span data-stu-id="3a4ca-131">to the console.</span></span> <span data-ttu-id="3a4ca-132">Después, realizaremos cambios en el código que usará este argumento.</span><span class="sxs-lookup"><span data-stu-id="3a4ca-132">Later, we'll make changes to the code that will make use of this argument.</span></span>

   [!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

   <span data-ttu-id="3a4ca-133">`dotnet new` llama a [`dotnet restore`](../tools/dotnet-restore.md) de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="3a4ca-133">`dotnet new` calls [`dotnet restore`](../tools/dotnet-restore.md) implicitly.</span></span> <span data-ttu-id="3a4ca-134">`dotnet restore` llama a [NuGet](https://www.nuget.org/) (el administrador de paquetes de .NET) para restaurar el árbol de dependencias.</span><span class="sxs-lookup"><span data-stu-id="3a4ca-134">`dotnet restore` calls into [NuGet](https://www.nuget.org/) (.NET package manager) to restore the tree of dependencies.</span></span> <span data-ttu-id="3a4ca-135">NuGet analiza el archivo *Hello.csproj*, descarga las dependencias descritas en el archivo (o las toma de la memoria caché del equipo) y escribe el archivo *obj/project.assets.json*, que es necesario para compilar y ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="3a4ca-135">NuGet analyzes the *Hello.csproj* file, downloads the dependencies defined in the file (or grabs them from a cache on your machine), and writes the *obj/project.assets.json* file, which is necessary to compile and run the sample.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="3a4ca-136">Si usa una versión .NET Core 1.x del SDK, tendrá que llamar a `dotnet restore` usted mismo después de llamar a `dotnet new`.</span><span class="sxs-lookup"><span data-stu-id="3a4ca-136">If you're using a .NET Core 1.x version of the SDK, you'll have to call `dotnet restore` yourself after calling `dotnet new`.</span></span>

2. `dotnet run`

   <span data-ttu-id="3a4ca-137">[`dotnet run`](../tools/dotnet-run.md) llama a [`dotnet build`](../tools/dotnet-build.md) para asegurarse de que los destinos de la compilación se han creado y, después, llama a `dotnet <assembly.dll>` para ejecutar la aplicación de destino.</span><span class="sxs-lookup"><span data-stu-id="3a4ca-137">[`dotnet run`](../tools/dotnet-run.md) calls [`dotnet build`](../tools/dotnet-build.md) to ensure that the build targets have been built, and then calls `dotnet <assembly.dll>` to run the target application.</span></span>

    ```console
    $ dotnet run
    Hello World!
    ```

    <span data-ttu-id="3a4ca-138">También puede ejecutar [`dotnet build`](../tools/dotnet-build.md) para compilar el código sin ejecutar las aplicaciones de consola de compilación.</span><span class="sxs-lookup"><span data-stu-id="3a4ca-138">Alternatively, you can also execute [`dotnet build`](../tools/dotnet-build.md) to compile the code without running the build console applications.</span></span> <span data-ttu-id="3a4ca-139">El resultado es una aplicación compilada como un archivo DLL que se puede ejecutar con `dotnet bin\Debug\netcoreapp2.1\Hello.dll` en Windows (use `/` para otros sistemas que no sean de Windows).</span><span class="sxs-lookup"><span data-stu-id="3a4ca-139">This results in a compiled application as a DLL file that can be run with `dotnet bin\Debug\netcoreapp2.1\Hello.dll` on Windows (use `/` for non-Windows systems).</span></span> <span data-ttu-id="3a4ca-140">También puede especificar argumentos para la aplicación como verá posteriormente en el tema.</span><span class="sxs-lookup"><span data-stu-id="3a4ca-140">You may also specify arguments to the application as you'll see later on the topic.</span></span>

    ```console
    $ dotnet bin\Debug\netcoreapp2.1\Hello.dll
    Hello World!
    ```

    <span data-ttu-id="3a4ca-141">Como escenario avanzado, es posible compilar la aplicación como un conjunto autocontenido de archivos específicos de la plataforma que se puede implementar y ejecutar en una máquina que no tiene necesariamente instalado .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3a4ca-141">As an advanced scenario, it's possible to build the application as a self-contained set of platform-specific files that can be deployed and run to a machine that doesn't necessarily have .NET Core installed.</span></span> <span data-ttu-id="3a4ca-142">Consulte [Implementación de aplicaciones .NET Core](../deploying/index.md) para más información.</span><span class="sxs-lookup"><span data-stu-id="3a4ca-142">See [.NET Core Application Deployment](../deploying/index.md) for details.</span></span>

### <a name="augmenting-the-program"></a><span data-ttu-id="3a4ca-143">Aumento del programa</span><span class="sxs-lookup"><span data-stu-id="3a4ca-143">Augmenting the program</span></span>

<span data-ttu-id="3a4ca-144">Cambiemos un poco el programa.</span><span class="sxs-lookup"><span data-stu-id="3a4ca-144">Let's change the program a bit.</span></span> <span data-ttu-id="3a4ca-145">Los números Fibonacci son divertidos, así que vamos a agregarlos además de usar el argumento para saludar a la persona que ejecuta la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3a4ca-145">Fibonacci numbers are fun, so let's add that in addition to use the argument to greet the person running the app.</span></span>

1. <span data-ttu-id="3a4ca-146">Reemplace el contenido de su archivo *Program.cs* por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="3a4ca-146">Replace the contents of your *Program.cs*  file with the following code:</span></span>

   [!code-csharp[Fibonacci](../../../samples/core/console-apps/fibonacci-msbuild/Program.cs)]

2. <span data-ttu-id="3a4ca-147">Ejecute [`dotnet build`](../tools/dotnet-build.md) para compilar los cambios.</span><span class="sxs-lookup"><span data-stu-id="3a4ca-147">Execute [`dotnet build`](../tools/dotnet-build.md) to compile the changes.</span></span>

3. <span data-ttu-id="3a4ca-148">Ejecute el programa pasando un parámetro a la aplicación:</span><span class="sxs-lookup"><span data-stu-id="3a4ca-148">Run the program passing a parameter to the app:</span></span>

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

<span data-ttu-id="3a4ca-149">Y listo.</span><span class="sxs-lookup"><span data-stu-id="3a4ca-149">And that's it!</span></span>  <span data-ttu-id="3a4ca-150">Puede aumentar `Program.cs` como desee.</span><span class="sxs-lookup"><span data-stu-id="3a4ca-150">You can augment `Program.cs` any way you like.</span></span>

## <a name="working-with-multiple-files"></a><span data-ttu-id="3a4ca-151">Trabajar con varios archivos</span><span class="sxs-lookup"><span data-stu-id="3a4ca-151">Working with multiple files</span></span>

<span data-ttu-id="3a4ca-152">Los archivos únicos son adecuados para programas sencillos de uso único, pero, si va a crear una aplicación más compleja, probablemente tendrá varios archivos de origen en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="3a4ca-152">Single files are fine for simple one-off programs, but if you're building a more complex app, you're probably going to have multiple source files on your project.</span></span>
<span data-ttu-id="3a4ca-153">Se compilará sobre el ejemplo de Fibonacci anterior mediante el almacenamiento en caché de algunos valores de Fibonacci y la adición de varias características recursivas.</span><span class="sxs-lookup"><span data-stu-id="3a4ca-153">Let's build off of the previous Fibonacci example by caching some Fibonacci values and add some recursive features.</span></span>

1. <span data-ttu-id="3a4ca-154">Agregue un archivo nuevo dentro del directorio *Hello* denominado *FibonacciGenerator.cs* con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="3a4ca-154">Add a new file inside the *Hello* directory named *FibonacciGenerator.cs* with the following code:</span></span>

   [!code-csharp[Fibonacci Generator](../../../samples/core/console-apps/FibonacciBetterMsBuild/FibonacciGenerator.cs)]

2. <span data-ttu-id="3a4ca-155">Cambie el método `Main` en su archivo *Program.cs* para crear una instancia de la nueva clase y llamar a su método como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3a4ca-155">Change the `Main` method in your *Program.cs* file to instantiate the new class and call its method as in the following example:</span></span>

   [!code-csharp[New Program.cs](../../../samples/core/console-apps/FibonacciBetterMsBuild/Program.cs)]

3. <span data-ttu-id="3a4ca-156">Ejecute [`dotnet build`](../tools/dotnet-build.md) para compilar los cambios.</span><span class="sxs-lookup"><span data-stu-id="3a4ca-156">Execute [`dotnet build`](../tools/dotnet-build.md) to compile the changes.</span></span>

4. <span data-ttu-id="3a4ca-157">Ejecute su aplicación con la ejecución de [`dotnet run`](../tools/dotnet-run.md).</span><span class="sxs-lookup"><span data-stu-id="3a4ca-157">Run your app by executing [`dotnet run`](../tools/dotnet-run.md).</span></span> <span data-ttu-id="3a4ca-158">A continuación se muestra el resultado del programa:</span><span class="sxs-lookup"><span data-stu-id="3a4ca-158">The following shows the program output:</span></span>

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

## <a name="publish-your-app"></a><span data-ttu-id="3a4ca-159">Publicación de la aplicación</span><span class="sxs-lookup"><span data-stu-id="3a4ca-159">Publish your app</span></span>

<span data-ttu-id="3a4ca-160">Una vez que esté listo para distribuir la aplicación, use el comando [`dotnet publish`](../tools/dotnet-publish.md) para generar la carpeta _publish_ en _bin\\debug\\netcoreapp2.1\\publish\\_ (utilice `/` para sistemas que no son de Windows).</span><span class="sxs-lookup"><span data-stu-id="3a4ca-160">Once you're ready to distribute your app, use the [`dotnet publish`](../tools/dotnet-publish.md) command to generate the _publish_ folder at _bin\\debug\\netcoreapp2.1\\publish\\_ (use `/` for non-Windows systems).</span></span> <span data-ttu-id="3a4ca-161">Puede distribuir el contenido de la carpeta _publish_ en otras plataformas siempre y cuando ya haya instalado el entorno de ejecución de dotnet.</span><span class="sxs-lookup"><span data-stu-id="3a4ca-161">You can distribute the contents of the _publish_ folder to other platforms as long as they've already installed the dotnet runtime.</span></span>

<span data-ttu-id="3a4ca-162">Puede ejecutar la aplicación publicada con el comando [dotnet](../tools/dotnet.md):</span><span class="sxs-lookup"><span data-stu-id="3a4ca-162">You can run your published app with the [dotnet](../tools/dotnet.md) command:</span></span>

```console
$ dotnet bin\Debug\netcoreapp2.1\publish\Hello.dll
Hello World!
```

## <a name="conclusion"></a><span data-ttu-id="3a4ca-163">Conclusión</span><span class="sxs-lookup"><span data-stu-id="3a4ca-163">Conclusion</span></span>

<span data-ttu-id="3a4ca-164">Y listo.</span><span class="sxs-lookup"><span data-stu-id="3a4ca-164">And that's it!</span></span> <span data-ttu-id="3a4ca-165">Ahora, puede empezar a usar los conceptos básicos que ha aprendido aquí para crear sus propios programas.</span><span class="sxs-lookup"><span data-stu-id="3a4ca-165">Now, you can start using the basic concepts learned here to create your own programs.</span></span>

## <a name="see-also"></a><span data-ttu-id="3a4ca-166">Vea también</span><span class="sxs-lookup"><span data-stu-id="3a4ca-166">See also</span></span>

- [<span data-ttu-id="3a4ca-167">Organización y prueba de proyectos con las herramientas de la CLI de .NET Core</span><span class="sxs-lookup"><span data-stu-id="3a4ca-167">Organizing and testing projects with the .NET Core CLI tools</span></span>](testing-with-cli.md)
- [<span data-ttu-id="3a4ca-168">Publicación de aplicaciones .NET Core con la CLI</span><span class="sxs-lookup"><span data-stu-id="3a4ca-168">Publish .NET Core apps with the CLI</span></span>](../deploying/deploy-with-cli.md)
- [<span data-ttu-id="3a4ca-169">Más información acerca de la implementación</span><span class="sxs-lookup"><span data-stu-id="3a4ca-169">Learn more about app deployment</span></span>](../deploying/index.md)
