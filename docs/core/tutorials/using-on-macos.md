---
title: 'Tutorial: Creación de una solución de .NET Core en macOS con Visual Studio Code'
description: En este documento se proporcionan los pasos y el flujo de trabajo para crear una solución de .NET Core con Visual Studio Code.
ms.date: 12/19/2019
ms.openlocfilehash: f5da16d413ddc25587ff35550fe9f308dc87f4bb
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156600"
---
# <a name="tutorial-create-a-net-core-solution-in-macos-using-visual-studio-code"></a><span data-ttu-id="a2b60-103">Tutorial: Creación de una solución de .NET Core en macOS con Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="a2b60-103">Tutorial: Create a .NET Core solution in macOS using Visual Studio Code</span></span>

<span data-ttu-id="a2b60-104">En este documento se proporcionan los pasos y el flujo de trabajo para crear una solución de .NET Core para macOS.</span><span class="sxs-lookup"><span data-stu-id="a2b60-104">This document provides the steps and workflow to create a .NET Core solution for macOS.</span></span> <span data-ttu-id="a2b60-105">Obtendrá información sobre cómo crear proyectos, pruebas unitarias, usar las herramientas de depuración e incorporar bibliotecas de terceros a través de [NuGet](https://www.nuget.org/).</span><span class="sxs-lookup"><span data-stu-id="a2b60-105">Learn how to create projects, unit tests, use the debugging tools, and incorporate third-party libraries via [NuGet](https://www.nuget.org/).</span></span>

> [!NOTE]
> <span data-ttu-id="a2b60-106">En este artículo se usa [Visual Studio Code](https://code.visualstudio.com) en macOS.</span><span class="sxs-lookup"><span data-stu-id="a2b60-106">This article uses [Visual Studio Code](https://code.visualstudio.com) on macOS.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a2b60-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a2b60-107">Prerequisites</span></span>

<span data-ttu-id="a2b60-108">Instale el [SDK de .NET Core](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="a2b60-108">Install the [.NET Core SDK](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="a2b60-109">El SDK de .NET Core incluye la última versión de la plataforma de .NET Core y el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a2b60-109">The .NET Core SDK includes the latest release of the .NET Core framework and runtime.</span></span>

<span data-ttu-id="a2b60-110">Instale [Visual Studio Code](https://code.visualstudio.com).</span><span class="sxs-lookup"><span data-stu-id="a2b60-110">Install [Visual Studio Code](https://code.visualstudio.com).</span></span> <span data-ttu-id="a2b60-111">Durante el transcurso de este artículo, también instalará las extensiones de Visual Studio Code que mejoran la experiencia de desarrollo de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a2b60-111">During the course of this article, you also install Visual Studio Code extensions that improve the .NET Core development experience.</span></span>

<span data-ttu-id="a2b60-112">Instale la extensión de C# de Visual Studio Code; para ello, abra Visual Studio Code y presione <kbd>Fn</kbd>+<kbd>F1</kbd> para abrir la paleta de Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="a2b60-112">Install the Visual Studio Code C# extension by opening Visual Studio Code and pressing <kbd>Fn</kbd>+<kbd>F1</kbd> to open the Visual Studio Code palette.</span></span> <span data-ttu-id="a2b60-113">Escriba **ext install** para ver la lista de extensiones.</span><span class="sxs-lookup"><span data-stu-id="a2b60-113">Type **ext install** to see the list of extensions.</span></span> <span data-ttu-id="a2b60-114">Seleccione la extensión de C#.</span><span class="sxs-lookup"><span data-stu-id="a2b60-114">Select the C# extension.</span></span> <span data-ttu-id="a2b60-115">Reinicie Visual Studio Code para activar la extensión.</span><span class="sxs-lookup"><span data-stu-id="a2b60-115">Restart Visual Studio Code to activate the extension.</span></span> <span data-ttu-id="a2b60-116">Para obtener más información, vea la [documentación de la extensión de C# enVisual Studio Code](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).</span><span class="sxs-lookup"><span data-stu-id="a2b60-116">For more information, see the [Visual Studio Code C# Extension documentation](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).</span></span>

## <a name="get-started"></a><span data-ttu-id="a2b60-117">Primeros pasos</span><span class="sxs-lookup"><span data-stu-id="a2b60-117">Get started</span></span>

<span data-ttu-id="a2b60-118">En este tutorial, creará tres proyectos: un proyecto de biblioteca, pruebas para ese proyecto de biblioteca y una aplicación de consola que usa la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="a2b60-118">In this tutorial, you create three projects: a library project, tests for that library project, and a console application that makes use of the library.</span></span> <span data-ttu-id="a2b60-119">Puede [ver o descargar el origen](https://github.com/dotnet/samples/tree/master/core/getting-started/golden) de este artículo en el repositorio dotnet/samples de GitHub.</span><span class="sxs-lookup"><span data-stu-id="a2b60-119">You can [view or download the source](https://github.com/dotnet/samples/tree/master/core/getting-started/golden) for this article at the dotnet/samples repository on GitHub.</span></span> <span data-ttu-id="a2b60-120">Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="a2b60-120">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

<span data-ttu-id="a2b60-121">Inicie Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="a2b60-121">Start Visual Studio Code.</span></span> <span data-ttu-id="a2b60-122">Presione <kbd>Ctrl</kbd><kbd>\`</kbd> (carácter de comilla inversa o tilde aguda) o seleccione **Ver** > **Terminal** en el menú para abrir un terminal insertado en Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="a2b60-122">Press <kbd>Ctrl</kbd><kbd>\`</kbd> (the backquote or backtick character) or select **View** > **Terminal** from the menu to open an embedded terminal in Visual Studio Code.</span></span> <span data-ttu-id="a2b60-123">Puede abrir un shell externo con el comando **Abrir en símbolo del sistema** del explorador (**Abrir en terminal** en macOS o Linux) si prefiere trabajar fuera de Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="a2b60-123">You can still open an external shell with the Explorer **Open in Command Prompt** command (**Open in Terminal** on macOS or Linux) if you prefer to work outside of Visual Studio Code.</span></span>

<span data-ttu-id="a2b60-124">Comience creando un archivo de solución, que actúa como un contenedor para uno o más proyectos de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a2b60-124">Begin by creating a solution file, which serves as a container for one or more .NET Core projects.</span></span> <span data-ttu-id="a2b60-125">En el terminal, ejecute el comando [`dotnet new`](../tools/dotnet-new.md) para crear una solución *golden.sln* dentro de una nueva carpeta denominada *golden*:</span><span class="sxs-lookup"><span data-stu-id="a2b60-125">In the terminal, run the [`dotnet new`](../tools/dotnet-new.md) command to create a new solution *golden.sln* inside a new folder named *golden*:</span></span>

```dotnetcli
dotnet new sln -o golden
```

<span data-ttu-id="a2b60-126">Navegue a la nueva carpeta *golden* y ejecute el siguiente comando para crear un proyecto de biblioteca, que produce dos archivos,*library.csproj* y *Class1.cs*, en la carpeta *library*:</span><span class="sxs-lookup"><span data-stu-id="a2b60-126">Navigate to the new *golden* folder and execute the following command to create a library project, which produces two files,*library.csproj* and *Class1.cs*, in the *library* folder:</span></span>

```dotnetcli
dotnet new classlib -o library
```

<span data-ttu-id="a2b60-127">Ejecute el comando [`dotnet sln`](../tools/dotnet-sln.md) para agregar el proyecto *library.csproj* recién creado a la solución:</span><span class="sxs-lookup"><span data-stu-id="a2b60-127">Execute the [`dotnet sln`](../tools/dotnet-sln.md) command to add the newly created *library.csproj* project to the solution:</span></span>

```dotnetcli
dotnet sln add library/library.csproj
```

<span data-ttu-id="a2b60-128">El archivo *library.csproj* contiene la información siguiente:</span><span class="sxs-lookup"><span data-stu-id="a2b60-128">The *library.csproj* file contains the following information:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFramework>netstandard2.0</TargetFramework>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="a2b60-129">Nuestros métodos de biblioteca serializan y deserializan objetos en formato JSON.</span><span class="sxs-lookup"><span data-stu-id="a2b60-129">Our library methods serialize and deserialize objects in JSON format.</span></span> <span data-ttu-id="a2b60-130">Para admitir la serialización y deserialización JSON, agregue una referencia al paquete NuGet `Newtonsoft.Json`.</span><span class="sxs-lookup"><span data-stu-id="a2b60-130">To support JSON serialization and deserialization, add a reference to the `Newtonsoft.Json` NuGet package.</span></span> <span data-ttu-id="a2b60-131">El comando `dotnet add` agrega elementos nuevos a un proyecto.</span><span class="sxs-lookup"><span data-stu-id="a2b60-131">The `dotnet add` command adds new items to a project.</span></span> <span data-ttu-id="a2b60-132">Para agregar una referencia a un paquete NuGet, use el comando [`dotnet add package`](../tools/dotnet-add-package.md) y especifique el nombre del paquete:</span><span class="sxs-lookup"><span data-stu-id="a2b60-132">To add a reference to a NuGet package, use the [`dotnet add package`](../tools/dotnet-add-package.md) command and specify the name of the package:</span></span>

```dotnetcli
dotnet add library package Newtonsoft.Json
```

<span data-ttu-id="a2b60-133">Esto agrega `Newtonsoft.Json` y sus dependencias al proyecto de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="a2b60-133">This adds `Newtonsoft.Json` and its dependencies to the library project.</span></span> <span data-ttu-id="a2b60-134">De manera alternativa, edite manualmente el archivo *library.csproj* y agregue el nodo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a2b60-134">Alternatively, manually edit the *library.csproj* file and add the following node:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Newtonsoft.Json" Version="12.0.2" />
</ItemGroup>
```

<span data-ttu-id="a2b60-135">Ejecute [`dotnet restore`](../tools/dotnet-restore.md) ([vea la nota](#dotnet-restore-note)), lo que restaura las dependencias y crea una carpeta *obj* dentro de *library* con tres archivos, incluido un archivo *project.assets.json*:</span><span class="sxs-lookup"><span data-stu-id="a2b60-135">Execute [`dotnet restore`](../tools/dotnet-restore.md), ([see note](#dotnet-restore-note)) which restores dependencies and creates an *obj* folder inside *library* with three files in it, including a *project.assets.json* file:</span></span>

```dotnetcli
dotnet restore
```

<span data-ttu-id="a2b60-136">En la carpeta *library*, cambie el nombre del archivo *Class1.cs* a *Thing.cs*.</span><span class="sxs-lookup"><span data-stu-id="a2b60-136">In the *library* folder, rename the file *Class1.cs* to *Thing.cs*.</span></span> <span data-ttu-id="a2b60-137">Reemplace el código por el siguiente:</span><span class="sxs-lookup"><span data-stu-id="a2b60-137">Replace the code with the following:</span></span>

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

<span data-ttu-id="a2b60-138">La clase `Thing` contiene un método público, `Get`, que devuelve la suma de dos números pero lo hace convirtiendo la suma en una cadena y, después, deserializándola en un entero.</span><span class="sxs-lookup"><span data-stu-id="a2b60-138">The `Thing` class contains one public method, `Get`, which returns the sum of two numbers but does so by converting the sum into a string and then deserializing it into an integer.</span></span> <span data-ttu-id="a2b60-139">Esto usa varias características de C# recientes, como las  [directivas `using static`](../../csharp/language-reference/keywords/using-static.md), los [miembros con forma de expresión](../../csharp/whats-new/csharp-7.md#more-expression-bodied-members) y la [interpolación de cadenas](../../csharp/language-reference/tokens/interpolated.md).</span><span class="sxs-lookup"><span data-stu-id="a2b60-139">This makes use of a number of modern C# features, such as [`using static` directives](../../csharp/language-reference/keywords/using-static.md), [expression-bodied members](../../csharp/whats-new/csharp-7.md#more-expression-bodied-members), and [string interpolation](../../csharp/language-reference/tokens/interpolated.md).</span></span>

<span data-ttu-id="a2b60-140">Compile la biblioteca con el comando [`dotnet build`](../tools/dotnet-build.md).</span><span class="sxs-lookup"><span data-stu-id="a2b60-140">Build the library with the [`dotnet build`](../tools/dotnet-build.md) command.</span></span> <span data-ttu-id="a2b60-141">Esto crea un archivo *library.dll* en *golden/library/bin/Debug/netstandard1.4*:</span><span class="sxs-lookup"><span data-stu-id="a2b60-141">This produces a *library.dll* file under *golden/library/bin/Debug/netstandard1.4*:</span></span>

```dotnetcli
dotnet build
```

## <a name="create-the-test-project"></a><span data-ttu-id="a2b60-142">Crear el proyecto de prueba</span><span class="sxs-lookup"><span data-stu-id="a2b60-142">Create the test project</span></span>

<span data-ttu-id="a2b60-143">Cree un proyecto de prueba para la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="a2b60-143">Build a test project for the library.</span></span> <span data-ttu-id="a2b60-144">Desde la carpeta *golden*, cree un nuevo proyecto de prueba:</span><span class="sxs-lookup"><span data-stu-id="a2b60-144">From the *golden* folder, create a new test project:</span></span>

```dotnetcli
dotnet new xunit -o test-library
```

<span data-ttu-id="a2b60-145">Agregue el proyecto de prueba a la solución:</span><span class="sxs-lookup"><span data-stu-id="a2b60-145">Add the test project to the solution:</span></span>

```dotnetcli
dotnet sln add test-library/test-library.csproj
```

<span data-ttu-id="a2b60-146">Agregue una referencia del proyecto a la biblioteca que ha creado en la sección anterior, de manera que el compilador pueda buscar y usar el proyecto de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="a2b60-146">Add a project reference the library you created in the previous section so that the compiler can find and use the library project.</span></span> <span data-ttu-id="a2b60-147">Use el comando [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="a2b60-147">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```dotnetcli
dotnet add test-library/test-library.csproj reference library/library.csproj
```

<span data-ttu-id="a2b60-148">De manera alternativa, edite manualmente el archivo *test-library.csproj* y agregue el nodo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a2b60-148">Alternatively, manually edit the *test-library.csproj* file and add the following node:</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="..\library\library.csproj" />
</ItemGroup>
```

<span data-ttu-id="a2b60-149">Ahora que se han configurado correctamente las dependencias, cree las pruebas para la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="a2b60-149">Now that the dependencies have been properly configured, create the tests for your library.</span></span> <span data-ttu-id="a2b60-150">Abra *UnitTest1.cs* y reemplace el contenido por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="a2b60-150">Open *UnitTest1.cs* and replace its contents with the following code:</span></span>

```csharp
using Library;
using Xunit;

namespace TestApp
{
    public class LibraryTests
    {
        [Fact]
        public void TestThing()
        {
            Assert.NotEqual(42, new Thing().Get(19, 23));
        }
    }
}
```

<span data-ttu-id="a2b60-151">Tenga en cuenta que afirma que el valor 42 no es igual a 19+23 (o 42) cuando se crea la prueba unitaria por primera vez (`Assert.NotEqual`), lo que producirá un error.</span><span class="sxs-lookup"><span data-stu-id="a2b60-151">Note that you assert the value 42 is not equal to 19+23 (or 42) when you first create the unit test (`Assert.NotEqual`), which will fail.</span></span> <span data-ttu-id="a2b60-152">Un paso importante en la creación de las pruebas unitarias es crear la prueba para que produzca un error la primera vez para confirmar su lógica.</span><span class="sxs-lookup"><span data-stu-id="a2b60-152">An important step in building unit tests is to create the test to fail once first to confirm its logic.</span></span>

<span data-ttu-id="a2b60-153">Desde la carpeta *golden*, ejecute los comandos siguientes:</span><span class="sxs-lookup"><span data-stu-id="a2b60-153">From the *golden* folder, execute the following commands:</span></span>

```dotnetcli
dotnet restore
dotnet test test-library/test-library.csproj
```

<span data-ttu-id="a2b60-154">Estos comandos buscarán de manera recursiva todos los proyectos para restaurar dependencias, compilarlos y activar el ejecutor de pruebas xUnit para ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="a2b60-154">These commands will recursively find all projects to restore dependencies, build them, and activate the xUnit test runner to run the tests.</span></span> <span data-ttu-id="a2b60-155">Se produce un error en la prueba, como se esperaba.</span><span class="sxs-lookup"><span data-stu-id="a2b60-155">The single test fails, as you expect.</span></span>

<span data-ttu-id="a2b60-156">Edite el archivo *UnitTest1.cs* y cambie la aserción de `Assert.NotEqual` a `Assert.Equal`.</span><span class="sxs-lookup"><span data-stu-id="a2b60-156">Edit the *UnitTest1.cs* file and change the assertion from `Assert.NotEqual` to `Assert.Equal`.</span></span> <span data-ttu-id="a2b60-157">Ejecute el comando siguiente desde la carpeta *golden* para volver a ejecutar la prueba, que se pasa esta vez:</span><span class="sxs-lookup"><span data-stu-id="a2b60-157">Execute the following command from the *golden* folder to re-run the test, which passes this time:</span></span>

```dotnetcli
dotnet test test-library/test-library.csproj
```

## <a name="create-the-console-app"></a><span data-ttu-id="a2b60-158">Crear la aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="a2b60-158">Create the console app</span></span>

<span data-ttu-id="a2b60-159">La aplicación de consola que crea con los pasos siguientes toma una dependencia del proyecto de biblioteca que ha creado anteriormente y llama a su método de biblioteca cuando se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="a2b60-159">The console app you create over the following steps takes a dependency on the library project you created earlier and calls its library method when it runs.</span></span> <span data-ttu-id="a2b60-160">Con este patrón de desarrollo, ve cómo crear bibliotecas reutilizables en varios proyectos.</span><span class="sxs-lookup"><span data-stu-id="a2b60-160">Using this pattern of development, you see how to create reusable libraries for multiple projects.</span></span>

<span data-ttu-id="a2b60-161">Cree una aplicación de consola nueva desde la carpeta *golden*:</span><span class="sxs-lookup"><span data-stu-id="a2b60-161">Create a new console application from the *golden* folder:</span></span>

```dotnetcli
dotnet new console -o app
```

<span data-ttu-id="a2b60-162">Agregue el proyecto de la aplicación de consola a la solución:</span><span class="sxs-lookup"><span data-stu-id="a2b60-162">Add the console app project to the solution:</span></span>

```dotnetcli
dotnet sln add app/app.csproj
```

<span data-ttu-id="a2b60-163">Cree la dependencia en la biblioteca ejecutando el comando `dotnet add reference`:</span><span class="sxs-lookup"><span data-stu-id="a2b60-163">Create the dependency on the library by running the `dotnet add reference` command:</span></span>

```dotnetcli
dotnet add app/app.csproj reference library/library.csproj
```

<span data-ttu-id="a2b60-164">Ejecute `dotnet restore` ([vea la nota](#dotnet-restore-note)) para restaurar las dependencias de los tres proyectos en la solución.</span><span class="sxs-lookup"><span data-stu-id="a2b60-164">Run `dotnet restore` ([see note](#dotnet-restore-note)) to restore the dependencies of the three projects in the solution.</span></span> <span data-ttu-id="a2b60-165">Abra *Program.cs* y reemplace el contenido del método `Main` por la siguiente línea:</span><span class="sxs-lookup"><span data-stu-id="a2b60-165">Open *Program.cs* and replace the contents of the `Main` method with the following line:</span></span>

```csharp
WriteLine($"The answer is {new Thing().Get(19, 23)}");
```

<span data-ttu-id="a2b60-166">Agregue dos directivas `using` en la parte superior del archivo *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="a2b60-166">Add two `using` directives to the top of the *Program.cs* file:</span></span>

```csharp
using static System.Console;
using Library;
```

<span data-ttu-id="a2b60-167">Ejecute el siguiente comando `dotnet run` para ejecutar el ejecutable, donde la opción `-p` en `dotnet run` especifica el proyecto para la aplicación principal.</span><span class="sxs-lookup"><span data-stu-id="a2b60-167">Execute the following `dotnet run` command to run the executable, where the `-p` option to `dotnet run` specifies the project for the main application.</span></span> <span data-ttu-id="a2b60-168">La aplicación genera la cadena "La respuesta es 42".</span><span class="sxs-lookup"><span data-stu-id="a2b60-168">The app produces the string "The answer is 42".</span></span>

```dotnetcli
dotnet run -p app/app.csproj
```

## <a name="debug-the-application"></a><span data-ttu-id="a2b60-169">Depurar la aplicación</span><span class="sxs-lookup"><span data-stu-id="a2b60-169">Debug the application</span></span>

<span data-ttu-id="a2b60-170">Establezca un punto de interrupción en la instrucción `WriteLine` del método `Main`.</span><span class="sxs-lookup"><span data-stu-id="a2b60-170">Set a breakpoint at the `WriteLine` statement in the `Main` method.</span></span> <span data-ttu-id="a2b60-171">Haga esto presionando la tecla <kbd>Fn</kbd>+<kbd>F9</kbd> cuando el cursor se encuentre encima de la línea `WriteLine` o haciendo clic con el mouse en el margen izquierdo de la línea donde quiera establecer el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="a2b60-171">Do this by either pressing the <kbd>Fn</kbd>+<kbd>F9</kbd> key when the cursor is over the `WriteLine` line or by clicking the mouse in the left margin on the line where you want to set the breakpoint.</span></span> <span data-ttu-id="a2b60-172">Aparecerá un círculo rojo en el margen junto a la línea de código.</span><span class="sxs-lookup"><span data-stu-id="a2b60-172">A red circle will appear in the margin next to the line of code.</span></span> <span data-ttu-id="a2b60-173">Cuando se alcance el punto de interrupción, la ejecución de código se detendrá *antes* de que se ejecute la línea del punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="a2b60-173">When the breakpoint is reached, code execution will stop *before* the breakpoint line is executed.</span></span>

<span data-ttu-id="a2b60-174">Abra la pestaña del depurador; para ello, seleccione el icono Depurar en la barra de herramientas de Visual Studio Code, seleccione **Ver** > **Depurar** en la barra de menús o use el método abreviado de teclado <kbd>&#8679;</kbd><kbd>&#8984;</kbd><kbd>D</kbd>:</span><span class="sxs-lookup"><span data-stu-id="a2b60-174">Open the debugger tab by selecting the Debug icon in the Visual Studio Code toolbar, selecting **View** > **Debug** from the menu bar, or using the keyboard shortcut <kbd>&#8679;</kbd><kbd>&#8984;</kbd><kbd>D</kbd>:</span></span>

![Depurador de Visual Studio Code](./media/using-on-macos/visual-studio-code-debugger.png)

<span data-ttu-id="a2b60-176">Presione el botón Reproducir para iniciar la aplicación en el depurador.</span><span class="sxs-lookup"><span data-stu-id="a2b60-176">Press the Play button to start the application under the debugger.</span></span> <span data-ttu-id="a2b60-177">En este proyecto ha creado un proyecto de prueba y una aplicación.</span><span class="sxs-lookup"><span data-stu-id="a2b60-177">You've created both a test project and an application in this project.</span></span> <span data-ttu-id="a2b60-178">El depurador pregunta qué proyecto desea iniciar.</span><span class="sxs-lookup"><span data-stu-id="a2b60-178">The debugger asks which project you want to start.</span></span> <span data-ttu-id="a2b60-179">Seleccione el proyecto "aplicación".</span><span class="sxs-lookup"><span data-stu-id="a2b60-179">Select the "app" project.</span></span> <span data-ttu-id="a2b60-180">La aplicación comienza la ejecución y se ejecuta hasta el punto de interrupción, donde se detiene.</span><span class="sxs-lookup"><span data-stu-id="a2b60-180">The app begins execution and runs to the breakpoint, where it stops.</span></span> <span data-ttu-id="a2b60-181">Recorra paso a paso el método `Get` y asegúrese de que hayan pasado los argumentos correctos.</span><span class="sxs-lookup"><span data-stu-id="a2b60-181">Step into the `Get` method and make sure that you have passed in the correct arguments.</span></span> <span data-ttu-id="a2b60-182">Confirme que la respuesta es 42.</span><span class="sxs-lookup"><span data-stu-id="a2b60-182">Confirm that the answer is 42.</span></span>

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
