---
title: Bibliotecas de F# de prueba unitaria en .NET Core con pruebas de dotnet y NUnit
description: "Aprenda los conceptos de pruebas unitarias para F# en .NET Core: cree paso a paso una solución de ejemplo mediante pruebas de dotnet y NUnit."
author: rprouse
ms.date: 12/01/2017
ms.topic: article
dev_langs:
- fsharp
ms.prod: .net-core
ms.openlocfilehash: 27a7bb889fd736294252da39b1839b2197b8df03
ms.sourcegitcommit: 401c4427a3ec0d1263543033b3084039278509dc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2017
---
# <a name="unit-testing-f-libraries-in-net-core-using-dotnet-test-and-nunit"></a><span data-ttu-id="b3301-103">Bibliotecas de F# de prueba unitaria en .NET Core con pruebas de dotnet y NUnit</span><span class="sxs-lookup"><span data-stu-id="b3301-103">Unit testing F# libraries in .NET Core using dotnet test and NUnit</span></span>

<span data-ttu-id="b3301-104">Este tutorial le guía por una experiencia interactiva de creación de una solución de ejemplo paso a paso para aprender los conceptos de pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="b3301-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="b3301-105">Si prefiere seguir el tutorial con una solución precompilada, [vea o descargue el código de ejemplo](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/unit-testing-with-fsharp-nunit/) antes de comenzar.</span><span class="sxs-lookup"><span data-stu-id="b3301-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/unit-testing-with-fsharp-nunit/) before you begin.</span></span> <span data-ttu-id="b3301-106">Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="b3301-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="creating-the-source-project"></a><span data-ttu-id="b3301-107">Crear el proyecto de origen</span><span class="sxs-lookup"><span data-stu-id="b3301-107">Creating the source project</span></span>

<span data-ttu-id="b3301-108">Abra una ventana del Shell.</span><span class="sxs-lookup"><span data-stu-id="b3301-108">Open a shell window.</span></span> <span data-ttu-id="b3301-109">Cree un directorio llamado *unit-testing-with-fsharp* que contenga la solución.</span><span class="sxs-lookup"><span data-stu-id="b3301-109">Create a directory called *unit-testing-with-fsharp* to hold the solution.</span></span>
<span data-ttu-id="b3301-110">En este directorio nuevo, ejecute [`dotnet new sln`](../tools/dotnet-new.md) para crear una solución nueva.</span><span class="sxs-lookup"><span data-stu-id="b3301-110">Inside this new directory, run [`dotnet new sln`](../tools/dotnet-new.md) to create a new solution.</span></span> <span data-ttu-id="b3301-111">Esto permite facilitar la administración de la biblioteca de clases y del proyecto de prueba unitaria.</span><span class="sxs-lookup"><span data-stu-id="b3301-111">This makes it easier to manage both the class library and the unit test project.</span></span>
<span data-ttu-id="b3301-112">En el directorio de la solución, cree un directorio *MathService*.</span><span class="sxs-lookup"><span data-stu-id="b3301-112">Inside the solution directory, create a *MathService* directory.</span></span> <span data-ttu-id="b3301-113">Esta es la estructura de directorios y archivos hasta el momento:</span><span class="sxs-lookup"><span data-stu-id="b3301-113">The directory and file structure thus far is shown below:</span></span>

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
```

<span data-ttu-id="b3301-114">Make *MathService* the current directory and run [`dotnet new classlib -lang F#`](../tools/dotnet-new.md) to create the source project.</span><span class="sxs-lookup"><span data-stu-id="b3301-114">Make *MathService* the current directory and run [`dotnet new classlib -lang F#`](../tools/dotnet-new.md) to create the source project.</span></span>  <span data-ttu-id="b3301-115">Para usar el desarrollo controlado por pruebas (TDD), tendrá que crear una implementación de errores del servicio de matemáticas:</span><span class="sxs-lookup"><span data-stu-id="b3301-115">To use test-driven development (TDD), you'll create a failing implementation of the math service:</span></span>

```fsharp
module MyMath =
    let sumOfSquares xs = raise (System.NotImplementedException("You haven't written a test yet!"))
```

<span data-ttu-id="b3301-116">Cambie nuevamente el directorio al directorio *unit-testing-with-fsharp*.</span><span class="sxs-lookup"><span data-stu-id="b3301-116">Change the directory back to the *unit-testing-with-fsharp* directory.</span></span> <span data-ttu-id="b3301-117">Ejecute [`dotnet sln add .\MathService\MathService.fsproj`](../tools/dotnet-sln.md) para agregar el proyecto de biblioteca de clases a la solución.</span><span class="sxs-lookup"><span data-stu-id="b3301-117">Run [`dotnet sln add .\MathService\MathService.fsproj`](../tools/dotnet-sln.md) to add the class library project to the solution.</span></span>

## <a name="install-the-nunit-project-template"></a><span data-ttu-id="b3301-118">Instalación de la plantilla de proyecto NUnit</span><span class="sxs-lookup"><span data-stu-id="b3301-118">Install the NUnit project template</span></span>

<span data-ttu-id="b3301-119">Debe instalar las plantillas de proyecto de prueba NUnit para poder crear un proyecto de prueba.</span><span class="sxs-lookup"><span data-stu-id="b3301-119">The NUnit test project templates need to be installed before creating a test project.</span></span> <span data-ttu-id="b3301-120">Solo deberá hacerlo una vez en cada máquina de desarrollador en la que creará proyectos NUnit.</span><span class="sxs-lookup"><span data-stu-id="b3301-120">This only needs to be done once on each developer machine where you'll create new NUnit projects.</span></span> <span data-ttu-id="b3301-121">Ejecute [`dotnet new -i NUnit3.DotNetNew.Template`](../tools/dotnet-new.md) para instalar las plantillas NUnit.</span><span class="sxs-lookup"><span data-stu-id="b3301-121">Run [`dotnet new -i NUnit3.DotNetNew.Template`](../tools/dotnet-new.md) to install the NUnit templates.</span></span>

 ```
 dotnet new -i NUnit3.DotNetNew.Template
 ```

## <a name="creating-the-test-project"></a><span data-ttu-id="b3301-122">Crear el proyecto de prueba</span><span class="sxs-lookup"><span data-stu-id="b3301-122">Creating the test project</span></span>

<span data-ttu-id="b3301-123">A continuación, cree el directorio *MathService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="b3301-123">Next, create the *MathService.Tests* directory.</span></span> <span data-ttu-id="b3301-124">En el esquema siguiente se muestra la estructura de directorios:</span><span class="sxs-lookup"><span data-stu-id="b3301-124">The following outline shows the directory structure:</span></span>

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
        Source Files
        MathService.fsproj
    /MathService.Tests
```

<span data-ttu-id="b3301-125">Convierta el directorio *MathService.Tests* en el directorio actual y cree un proyecto nuevo con [`dotnet new nunit -lang F#`](../tools/dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="b3301-125">Make the *MathService.Tests* directory the current directory and create a new project using [`dotnet new nunit -lang F#`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="b3301-126">Esto crea un proyecto de prueba que usa NUnit como el marco de pruebas.</span><span class="sxs-lookup"><span data-stu-id="b3301-126">This creates a test project that uses NUnit as the test framework.</span></span> <span data-ttu-id="b3301-127">La plantilla generada configura el ejecutor de pruebas en *MathServiceTests.fsproj*:</span><span class="sxs-lookup"><span data-stu-id="b3301-127">The generated template configures the test runner in the *MathServiceTests.fsproj*:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.5.0" />
  <PackageReference Include="NUnit" Version="3.9.0" />
  <PackageReference Include="NUnit3TestAdapter" Version="3.9.0" />
</ItemGroup>
```

<span data-ttu-id="b3301-128">El proyecto de prueba requiere otros paquetes para crear y ejecutar pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="b3301-128">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="b3301-129">En el paso anterior, `dotnet new` agrega NUnit y el adaptador de prueba NUnit.</span><span class="sxs-lookup"><span data-stu-id="b3301-129">`dotnet new` in the previous step added NUnit and the NUnit test adapter.</span></span> <span data-ttu-id="b3301-130">Ahora, agregue la biblioteca de clases `MathService` como otra dependencia al proyecto.</span><span class="sxs-lookup"><span data-stu-id="b3301-130">Now, add the `MathService` class library as another dependency to the project.</span></span> <span data-ttu-id="b3301-131">Use el comando [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="b3301-131">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```
dotnet add reference ../MathService/MathService.fsproj
```

<span data-ttu-id="b3301-132">Puede ver todo el archivo en el [repositorio de muestras](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-with-fsharp/MathService.Tests/MathService.Tests.fsproj) en GitHub.</span><span class="sxs-lookup"><span data-stu-id="b3301-132">You can see the entire file in the [samples repository](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-with-fsharp/MathService.Tests/MathService.Tests.fsproj) on GitHub.</span></span>

<span data-ttu-id="b3301-133">Tiene el diseño de solución final siguiente:</span><span class="sxs-lookup"><span data-stu-id="b3301-133">You have the following final solution layout:</span></span>

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

<span data-ttu-id="b3301-134">Ejecute [`dotnet sln add .\MathService.Tests\MathService.Tests.fsproj`](../tools/dotnet-sln.md) en el directorio *unit-testing-with-fsharp*.</span><span class="sxs-lookup"><span data-stu-id="b3301-134">Execute [`dotnet sln add .\MathService.Tests\MathService.Tests.fsproj`](../tools/dotnet-sln.md) in the *unit-testing-with-fsharp* directory.</span></span>

## <a name="creating-the-first-test"></a><span data-ttu-id="b3301-135">Crear la primera prueba</span><span class="sxs-lookup"><span data-stu-id="b3301-135">Creating the first test</span></span>

<span data-ttu-id="b3301-136">El enfoque de TDD requiere la escritura de una prueba con errores, después la valida y finalmente repite el proceso.</span><span class="sxs-lookup"><span data-stu-id="b3301-136">The TDD approach calls for writing one failing test, making it pass, then repeating the process.</span></span> <span data-ttu-id="b3301-137">Abra *Tests.fs* y agregue el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="b3301-137">Open *Tests.fs* and add the following code:</span></span>

```fsharp
namespace MathService.Tests

open System
open NUnit.Framework
open MathService

[<TestFixture>]
type TestClass () =

    [<Test>]
    member this.TestMethodPassing() =
        Assert.True(true)

    [<Test>]
     member this.FailEveryTime() = Assert.True(false)
```

<span data-ttu-id="b3301-138">El atributo `[<TestFixture>]` indica una clase que contiene pruebas.</span><span class="sxs-lookup"><span data-stu-id="b3301-138">The `[<TestFixture>]` attribute denotes a class that contains tests.</span></span> <span data-ttu-id="b3301-139">El atributo `[<Test>]` indica un método de prueba que el ejecutor de pruebas ejecuta.</span><span class="sxs-lookup"><span data-stu-id="b3301-139">The `[<Test>]` attribute denotes a test method that is run by the test runner.</span></span> <span data-ttu-id="b3301-140">En el directorio *unit-testing-with-fsharp*, ejecute [`dotnet test`](../tools/dotnet-test.md) para compilar las pruebas y la biblioteca de clases y luego ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="b3301-140">From the *unit-testing-with-fsharp* directory, execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="b3301-141">El ejecutor de pruebas de NUnit tiene el punto de entrada del programa para ejecutar las pruebas desde la consola.</span><span class="sxs-lookup"><span data-stu-id="b3301-141">The NUnit test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="b3301-142">`dotnet test` inicia el ejecutor de pruebas con el proyecto de prueba unitaria que creó.</span><span class="sxs-lookup"><span data-stu-id="b3301-142">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="b3301-143">Estas dos pruebas muestran las pruebas superadas y con errores más básicas.</span><span class="sxs-lookup"><span data-stu-id="b3301-143">These two tests show the most basic passing and failing tests.</span></span> <span data-ttu-id="b3301-144">`My test` indica que se supera y `Fail every time` indica que no.</span><span class="sxs-lookup"><span data-stu-id="b3301-144">`My test` passes, and `Fail every time` fails.</span></span> <span data-ttu-id="b3301-145">Ahora, cree una prueba para el método `sumOfSquares`.</span><span class="sxs-lookup"><span data-stu-id="b3301-145">Now, create a test for the `sumOfSquares` method.</span></span> <span data-ttu-id="b3301-146">El método `sumOfSquares` devuelve la suma de los cuadrados de todos los valores enteros impares que forman parte de la secuencia de entrada.</span><span class="sxs-lookup"><span data-stu-id="b3301-146">The `sumOfSquares` method returns the sum of the squares of all odd integer values that are part of the input sequence.</span></span> <span data-ttu-id="b3301-147">En lugar de intentar escribir todas esas funciones a la vez, puede crear de forma iterativa pruebas que validen la funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="b3301-147">Rather than trying to write all of those functions at once, you can iteratively create tests that validate the functionality.</span></span> <span data-ttu-id="b3301-148">Hacer cada prueba superada significa crear la funcionalidad necesaria para el método.</span><span class="sxs-lookup"><span data-stu-id="b3301-148">Making each test pass means creating the necessary functionality for the method.</span></span>

<span data-ttu-id="b3301-149">La prueba más sencilla que se puede escribir es llamar a `sumOfSquares` con todos los números impares, donde el resultado sea una secuencia de enteros vacía.</span><span class="sxs-lookup"><span data-stu-id="b3301-149">The simplest test we can write is to call `sumOfSquares` with all even numbers, where the result should be an empty sequence of integers.</span></span>  <span data-ttu-id="b3301-150">Aquí se muestra la prueba:</span><span class="sxs-lookup"><span data-stu-id="b3301-150">Here's that test:</span></span>

```fsharp
[<Test>]
member this.TestEvenSequence() =
    let expected = Seq.empty<int> |> Seq.toList
    let actual = MyMath.sumOfSquares [2; 4; 6; 8; 10]
    Assert.That(actual, Is.EqualTo(expected))
```

<span data-ttu-id="b3301-151">Observe que la secuencia `expected` se convirtió en lista.</span><span class="sxs-lookup"><span data-stu-id="b3301-151">Notice that the `expected` sequence has been converted to a list.</span></span> <span data-ttu-id="b3301-152">El marco de NUnit se basa en muchos tipos de .NET estándar.</span><span class="sxs-lookup"><span data-stu-id="b3301-152">The NUnit framework relies on many standard .NET types.</span></span> <span data-ttu-id="b3301-153">Esa dependencia significa que la interfaz pública y los resultados esperados admiten <xref:System.Collections.ICollection> en lugar de <xref:System.Collections.IEnumerable>.</span><span class="sxs-lookup"><span data-stu-id="b3301-153">That dependency means that your public interface and expected results support <xref:System.Collections.ICollection> rather than <xref:System.Collections.IEnumerable>.</span></span>

<span data-ttu-id="b3301-154">Cuando ejecuta la prueba, se observa que no se supera la prueba.</span><span class="sxs-lookup"><span data-stu-id="b3301-154">When you run the test, you see that your test fails.</span></span> <span data-ttu-id="b3301-155">Todavía no ha creado la implementación.</span><span class="sxs-lookup"><span data-stu-id="b3301-155">You haven't created the implementation yet.</span></span> <span data-ttu-id="b3301-156">Cree esta prueba escribiendo el código más simple en la clase `Mathservice` que funciona:</span><span class="sxs-lookup"><span data-stu-id="b3301-156">Make this test by writing the simplest code in the `Mathservice` class that works:</span></span>

```csharp
let sumOfSquares xs =
    Seq.empty<int> |> Seq.toList
```

<span data-ttu-id="b3301-157">En el directorio *unit-testing-with-fsharp*, vuelva a ejecutar `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="b3301-157">In the *unit-testing-with-fsharp* directory, run `dotnet test` again.</span></span> <span data-ttu-id="b3301-158">El comando `dotnet test` ejecuta una compilación del proyecto `MathService` y luego del proyecto `MathService.Tests`.</span><span class="sxs-lookup"><span data-stu-id="b3301-158">The `dotnet test` command runs a build for the `MathService` project and then for the `MathService.Tests` project.</span></span> <span data-ttu-id="b3301-159">Después de compilar ambos proyectos, se ejecuta esta única prueba.</span><span class="sxs-lookup"><span data-stu-id="b3301-159">After building both projects, it runs this single test.</span></span> <span data-ttu-id="b3301-160">Pasa.</span><span class="sxs-lookup"><span data-stu-id="b3301-160">It passes.</span></span>

## <a name="completing-the-requirements"></a><span data-ttu-id="b3301-161">Finalización de los requisitos</span><span class="sxs-lookup"><span data-stu-id="b3301-161">Completing the requirements</span></span>

<span data-ttu-id="b3301-162">Ahora que la prueba se ha superado, es el momento de escribir más.</span><span class="sxs-lookup"><span data-stu-id="b3301-162">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="b3301-163">El próximo caso simple funciona con una secuencia cuyo único número impar es `1`.</span><span class="sxs-lookup"><span data-stu-id="b3301-163">The next simple case works with a sequence whose only odd number is `1`.</span></span> <span data-ttu-id="b3301-164">El número 1 es más simple, porque el cuadrado de 1 es 1.</span><span class="sxs-lookup"><span data-stu-id="b3301-164">The number 1 is easier because the square of 1 is 1.</span></span> <span data-ttu-id="b3301-165">Aquí está la prueba siguiente:</span><span class="sxs-lookup"><span data-stu-id="b3301-165">Here's that next test:</span></span>

```fsharp
[<Test>]
member public this.SumOnesAndEvens() =
    let expected = [1; 1; 1; 1]
    let actual = MyMath.sumOfSquares [2; 1; 4; 1; 6; 1; 8; 1; 10]
    Assert.That(actual, Is.EqualTo(expected))
```

<span data-ttu-id="b3301-166">Si se ejecuta `dotnet test`, la prueba nueva se falla.</span><span class="sxs-lookup"><span data-stu-id="b3301-166">Executing `dotnet test` fails the new test.</span></span> <span data-ttu-id="b3301-167">Debe actualizar el método `sumOfSquares` para controlar esta prueba nueva.</span><span class="sxs-lookup"><span data-stu-id="b3301-167">You must update the `sumOfSquares` method to handle this new test.</span></span> <span data-ttu-id="b3301-168">Debe filtrar todos los números impares y quitarlos de la secuencia para que se supere esta prueba.</span><span class="sxs-lookup"><span data-stu-id="b3301-168">You must filter all the even numbers out of the sequence to make this test pass.</span></span> <span data-ttu-id="b3301-169">Para hacerlo, escriba una función de filtro pequeña y use `Seq.filter`:</span><span class="sxs-lookup"><span data-stu-id="b3301-169">You can do that by writing a small filter function and using `Seq.filter`:</span></span>

```fsharp
let private isOdd x = x % 2 <> 0

let sumOfSquares xs =
    xs
    |> Seq.filter isOdd
    |> Seq.toList
```

<span data-ttu-id="b3301-170">Observe la llamada a `Seq.toList`.</span><span class="sxs-lookup"><span data-stu-id="b3301-170">Notice the call to `Seq.toList`.</span></span> <span data-ttu-id="b3301-171">Esa acción crea una lista, que implemente la interfaz <xref:System.Collections.ICollection>.</span><span class="sxs-lookup"><span data-stu-id="b3301-171">That creates a list, which implements the <xref:System.Collections.ICollection> interface.</span></span>

<span data-ttu-id="b3301-172">Falta un paso todavía: el cuadrado de cada uno de los números impares.</span><span class="sxs-lookup"><span data-stu-id="b3301-172">There's one more step to go: square each of the odd numbers.</span></span> <span data-ttu-id="b3301-173">Comience escribiendo una prueba nueva:</span><span class="sxs-lookup"><span data-stu-id="b3301-173">Start by writing a new test:</span></span>

```fsharp
[<Test>]
member public this.TestSquaresOfOdds() =
    let expected = [1; 9; 25; 49; 81]
    let actual = MyMath.sumOfSquares [1; 2; 3; 4; 5; 6; 7; 8; 9; 10]
    Assert.That(actual, Is.EqualTo(expected))
```

<span data-ttu-id="b3301-174">Puede corregir la prueba si canaliza la secuencia filtrada a través de una operación de asignación para calcular el cuadrado de cada número impar:</span><span class="sxs-lookup"><span data-stu-id="b3301-174">You can fix the test by piping the filtered sequence through a map operation to compute the square of each odd number:</span></span>

```fsharp
let private square x = x * x
let private isOdd x = x % 2 <> 0

let sumOfSquares xs =
    xs
    |> Seq.filter isOdd
    |> Seq.map square
    |> Seq.toList
```

<span data-ttu-id="b3301-175">Ha creado una biblioteca pequeña y un conjunto de pruebas unitarias para esa biblioteca.</span><span class="sxs-lookup"><span data-stu-id="b3301-175">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="b3301-176">Ha estructurado la solución, por lo que agregar pruebas y paquetes nuevos es parte del flujo de trabajo normal.</span><span class="sxs-lookup"><span data-stu-id="b3301-176">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="b3301-177">Ha centrado la mayor parte del tiempo y del esfuerzo en resolver los objetivos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b3301-177">You've concentrated most of your time and effort on solving the goals of the application.</span></span>
