---
title: Introducción a .NET Core con la CLI
description: Un tutorial paso a paso que muestra cómo empezar a trabajar con .NET Core en Windows, Linux o macOS con la interfaz de la línea de comandos (CLI) de .NET Core.
author: cartermp
ms.date: 09/10/2018
ms.technology: dotnet-cli
ms.custom: seodec18
ms.openlocfilehash: 92ca5149ad5f0e4a50c809a316123fbf77d4152d
ms.sourcegitcommit: 4a8c2b8d0df44142728b68ebc842575840476f6d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2019
ms.locfileid: "58545369"
---
# <a name="get-started-with-net-core-on-windowslinuxmacos-using-the-command-line"></a><span data-ttu-id="3e7cc-103">Introducción a .NET Core en Windows, Linux y macOS con la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="3e7cc-103">Get started with .NET Core on Windows/Linux/macOS using the command line</span></span>

<span data-ttu-id="3e7cc-104">Este tema le mostrará cómo empezar a desarrollar aplicaciones multiplataforma en su equipo con las herramientas de la CLI de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3e7cc-104">This topic will show you how to start developing cross-platforms apps in your machine using the .NET Core CLI tools.</span></span>

<span data-ttu-id="3e7cc-105">Si no está familiarizado con el conjunto de herramientas de la CLI de .NET Core, vea la [información general del SDK de .NET Core](../tools/index.md).</span><span class="sxs-lookup"><span data-stu-id="3e7cc-105">If you're unfamiliar with the .NET Core CLI toolset, read the [.NET Core SDK overview](../tools/index.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3e7cc-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="3e7cc-106">Prerequisites</span></span>

- <span data-ttu-id="3e7cc-107">[SDK de .NET Core 2.1](https://www.microsoft.com/net/download/core).</span><span class="sxs-lookup"><span data-stu-id="3e7cc-107">[.NET Core SDK 2.1](https://www.microsoft.com/net/download/core).</span></span>
- <span data-ttu-id="3e7cc-108">Un editor de texto o un editor de código de su elección.</span><span class="sxs-lookup"><span data-stu-id="3e7cc-108">A text editor or code editor of your choice.</span></span>

## <a name="hello-console-app"></a><span data-ttu-id="3e7cc-109">Hola, aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="3e7cc-109">Hello, Console App!</span></span>

<span data-ttu-id="3e7cc-110">Puede [ver o descargar el código de ejemplo](https://github.com/dotnet/samples/tree/master/core/console-apps/HelloMsBuild) del repositorio dotnet/samples de GitHub.</span><span class="sxs-lookup"><span data-stu-id="3e7cc-110">You can [view or download the sample code](https://github.com/dotnet/samples/tree/master/core/console-apps/HelloMsBuild) from the dotnet/samples GitHub repository.</span></span> <span data-ttu-id="3e7cc-111">Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="3e7cc-111">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

<span data-ttu-id="3e7cc-112">Abra un símbolo del sistema y cree una carpeta denominada *Hello*.</span><span class="sxs-lookup"><span data-stu-id="3e7cc-112">Open a command prompt and create a folder named *Hello*.</span></span> <span data-ttu-id="3e7cc-113">Vaya a la carpeta que ha creado y escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3e7cc-113">Navigate to the folder you created and type the following:</span></span>

```console
dotnet new console
dotnet run
```

<span data-ttu-id="3e7cc-114">Veamos un tutorial rápido:</span><span class="sxs-lookup"><span data-stu-id="3e7cc-114">Let's do a quick walkthrough:</span></span>

1. `dotnet new console`

   <span data-ttu-id="3e7cc-115">[`dotnet new`](../tools/dotnet-new.md) crea un archivo de proyecto `Hello.csproj` actualizado con las dependencias necesarias para compilar una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="3e7cc-115">[`dotnet new`](../tools/dotnet-new.md) creates an up-to-date `Hello.csproj` project file with the dependencies necessary to build a console app.</span></span>  <span data-ttu-id="3e7cc-116">Además, se crea un archivo `Program.cs`, un archivo básico que contiene el punto de entrada para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3e7cc-116">It also creates a `Program.cs`, a basic file containing the entry point for the application.</span></span>

   <span data-ttu-id="3e7cc-117">`Hello.csproj`:</span><span class="sxs-lookup"><span data-stu-id="3e7cc-117">`Hello.csproj`:</span></span>

   [!code[Hello.csproj](../../../samples/core/console-apps/HelloMsBuild/Hello.csproj)]

   <span data-ttu-id="3e7cc-118">El archivo de proyecto especifica todo lo que es necesario para restaurar las dependencias y compilar el programa.</span><span class="sxs-lookup"><span data-stu-id="3e7cc-118">The project file specifies everything that's needed to restore dependencies and build the program.</span></span>

   * <span data-ttu-id="3e7cc-119">La etiqueta `OutputType` especifica que estamos creando un archivo ejecutable, es decir, una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="3e7cc-119">The `OutputType` tag specifies that we're building an executable, in other words a console application.</span></span>
   * <span data-ttu-id="3e7cc-120">La etiqueta `TargetFramework` especifica la implementación .NET a la que nos dirigimos.</span><span class="sxs-lookup"><span data-stu-id="3e7cc-120">The `TargetFramework` tag specifies what .NET implementation we're targeting.</span></span> <span data-ttu-id="3e7cc-121">En un escenario avanzado, con una sola operación puede especificar varios marcos de destino y compilar en todos ellos.</span><span class="sxs-lookup"><span data-stu-id="3e7cc-121">In an advanced scenario, you can specify multiple target frameworks and build to all those in a single operation.</span></span> <span data-ttu-id="3e7cc-122">En este tutorial, nos centraremos en compilar únicamente para .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="3e7cc-122">In this tutorial, we'll stick to building only for .NET Core 2.1.</span></span>

   <span data-ttu-id="3e7cc-123">`Program.cs`:</span><span class="sxs-lookup"><span data-stu-id="3e7cc-123">`Program.cs`:</span></span>

   [!code-csharp[Program.cs](../../../samples/core/console-apps/HelloMsBuild/Program.cs)]

   <span data-ttu-id="3e7cc-124">El programa se inicia mediante `using System`, lo que significa "llevar cada cosa del espacio de nombres `System` al ámbito de este archivo".</span><span class="sxs-lookup"><span data-stu-id="3e7cc-124">The program starts by `using System`, which means "bring everything in the `System` namespace into scope for this file".</span></span> <span data-ttu-id="3e7cc-125">El espacio de nombres `System` incluye construcciones básicas, como `string` o tipos numéricos.</span><span class="sxs-lookup"><span data-stu-id="3e7cc-125">The `System` namespace includes basic constructs such as `string`, or numeric types.</span></span>

   <span data-ttu-id="3e7cc-126">Después, definimos un espacio de nombres denominado `Hello`.</span><span class="sxs-lookup"><span data-stu-id="3e7cc-126">We then define a namespace called `Hello`.</span></span> <span data-ttu-id="3e7cc-127">Puede cambiar esto por cualquier cosa que desee.</span><span class="sxs-lookup"><span data-stu-id="3e7cc-127">You can change this to anything you want.</span></span> <span data-ttu-id="3e7cc-128">Se define una clase denominada `Program` dentro del espacio de nombres, con un método `Main` que toma una matriz de cadenas como argumento.</span><span class="sxs-lookup"><span data-stu-id="3e7cc-128">A class named `Program` is defined within that namespace, with a `Main` method that takes an array of strings as its argument.</span></span> <span data-ttu-id="3e7cc-129">Esta matriz contiene la lista de argumentos que se ha pasado cuando se llama al programa compilado.</span><span class="sxs-lookup"><span data-stu-id="3e7cc-129">This array contains the list of arguments passed in when the compiled program is called.</span></span> <span data-ttu-id="3e7cc-130">Tal y como está, esta matriz no se usa: todo lo que hace el programa es escribir "¡Hola a todos!"</span><span class="sxs-lookup"><span data-stu-id="3e7cc-130">As it is, this array is not used: all the program is doing is to write "Hello World!"</span></span> <span data-ttu-id="3e7cc-131">en la consola.</span><span class="sxs-lookup"><span data-stu-id="3e7cc-131">to the console.</span></span> <span data-ttu-id="3e7cc-132">Después, realizaremos cambios en el código que usará este argumento.</span><span class="sxs-lookup"><span data-stu-id="3e7cc-132">Later, we'll make changes to the code that will make use of this argument.</span></span>

   [!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

   <span data-ttu-id="3e7cc-133">`dotnet new` llama a [`dotnet restore`](../tools/dotnet-restore.md) de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="3e7cc-133">`dotnet new` calls [`dotnet restore`](../tools/dotnet-restore.md) implicitly.</span></span> <span data-ttu-id="3e7cc-134">`dotnet restore` llama a [NuGet](https://www.nuget.org/) (el administrador de paquetes de .NET) para restaurar el árbol de dependencias.</span><span class="sxs-lookup"><span data-stu-id="3e7cc-134">`dotnet restore` calls into [NuGet](https://www.nuget.org/) (.NET package manager) to restore the tree of dependencies.</span></span> <span data-ttu-id="3e7cc-135">NuGet analiza el archivo *Hello.csproj*, descarga las dependencias descritas en el archivo (o las toma de la memoria caché del equipo) y escribe el archivo *obj/project.assets.json*, que es necesario para compilar y ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="3e7cc-135">NuGet analyzes the *Hello.csproj* file, downloads the dependencies defined in the file (or grabs them from a cache on your machine), and writes the *obj/project.assets.json* file, which is necessary to compile and run the sample.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="3e7cc-136">Si usa una versión .NET Core 1.x del SDK, tendrá que llamar a `dotnet restore` usted mismo después de llamar a `dotnet new`.</span><span class="sxs-lookup"><span data-stu-id="3e7cc-136">If you're using a .NET Core 1.x version of the SDK, you'll have to call `dotnet restore` yourself after calling `dotnet new`.</span></span>

2. `dotnet run`

   <span data-ttu-id="3e7cc-137">[`dotnet run`](../tools/dotnet-run.md) llama a [`dotnet build`](../tools/dotnet-build.md) para asegurarse de que los destinos de la compilación se han creado y, después, llama a `dotnet <assembly.dll>` para ejecutar la aplicación de destino.</span><span class="sxs-lookup"><span data-stu-id="3e7cc-137">[`dotnet run`](../tools/dotnet-run.md) calls [`dotnet build`](../tools/dotnet-build.md) to ensure that the build targets have been built, and then calls `dotnet <assembly.dll>` to run the target application.</span></span>

    ```console
    $ dotnet run
    Hello World!
    ```

    <span data-ttu-id="3e7cc-138">También puede ejecutar [`dotnet build`](../tools/dotnet-build.md) para compilar el código sin ejecutar las aplicaciones de consola de compilación.</span><span class="sxs-lookup"><span data-stu-id="3e7cc-138">Alternatively, you can also execute [`dotnet build`](../tools/dotnet-build.md) to compile the code without running the build console applications.</span></span> <span data-ttu-id="3e7cc-139">El resultado es una aplicación compilada como un archivo DLL que se puede ejecutar con `dotnet bin\Debug\netcoreapp2.1\Hello.dll` en Windows (use `/` para otros sistemas que no sean de Windows).</span><span class="sxs-lookup"><span data-stu-id="3e7cc-139">This results in a compiled application as a DLL file that can be run with `dotnet bin\Debug\netcoreapp2.1\Hello.dll` on Windows (use `/` for non-Windows systems).</span></span> <span data-ttu-id="3e7cc-140">También puede especificar argumentos para la aplicación como verá posteriormente en el tema.</span><span class="sxs-lookup"><span data-stu-id="3e7cc-140">You may also specify arguments to the application as you'll see later on the topic.</span></span>

    ```console
    $ dotnet bin\Debug\netcoreapp2.1\Hello.dll
    Hello World!
    ```

    <span data-ttu-id="3e7cc-141">Como escenario avanzado, es posible compilar la aplicación como un conjunto autocontenido de archivos específicos de la plataforma que se puede implementar y ejecutar en una máquina que no tiene necesariamente instalado .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3e7cc-141">As an advanced scenario, it's possible to build the application as a self-contained set of platform-specific files that can be deployed and run to a machine that doesn't necessarily have .NET Core installed.</span></span> <span data-ttu-id="3e7cc-142">Consulte [Implementación de aplicaciones .NET Core](../deploying/index.md) para más información.</span><span class="sxs-lookup"><span data-stu-id="3e7cc-142">See [.NET Core Application Deployment](../deploying/index.md) for details.</span></span>

### <a name="augmenting-the-program"></a><span data-ttu-id="3e7cc-143">Aumento del programa</span><span class="sxs-lookup"><span data-stu-id="3e7cc-143">Augmenting the program</span></span>

<span data-ttu-id="3e7cc-144">Cambiemos un poco el programa.</span><span class="sxs-lookup"><span data-stu-id="3e7cc-144">Let's change the program a bit.</span></span> <span data-ttu-id="3e7cc-145">Los números Fibonacci son divertidos, así que vamos a agregarlos además de usar el argumento para saludar a la persona que ejecuta la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3e7cc-145">Fibonacci numbers are fun, so let's add that in addition to use the argument to greet the person running the app.</span></span>

1. <span data-ttu-id="3e7cc-146">Reemplace el contenido de su archivo *Program.cs* por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="3e7cc-146">Replace the contents of your *Program.cs*  file with the following code:</span></span>

   [!code-csharp[Fibonacci](../../../samples/core/console-apps/fibonacci-msbuild/Program.cs)]

2. <span data-ttu-id="3e7cc-147">Ejecute [`dotnet build`](../tools/dotnet-build.md) para compilar los cambios.</span><span class="sxs-lookup"><span data-stu-id="3e7cc-147">Execute [`dotnet build`](../tools/dotnet-build.md) to compile the changes.</span></span>

3. <span data-ttu-id="3e7cc-148">Ejecute el programa pasando un parámetro a la aplicación:</span><span class="sxs-lookup"><span data-stu-id="3e7cc-148">Run the program passing a parameter to the app:</span></span>

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

<span data-ttu-id="3e7cc-149">Y listo.</span><span class="sxs-lookup"><span data-stu-id="3e7cc-149">And that's it!</span></span>  <span data-ttu-id="3e7cc-150">Puede aumentar `Program.cs` como desee.</span><span class="sxs-lookup"><span data-stu-id="3e7cc-150">You can augment `Program.cs` any way you like.</span></span>

## <a name="working-with-multiple-files"></a><span data-ttu-id="3e7cc-151">Trabajar con varios archivos</span><span class="sxs-lookup"><span data-stu-id="3e7cc-151">Working with multiple files</span></span>

<span data-ttu-id="3e7cc-152">Los archivos únicos son adecuados para programas sencillos de uso único, pero, si va a crear una aplicación más compleja, probablemente tendrá varios archivos de origen en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="3e7cc-152">Single files are fine for simple one-off programs, but if you're building a more complex app, you're probably going to have multiple source files on your project.</span></span>
<span data-ttu-id="3e7cc-153">Se compilará sobre el ejemplo de Fibonacci anterior mediante el almacenamiento en caché de algunos valores de Fibonacci y la adición de varias características recursivas.</span><span class="sxs-lookup"><span data-stu-id="3e7cc-153">Let's build off of the previous Fibonacci example by caching some Fibonacci values and add some recursive features.</span></span>

1. <span data-ttu-id="3e7cc-154">Agregue un archivo nuevo dentro del directorio *Hello* denominado *FibonacciGenerator.cs* con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="3e7cc-154">Add a new file inside the *Hello* directory named *FibonacciGenerator.cs* with the following code:</span></span>

   [!code-csharp[Fibonacci Generator](../../../samples/core/console-apps/FibonacciBetterMsBuild/FibonacciGenerator.cs)]

2. <span data-ttu-id="3e7cc-155">Cambie el método `Main` en su archivo *Program.cs* para crear una instancia de la nueva clase y llamar a su método como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3e7cc-155">Change the `Main` method in your *Program.cs* file to instantiate the new class and call its method as in the following example:</span></span>

   [!code-csharp[New Program.cs](../../../samples/core/console-apps/FibonacciBetterMsBuild/Program.cs)]

3. <span data-ttu-id="3e7cc-156">Ejecute [`dotnet build`](../tools/dotnet-build.md) para compilar los cambios.</span><span class="sxs-lookup"><span data-stu-id="3e7cc-156">Execute [`dotnet build`](../tools/dotnet-build.md) to compile the changes.</span></span>

4. <span data-ttu-id="3e7cc-157">Ejecute su aplicación con la ejecución de [`dotnet run`](../tools/dotnet-run.md).</span><span class="sxs-lookup"><span data-stu-id="3e7cc-157">Run your app by executing [`dotnet run`](../tools/dotnet-run.md).</span></span> <span data-ttu-id="3e7cc-158">A continuación se muestra el resultado del programa:</span><span class="sxs-lookup"><span data-stu-id="3e7cc-158">The following shows the program output:</span></span>

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

<span data-ttu-id="3e7cc-159">Y listo.</span><span class="sxs-lookup"><span data-stu-id="3e7cc-159">And that's it!</span></span> <span data-ttu-id="3e7cc-160">Ahora, puede empezar a usar los conceptos básicos que ha aprendido aquí para crear sus propios programas.</span><span class="sxs-lookup"><span data-stu-id="3e7cc-160">Now, you can start using the basic concepts learned here to create your own programs.</span></span>

<span data-ttu-id="3e7cc-161">Tenga en cuenta que los comandos y los pasos que se muestran en este tutorial para ejecutar la aplicación se usan solo durante el desarrollo.</span><span class="sxs-lookup"><span data-stu-id="3e7cc-161">Note that the commands and steps shown in this tutorial to run your application are used during development time only.</span></span> <span data-ttu-id="3e7cc-162">Una vez que esté listo para implementar la aplicación, querrá echar un vistazo a las diferentes [estrategias de implementación](../deploying/index.md) para aplicaciones de .NET Core y al comando [`dotnet publish`](../tools/dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="3e7cc-162">Once you're ready to deploy your app, you'll want to take a look at the different [deployment strategies](../deploying/index.md) for .NET Core apps and the [`dotnet publish`](../tools/dotnet-publish.md) command.</span></span>

## <a name="see-also"></a><span data-ttu-id="3e7cc-163">Vea también</span><span class="sxs-lookup"><span data-stu-id="3e7cc-163">See also</span></span>

- [<span data-ttu-id="3e7cc-164">Organización y prueba de proyectos con las herramientas de la CLI de .NET Core</span><span class="sxs-lookup"><span data-stu-id="3e7cc-164">Organizing and testing projects with the .NET Core CLI tools</span></span>](testing-with-cli.md)
