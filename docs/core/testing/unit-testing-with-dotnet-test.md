---
title: Prueba unitaria de .NET Core mediante pruebas de dotnet y xUnit
description: "Aprenda los conceptos de pruebas unitarias en .NET Core: cree paso a paso una solución de ejemplo mediante pruebas de dotnet y xUnit."
author: ardalis
ms.author: wiwagn
ms.date: 03/21/2017
ms.topic: article
ms.prod: .net-core
ms.translationtype: HT
ms.sourcegitcommit: 867f9eb286fa7ff5ef3e9167c1ab944c81161216
ms.openlocfilehash: d989ee731d7ffd0439bac69afe1458e2aa10733a
ms.contentlocale: es-es
ms.lasthandoff: 08/17/2017

---
# <a name="unit-testing-in-net-core-using-dotnet-test-and-xunit"></a><span data-ttu-id="24061-103">Prueba unitaria de .NET Core mediante pruebas de dotnet y xUnit</span><span class="sxs-lookup"><span data-stu-id="24061-103">Unit testing in .NET Core using dotnet test and xUnit</span></span>

<span data-ttu-id="24061-104">Este tutorial le guía por una experiencia interactiva de creación de una solución de ejemplo paso a paso para aprender los conceptos de pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="24061-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="24061-105">Si prefiere seguir el tutorial con una solución precompilada, [vea o descargue el código de ejemplo](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/unit-testing-using-dotnet-test/) antes de comenzar.</span><span class="sxs-lookup"><span data-stu-id="24061-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/unit-testing-using-dotnet-test/) before you begin.</span></span> <span data-ttu-id="24061-106">Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="24061-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="creating-the-source-project"></a><span data-ttu-id="24061-107">Crear el proyecto de origen</span><span class="sxs-lookup"><span data-stu-id="24061-107">Creating the source project</span></span>

<span data-ttu-id="24061-108">Abra una ventana del Shell.</span><span class="sxs-lookup"><span data-stu-id="24061-108">Open a shell window.</span></span> <span data-ttu-id="24061-109">Cree un directorio denominado *unit-testing-using-dotnet-test* que contenga la solución.</span><span class="sxs-lookup"><span data-stu-id="24061-109">Create a directory called *unit-testing-using-dotnet-test* to hold the solution.</span></span> <span data-ttu-id="24061-110">Dentro de este nuevo directorio, cree un directorio *PrimeService*.</span><span class="sxs-lookup"><span data-stu-id="24061-110">Inside this new directory, create a *PrimeService* directory.</span></span> <span data-ttu-id="24061-111">Esta es la estructura de directorios hasta el momento:</span><span class="sxs-lookup"><span data-stu-id="24061-111">The directory structure thus far is shown below:</span></span>

```
/unit-testing-using-dotnet-test
    /PrimeService
```

<span data-ttu-id="24061-112">Convierta *PrimeService* en el directorio actual y ejecute [`dotnet new classlib`](../tools/dotnet-new.md) para crear el proyecto de origen.</span><span class="sxs-lookup"><span data-stu-id="24061-112">Make *PrimeService* the current directory and run [`dotnet new classlib`](../tools/dotnet-new.md) to create the source project.</span></span> <span data-ttu-id="24061-113">Cambie el nombre de *Class1.cs* a *PrimeService.cs*.</span><span class="sxs-lookup"><span data-stu-id="24061-113">Rename *Class1.cs* to *PrimeService.cs*.</span></span> <span data-ttu-id="24061-114">Para usar el desarrollo controlado por pruebas (TDD), tendrá que crear una implementación de errores de la clase `PrimeService`:</span><span class="sxs-lookup"><span data-stu-id="24061-114">To use test-driven development (TDD), you'll create a failing implementation of the `PrimeService` class:</span></span>

```csharp
using System;

namespace Prime.Services
{
    public class PrimeService
    {
        public bool IsPrime(int candidate) 
        {
            throw new NotImplementedException("Please create a test first");
        } 
    }
}
```

## <a name="creating-the-test-project"></a><span data-ttu-id="24061-115">Crear el proyecto de prueba</span><span class="sxs-lookup"><span data-stu-id="24061-115">Creating the test project</span></span>

<span data-ttu-id="24061-116">Cambie el directorio de nuevo al directorio *unit-testing-using-dotnet-test* y cree el directorio *PrimeService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="24061-116">Change the directory back to the *unit-testing-using-dotnet-test* directory and create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="24061-117">Esta es la estructura de directorios:</span><span class="sxs-lookup"><span data-stu-id="24061-117">The directory structure is shown below:</span></span>

```
/unit-testing-using-dotnet-test
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

<span data-ttu-id="24061-118">Convierta el directorio *PrimeService.Tests* en el directorio actual y cree un proyecto nuevo con [`dotnet new xunit`](../tools/dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="24061-118">Make the *PrimeService.Tests* directory the current directory and create a new project using [`dotnet new xunit`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="24061-119">Esto crea un proyecto de prueba que usa xUnit como biblioteca de pruebas.</span><span class="sxs-lookup"><span data-stu-id="24061-119">This creates a test project that uses xUnit as the test library.</span></span> <span data-ttu-id="24061-120">La plantilla generada ha configurado el ejecutor de pruebas en *PrimeServiceTests.csproj*:</span><span class="sxs-lookup"><span data-stu-id="24061-120">The generated template configures the test runner in the *PrimeServiceTests.csproj*:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.0.0" />
  <PackageReference Include="xunit" Version="2.2.0" />
  <PackageReference Include="xunit.runner.visualstudio" Version="2.2.0" />
</ItemGroup>
```

<span data-ttu-id="24061-121">El proyecto de prueba requiere otros paquetes para crear y ejecutar pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="24061-121">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="24061-122">`dotnet new` en el paso anterior, agregó xUnit y el ejecutor de xUnit.</span><span class="sxs-lookup"><span data-stu-id="24061-122">`dotnet new` in the previous step added xUnit and the xUnit runner.</span></span> <span data-ttu-id="24061-123">Ahora, agregue la biblioteca de clases `PrimeService` como otra dependencia al proyecto.</span><span class="sxs-lookup"><span data-stu-id="24061-123">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="24061-124">Use el comando [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="24061-124">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```
dotnet add reference ../PrimeService/PrimeService.csproj
```

<span data-ttu-id="24061-125">Otra opción consiste en editar el archivo *PrimeService.Tests.csproj*.</span><span class="sxs-lookup"><span data-stu-id="24061-125">Another option is to edit the *PrimeService.Tests.csproj* file.</span></span> <span data-ttu-id="24061-126">Directamente en el primer nodo `<ItemGroup>`, agregue otro nodo `<ItemGroup>` con una referencia al proyecto de biblioteca:</span><span class="sxs-lookup"><span data-stu-id="24061-126">Directly under the first `<ItemGroup>` node, add another `<ItemGroup>` node with a reference to the library project:</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="..\PrimeService\PrimeService.csproj" />
</ItemGroup>
```

<span data-ttu-id="24061-127">Puede ver todo el archivo en el [repositorio de muestras](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService.Tests.csproj) en GitHub.</span><span class="sxs-lookup"><span data-stu-id="24061-127">You can see the entire file in the [samples repository](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService.Tests.csproj) on GitHub.</span></span>

<span data-ttu-id="24061-128">A continuación se muestra el diseño de la solución final:</span><span class="sxs-lookup"><span data-stu-id="24061-128">The final solution layout is shown below:</span></span>

```
/unit-testing-using-mstest
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
        PrimeService
        PrimeServiceTests.csproj
```

## <a name="creating-the-first-test"></a><span data-ttu-id="24061-129">Crear la primera prueba</span><span class="sxs-lookup"><span data-stu-id="24061-129">Creating the first test</span></span>

<span data-ttu-id="24061-130">Antes de compilar la biblioteca o las pruebas, ejecute [`dotnet restore`](../tools/dotnet-restore.md) en el directorio *PrimeService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="24061-130">Before building the library or the tests, execute [`dotnet restore`](../tools/dotnet-restore.md) in the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="24061-131">Este comando restaura todos los paquetes de NuGet necesarios para cada proyecto.</span><span class="sxs-lookup"><span data-stu-id="24061-131">This command restores all the necessary NuGet packages for each project.</span></span>

<span data-ttu-id="24061-132">El enfoque de TDD requiere la escritura de una prueba con errores, después la valida y finalmente repite el proceso.</span><span class="sxs-lookup"><span data-stu-id="24061-132">The TDD approach calls for writing one failing test, making it pass, then repeating the process.</span></span> <span data-ttu-id="24061-133">Quite *UnitTest1.cs* del directorio *PrimeService.Tests* y cree un nuevo archivo de C# denominado *PrimeService_IsPrimeShould.cs* con el siguiente contenido:</span><span class="sxs-lookup"><span data-stu-id="24061-133">Remove *UnitTest1.cs* from the *PrimeService.Tests* directory and create a new C# file named *PrimeService_IsPrimeShould.cs* with the following content:</span></span>

```csharp
using Xunit;
using Prime.Services;

namespace Prime.UnitTests.Services
{
    public class PrimeService_IsPrimeShould
    {
        private readonly PrimeService _primeService;

        public PrimeService_IsPrimeShould()
        {
            _primeService = new PrimeService();
        }

        [Fact]
        public void ReturnFalseGivenValueOf1()
        {
            var result = _primeService.IsPrime(1);

            Assert.False(result, $"1 should not be prime");
        }
    }
}
```

<span data-ttu-id="24061-134">El atributo `[Fact]` indica un método como una única prueba.</span><span class="sxs-lookup"><span data-stu-id="24061-134">The `[Fact]` attribute denotes a method as a single test.</span></span> <span data-ttu-id="24061-135">Ejecute [`dotnet test`](../tools/dotnet-test.md) para generar las pruebas y la biblioteca de clases y, a continuación, ejecute las pruebas.</span><span class="sxs-lookup"><span data-stu-id="24061-135">Execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="24061-136">El ejecutor de pruebas de xUnit tiene el punto de entrada del programa para ejecutar las pruebas desde la consola.</span><span class="sxs-lookup"><span data-stu-id="24061-136">The xUnit test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="24061-137">`dotnet test` inicia el ejecutor de pruebas y proporciona un argumento de línea de comandos al ejecutor de pruebas que indica el ensamblado que contiene las pruebas.</span><span class="sxs-lookup"><span data-stu-id="24061-137">`dotnet test` starts the test runner and provides a command-line argument to the test runner indicating the assembly that contains your tests.</span></span>

<span data-ttu-id="24061-138">La prueba produce un error.</span><span class="sxs-lookup"><span data-stu-id="24061-138">Your test fails.</span></span> <span data-ttu-id="24061-139">Todavía no ha creado la implementación.</span><span class="sxs-lookup"><span data-stu-id="24061-139">You haven't created the implementation yet.</span></span> <span data-ttu-id="24061-140">Escriba el código más simple en la clase `PrimeService` para pasar esta prueba:</span><span class="sxs-lookup"><span data-stu-id="24061-140">Write the simplest code in the `PrimeService` class to make this test pass:</span></span>

```csharp
public bool IsPrime(int candidate) 
{
    if (candidate == 1) 
    { 
        return false;
    } 
    throw new NotImplementedException("Please create a test first");
} 
```

<span data-ttu-id="24061-141">En el directorio *PrimeService.Tests*, ejecute `dotnet test` de nuevo.</span><span class="sxs-lookup"><span data-stu-id="24061-141">In the *PrimeService.Tests* directory, run `dotnet test` again.</span></span> <span data-ttu-id="24061-142">El comando `dotnet test` ejecuta una compilación del proyecto `PrimeService` y luego del proyecto `PrimeService.Tests`.</span><span class="sxs-lookup"><span data-stu-id="24061-142">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="24061-143">Después de compilar ambos proyectos, se ejecuta esta única prueba.</span><span class="sxs-lookup"><span data-stu-id="24061-143">After building both projects, it runs this single test.</span></span> <span data-ttu-id="24061-144">Pasa.</span><span class="sxs-lookup"><span data-stu-id="24061-144">It passes.</span></span>

## <a name="adding-more-features"></a><span data-ttu-id="24061-145">Agregar más características</span><span class="sxs-lookup"><span data-stu-id="24061-145">Adding more features</span></span>

<span data-ttu-id="24061-146">Ahora que la prueba se ha superado, es el momento de escribir más.</span><span class="sxs-lookup"><span data-stu-id="24061-146">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="24061-147">Hay algunos otros casos simples para números primos: 0, -1.</span><span class="sxs-lookup"><span data-stu-id="24061-147">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="24061-148">Puede agregarlas como nuevas pruebas con el atributo `[Fact]`, pero enseguida este proceso se hace tedioso.</span><span class="sxs-lookup"><span data-stu-id="24061-148">You could add those as new tests with the `[Fact]` attribute, but that quickly becomes tedious.</span></span> <span data-ttu-id="24061-149">Hay otros atributos de xUnit que le permiten escribir un conjunto de pruebas similares.</span><span class="sxs-lookup"><span data-stu-id="24061-149">There are other xUnit attributes that enable you to write a suite of similar tests.</span></span>  <span data-ttu-id="24061-150">Un atributo `[Theory]` representa un conjunto de pruebas que ejecutan el mismo código, pero tienen diferentes argumentos de entrada.</span><span class="sxs-lookup"><span data-stu-id="24061-150">A `[Theory]` attribute represents a suite of tests that execute the same code but have different input arguments.</span></span> <span data-ttu-id="24061-151">Puede usar el atributo `[InlineData]` para especificar valores para esas entradas.</span><span class="sxs-lookup"><span data-stu-id="24061-151">You can use the `[InlineData]` attribute to specify values for those inputs.</span></span> 
 
<span data-ttu-id="24061-152">En lugar de crear nuevas pruebas, aproveche estos dos atributos para crear una teoría que prueba algunos valores inferiores a 2, que es el número primo más bajo:</span><span class="sxs-lookup"><span data-stu-id="24061-152">Instead of creating new tests, leverage these two attributes to create a single theory that tests several values less than two, which is the lowest prime number:</span></span>

<span data-ttu-id="24061-153">[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]</span><span class="sxs-lookup"><span data-stu-id="24061-153">[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]</span></span>

<span data-ttu-id="24061-154">Ejecute `dotnet test`, y dos de estas pruebas no se superarán.</span><span class="sxs-lookup"><span data-stu-id="24061-154">Run `dotnet test`, and two of these tests fail.</span></span> <span data-ttu-id="24061-155">Para superar todas las pruebas, cambie la cláusula `if` al principio del método:</span><span class="sxs-lookup"><span data-stu-id="24061-155">To make all of the tests pass, change the `if` clause at the beginning of the method:</span></span>

```csharp
if (candidate < 2)
```

<span data-ttu-id="24061-156">Puede continuar recorriendo en iteración agregando más pruebas, más teorías y más código en la biblioteca principal.</span><span class="sxs-lookup"><span data-stu-id="24061-156">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="24061-157">Acabará con la [versión terminada de las pruebas](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs) y con la [implementación completa de la biblioteca](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService/PrimeService.cs).</span><span class="sxs-lookup"><span data-stu-id="24061-157">You'll end up with the [finished version of the tests](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs) and the [complete implementation of the library](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService/PrimeService.cs).</span></span>

<span data-ttu-id="24061-158">Ha creado una biblioteca pequeña y un conjunto de pruebas unitarias para esa biblioteca.</span><span class="sxs-lookup"><span data-stu-id="24061-158">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="24061-159">Ha estructurado la solución para que el proceso de agregar nuevos paquetes y pruebas sea continuo y pueda concentrar la mayor parte de su tiempo y esfuerzo en solucionar los objetivos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="24061-159">You've structured the solution so that adding new packages and tests is seamless, and you can concentrate most of your time and effort on solving the goals of the applicaiton.</span></span>

