---
title: Introducción a .NET Core en macOS
description: En este documento se proporcionan los pasos y el flujo de trabajo para crear una solución de .NET Core con Visual Studio Code.
author: bleroy
ms.date: 03/23/2017
ms.custom: seodec18
ms.openlocfilehash: e79f5dd90124d2a1902194af2edbde0f5df107c7
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633975"
---
# <a name="get-started-with-net-core-on-macos"></a><span data-ttu-id="61e3c-103">Introducción a .NET Core en macOS</span><span class="sxs-lookup"><span data-stu-id="61e3c-103">Get started with .NET Core on macOS</span></span>

<span data-ttu-id="61e3c-104">En este documento se proporcionan los pasos y el flujo de trabajo para crear una solución de .NET Core para macOS.</span><span class="sxs-lookup"><span data-stu-id="61e3c-104">This document provides the steps and workflow to create a .NET Core solution for macOS.</span></span> <span data-ttu-id="61e3c-105">Obtendrá información sobre cómo crear proyectos, pruebas unitarias, usar las herramientas de depuración e incorporar bibliotecas de terceros a través de [NuGet](https://www.nuget.org/).</span><span class="sxs-lookup"><span data-stu-id="61e3c-105">Learn how to create projects, unit tests, use the debugging tools, and incorporate third-party libraries via [NuGet](https://www.nuget.org/).</span></span>

> [!NOTE]
> <span data-ttu-id="61e3c-106">En este artículo se usa [Visual Studio Code](https://code.visualstudio.com) en macOS.</span><span class="sxs-lookup"><span data-stu-id="61e3c-106">This article uses [Visual Studio Code](https://code.visualstudio.com) on macOS.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="61e3c-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="61e3c-107">Prerequisites</span></span>

<span data-ttu-id="61e3c-108">Instale el [SDK de .NET Core](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="61e3c-108">Install the [.NET Core SDK](https://www.microsoft.com/net/core).</span></span> <span data-ttu-id="61e3c-109">El SDK de .NET Core incluye la última versión de la plataforma de .NET Core y el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="61e3c-109">The .NET Core SDK includes the latest release of the .NET Core framework and runtime.</span></span>

<span data-ttu-id="61e3c-110">Instale [Visual Studio Code](https://code.visualstudio.com).</span><span class="sxs-lookup"><span data-stu-id="61e3c-110">Install [Visual Studio Code](https://code.visualstudio.com).</span></span> <span data-ttu-id="61e3c-111">Durante el transcurso de este artículo, también instalará las extensiones de Visual Studio Code que mejoran la experiencia de desarrollo de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="61e3c-111">During the course of this article, you also install Visual Studio Code extensions that improve the .NET Core development experience.</span></span>

<span data-ttu-id="61e3c-112">Instale la extensión de C# de Visual Studio Code; para ello, abra Visual Studio Code y presione <kbd>F1</kbd> para abrir la paleta de Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="61e3c-112">Install the Visual Studio Code C# extension by opening Visual Studio Code and pressing <kbd>F1</kbd> to open the Visual Studio Code palette.</span></span> <span data-ttu-id="61e3c-113">Escriba **ext install** para ver la lista de extensiones.</span><span class="sxs-lookup"><span data-stu-id="61e3c-113">Type **ext install** to see the list of extensions.</span></span> <span data-ttu-id="61e3c-114">Seleccione la extensión de C#.</span><span class="sxs-lookup"><span data-stu-id="61e3c-114">Select the C# extension.</span></span> <span data-ttu-id="61e3c-115">Reinicie Visual Studio Code para activar la extensión.</span><span class="sxs-lookup"><span data-stu-id="61e3c-115">Restart Visual Studio Code to activate the extension.</span></span> <span data-ttu-id="61e3c-116">Para obtener más información, vea la [documentación de la extensión de C# en Visual Studio Code](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).</span><span class="sxs-lookup"><span data-stu-id="61e3c-116">For more information, see the [Visual Studio Code C# Extension documentation](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).</span></span>

## <a name="get-started"></a><span data-ttu-id="61e3c-117">Primeros pasos</span><span class="sxs-lookup"><span data-stu-id="61e3c-117">Get started</span></span>

<span data-ttu-id="61e3c-118">En este tutorial, creará tres proyectos: un proyecto de biblioteca, pruebas para ese proyecto de biblioteca y una aplicación de consola que usa la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="61e3c-118">In this tutorial, you create three projects: a library project, tests for that library project, and a console application that makes use of the library.</span></span> <span data-ttu-id="61e3c-119">Puede [ver o descargar el origen](https://github.com/dotnet/samples/tree/master/core/getting-started/golden) de este tema en el repositorio dotnet/samples de GitHub.</span><span class="sxs-lookup"><span data-stu-id="61e3c-119">You can [view or download the source](https://github.com/dotnet/samples/tree/master/core/getting-started/golden) for this topic at the dotnet/samples repository on GitHub.</span></span> <span data-ttu-id="61e3c-120">Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="61e3c-120">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

<span data-ttu-id="61e3c-121">Inicie Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="61e3c-121">Start Visual Studio Code.</span></span> <span data-ttu-id="61e3c-122">Presione <kbd>Ctrl</kbd>+<kbd>\`</kbd> (el carácter de comilla inversa o tilde aguda) o seleccione **Ver > Terminal integrado** desde el menú para abrir un terminal insertado en Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="61e3c-122">Press <kbd>Ctrl</kbd>+<kbd>\`</kbd> (the backquote or backtick character) or select **View > Integrated Terminal** from the menu to open an embedded terminal in Visual Studio Code.</span></span> <span data-ttu-id="61e3c-123">Todavía puede abrir un shell externo con el comando **Abrir en símbolo del sistema** del Explorador (**Abrir en terminal** en Mac o Linux) si prefiere trabajar fuera de Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="61e3c-123">You can still open an external shell with the Explorer **Open in Command Prompt** command (**Open in Terminal** on Mac or Linux) if you prefer to work outside of Visual Studio Code.</span></span>

<span data-ttu-id="61e3c-124">Comience creando un archivo de solución, que actúa como un contenedor para uno o más proyectos de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="61e3c-124">Begin by creating a solution file, which serves as a container for one or more .NET Core projects.</span></span> <span data-ttu-id="61e3c-125">En el terminal, cree una carpeta *golden* y abra la carpeta.</span><span class="sxs-lookup"><span data-stu-id="61e3c-125">In the terminal, create a *golden* folder and open the folder.</span></span> <span data-ttu-id="61e3c-126">Esta carpeta es la raíz de la solución.</span><span class="sxs-lookup"><span data-stu-id="61e3c-126">This folder is the root of your solution.</span></span> <span data-ttu-id="61e3c-127">Ejecute el comando [`dotnet new`](../tools/dotnet-new.md) para crear una nueva solución, *golden.sln*:</span><span class="sxs-lookup"><span data-stu-id="61e3c-127">Run the [`dotnet new`](../tools/dotnet-new.md) command to create a new solution, *golden.sln*:</span></span>

```console
dotnet new sln
```

<span data-ttu-id="61e3c-128">Desde la carpeta *golden*, ejecute el siguiente comando para crear un proyecto de biblioteca, que produce dos archivos, *library.csproj* y *Class1.cs*, en la carpeta *library*:</span><span class="sxs-lookup"><span data-stu-id="61e3c-128">From the *golden* folder, execute the following command to create a library project, which produces two files,*library.csproj* and *Class1.cs*, in the *library* folder:</span></span>

```console
dotnet new classlib -o library
```

<span data-ttu-id="61e3c-129">Ejecute el comando [`dotnet sln`](../tools/dotnet-sln.md) para agregar el proyecto *library.csproj* recién creado a la solución:</span><span class="sxs-lookup"><span data-stu-id="61e3c-129">Execute the [`dotnet sln`](../tools/dotnet-sln.md) command to add the newly created *library.csproj* project to the solution:</span></span>

```console
dotnet sln add library/library.csproj
```

<span data-ttu-id="61e3c-130">El archivo *library.csproj* contiene la información siguiente:</span><span class="sxs-lookup"><span data-stu-id="61e3c-130">The *library.csproj* file contains the following information:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFramework>netstandard1.4</TargetFramework>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="61e3c-131">Nuestros métodos de biblioteca serializan y deserializan objetos en formato JSON.</span><span class="sxs-lookup"><span data-stu-id="61e3c-131">Our library methods serialize and deserialize objects in JSON format.</span></span> <span data-ttu-id="61e3c-132">Para admitir la serialización y deserialización JSON, agregue una referencia al paquete NuGet `Newtonsoft.Json`.</span><span class="sxs-lookup"><span data-stu-id="61e3c-132">To support JSON serialization and deserialization, add a reference to the `Newtonsoft.Json` NuGet package.</span></span> <span data-ttu-id="61e3c-133">El comando `dotnet add` agrega elementos nuevos a un proyecto.</span><span class="sxs-lookup"><span data-stu-id="61e3c-133">The `dotnet add` command adds new items to a project.</span></span> <span data-ttu-id="61e3c-134">Para agregar una referencia a un paquete NuGet, use el comando [`dotnet add package`](../tools/dotnet-add-package.md) y especifique el nombre del paquete:</span><span class="sxs-lookup"><span data-stu-id="61e3c-134">To add a reference to a NuGet package, use the [`dotnet add package`](../tools/dotnet-add-package.md) command and specify the name of the package:</span></span>

```console
dotnet add library package Newtonsoft.Json
```

<span data-ttu-id="61e3c-135">Esto agrega `Newtonsoft.Json` y sus dependencias al proyecto de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="61e3c-135">This adds `Newtonsoft.Json` and its dependencies to the library project.</span></span> <span data-ttu-id="61e3c-136">De manera alternativa, edite manualmente el archivo *library.csproj* y agregue el nodo siguiente:</span><span class="sxs-lookup"><span data-stu-id="61e3c-136">Alternatively, manually edit the *library.csproj* file and add the following node:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Newtonsoft.Json" Version="10.0.1" />
</ItemGroup>
```

<span data-ttu-id="61e3c-137">Ejecute [`dotnet restore`](../tools/dotnet-restore.md) ([vea la nota](#dotnet-restore-note)), lo que restaura las dependencias y crea una carpeta *obj* dentro de *library* con tres archivos, incluido un archivo *project.assets.json*:</span><span class="sxs-lookup"><span data-stu-id="61e3c-137">Execute [`dotnet restore`](../tools/dotnet-restore.md), ([see note](#dotnet-restore-note)) which restores dependencies and creates an *obj* folder inside *library* with three files in it, including a *project.assets.json* file:</span></span>

```console
dotnet restore
```

<span data-ttu-id="61e3c-138">En la carpeta *library*, cambie el nombre del archivo *Class1.cs* a *Thing.cs*.</span><span class="sxs-lookup"><span data-stu-id="61e3c-138">In the *library* folder, rename the file *Class1.cs* to *Thing.cs*.</span></span> <span data-ttu-id="61e3c-139">Reemplace el código por el siguiente:</span><span class="sxs-lookup"><span data-stu-id="61e3c-139">Replace the code with the following:</span></span>

```csharp
using static Newtonsoft.Json.JsonConvert;

namespace Library
{
    public class Thing
    {
        public int Get(int left, int right) =>
            DeserializeObject<int>($"{left + right}");
    }
}
```

<span data-ttu-id="61e3c-140">La clase `Thing` contiene un método público, `Get`, que devuelve la suma de dos números pero lo hace convirtiendo la suma en una cadena y, después, deserializándola en un entero.</span><span class="sxs-lookup"><span data-stu-id="61e3c-140">The `Thing` class contains one public method, `Get`, which returns the sum of two numbers but does so by converting the sum into a string and then deserializing it into an integer.</span></span> <span data-ttu-id="61e3c-141">Esto usa varias características de C# recientes, como las  [directivas `using static`](../../csharp/language-reference/keywords/using-static.md), los [miembros con forma de expresión](../../csharp/whats-new/csharp-7.md#more-expression-bodied-members) y la [interpolación de cadenas](../../csharp/language-reference/tokens/interpolated.md).</span><span class="sxs-lookup"><span data-stu-id="61e3c-141">This makes use of a number of modern C# features, such as [`using static` directives](../../csharp/language-reference/keywords/using-static.md), [expression-bodied members](../../csharp/whats-new/csharp-7.md#more-expression-bodied-members), and [string interpolation](../../csharp/language-reference/tokens/interpolated.md).</span></span>

<span data-ttu-id="61e3c-142">Compile la biblioteca con el comando [`dotnet build`](../tools/dotnet-build.md).</span><span class="sxs-lookup"><span data-stu-id="61e3c-142">Build the library with the [`dotnet build`](../tools/dotnet-build.md) command.</span></span> <span data-ttu-id="61e3c-143">Esto crea un archivo *library.dll* en *golden/library/bin/Debug/netstandard1.4*:</span><span class="sxs-lookup"><span data-stu-id="61e3c-143">This produces a *library.dll* file under *golden/library/bin/Debug/netstandard1.4*:</span></span>

```console
dotnet build
```

## <a name="create-the-test-project"></a><span data-ttu-id="61e3c-144">Crear el proyecto de prueba</span><span class="sxs-lookup"><span data-stu-id="61e3c-144">Create the test project</span></span>

<span data-ttu-id="61e3c-145">Cree un proyecto de prueba para la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="61e3c-145">Build a test project for the library.</span></span> <span data-ttu-id="61e3c-146">Desde la carpeta *golden*, cree un nuevo proyecto de prueba:</span><span class="sxs-lookup"><span data-stu-id="61e3c-146">From the *golden* folder, create a new test project:</span></span>

```console
dotnet new xunit -o test-library
```

<span data-ttu-id="61e3c-147">Agregue el proyecto de prueba a la solución:</span><span class="sxs-lookup"><span data-stu-id="61e3c-147">Add the test project to the solution:</span></span>

```console
dotnet sln add test-library/test-library.csproj
```

<span data-ttu-id="61e3c-148">Agregue una referencia del proyecto a la biblioteca que ha creado en la sección anterior, de manera que el compilador pueda buscar y usar el proyecto de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="61e3c-148">Add a project reference the library you created in the previous section so that the compiler can find and use the library project.</span></span> <span data-ttu-id="61e3c-149">Use el comando [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="61e3c-149">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```console
dotnet add test-library/test-library.csproj reference library/library.csproj
```

<span data-ttu-id="61e3c-150">De manera alternativa, edite manualmente el archivo *test-library.csproj* y agregue el nodo siguiente:</span><span class="sxs-lookup"><span data-stu-id="61e3c-150">Alternatively, manually edit the *test-library.csproj* file and add the following node:</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="..\library\library.csproj" />
</ItemGroup>
```

<span data-ttu-id="61e3c-151">Ahora que se han configurado correctamente las dependencias, cree las pruebas para la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="61e3c-151">Now that the dependencies have been properly configured, create the tests for your library.</span></span> <span data-ttu-id="61e3c-152">Abra *UnitTest1.cs* y reemplace el contenido por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="61e3c-152">Open *UnitTest1.cs* and replace its contents with the following code:</span></span>

```csharp
using Library;
using Xunit;

namespace TestApp
{
    public class LibraryTests
    {
        [Fact]
        public void TestThing() {
            Assert.NotEqual(42, new Thing().Get(19, 23));
        }
    }
}
```

<span data-ttu-id="61e3c-153">Tenga en cuenta que afirma que el valor 42 no es igual a 19+23 (o 42) cuando se crea la prueba unitaria por primera vez (`Assert.NotEqual`), lo que producirá un error.</span><span class="sxs-lookup"><span data-stu-id="61e3c-153">Note that you assert the value 42 is not equal to 19+23 (or 42) when you first create the unit test (`Assert.NotEqual`), which will fail.</span></span> <span data-ttu-id="61e3c-154">Un paso importante en la creación de las pruebas unitarias es crear la prueba para que produzca un error la primera vez para confirmar su lógica.</span><span class="sxs-lookup"><span data-stu-id="61e3c-154">An important step in building unit tests is to create the test to fail once first to confirm its logic.</span></span>

<span data-ttu-id="61e3c-155">Desde la carpeta *golden*, ejecute los comandos siguientes:</span><span class="sxs-lookup"><span data-stu-id="61e3c-155">From the *golden* folder, execute the following commands:</span></span>

```console
dotnet restore 
dotnet test test-library/test-library.csproj
```

<span data-ttu-id="61e3c-156">Estos comandos buscarán de manera recursiva todos los proyectos para restaurar dependencias, compilarlos y activar el ejecutor de pruebas xUnit para ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="61e3c-156">These commands will recursively find all projects to restore dependencies, build them, and activate the xUnit test runner to run the tests.</span></span> <span data-ttu-id="61e3c-157">Se produce un error en la prueba, como se esperaba.</span><span class="sxs-lookup"><span data-stu-id="61e3c-157">The single test fails, as you expect.</span></span>

<span data-ttu-id="61e3c-158">Edite el archivo *UnitTest1.cs* y cambie la aserción de `Assert.NotEqual` a `Assert.Equal`.</span><span class="sxs-lookup"><span data-stu-id="61e3c-158">Edit the *UnitTest1.cs* file and change the assertion from `Assert.NotEqual` to `Assert.Equal`.</span></span> <span data-ttu-id="61e3c-159">Ejecute el comando siguiente desde la carpeta *golden* para volver a ejecutar la prueba, que se pasa esta vez:</span><span class="sxs-lookup"><span data-stu-id="61e3c-159">Execute the following command from the *golden* folder to re-run the test, which passes this time:</span></span>

```console
dotnet test test-library/test-library.csproj
```

## <a name="create-the-console-app"></a><span data-ttu-id="61e3c-160">Crear la aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="61e3c-160">Create the console app</span></span>

<span data-ttu-id="61e3c-161">La aplicación de consola que crea con los pasos siguientes toma una dependencia del proyecto de biblioteca que ha creado anteriormente y llama a su método de biblioteca cuando se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="61e3c-161">The console app you create over the following steps takes a dependency on the library project you created earlier and calls its library method when it runs.</span></span> <span data-ttu-id="61e3c-162">Con este patrón de desarrollo, ve cómo crear bibliotecas reutilizables en varios proyectos.</span><span class="sxs-lookup"><span data-stu-id="61e3c-162">Using this pattern of development, you see how to create reusable libraries for multiple projects.</span></span>

<span data-ttu-id="61e3c-163">Cree una aplicación de consola nueva desde la carpeta *golden*:</span><span class="sxs-lookup"><span data-stu-id="61e3c-163">Create a new console application from the *golden* folder:</span></span>

```console
dotnet new console -o app
```

<span data-ttu-id="61e3c-164">Agregue el proyecto de la aplicación de consola a la solución:</span><span class="sxs-lookup"><span data-stu-id="61e3c-164">Add the console app project to the solution:</span></span>

```console
dotnet sln add app/app.csproj
```

<span data-ttu-id="61e3c-165">Cree la dependencia en la biblioteca ejecutando el comando `dotnet add reference`:</span><span class="sxs-lookup"><span data-stu-id="61e3c-165">Create the dependency on the library by running the `dotnet add reference` command:</span></span>

```console
dotnet add app/app.csproj reference library/library.csproj
```

<span data-ttu-id="61e3c-166">Ejecute `dotnet restore` ([vea la nota](#dotnet-restore-note)) para restaurar las dependencias de los tres proyectos en la solución.</span><span class="sxs-lookup"><span data-stu-id="61e3c-166">Run `dotnet restore` ([see note](#dotnet-restore-note)) to restore the dependencies of the three projects in the solution.</span></span> <span data-ttu-id="61e3c-167">Abra *Program.cs* y reemplace el contenido del método `Main` por la siguiente línea:</span><span class="sxs-lookup"><span data-stu-id="61e3c-167">Open *Program.cs* and replace the contents of the `Main` method with the following line:</span></span>

```csharp
WriteLine($"The answer is {new Thing().Get(19, 23)}");
```

<span data-ttu-id="61e3c-168">Agregue dos directivas `using` en la parte superior del archivo *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="61e3c-168">Add two `using` directives to the top of the *Program.cs* file:</span></span>

```csharp
using static System.Console;
using Library;
```

<span data-ttu-id="61e3c-169">Ejecute el siguiente comando `dotnet run` para ejecutar el ejecutable, donde la opción `-p` en `dotnet run` especifica el proyecto para la aplicación principal.</span><span class="sxs-lookup"><span data-stu-id="61e3c-169">Execute the following `dotnet run` command to run the executable, where the `-p` option to `dotnet run` specifies the project for the main application.</span></span> <span data-ttu-id="61e3c-170">La aplicación genera la cadena "La respuesta es 42".</span><span class="sxs-lookup"><span data-stu-id="61e3c-170">The app produces the string "The answer is 42".</span></span>

```console
dotnet run -p app/app.csproj
```

## <a name="debug-the-application"></a><span data-ttu-id="61e3c-171">Depurar la aplicación</span><span class="sxs-lookup"><span data-stu-id="61e3c-171">Debug the application</span></span>

<span data-ttu-id="61e3c-172">Establezca un punto de interrupción en la instrucción `WriteLine` del método `Main`.</span><span class="sxs-lookup"><span data-stu-id="61e3c-172">Set a breakpoint at the `WriteLine` statement in the `Main` method.</span></span> <span data-ttu-id="61e3c-173">Haga esto presionando la tecla <kbd>F9</kbd> cuando el cursor se encuentre encima de la línea `WriteLine` o haciendo clic con el mouse en el margen izquierdo de la línea donde quiera establecer el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="61e3c-173">Do this by either pressing the <kbd>F9</kbd> key when the cursor is over the `WriteLine` line or by clicking the mouse in the left margin on the line where you want to set the breakpoint.</span></span> <span data-ttu-id="61e3c-174">Aparecerá un círculo rojo en el margen junto a la línea de código.</span><span class="sxs-lookup"><span data-stu-id="61e3c-174">A red circle will appear in the margin next to the line of code.</span></span> <span data-ttu-id="61e3c-175">Cuando se alcance el punto de interrupción, la ejecución de código se detendrá *antes* de que se ejecute la línea del punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="61e3c-175">When the breakpoint is reached, code execution will stop *before* the breakpoint line is executed.</span></span>

<span data-ttu-id="61e3c-176">Abra la pestaña del depurador; para ello, seleccione el icono Depurar en la barra de herramientas de Visual Studio Code, seleccione **Ver > Depurar** desde la barra de menús o con el método abreviado de teclado <kbd>CTRL</kbd>+<kbd>Mayús</kbd>+<kbd>D</kbd>:</span><span class="sxs-lookup"><span data-stu-id="61e3c-176">Open the debugger tab by selecting the Debug icon in the Visual Studio Code toolbar, selecting **View > Debug** from the menu bar, or using the keyboard shortcut <kbd>CTRL</kbd>+<kbd>SHIFT</kbd>+<kbd>D</kbd>:</span></span>

![Depurador de Visual Studio Code](./media/using-on-macos/visual-studio-code-debugger.png)

<span data-ttu-id="61e3c-178">Presione el botón Reproducir para iniciar la aplicación en el depurador.</span><span class="sxs-lookup"><span data-stu-id="61e3c-178">Press the Play button to start the application under the debugger.</span></span> <span data-ttu-id="61e3c-179">La aplicación comienza la ejecución y se ejecuta hasta el punto de interrupción, donde se detiene.</span><span class="sxs-lookup"><span data-stu-id="61e3c-179">The app begins execution and runs to the breakpoint, where it stops.</span></span> <span data-ttu-id="61e3c-180">Recorra paso a paso el método `Get` y asegúrese de que hayan pasado los argumentos correctos.</span><span class="sxs-lookup"><span data-stu-id="61e3c-180">Step into the `Get` method and make sure that you have passed in the correct arguments.</span></span> <span data-ttu-id="61e3c-181">Confirme que la respuesta es 42.</span><span class="sxs-lookup"><span data-stu-id="61e3c-181">Confirm that the answer is 42.</span></span>

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
