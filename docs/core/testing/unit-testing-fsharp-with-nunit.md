---
title: Prueba unitaria de F# en .NET Core con dotnet test y NUnit
description: 'Aprenda los conceptos de pruebas unitarias para F# en .NET Core: cree paso a paso una solución de ejemplo mediante pruebas de dotnet y NUnit.'
author: rprouse
ms.date: 10/04/2018
dev_langs:
- fsharp
ms.openlocfilehash: 3347e5b90c31589e9a0f99ac0d9298927a717f56
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75715443"
---
# <a name="unit-testing-f-libraries-in-net-core-using-dotnet-test-and-nunit"></a><span data-ttu-id="98057-103">Bibliotecas de F# de prueba unitaria en .NET Core con pruebas de dotnet y NUnit</span><span class="sxs-lookup"><span data-stu-id="98057-103">Unit testing F# libraries in .NET Core using dotnet test and NUnit</span></span>

<span data-ttu-id="98057-104">Este tutorial le guía por una experiencia interactiva de creación de una solución de ejemplo paso a paso para aprender los conceptos de pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="98057-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="98057-105">Si prefiere seguir el tutorial con una solución precompilada, [vea o descargue el código de ejemplo](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-with-fsharp-nunit/) antes de comenzar.</span><span class="sxs-lookup"><span data-stu-id="98057-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-with-fsharp-nunit/) before you begin.</span></span> <span data-ttu-id="98057-106">Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="98057-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

[!INCLUDE [testing an ASP.NET Core project from .NET Core](../../../includes/core-testing-note-aspnet.md)]

## <a name="prerequisites"></a><span data-ttu-id="98057-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="98057-107">Prerequisites</span></span>

- <span data-ttu-id="98057-108">[SDK de .NET Core 2.1](https://dotnet.microsoft.com/download) o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="98057-108">[.NET Core 2.1 SDK](https://dotnet.microsoft.com/download) or later versions.</span></span>
- <span data-ttu-id="98057-109">Un editor de texto o un editor de código de su elección.</span><span class="sxs-lookup"><span data-stu-id="98057-109">A text editor or code editor of your choice.</span></span>

## <a name="creating-the-source-project"></a><span data-ttu-id="98057-110">Crear el proyecto de origen</span><span class="sxs-lookup"><span data-stu-id="98057-110">Creating the source project</span></span>

<span data-ttu-id="98057-111">Abra una ventana del Shell.</span><span class="sxs-lookup"><span data-stu-id="98057-111">Open a shell window.</span></span> <span data-ttu-id="98057-112">Cree un directorio llamado *unit-testing-with-fsharp* que contenga la solución.</span><span class="sxs-lookup"><span data-stu-id="98057-112">Create a directory called *unit-testing-with-fsharp* to hold the solution.</span></span>
<span data-ttu-id="98057-113">En este directorio nuevo, ejecute el comando siguiente para crear un archivo de solución nuevo para la biblioteca de clases y el proyecto de prueba:</span><span class="sxs-lookup"><span data-stu-id="98057-113">Inside this new directory, run the following command to create a new solution file for the class library and the test project:</span></span>

```dotnetcli
dotnet new sln
```

<span data-ttu-id="98057-114">A continuación, cree un directorio *MathService*.</span><span class="sxs-lookup"><span data-stu-id="98057-114">Next, create a *MathService* directory.</span></span> <span data-ttu-id="98057-115">En el esquema siguiente se muestra la estructura de directorios y archivos hasta el momento:</span><span class="sxs-lookup"><span data-stu-id="98057-115">The following outline shows the directory and file structure so far:</span></span>

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
```

<span data-ttu-id="98057-116">Convierta *MathService* en el directorio actual y ejecute el siguiente comando para crear el proyecto de origen:</span><span class="sxs-lookup"><span data-stu-id="98057-116">Make *MathService* the current directory and run the following command to create the source project:</span></span>

```dotnetcli
dotnet new classlib -lang "F#"
```

<span data-ttu-id="98057-117">Creará una implementación de errores del servicio de matemáticas:</span><span class="sxs-lookup"><span data-stu-id="98057-117">You create a failing implementation of the math service:</span></span>

```fsharp
module MyMath =
    let squaresOfOdds xs = raise (System.NotImplementedException("You haven't written a test yet!"))
```

<span data-ttu-id="98057-118">Cambie nuevamente el directorio al directorio *unit-testing-with-fsharp*.</span><span class="sxs-lookup"><span data-stu-id="98057-118">Change the directory back to the *unit-testing-with-fsharp* directory.</span></span> <span data-ttu-id="98057-119">Ejecute el siguiente comando para agregar el proyecto de biblioteca de clases a la solución:</span><span class="sxs-lookup"><span data-stu-id="98057-119">Run the following command to add the class library project to the solution:</span></span>

```dotnetcli
dotnet sln add .\MathService\MathService.fsproj
```

## <a name="creating-the-test-project"></a><span data-ttu-id="98057-120">Crear el proyecto de prueba</span><span class="sxs-lookup"><span data-stu-id="98057-120">Creating the test project</span></span>

<span data-ttu-id="98057-121">A continuación, cree el directorio *MathService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="98057-121">Next, create the *MathService.Tests* directory.</span></span> <span data-ttu-id="98057-122">En el esquema siguiente se muestra la estructura de directorios:</span><span class="sxs-lookup"><span data-stu-id="98057-122">The following outline shows the directory structure:</span></span>

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
        Source Files
        MathService.fsproj
    /MathService.Tests
```

<span data-ttu-id="98057-123">Convierta el directorio *MathService.Tests* en el directorio actual y cree un proyecto nuevo con el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="98057-123">Make the *MathService.Tests* directory the current directory and create a new project using the following command:</span></span>

```dotnetcli
dotnet new nunit -lang "F#"
```

<span data-ttu-id="98057-124">Esto crea un proyecto de prueba que usa NUnit como el marco de pruebas.</span><span class="sxs-lookup"><span data-stu-id="98057-124">This creates a test project that uses NUnit as the test framework.</span></span> <span data-ttu-id="98057-125">La plantilla generada configura el ejecutor de pruebas en *MathServiceTests.fsproj*:</span><span class="sxs-lookup"><span data-stu-id="98057-125">The generated template configures the test runner in the *MathServiceTests.fsproj*:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.5.0" />
  <PackageReference Include="NUnit" Version="3.9.0" />
  <PackageReference Include="NUnit3TestAdapter" Version="3.9.0" />
</ItemGroup>
```

<span data-ttu-id="98057-126">El proyecto de prueba requiere otros paquetes para crear y ejecutar pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="98057-126">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="98057-127">En el paso anterior, `dotnet new` agrega NUnit y el adaptador de prueba NUnit.</span><span class="sxs-lookup"><span data-stu-id="98057-127">`dotnet new` in the previous step added NUnit and the NUnit test adapter.</span></span> <span data-ttu-id="98057-128">Ahora, agregue la biblioteca de clases `MathService` como otra dependencia al proyecto.</span><span class="sxs-lookup"><span data-stu-id="98057-128">Now, add the `MathService` class library as another dependency to the project.</span></span> <span data-ttu-id="98057-129">Use el comando `dotnet add reference`:</span><span class="sxs-lookup"><span data-stu-id="98057-129">Use the `dotnet add reference` command:</span></span>

```dotnetcli
dotnet add reference ../MathService/MathService.fsproj
```

<span data-ttu-id="98057-130">Puede ver todo el archivo en el [repositorio de muestras](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-with-fsharp/MathService.Tests/MathService.Tests.fsproj) en GitHub.</span><span class="sxs-lookup"><span data-stu-id="98057-130">You can see the entire file in the [samples repository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-with-fsharp/MathService.Tests/MathService.Tests.fsproj) on GitHub.</span></span>

<span data-ttu-id="98057-131">Tiene el diseño de solución final siguiente:</span><span class="sxs-lookup"><span data-stu-id="98057-131">You have the following final solution layout:</span></span>

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
        Source Files
        MathService.fsproj
    /MathService.Tests
        Test Source Files
        MathService.Tests.fsproj
```

<span data-ttu-id="98057-132">Ejecute el comando siguiente en el directorio *unit-testing-with-fsharp*:</span><span class="sxs-lookup"><span data-stu-id="98057-132">Execute the following command in the *unit-testing-with-fsharp* directory:</span></span>

```dotnetcli
dotnet sln add .\MathService.Tests\MathService.Tests.fsproj
```

## <a name="creating-the-first-test"></a><span data-ttu-id="98057-133">Crear la primera prueba</span><span class="sxs-lookup"><span data-stu-id="98057-133">Creating the first test</span></span>

<span data-ttu-id="98057-134">Escribirá una prueba de errores, la aprobará y, luego, repetirá el proceso.</span><span class="sxs-lookup"><span data-stu-id="98057-134">You write one failing test, make it pass, then repeat the process.</span></span> <span data-ttu-id="98057-135">Abra *UnitTest1.fs* y agregue el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="98057-135">Open *UnitTest1.fs* and add the following code:</span></span>

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

<span data-ttu-id="98057-136">El atributo `[<TestFixture>]` indica una clase que contiene pruebas.</span><span class="sxs-lookup"><span data-stu-id="98057-136">The `[<TestFixture>]` attribute denotes a class that contains tests.</span></span> <span data-ttu-id="98057-137">El atributo `[<Test>]` indica un método de prueba que el ejecutor de pruebas ejecuta.</span><span class="sxs-lookup"><span data-stu-id="98057-137">The `[<Test>]` attribute denotes a test method that is run by the test runner.</span></span> <span data-ttu-id="98057-138">En el directorio *unit-testing-with-fsharp*, ejecute `dotnet test` para compilar las pruebas y la biblioteca de clases y luego ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="98057-138">From the *unit-testing-with-fsharp* directory, execute `dotnet test` to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="98057-139">El ejecutor de pruebas de NUnit tiene el punto de entrada del programa para ejecutar las pruebas desde la consola.</span><span class="sxs-lookup"><span data-stu-id="98057-139">The NUnit test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="98057-140">`dotnet test` inicia el ejecutor de pruebas con el proyecto de prueba unitaria que creó.</span><span class="sxs-lookup"><span data-stu-id="98057-140">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="98057-141">Estas dos pruebas muestran las pruebas superadas y con errores más básicas.</span><span class="sxs-lookup"><span data-stu-id="98057-141">These two tests show the most basic passing and failing tests.</span></span> <span data-ttu-id="98057-142">`My test` indica que se supera y `Fail every time` indica que no.</span><span class="sxs-lookup"><span data-stu-id="98057-142">`My test` passes, and `Fail every time` fails.</span></span> <span data-ttu-id="98057-143">Ahora, cree una prueba para el método `squaresOfOdds`.</span><span class="sxs-lookup"><span data-stu-id="98057-143">Now, create a test for the `squaresOfOdds` method.</span></span> <span data-ttu-id="98057-144">El método `squaresOfOdds` devuelve una secuencia de los cuadrados de todos los valores enteros impares que forman parte de la secuencia de entrada.</span><span class="sxs-lookup"><span data-stu-id="98057-144">The `squaresOfOdds` method returns a sequence of the squares of all odd integer values that are part of the input sequence.</span></span> <span data-ttu-id="98057-145">En lugar de intentar escribir todas esas funciones a la vez, puede crear de forma iterativa pruebas que validen la funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="98057-145">Rather than trying to write all of those functions at once, you can iteratively create tests that validate the functionality.</span></span> <span data-ttu-id="98057-146">Hacer cada prueba superada significa crear la funcionalidad necesaria para el método.</span><span class="sxs-lookup"><span data-stu-id="98057-146">Making each test pass means creating the necessary functionality for the method.</span></span>

<span data-ttu-id="98057-147">La prueba más sencilla que se puede escribir es llamar a `squaresOfOdds` con todos los números impares, donde el resultado sea una secuencia de enteros vacía.</span><span class="sxs-lookup"><span data-stu-id="98057-147">The simplest test we can write is to call `squaresOfOdds` with all even numbers, where the result should be an empty sequence of integers.</span></span>  <span data-ttu-id="98057-148">Aquí se muestra la prueba:</span><span class="sxs-lookup"><span data-stu-id="98057-148">Here's that test:</span></span>

```fsharp
[<Test>]
member this.TestEvenSequence() =
    let expected = Seq.empty<int>
    let actual = MyMath.squaresOfOdds [2; 4; 6; 8; 10]
    Assert.That(actual, Is.EqualTo(expected))
```

<span data-ttu-id="98057-149">Observe que la secuencia `expected` se convirtió en lista.</span><span class="sxs-lookup"><span data-stu-id="98057-149">Notice that the `expected` sequence has been converted to a list.</span></span> <span data-ttu-id="98057-150">El marco de NUnit se basa en muchos tipos de .NET estándar.</span><span class="sxs-lookup"><span data-stu-id="98057-150">The NUnit framework relies on many standard .NET types.</span></span> <span data-ttu-id="98057-151">Esa dependencia significa que la interfaz pública y los resultados esperados admiten <xref:System.Collections.ICollection> en lugar de <xref:System.Collections.IEnumerable>.</span><span class="sxs-lookup"><span data-stu-id="98057-151">That dependency means that your public interface and expected results support <xref:System.Collections.ICollection> rather than <xref:System.Collections.IEnumerable>.</span></span>

<span data-ttu-id="98057-152">Cuando ejecuta la prueba, se observa que no se supera la prueba.</span><span class="sxs-lookup"><span data-stu-id="98057-152">When you run the test, you see that your test fails.</span></span> <span data-ttu-id="98057-153">Todavía no ha creado la implementación.</span><span class="sxs-lookup"><span data-stu-id="98057-153">You haven't created the implementation yet.</span></span> <span data-ttu-id="98057-154">Haga que esta prueba se supere escribiendo el código más simple de la clase *Library.fs* en su proyecto MathService que funciona:</span><span class="sxs-lookup"><span data-stu-id="98057-154">Make this test pass by writing the simplest code in the *Library.fs* class in your MathService project that works:</span></span>

```fsharp
let squaresOfOdds xs =
    Seq.empty<int>
```

<span data-ttu-id="98057-155">En el directorio *unit-testing-with-fsharp*, vuelva a ejecutar `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="98057-155">In the *unit-testing-with-fsharp* directory, run `dotnet test` again.</span></span> <span data-ttu-id="98057-156">El comando `dotnet test` ejecuta una compilación del proyecto `MathService` y luego del proyecto `MathService.Tests`.</span><span class="sxs-lookup"><span data-stu-id="98057-156">The `dotnet test` command runs a build for the `MathService` project and then for the `MathService.Tests` project.</span></span> <span data-ttu-id="98057-157">Después de compilar ambos proyectos, las pruebas se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="98057-157">After building both projects, it runs your tests.</span></span> <span data-ttu-id="98057-158">Ahora se superan dos pruebas.</span><span class="sxs-lookup"><span data-stu-id="98057-158">Two tests pass now.</span></span>

## <a name="completing-the-requirements"></a><span data-ttu-id="98057-159">Finalización de los requisitos</span><span class="sxs-lookup"><span data-stu-id="98057-159">Completing the requirements</span></span>

<span data-ttu-id="98057-160">Ahora que la prueba se ha superado, es el momento de escribir más.</span><span class="sxs-lookup"><span data-stu-id="98057-160">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="98057-161">El próximo caso simple funciona con una secuencia cuyo único número impar es `1`.</span><span class="sxs-lookup"><span data-stu-id="98057-161">The next simple case works with a sequence whose only odd number is `1`.</span></span> <span data-ttu-id="98057-162">El número 1 es más simple, porque el cuadrado de 1 es 1.</span><span class="sxs-lookup"><span data-stu-id="98057-162">The number 1 is easier because the square of 1 is 1.</span></span> <span data-ttu-id="98057-163">Aquí está la prueba siguiente:</span><span class="sxs-lookup"><span data-stu-id="98057-163">Here's that next test:</span></span>

```fsharp
[<Test>]
member public this.TestOnesAndEvens() =
    let expected = [1; 1; 1; 1]
    let actual = MyMath.squaresOfOdds [2; 1; 4; 1; 6; 1; 8; 1; 10]
    Assert.That(actual, Is.EqualTo(expected))
```

<span data-ttu-id="98057-164">Si se ejecuta `dotnet test`, la prueba nueva se falla.</span><span class="sxs-lookup"><span data-stu-id="98057-164">Executing `dotnet test` fails the new test.</span></span> <span data-ttu-id="98057-165">Debe actualizar el método `squaresOfOdds` para controlar esta prueba nueva.</span><span class="sxs-lookup"><span data-stu-id="98057-165">You must update the `squaresOfOdds` method to handle this new test.</span></span> <span data-ttu-id="98057-166">Debe filtrar todos los números impares y quitarlos de la secuencia para que se supere esta prueba.</span><span class="sxs-lookup"><span data-stu-id="98057-166">You must filter all the even numbers out of the sequence to make this test pass.</span></span> <span data-ttu-id="98057-167">Para hacerlo, escriba una función de filtro pequeña y use `Seq.filter`:</span><span class="sxs-lookup"><span data-stu-id="98057-167">You can do that by writing a small filter function and using `Seq.filter`:</span></span>

```fsharp
let private isOdd x = x % 2 <> 0

let squaresOfOdds xs =
    xs
    |> Seq.filter isOdd
```

<span data-ttu-id="98057-168">Observe la llamada a `Seq.toList`.</span><span class="sxs-lookup"><span data-stu-id="98057-168">Notice the call to `Seq.toList`.</span></span> <span data-ttu-id="98057-169">Esa acción crea una lista, que implemente la interfaz <xref:System.Collections.ICollection>.</span><span class="sxs-lookup"><span data-stu-id="98057-169">That creates a list, which implements the <xref:System.Collections.ICollection> interface.</span></span>

<span data-ttu-id="98057-170">Falta un paso todavía: el cuadrado de cada uno de los números impares.</span><span class="sxs-lookup"><span data-stu-id="98057-170">There's one more step to go: square each of the odd numbers.</span></span> <span data-ttu-id="98057-171">Comience escribiendo una prueba nueva:</span><span class="sxs-lookup"><span data-stu-id="98057-171">Start by writing a new test:</span></span>

```fsharp
[<Test>]
member public this.TestSquaresOfOdds() =
    let expected = [1; 9; 25; 49; 81]
    let actual = MyMath.squaresOfOdds [1; 2; 3; 4; 5; 6; 7; 8; 9; 10]
    Assert.That(actual, Is.EqualTo(expected))
```

<span data-ttu-id="98057-172">Puede corregir la prueba si canaliza la secuencia filtrada a través de una operación de asignación para calcular el cuadrado de cada número impar:</span><span class="sxs-lookup"><span data-stu-id="98057-172">You can fix the test by piping the filtered sequence through a map operation to compute the square of each odd number:</span></span>

```fsharp
let private square x = x * x
let private isOdd x = x % 2 <> 0

let squaresOfOdds xs =
    xs
    |> Seq.filter isOdd
    |> Seq.map square
```

<span data-ttu-id="98057-173">Ha creado una biblioteca pequeña y un conjunto de pruebas unitarias para esa biblioteca.</span><span class="sxs-lookup"><span data-stu-id="98057-173">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="98057-174">Ha estructurado la solución, por lo que agregar pruebas y paquetes nuevos es parte del flujo de trabajo normal.</span><span class="sxs-lookup"><span data-stu-id="98057-174">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="98057-175">Ha centrado la mayor parte del tiempo y del esfuerzo en resolver los objetivos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="98057-175">You've concentrated most of your time and effort on solving the goals of the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="98057-176">Vea también</span><span class="sxs-lookup"><span data-stu-id="98057-176">See also</span></span>

- [<span data-ttu-id="98057-177">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="98057-177">dotnet add reference</span></span>](../tools/dotnet-add-reference.md)
- [<span data-ttu-id="98057-178">dotnet test</span><span class="sxs-lookup"><span data-stu-id="98057-178">dotnet test</span></span>](../tools/dotnet-test.md)
