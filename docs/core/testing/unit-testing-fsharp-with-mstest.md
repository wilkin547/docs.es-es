---
title: Prueba unitaria de F# en .NET Core con dotnet test y MSTest
description: 'Aprenda los conceptos de pruebas unitarias para F# en .NET Core: cree paso a paso una solución de ejemplo mediante pruebas de dotnet y MSTest.'
author: billwagner
ms.author: wiwagn
ms.date: 08/30/2017
ms.openlocfilehash: 2245efef9ab63303b3ae8b5d45ad8955b334e6e5
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104873528"
---
# <a name="unit-testing-f-libraries-in-net-core-using-dotnet-test-and-mstest"></a><span data-ttu-id="55273-103">Bibliotecas de F# de prueba unitaria en .NET Core con pruebas de dotnet y MSTest</span><span class="sxs-lookup"><span data-stu-id="55273-103">Unit testing F# libraries in .NET Core using dotnet test and MSTest</span></span>

<span data-ttu-id="55273-104">Este tutorial le guía por una experiencia interactiva de creación de una solución de ejemplo paso a paso para aprender los conceptos de pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="55273-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="55273-105">Si prefiere seguir el tutorial con una solución precompilada, [vea o descargue el código de ejemplo](https://github.com/dotnet/samples/tree/main/core/getting-started/unit-testing-with-fsharp-mstest/) antes de comenzar.</span><span class="sxs-lookup"><span data-stu-id="55273-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/samples/tree/main/core/getting-started/unit-testing-with-fsharp-mstest/) before you begin.</span></span> <span data-ttu-id="55273-106">Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../../samples-and-tutorials/index.md#view-and-download-samples).</span><span class="sxs-lookup"><span data-stu-id="55273-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#view-and-download-samples).</span></span>

[!INCLUDE [testing an ASP.NET Core project from .NET Core](../../../includes/core-testing-note-aspnet.md)]

## <a name="creating-the-source-project"></a><span data-ttu-id="55273-107">Crear el proyecto de origen</span><span class="sxs-lookup"><span data-stu-id="55273-107">Creating the source project</span></span>

<span data-ttu-id="55273-108">Abra una ventana del Shell.</span><span class="sxs-lookup"><span data-stu-id="55273-108">Open a shell window.</span></span> <span data-ttu-id="55273-109">Cree un directorio llamado *unit-testing-with-fsharp* que contenga la solución.</span><span class="sxs-lookup"><span data-stu-id="55273-109">Create a directory called *unit-testing-with-fsharp* to hold the solution.</span></span>
<span data-ttu-id="55273-110">En este directorio nuevo, ejecute `dotnet new sln` para crear una solución nueva.</span><span class="sxs-lookup"><span data-stu-id="55273-110">Inside this new directory, run `dotnet new sln` to create a new solution.</span></span> <span data-ttu-id="55273-111">Esto permite facilitar la administración de la biblioteca de clases y del proyecto de prueba unitaria.</span><span class="sxs-lookup"><span data-stu-id="55273-111">This makes it easier to manage both the class library and the unit test project.</span></span>
<span data-ttu-id="55273-112">En el directorio de la solución, cree un directorio *MathService*.</span><span class="sxs-lookup"><span data-stu-id="55273-112">Inside the solution directory, create a *MathService* directory.</span></span> <span data-ttu-id="55273-113">Esta es la estructura de directorios y archivos hasta el momento:</span><span class="sxs-lookup"><span data-stu-id="55273-113">The directory and file structure thus far is shown below:</span></span>

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
```

<span data-ttu-id="55273-114">Convierta *MathService* en el directorio actual y ejecute `dotnet new classlib -lang "F#"` para crear el proyecto de origen.</span><span class="sxs-lookup"><span data-stu-id="55273-114">Make *MathService* the current directory and run `dotnet new classlib -lang "F#"` to create the source project.</span></span>  <span data-ttu-id="55273-115">Creará una implementación de errores del servicio de matemáticas:</span><span class="sxs-lookup"><span data-stu-id="55273-115">You'll create a failing implementation of the math service:</span></span>

```fsharp
module MyMath =
    let squaresOfOdds xs = raise (System.NotImplementedException("You haven't written a test yet!"))
```

<span data-ttu-id="55273-116">Cambie nuevamente el directorio al directorio *unit-testing-with-fsharp*.</span><span class="sxs-lookup"><span data-stu-id="55273-116">Change the directory back to the *unit-testing-with-fsharp* directory.</span></span> <span data-ttu-id="55273-117">Ejecute `dotnet sln add .\MathService\MathService.fsproj` para agregar el proyecto de biblioteca de clases a la solución.</span><span class="sxs-lookup"><span data-stu-id="55273-117">Run `dotnet sln add .\MathService\MathService.fsproj` to add the class library project to the solution.</span></span>

## <a name="creating-the-test-project"></a><span data-ttu-id="55273-118">Crear el proyecto de prueba</span><span class="sxs-lookup"><span data-stu-id="55273-118">Creating the test project</span></span>

<span data-ttu-id="55273-119">A continuación, cree el directorio *MathService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="55273-119">Next, create the *MathService.Tests* directory.</span></span> <span data-ttu-id="55273-120">En el esquema siguiente se muestra la estructura de directorios:</span><span class="sxs-lookup"><span data-stu-id="55273-120">The following outline shows the directory structure:</span></span>

```console
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
        Source Files
        MathService.fsproj
    /MathService.Tests
```

<span data-ttu-id="55273-121">Convierta el directorio *MathService.Tests* en el directorio actual y cree un proyecto nuevo con `dotnet new mstest -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="55273-121">Make the *MathService.Tests* directory the current directory and create a new project using `dotnet new mstest -lang "F#"`.</span></span> <span data-ttu-id="55273-122">Esto crea un proyecto de prueba que usa MSTest como el marco de pruebas.</span><span class="sxs-lookup"><span data-stu-id="55273-122">This creates a test project that uses MSTest as the test framework.</span></span> <span data-ttu-id="55273-123">La plantilla generada configura el ejecutor de pruebas en *MathServiceTests.fsproj*:</span><span class="sxs-lookup"><span data-stu-id="55273-123">The generated template configures the test runner in the *MathServiceTests.fsproj*:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.3.0-preview-20170628-02" />
  <PackageReference Include="MSTest.TestAdapter" Version="1.1.18" />
  <PackageReference Include="MSTest.TestFramework" Version="1.1.18" />
</ItemGroup>
```

<span data-ttu-id="55273-124">El proyecto de prueba requiere otros paquetes para crear y ejecutar pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="55273-124">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="55273-125">`dotnet new` en el paso anterior agregó MSTest y el ejecutor de MSTest.</span><span class="sxs-lookup"><span data-stu-id="55273-125">`dotnet new` in the previous step added MSTest and the MSTest runner.</span></span> <span data-ttu-id="55273-126">Ahora, agregue la biblioteca de clases `MathService` como otra dependencia al proyecto.</span><span class="sxs-lookup"><span data-stu-id="55273-126">Now, add the `MathService` class library as another dependency to the project.</span></span> <span data-ttu-id="55273-127">Use el comando `dotnet add reference`:</span><span class="sxs-lookup"><span data-stu-id="55273-127">Use the `dotnet add reference` command:</span></span>

```dotnetcli
dotnet add reference ../MathService/MathService.fsproj
```

<span data-ttu-id="55273-128">Puede ver todo el archivo en el [repositorio de muestras](https://github.com/dotnet/samples/blob/main/core/getting-started/unit-testing-with-fsharp/MathService.Tests/MathService.Tests.fsproj) en GitHub.</span><span class="sxs-lookup"><span data-stu-id="55273-128">You can see the entire file in the [samples repository](https://github.com/dotnet/samples/blob/main/core/getting-started/unit-testing-with-fsharp/MathService.Tests/MathService.Tests.fsproj) on GitHub.</span></span>

<span data-ttu-id="55273-129">Tiene el diseño de solución final siguiente:</span><span class="sxs-lookup"><span data-stu-id="55273-129">You have the following final solution layout:</span></span>

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

<span data-ttu-id="55273-130">Ejecute `dotnet sln add .\MathService.Tests\MathService.Tests.fsproj` en el directorio *unit-testing-with-fsharp*.</span><span class="sxs-lookup"><span data-stu-id="55273-130">Execute `dotnet sln add .\MathService.Tests\MathService.Tests.fsproj` in the *unit-testing-with-fsharp* directory.</span></span>

## <a name="creating-the-first-test"></a><span data-ttu-id="55273-131">Crear la primera prueba</span><span class="sxs-lookup"><span data-stu-id="55273-131">Creating the first test</span></span>

<span data-ttu-id="55273-132">Escribirá una prueba de errores, la aprobará y, luego, repetirá el proceso.</span><span class="sxs-lookup"><span data-stu-id="55273-132">You write one failing test, make it pass, then repeat the process.</span></span> <span data-ttu-id="55273-133">Abra *Tests.fs* y agregue el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="55273-133">Open *Tests.fs* and add the following code:</span></span>

```fsharp
namespace MathService.Tests

open System
open Microsoft.VisualStudio.TestTools.UnitTesting
open MathService

[<TestClass>]
type TestClass () =

    [<TestMethod>]
    member this.TestMethodPassing() =
        Assert.IsTrue(true)

    [<TestMethod>]
     member this.FailEveryTime() = Assert.IsTrue(false)
```

<span data-ttu-id="55273-134">El atributo `[<TestClass>]` indica una clase que contiene pruebas.</span><span class="sxs-lookup"><span data-stu-id="55273-134">The `[<TestClass>]` attribute denotes a class that contains tests.</span></span> <span data-ttu-id="55273-135">El atributo `[<TestMethod>]` indica un método de prueba que el ejecutor de pruebas ejecuta.</span><span class="sxs-lookup"><span data-stu-id="55273-135">The `[<TestMethod>]` attribute denotes a test method that is run by the test runner.</span></span> <span data-ttu-id="55273-136">En el directorio *unit-testing-with-fsharp*, ejecute `dotnet test` para compilar las pruebas y la biblioteca de clases y luego ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="55273-136">From the *unit-testing-with-fsharp* directory, execute `dotnet test` to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="55273-137">El ejecutor de pruebas de MSTest tiene el punto de entrada del programa para ejecutar las pruebas desde la consola.</span><span class="sxs-lookup"><span data-stu-id="55273-137">The MSTest test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="55273-138">`dotnet test` inicia el ejecutor de pruebas con el proyecto de prueba unitaria que creó.</span><span class="sxs-lookup"><span data-stu-id="55273-138">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="55273-139">Estas dos pruebas muestran las pruebas superadas y con errores más básicas.</span><span class="sxs-lookup"><span data-stu-id="55273-139">These two tests show the most basic passing and failing tests.</span></span> <span data-ttu-id="55273-140">`My test` indica que se supera y `Fail every time` indica que no.</span><span class="sxs-lookup"><span data-stu-id="55273-140">`My test` passes, and `Fail every time` fails.</span></span> <span data-ttu-id="55273-141">Ahora, cree una prueba para el método `squaresOfOdds`.</span><span class="sxs-lookup"><span data-stu-id="55273-141">Now, create a test for the `squaresOfOdds` method.</span></span> <span data-ttu-id="55273-142">El método `squaresOfOdds` devuelve una lista de los cuadrados de todos los valores enteros impares que forman parte de la secuencia de entrada.</span><span class="sxs-lookup"><span data-stu-id="55273-142">The `squaresOfOdds` method returns a list of the squares of all odd integer values that are part of the input sequence.</span></span> <span data-ttu-id="55273-143">En lugar de intentar escribir todas esas funciones a la vez, puede crear de forma iterativa pruebas que validen la funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="55273-143">Rather than trying to write all of those functions at once, you can iteratively create tests that validate the functionality.</span></span> <span data-ttu-id="55273-144">Hacer cada prueba superada significa crear la funcionalidad necesaria para el método.</span><span class="sxs-lookup"><span data-stu-id="55273-144">Making each test pass means creating the necessary functionality for the method.</span></span>

<span data-ttu-id="55273-145">La prueba más sencilla que se puede escribir es llamar a `squaresOfOdds` con todos los números impares, donde el resultado sea una secuencia de enteros vacía.</span><span class="sxs-lookup"><span data-stu-id="55273-145">The simplest test we can write is to call `squaresOfOdds` with all even numbers, where the result should be an empty sequence of integers.</span></span>  <span data-ttu-id="55273-146">Aquí se muestra la prueba:</span><span class="sxs-lookup"><span data-stu-id="55273-146">Here's that test:</span></span>

```fsharp
[<TestMethod>]
member this.TestEvenSequence() =
    let expected = Seq.empty<int> |> Seq.toList
    let actual = MyMath.squaresOfOdds [2; 4; 6; 8; 10]
    Assert.AreEqual(expected, actual)
```

<span data-ttu-id="55273-147">Observe que la secuencia `expected` se convirtió en lista.</span><span class="sxs-lookup"><span data-stu-id="55273-147">Notice that the `expected` sequence has been converted to a list.</span></span> <span data-ttu-id="55273-148">La biblioteca de MSTest se basa en muchos tipos de .NET estándar.</span><span class="sxs-lookup"><span data-stu-id="55273-148">The MSTest library relies on many standard .NET types.</span></span> <span data-ttu-id="55273-149">Esa dependencia significa que la interfaz pública y los resultados esperados admiten <xref:System.Collections.ICollection> en lugar de <xref:System.Collections.IEnumerable>.</span><span class="sxs-lookup"><span data-stu-id="55273-149">That dependency means that your public interface and expected results support <xref:System.Collections.ICollection> rather than <xref:System.Collections.IEnumerable>.</span></span>

<span data-ttu-id="55273-150">Cuando ejecuta la prueba, se observa que no se supera la prueba.</span><span class="sxs-lookup"><span data-stu-id="55273-150">When you run the test, you see that your test fails.</span></span> <span data-ttu-id="55273-151">Todavía no ha creado la implementación.</span><span class="sxs-lookup"><span data-stu-id="55273-151">You haven't created the implementation yet.</span></span> <span data-ttu-id="55273-152">Cree esta prueba que se supera escribiendo el código más simple en la clase `Mathservice` que funciona:</span><span class="sxs-lookup"><span data-stu-id="55273-152">Make this test pass by writing the simplest code in the `Mathservice` class that works:</span></span>

```fsharp
let squaresOfOdds xs =
    Seq.empty<int> |> Seq.toList
```

<span data-ttu-id="55273-153">En el directorio *unit-testing-with-fsharp*, vuelva a ejecutar `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="55273-153">In the *unit-testing-with-fsharp* directory, run `dotnet test` again.</span></span> <span data-ttu-id="55273-154">El comando `dotnet test` ejecuta una compilación del proyecto `MathService` y luego del proyecto `MathService.Tests`.</span><span class="sxs-lookup"><span data-stu-id="55273-154">The `dotnet test` command runs a build for the `MathService` project and then for the `MathService.Tests` project.</span></span> <span data-ttu-id="55273-155">Después de compilar ambos proyectos, se ejecuta esta única prueba.</span><span class="sxs-lookup"><span data-stu-id="55273-155">After building both projects, it runs this single test.</span></span> <span data-ttu-id="55273-156">Pasa.</span><span class="sxs-lookup"><span data-stu-id="55273-156">It passes.</span></span>

## <a name="completing-the-requirements"></a><span data-ttu-id="55273-157">Finalización de los requisitos</span><span class="sxs-lookup"><span data-stu-id="55273-157">Completing the requirements</span></span>

<span data-ttu-id="55273-158">Ahora que la prueba se ha superado, es el momento de escribir más.</span><span class="sxs-lookup"><span data-stu-id="55273-158">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="55273-159">El próximo caso simple funciona con una secuencia cuyo único número impar es `1`.</span><span class="sxs-lookup"><span data-stu-id="55273-159">The next simple case works with a sequence whose only odd number is `1`.</span></span> <span data-ttu-id="55273-160">El número 1 es más simple, porque el cuadrado de 1 es 1.</span><span class="sxs-lookup"><span data-stu-id="55273-160">The number 1 is easier because the square of 1 is 1.</span></span> <span data-ttu-id="55273-161">Aquí está la prueba siguiente:</span><span class="sxs-lookup"><span data-stu-id="55273-161">Here's that next test:</span></span>

```fsharp
[<TestMethod>]
member public this.TestOnesAndEvens() =
    let expected = [1; 1; 1; 1]
    let actual = MyMath.squaresOfOdds [2; 1; 4; 1; 6; 1; 8; 1; 10]
    Assert.AreEqual(expected, actual)
```

<span data-ttu-id="55273-162">Si se ejecuta `dotnet test`, la prueba nueva se falla.</span><span class="sxs-lookup"><span data-stu-id="55273-162">Executing `dotnet test` fails the new test.</span></span> <span data-ttu-id="55273-163">Debe actualizar el método `squaresOfOdds` para controlar esta prueba nueva.</span><span class="sxs-lookup"><span data-stu-id="55273-163">You must update the `squaresOfOdds` method to handle this new test.</span></span> <span data-ttu-id="55273-164">Debe filtrar todos los números impares y quitarlos de la secuencia para que se supere esta prueba.</span><span class="sxs-lookup"><span data-stu-id="55273-164">You must filter all the even numbers out of the sequence to make this test pass.</span></span> <span data-ttu-id="55273-165">Para hacerlo, escriba una función de filtro pequeña y use `Seq.filter`:</span><span class="sxs-lookup"><span data-stu-id="55273-165">You can do that by writing a small filter function and using `Seq.filter`:</span></span>

```fsharp
let private isOdd x = x % 2 <> 0

let squaresOfOdds xs =
    xs
    |> Seq.filter isOdd |> Seq.toList
```

<span data-ttu-id="55273-166">Observe la llamada a `Seq.toList`.</span><span class="sxs-lookup"><span data-stu-id="55273-166">Notice the call to `Seq.toList`.</span></span> <span data-ttu-id="55273-167">Esa acción crea una lista, que implemente la interfaz <xref:System.Collections.ICollection>.</span><span class="sxs-lookup"><span data-stu-id="55273-167">That creates a list, which implements the <xref:System.Collections.ICollection> interface.</span></span>

<span data-ttu-id="55273-168">Falta un paso todavía: el cuadrado de cada uno de los números impares.</span><span class="sxs-lookup"><span data-stu-id="55273-168">There's one more step to go: square each of the odd numbers.</span></span> <span data-ttu-id="55273-169">Comience escribiendo una prueba nueva:</span><span class="sxs-lookup"><span data-stu-id="55273-169">Start by writing a new test:</span></span>

```fsharp
[<TestMethod>]
member public this.TestSquaresOfOdds() =
    let expected = [1; 9; 25; 49; 81]
    let actual = MyMath.squaresOfOdds [1; 2; 3; 4; 5; 6; 7; 8; 9; 10]
    Assert.AreEqual(expected, actual)
```

<span data-ttu-id="55273-170">Puede corregir la prueba si canaliza la secuencia filtrada a través de una operación de asignación para calcular el cuadrado de cada número impar:</span><span class="sxs-lookup"><span data-stu-id="55273-170">You can fix the test by piping the filtered sequence through a map operation to compute the square of each odd number:</span></span>

```fsharp
let private square x = x * x
let private isOdd x = x % 2 <> 0

let squaresOfOdds xs =
    xs
    |> Seq.filter isOdd
    |> Seq.map square
    |> Seq.toList
```

<span data-ttu-id="55273-171">Ha creado una biblioteca pequeña y un conjunto de pruebas unitarias para esa biblioteca.</span><span class="sxs-lookup"><span data-stu-id="55273-171">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="55273-172">Ha estructurado la solución, por lo que agregar pruebas y paquetes nuevos es parte del flujo de trabajo normal.</span><span class="sxs-lookup"><span data-stu-id="55273-172">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="55273-173">Ha centrado la mayor parte del tiempo y del esfuerzo en resolver los objetivos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="55273-173">You've concentrated most of your time and effort on solving the goals of the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="55273-174">Consulte también</span><span class="sxs-lookup"><span data-stu-id="55273-174">See also</span></span>

- [<span data-ttu-id="55273-175">dotnet new</span><span class="sxs-lookup"><span data-stu-id="55273-175">dotnet new</span></span>](../tools/dotnet-new.md)
- [<span data-ttu-id="55273-176">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="55273-176">dotnet sln</span></span>](../tools/dotnet-sln.md)
- [<span data-ttu-id="55273-177">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="55273-177">dotnet add reference</span></span>](../tools/dotnet-add-reference.md)
- [<span data-ttu-id="55273-178">dotnet test</span><span class="sxs-lookup"><span data-stu-id="55273-178">dotnet test</span></span>](../tools/dotnet-test.md)
