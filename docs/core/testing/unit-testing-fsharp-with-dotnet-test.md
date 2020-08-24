---
title: Prueba unitaria de F# en .NET Core con dotnet test y xUnit
description: 'Aprenda los conceptos de pruebas unitarias para F# en .NET Core: cree paso a paso una solución de ejemplo mediante pruebas de dotnet y xUnit.'
author: billwagner
ms.author: wiwagn
ms.date: 08/30/2017
ms.openlocfilehash: e0f2b6f88a650f412148f51cc0236fa46ed8c618
ms.sourcegitcommit: c4a15c6c4ecbb8a46ad4e67d9b3ab9b8b031d849
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/20/2020
ms.locfileid: "88656558"
---
# <a name="unit-testing-f-libraries-in-net-core-using-dotnet-test-and-xunit"></a><span data-ttu-id="3a78b-103">Bibliotecas de F# de prueba unitaria en .NET Core con pruebas de dotnet y xUnit</span><span class="sxs-lookup"><span data-stu-id="3a78b-103">Unit testing F# libraries in .NET Core using dotnet test and xUnit</span></span>

<span data-ttu-id="3a78b-104">Este tutorial le guía por una experiencia interactiva de creación de una solución de ejemplo paso a paso para aprender los conceptos de pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="3a78b-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="3a78b-105">Si prefiere seguir el tutorial con una solución precompilada, [vea o descargue el código de ejemplo](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-with-fsharp/) antes de comenzar.</span><span class="sxs-lookup"><span data-stu-id="3a78b-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-with-fsharp/) before you begin.</span></span> <span data-ttu-id="3a78b-106">Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../../samples-and-tutorials/index.md#view-and-download-samples).</span><span class="sxs-lookup"><span data-stu-id="3a78b-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#view-and-download-samples).</span></span>

[!INCLUDE [testing an ASP.NET Core project from .NET Core](../../../includes/core-testing-note-aspnet.md)]

## <a name="creating-the-source-project"></a><span data-ttu-id="3a78b-107">Crear el proyecto de origen</span><span class="sxs-lookup"><span data-stu-id="3a78b-107">Creating the source project</span></span>

<span data-ttu-id="3a78b-108">Abra una ventana del Shell.</span><span class="sxs-lookup"><span data-stu-id="3a78b-108">Open a shell window.</span></span> <span data-ttu-id="3a78b-109">Cree un directorio llamado *unit-testing-with-fsharp* que contenga la solución.</span><span class="sxs-lookup"><span data-stu-id="3a78b-109">Create a directory called *unit-testing-with-fsharp* to hold the solution.</span></span>
<span data-ttu-id="3a78b-110">En este directorio nuevo, ejecute `dotnet new sln` para crear una solución nueva.</span><span class="sxs-lookup"><span data-stu-id="3a78b-110">Inside this new directory, run `dotnet new sln` to create a new solution.</span></span> <span data-ttu-id="3a78b-111">Esto permite facilitar la administración de la biblioteca de clases y del proyecto de prueba unitaria.</span><span class="sxs-lookup"><span data-stu-id="3a78b-111">This makes it easier to manage both the class library and the unit test project.</span></span>
<span data-ttu-id="3a78b-112">En el directorio de la solución, cree un directorio *MathService*.</span><span class="sxs-lookup"><span data-stu-id="3a78b-112">Inside the solution directory, create a *MathService* directory.</span></span> <span data-ttu-id="3a78b-113">Esta es la estructura de directorios y archivos hasta el momento:</span><span class="sxs-lookup"><span data-stu-id="3a78b-113">The directory and file structure thus far is shown below:</span></span>

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
```

<span data-ttu-id="3a78b-114">Convierta *MathService* en el directorio actual y ejecute `dotnet new classlib -lang "F#"` para crear el proyecto de origen.</span><span class="sxs-lookup"><span data-stu-id="3a78b-114">Make *MathService* the current directory, and run `dotnet new classlib -lang "F#"` to create the source project.</span></span> <span data-ttu-id="3a78b-115">Creará una implementación de errores del servicio de matemáticas:</span><span class="sxs-lookup"><span data-stu-id="3a78b-115">You'll create a failing implementation of the math service:</span></span>

```fsharp
module MyMath =
    let squaresOfOdds xs = raise (System.NotImplementedException("You haven't written a test yet!"))
```

<span data-ttu-id="3a78b-116">Cambie nuevamente el directorio al directorio *unit-testing-with-fsharp*.</span><span class="sxs-lookup"><span data-stu-id="3a78b-116">Change the directory back to the *unit-testing-with-fsharp* directory.</span></span> <span data-ttu-id="3a78b-117">Ejecute `dotnet sln add .\MathService\MathService.fsproj` para agregar el proyecto de biblioteca de clases a la solución.</span><span class="sxs-lookup"><span data-stu-id="3a78b-117">Run `dotnet sln add .\MathService\MathService.fsproj` to add the class library project to the solution.</span></span>

## <a name="creating-the-test-project"></a><span data-ttu-id="3a78b-118">Crear el proyecto de prueba</span><span class="sxs-lookup"><span data-stu-id="3a78b-118">Creating the test project</span></span>

<span data-ttu-id="3a78b-119">A continuación, cree el directorio *MathService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="3a78b-119">Next, create the *MathService.Tests* directory.</span></span> <span data-ttu-id="3a78b-120">En el esquema siguiente se muestra la estructura de directorios:</span><span class="sxs-lookup"><span data-stu-id="3a78b-120">The following outline shows the directory structure:</span></span>

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
        Source Files
        MathService.fsproj
    /MathService.Tests
```

<span data-ttu-id="3a78b-121">Convierta el directorio *MathService.Tests* en el directorio actual y cree un proyecto nuevo con `dotnet new xunit -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="3a78b-121">Make the *MathService.Tests* directory the current directory and create a new project using `dotnet new xunit -lang "F#"`.</span></span> <span data-ttu-id="3a78b-122">Esto crea un proyecto de prueba que usa xUnit como biblioteca de pruebas.</span><span class="sxs-lookup"><span data-stu-id="3a78b-122">This creates a test project that uses xUnit as the test library.</span></span> <span data-ttu-id="3a78b-123">La plantilla generada configura el ejecutor de pruebas en *MathServiceTests.fsproj*:</span><span class="sxs-lookup"><span data-stu-id="3a78b-123">The generated template configures the test runner in the *MathServiceTests.fsproj*:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.3.0-preview-20170628-02" />
  <PackageReference Include="xunit" Version="2.2.0" />
  <PackageReference Include="xunit.runner.visualstudio" Version="2.2.0" />
</ItemGroup>
```

<span data-ttu-id="3a78b-124">El proyecto de prueba requiere otros paquetes para crear y ejecutar pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="3a78b-124">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="3a78b-125">`dotnet new` en el paso anterior, agregó xUnit y el ejecutor de xUnit.</span><span class="sxs-lookup"><span data-stu-id="3a78b-125">`dotnet new` in the previous step added xUnit and the xUnit runner.</span></span> <span data-ttu-id="3a78b-126">Ahora, agregue la biblioteca de clases `MathService` como otra dependencia al proyecto.</span><span class="sxs-lookup"><span data-stu-id="3a78b-126">Now, add the `MathService` class library as another dependency to the project.</span></span> <span data-ttu-id="3a78b-127">Use el comando `dotnet add reference`:</span><span class="sxs-lookup"><span data-stu-id="3a78b-127">Use the `dotnet add reference` command:</span></span>

```dotnetcli
dotnet add reference ../MathService/MathService.fsproj
```

<span data-ttu-id="3a78b-128">Puede ver todo el archivo en el [repositorio de muestras](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-with-fsharp/MathService.Tests/MathService.Tests.fsproj) en GitHub.</span><span class="sxs-lookup"><span data-stu-id="3a78b-128">You can see the entire file in the [samples repository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-with-fsharp/MathService.Tests/MathService.Tests.fsproj) on GitHub.</span></span>

<span data-ttu-id="3a78b-129">Tiene el diseño de solución final siguiente:</span><span class="sxs-lookup"><span data-stu-id="3a78b-129">You have the following final solution layout:</span></span>

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
        Source Files
        MathService.fsproj
    /MathService.Tests
        Test Source Files
        MathServiceTests.fsproj
```

<span data-ttu-id="3a78b-130">Ejecute `dotnet sln add .\MathService.Tests\MathService.Tests.fsproj` en el directorio *unit-testing-with-fsharp*.</span><span class="sxs-lookup"><span data-stu-id="3a78b-130">Execute `dotnet sln add .\MathService.Tests\MathService.Tests.fsproj` in the *unit-testing-with-fsharp* directory.</span></span>

## <a name="creating-the-first-test"></a><span data-ttu-id="3a78b-131">Crear la primera prueba</span><span class="sxs-lookup"><span data-stu-id="3a78b-131">Creating the first test</span></span>

<span data-ttu-id="3a78b-132">Escribirá una prueba de errores, la aprobará y, luego, repetirá el proceso.</span><span class="sxs-lookup"><span data-stu-id="3a78b-132">You write one failing test, make it pass, then repeat the process.</span></span> <span data-ttu-id="3a78b-133">Abra *Tests.fs* y agregue el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="3a78b-133">Open *Tests.fs* and add the following code:</span></span>

```fsharp
[<Fact>]
let ``My test`` () =
    Assert.True(true)

[<Fact>]
let ``Fail every time`` () = Assert.True(false)
```

<span data-ttu-id="3a78b-134">El atributo `[<Fact>]` indica un método de prueba que el ejecutor de pruebas ejecuta.</span><span class="sxs-lookup"><span data-stu-id="3a78b-134">The `[<Fact>]` attribute denotes a test method that is run by the test runner.</span></span> <span data-ttu-id="3a78b-135">En *unit-testing-with-fsharp*, ejecute `dotnet test` para compilar las pruebas y la biblioteca de clases y luego ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="3a78b-135">From the *unit-testing-with-fsharp*, execute `dotnet test` to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="3a78b-136">El ejecutor de pruebas de xUnit tiene el punto de entrada del programa para ejecutar las pruebas desde la consola.</span><span class="sxs-lookup"><span data-stu-id="3a78b-136">The xUnit test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="3a78b-137">`dotnet test` inicia el ejecutor de pruebas con el proyecto de prueba unitaria que creó.</span><span class="sxs-lookup"><span data-stu-id="3a78b-137">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="3a78b-138">Estas dos pruebas muestran las pruebas superadas y con errores más básicas.</span><span class="sxs-lookup"><span data-stu-id="3a78b-138">These two tests show the most basic passing and failing tests.</span></span> <span data-ttu-id="3a78b-139">`My test` indica que se supera y `Fail every time` indica que no.</span><span class="sxs-lookup"><span data-stu-id="3a78b-139">`My test` passes, and `Fail every time` fails.</span></span> <span data-ttu-id="3a78b-140">Ahora, cree una prueba para el método `squaresOfOdds`.</span><span class="sxs-lookup"><span data-stu-id="3a78b-140">Now, create a test for the `squaresOfOdds` method.</span></span> <span data-ttu-id="3a78b-141">El método `squaresOfOdds` devuelve una secuencia de los cuadrados de todos los valores enteros impares que forman parte de la secuencia de entrada.</span><span class="sxs-lookup"><span data-stu-id="3a78b-141">The `squaresOfOdds` method returns a sequence of the squares of all odd integer values that are part of the input sequence.</span></span> <span data-ttu-id="3a78b-142">En lugar de intentar escribir todas esas funciones a la vez, puede crear de forma iterativa pruebas que validen la funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="3a78b-142">Rather than trying to write all of those functions at once, you can iteratively create tests that validate the functionality.</span></span> <span data-ttu-id="3a78b-143">Hacer cada prueba superada significa crear la funcionalidad necesaria para el método.</span><span class="sxs-lookup"><span data-stu-id="3a78b-143">Making each test pass means creating the necessary functionality for the method.</span></span>

<span data-ttu-id="3a78b-144">La prueba más sencilla que se puede escribir es llamar a `squaresOfOdds` con todos los números impares, donde el resultado sea una secuencia de enteros vacía.</span><span class="sxs-lookup"><span data-stu-id="3a78b-144">The simplest test we can write is to call `squaresOfOdds` with all even numbers, where the result should be an empty sequence of integers.</span></span>  <span data-ttu-id="3a78b-145">Aquí se muestra la prueba:</span><span class="sxs-lookup"><span data-stu-id="3a78b-145">Here's that test:</span></span>

```fsharp
[<Fact>]
let ``Sequence of Evens returns empty collection`` () =
    let expected = Seq.empty<int>
    let actual = MyMath.squaresOfOdds [2; 4; 6; 8; 10]
    Assert.Equal<Collections.Generic.IEnumerable<int>>(expected, actual)
```

<span data-ttu-id="3a78b-146">La prueba produce un error.</span><span class="sxs-lookup"><span data-stu-id="3a78b-146">Your test fails.</span></span> <span data-ttu-id="3a78b-147">Todavía no ha creado la implementación.</span><span class="sxs-lookup"><span data-stu-id="3a78b-147">You haven't created the implementation yet.</span></span> <span data-ttu-id="3a78b-148">Cree esta prueba que se supera escribiendo el código más simple en la clase `MathService` que funciona:</span><span class="sxs-lookup"><span data-stu-id="3a78b-148">Make this test pass by writing the simplest code in the `MathService` class that works:</span></span>

```fsharp
let squaresOfOdds xs =
    Seq.empty<int>
```

<span data-ttu-id="3a78b-149">En el directorio *unit-testing-with-fsharp*, vuelva a ejecutar `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="3a78b-149">In the *unit-testing-with-fsharp* directory, run `dotnet test` again.</span></span> <span data-ttu-id="3a78b-150">El comando `dotnet test` ejecuta una compilación del proyecto `MathService` y luego del proyecto `MathService.Tests`.</span><span class="sxs-lookup"><span data-stu-id="3a78b-150">The `dotnet test` command runs a build for the `MathService` project and then for the `MathService.Tests` project.</span></span> <span data-ttu-id="3a78b-151">Después de compilar ambos proyectos, se ejecuta esta única prueba.</span><span class="sxs-lookup"><span data-stu-id="3a78b-151">After building both projects, it runs this single test.</span></span> <span data-ttu-id="3a78b-152">Pasa.</span><span class="sxs-lookup"><span data-stu-id="3a78b-152">It passes.</span></span>

## <a name="completing-the-requirements"></a><span data-ttu-id="3a78b-153">Finalización de los requisitos</span><span class="sxs-lookup"><span data-stu-id="3a78b-153">Completing the requirements</span></span>

<span data-ttu-id="3a78b-154">Ahora que la prueba se ha superado, es el momento de escribir más.</span><span class="sxs-lookup"><span data-stu-id="3a78b-154">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="3a78b-155">El próximo caso simple funciona con una secuencia cuyo único número impar es `1`.</span><span class="sxs-lookup"><span data-stu-id="3a78b-155">The next simple case works with a sequence whose only odd number is `1`.</span></span> <span data-ttu-id="3a78b-156">El número 1 es más simple, porque el cuadrado de 1 es 1.</span><span class="sxs-lookup"><span data-stu-id="3a78b-156">The number 1 is easier because the square of 1 is 1.</span></span> <span data-ttu-id="3a78b-157">Aquí está la prueba siguiente:</span><span class="sxs-lookup"><span data-stu-id="3a78b-157">Here's that next test:</span></span>

```fsharp
[<Fact>]
let ``Sequences of Ones and Evens returns Ones`` () =
    let expected = [1; 1; 1; 1]
    let actual = MyMath.squaresOfOdds [2; 1; 4; 1; 6; 1; 8; 1; 10]
    Assert.Equal<Collections.Generic.IEnumerable<int>>(expected, actual)
```

<span data-ttu-id="3a78b-158">La ejecución de `dotnet test` ejecuta las pruebas y muestra que la prueba nueva no se supera.</span><span class="sxs-lookup"><span data-stu-id="3a78b-158">Executing `dotnet test` runs your tests and shows you that the new test fails.</span></span> <span data-ttu-id="3a78b-159">Ahora actualice el método `squaresOfOdds` para controlar esta prueba nueva.</span><span class="sxs-lookup"><span data-stu-id="3a78b-159">Now, update the `squaresOfOdds` method to handle this new test.</span></span> <span data-ttu-id="3a78b-160">Filtre todos los números impares y quítelos de la secuencia para que se supere esta prueba.</span><span class="sxs-lookup"><span data-stu-id="3a78b-160">You filter all the even numbers out of the sequence to make this test pass.</span></span> <span data-ttu-id="3a78b-161">Para hacerlo, escriba una función de filtro pequeña y use `Seq.filter`:</span><span class="sxs-lookup"><span data-stu-id="3a78b-161">You can do that by writing a small filter function and using `Seq.filter`:</span></span>

```fsharp
let private isOdd x = x % 2 <> 0

let squaresOfOdds xs =
    xs
    |> Seq.filter isOdd
```

<span data-ttu-id="3a78b-162">Falta un paso todavía: el cuadrado de cada uno de los números impares.</span><span class="sxs-lookup"><span data-stu-id="3a78b-162">There's one more step to go: square each of the odd numbers.</span></span> <span data-ttu-id="3a78b-163">Comience escribiendo una prueba nueva:</span><span class="sxs-lookup"><span data-stu-id="3a78b-163">Start by writing a new test:</span></span>

```fsharp
[<Fact>]
let ``SquaresOfOdds works`` () =
    let expected = [1; 9; 25; 49; 81]
    let actual = MyMath.squaresOfOdds [1; 2; 3; 4; 5; 6; 7; 8; 9; 10]
    Assert.Equal(expected, actual)
```

<span data-ttu-id="3a78b-164">Puede corregir la prueba si canaliza la secuencia filtrada a través de una operación de asignación para calcular el cuadrado de cada número impar:</span><span class="sxs-lookup"><span data-stu-id="3a78b-164">You can fix the test by piping the filtered sequence through a map operation to compute the square of each odd number:</span></span>

```fsharp
let private square x = x * x
let private isOdd x = x % 2 <> 0

let squaresOfOdds xs =
    xs
    |> Seq.filter isOdd
    |> Seq.map square
```

<span data-ttu-id="3a78b-165">Ha creado una biblioteca pequeña y un conjunto de pruebas unitarias para esa biblioteca.</span><span class="sxs-lookup"><span data-stu-id="3a78b-165">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="3a78b-166">Ha estructurado la solución, por lo que agregar pruebas y paquetes nuevos es parte del flujo de trabajo normal.</span><span class="sxs-lookup"><span data-stu-id="3a78b-166">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="3a78b-167">Ha centrado la mayor parte del tiempo y del esfuerzo en resolver los objetivos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3a78b-167">You've concentrated most of your time and effort on solving the goals of the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="3a78b-168">Vea también</span><span class="sxs-lookup"><span data-stu-id="3a78b-168">See also</span></span>

- [<span data-ttu-id="3a78b-169">dotnet new</span><span class="sxs-lookup"><span data-stu-id="3a78b-169">dotnet new</span></span>](../tools/dotnet-new.md)
- [<span data-ttu-id="3a78b-170">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="3a78b-170">dotnet sln</span></span>](../tools/dotnet-new.md)
- [<span data-ttu-id="3a78b-171">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="3a78b-171">dotnet add reference</span></span>](../tools/dotnet-add-reference.md)
- [<span data-ttu-id="3a78b-172">dotnet test</span><span class="sxs-lookup"><span data-stu-id="3a78b-172">dotnet test</span></span>](../tools/dotnet-test.md)
