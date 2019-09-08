---
title: Prueba unitaria del código C# en .NET Core mediante pruebas de dotnet y xUnit
description: 'Aprenda los conceptos de pruebas unitarias en C# y .NET Core: cree paso a paso una solución de ejemplo mediante pruebas de dotnet y xUnit.'
author: ardalis
ms.author: wiwagn
ms.date: 11/29/2017
ms.custom: seodec18
ms.openlocfilehash: 1a6c8ed515e62bed921290a54e3d9687bb889a4d
ms.sourcegitcommit: c70542d02736e082e8dac67dad922c19249a8893
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2019
ms.locfileid: "70374154"
---
# <a name="unit-testing-c-in-net-core-using-dotnet-test-and-xunit"></a><span data-ttu-id="0d521-103">Prueba unitaria de C# en .NET Core mediante pruebas de dotnet y xUnit</span><span class="sxs-lookup"><span data-stu-id="0d521-103">Unit testing C# in .NET Core using dotnet test and xUnit</span></span>

<span data-ttu-id="0d521-104">Este tutorial le guía por una experiencia interactiva de creación de una solución de ejemplo paso a paso para aprender los conceptos de pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="0d521-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="0d521-105">Si prefiere seguir el tutorial con una solución precompilada, [vea o descargue el código de ejemplo](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-using-dotnet-test/) antes de comenzar.</span><span class="sxs-lookup"><span data-stu-id="0d521-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-using-dotnet-test/) before you begin.</span></span> <span data-ttu-id="0d521-106">Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="0d521-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

[!INCLUDE [testing an ASP.NET Core project from .NET Core](../../../includes/core-testing-note-aspnet.md)]

## <a name="creating-the-source-project"></a><span data-ttu-id="0d521-107">Crear el proyecto de origen</span><span class="sxs-lookup"><span data-stu-id="0d521-107">Creating the source project</span></span>

<span data-ttu-id="0d521-108">Abra una ventana del Shell.</span><span class="sxs-lookup"><span data-stu-id="0d521-108">Open a shell window.</span></span> <span data-ttu-id="0d521-109">Cree un directorio denominado *unit-testing-using-dotnet-test* que contenga la solución.</span><span class="sxs-lookup"><span data-stu-id="0d521-109">Create a directory called *unit-testing-using-dotnet-test* to hold the solution.</span></span>
<span data-ttu-id="0d521-110">En este directorio nuevo, ejecute [`dotnet new sln`](../tools/dotnet-new.md) para crear una solución nueva.</span><span class="sxs-lookup"><span data-stu-id="0d521-110">Inside this new directory, run [`dotnet new sln`](../tools/dotnet-new.md) to create a new solution.</span></span> <span data-ttu-id="0d521-111">El hecho de contar con una solución facilita la administración de la biblioteca de clases y del proyecto de prueba unitaria.</span><span class="sxs-lookup"><span data-stu-id="0d521-111">Having a solution makes it easier to manage both the class library and the unit test project.</span></span>
<span data-ttu-id="0d521-112">En el directorio de la solución, cree un directorio *PrimeService*.</span><span class="sxs-lookup"><span data-stu-id="0d521-112">Inside the solution directory, create a *PrimeService* directory.</span></span> <span data-ttu-id="0d521-113">La estructura de directorios y archivos hasta el momento sería la siguiente:</span><span class="sxs-lookup"><span data-stu-id="0d521-113">The directory and file structure thus far should be as follows:</span></span>

```console
/unit-testing-using-dotnet-test
    unit-testing-using-dotnet-test.sln
    /PrimeService
```

<span data-ttu-id="0d521-114">Convierta *PrimeService* en el directorio actual y ejecute [`dotnet new classlib`](../tools/dotnet-new.md) para crear el proyecto de origen.</span><span class="sxs-lookup"><span data-stu-id="0d521-114">Make *PrimeService* the current directory and run [`dotnet new classlib`](../tools/dotnet-new.md) to create the source project.</span></span> <span data-ttu-id="0d521-115">Cambie el nombre de *Class1.cs* a *PrimeService.cs*.</span><span class="sxs-lookup"><span data-stu-id="0d521-115">Rename *Class1.cs* to *PrimeService.cs*.</span></span> <span data-ttu-id="0d521-116">Primero, creará una implementación de errores de la clase `PrimeService`:</span><span class="sxs-lookup"><span data-stu-id="0d521-116">You first create a failing implementation of the `PrimeService` class:</span></span>

```csharp
using System;

namespace Prime.Services
{
    public class PrimeService
    {
        public bool IsPrime(int candidate)
        {
            throw new NotImplementedException("Please create a test first.");
        }
    }
}
```

<span data-ttu-id="0d521-117">Cambie nuevamente el directorio al directorio *unit-testing-using-dotnet-test*.</span><span class="sxs-lookup"><span data-stu-id="0d521-117">Change the directory back to the *unit-testing-using-dotnet-test* directory.</span></span>

<span data-ttu-id="0d521-118">Ejecute el comando [dotnet sln](../tools/dotnet-sln.md) para agregar el proyecto de biblioteca de clases a la solución:</span><span class="sxs-lookup"><span data-stu-id="0d521-118">Run the [dotnet sln](../tools/dotnet-sln.md) command to add the class library project to the solution:</span></span>

```console
dotnet sln add ./PrimeService/PrimeService.csproj
```

## <a name="creating-the-test-project"></a><span data-ttu-id="0d521-119">Crear el proyecto de prueba</span><span class="sxs-lookup"><span data-stu-id="0d521-119">Creating the test project</span></span>

<span data-ttu-id="0d521-120">A continuación, cree el directorio *PrimeService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="0d521-120">Next, create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="0d521-121">En el esquema siguiente se muestra la estructura de directorios:</span><span class="sxs-lookup"><span data-stu-id="0d521-121">The following outline shows the directory structure:</span></span>

```console
/unit-testing-using-dotnet-test
    unit-testing-using-dotnet-test.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

<span data-ttu-id="0d521-122">Convierta el directorio *PrimeService.Tests* en el directorio actual y cree un proyecto nuevo con [`dotnet new xunit`](../tools/dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="0d521-122">Make the *PrimeService.Tests* directory the current directory and create a new project using [`dotnet new xunit`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="0d521-123">Este comando crea un proyecto de prueba que usa [xUnit](https://xunit.github.io/) como biblioteca de pruebas.</span><span class="sxs-lookup"><span data-stu-id="0d521-123">This command creates a test project that uses [xUnit](https://xunit.github.io/) as the test library.</span></span> <span data-ttu-id="0d521-124">La plantilla generada configura el ejecutor de pruebas en el archivo *PrimeServiceTests.csproj* similar al código siguiente:</span><span class="sxs-lookup"><span data-stu-id="0d521-124">The generated template configures the test runner in the *PrimeServiceTests.csproj* file similar to the following code:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.3.0" />
  <PackageReference Include="xunit" Version="2.2.0" />
  <PackageReference Include="xunit.runner.visualstudio" Version="2.2.0" />
</ItemGroup>
```

<span data-ttu-id="0d521-125">El proyecto de prueba requiere otros paquetes para crear y ejecutar pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="0d521-125">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="0d521-126">`dotnet new` en el paso anterior, agregó xUnit y el ejecutor de xUnit.</span><span class="sxs-lookup"><span data-stu-id="0d521-126">`dotnet new` in the previous step added xUnit and the xUnit runner.</span></span> <span data-ttu-id="0d521-127">Ahora, agregue la biblioteca de clases `PrimeService` como otra dependencia al proyecto.</span><span class="sxs-lookup"><span data-stu-id="0d521-127">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="0d521-128">Use el comando [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="0d521-128">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```console
dotnet add reference ../PrimeService/PrimeService.csproj
```

<span data-ttu-id="0d521-129">Puede ver todo el archivo en el [repositorio de muestras](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService.Tests.csproj) en GitHub.</span><span class="sxs-lookup"><span data-stu-id="0d521-129">You can see the entire file in the [samples repository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService.Tests.csproj) on GitHub.</span></span>

<span data-ttu-id="0d521-130">Aquí se muestra el diseño de solución final:</span><span class="sxs-lookup"><span data-stu-id="0d521-130">The following shows the final solution layout:</span></span>

```console
/unit-testing-using-dotnet-test
    unit-testing-using-dotnet-test.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
        Test Source Files
        PrimeServiceTests.csproj
```

<span data-ttu-id="0d521-131">Para agregar el proyecto de pruebas a la solución, ejecute el comando [dotnet sln](../tools/dotnet-sln.md) en el directorio *unit-testing-using-dotnet-test*:</span><span class="sxs-lookup"><span data-stu-id="0d521-131">To add the test project to the solution, run the [dotnet sln](../tools/dotnet-sln.md) command in the *unit-testing-using-dotnet-test* directory:</span></span>

```console
dotnet sln add ./PrimeService.Tests/PrimeService.Tests.csproj
```

## <a name="creating-the-first-test"></a><span data-ttu-id="0d521-132">Crear la primera prueba</span><span class="sxs-lookup"><span data-stu-id="0d521-132">Creating the first test</span></span>

<span data-ttu-id="0d521-133">Escribirá una prueba de errores, la aprobará y, luego, repetirá el proceso.</span><span class="sxs-lookup"><span data-stu-id="0d521-133">You write one failing test, make it pass, then repeat the process.</span></span> <span data-ttu-id="0d521-134">Quite *UnitTest1.cs* del directorio *PrimeService.Tests* y cree un archivo de C# nuevo denominado *PrimeService_IsPrimeShould.cs*.</span><span class="sxs-lookup"><span data-stu-id="0d521-134">Remove *UnitTest1.cs* from the *PrimeService.Tests* directory and create a new C# file named *PrimeService_IsPrimeShould.cs*.</span></span> <span data-ttu-id="0d521-135">Agregue el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="0d521-135">Add the following code:</span></span>

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
        public void IsPrime_InputIs1_ReturnFalse()
        {
            var result = _primeService.IsPrime(1);

            Assert.False(result, "1 should not be prime");
        }
    }
}
```

<span data-ttu-id="0d521-136">El atributo `[Fact]` indica un método de prueba que el ejecutor de pruebas ejecuta.</span><span class="sxs-lookup"><span data-stu-id="0d521-136">The `[Fact]` attribute indicates a test method that is run by the test runner.</span></span> <span data-ttu-id="0d521-137">Para la carpeta *PrimeService.Tests*, ejecute [`dotnet test`](../tools/dotnet-test.md) para compilar las pruebas y la biblioteca de clases y luego ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="0d521-137">From the *PrimeService.Tests* folder, execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="0d521-138">El ejecutor de pruebas de xUnit tiene el punto de entrada del programa para ejecutar las pruebas desde la consola.</span><span class="sxs-lookup"><span data-stu-id="0d521-138">The xUnit test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="0d521-139">`dotnet test` inicia el ejecutor de pruebas con el proyecto de prueba unitaria que creó.</span><span class="sxs-lookup"><span data-stu-id="0d521-139">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="0d521-140">La prueba produce un error.</span><span class="sxs-lookup"><span data-stu-id="0d521-140">Your test fails.</span></span> <span data-ttu-id="0d521-141">Todavía no ha creado la implementación.</span><span class="sxs-lookup"><span data-stu-id="0d521-141">You haven't created the implementation yet.</span></span> <span data-ttu-id="0d521-142">Cree esta prueba que se supera escribiendo el código más simple en la clase `PrimeService` que funciona.</span><span class="sxs-lookup"><span data-stu-id="0d521-142">Make this test pass by writing the simplest code in the `PrimeService` class that works.</span></span> <span data-ttu-id="0d521-143">Reemplace la implementación de método existente de `IsPrime` por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="0d521-143">Replace the existing `IsPrime` method implementation with the following code:</span></span>

```csharp
public bool IsPrime(int candidate)
{
    if (candidate == 1)
    {
        return false;
    }
    throw new NotImplementedException("Please create a test first.");
}
```

<span data-ttu-id="0d521-144">En el directorio *PrimeService.Tests*, ejecute `dotnet test` de nuevo.</span><span class="sxs-lookup"><span data-stu-id="0d521-144">In the *PrimeService.Tests* directory, run `dotnet test` again.</span></span> <span data-ttu-id="0d521-145">El comando `dotnet test` ejecuta una compilación del proyecto `PrimeService` y luego del proyecto `PrimeService.Tests`.</span><span class="sxs-lookup"><span data-stu-id="0d521-145">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="0d521-146">Después de compilar ambos proyectos, se ejecuta esta única prueba.</span><span class="sxs-lookup"><span data-stu-id="0d521-146">After building both projects, it runs this single test.</span></span> <span data-ttu-id="0d521-147">Pasa.</span><span class="sxs-lookup"><span data-stu-id="0d521-147">It passes.</span></span>

## <a name="adding-more-features"></a><span data-ttu-id="0d521-148">Agregar más características</span><span class="sxs-lookup"><span data-stu-id="0d521-148">Adding more features</span></span>

<span data-ttu-id="0d521-149">Ahora que la prueba se ha superado, es el momento de escribir más.</span><span class="sxs-lookup"><span data-stu-id="0d521-149">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="0d521-150">Hay otros casos simples para números primos: 0, -1.</span><span class="sxs-lookup"><span data-stu-id="0d521-150">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="0d521-151">Puede agregar esos casos como nuevas pruebas con el atributo `[Fact]`, pero enseguida este proceso se hace tedioso.</span><span class="sxs-lookup"><span data-stu-id="0d521-151">You could add those cases as new tests with the `[Fact]` attribute, but that quickly becomes tedious.</span></span> <span data-ttu-id="0d521-152">Hay otros atributos de xUnit que le permiten escribir un conjunto de pruebas similares:</span><span class="sxs-lookup"><span data-stu-id="0d521-152">There are other xUnit attributes that enable you to write a suite of similar tests:</span></span>

- <span data-ttu-id="0d521-153">Un elemento `[Theory]` representa un conjunto de pruebas que ejecutan el mismo código, pero tienen diferentes argumentos de entrada.</span><span class="sxs-lookup"><span data-stu-id="0d521-153">`[Theory]` represents a suite of tests that execute the same code but have different input arguments.</span></span>

- <span data-ttu-id="0d521-154">Un atributo `[InlineData]` especifica valores para esas entradas.</span><span class="sxs-lookup"><span data-stu-id="0d521-154">`[InlineData]` attribute specifies values for those inputs.</span></span>

<span data-ttu-id="0d521-155">En lugar de crear pruebas nuevas, aplique estos dos atributos, `[Theory]` y `[InlineData]`, para crear una sola teoría en el archivo *PrimeService_IsPrimeShould.cs*.</span><span class="sxs-lookup"><span data-stu-id="0d521-155">Instead of creating new tests, apply these two attributes, `[Theory]` and `[InlineData]`, to create a single theory in the *PrimeService_IsPrimeShould.cs* file.</span></span> <span data-ttu-id="0d521-156">La teoría es un método que prueba varios valores menores que dos, que es el número primo menor:</span><span class="sxs-lookup"><span data-stu-id="0d521-156">The theory is a method that tests several values less than two, which is the lowest prime number:</span></span>

[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]

<span data-ttu-id="0d521-157">Ejecute `dotnet test` de nuevo, y dos de estas pruebas deben generar un error.</span><span class="sxs-lookup"><span data-stu-id="0d521-157">Run `dotnet test` again, and two of these tests should fail.</span></span> <span data-ttu-id="0d521-158">Para superar todas las pruebas, cambie la cláusula `if` al principio del método `IsPrime` en el archivo *PrimeService.cs*:</span><span class="sxs-lookup"><span data-stu-id="0d521-158">To make all of the tests pass, change the `if` clause at the beginning of the `IsPrime` method in the *PrimeService.cs* file:</span></span>

```csharp
if (candidate < 2)
```

<span data-ttu-id="0d521-159">Puede continuar recorriendo en iteración agregando más pruebas, más teorías y más código en la biblioteca principal.</span><span class="sxs-lookup"><span data-stu-id="0d521-159">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="0d521-160">Ya tiene la [versión terminada de las pruebas](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs) y la [implementación completa de la biblioteca](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-dotnet-test/PrimeService/PrimeService.cs).</span><span class="sxs-lookup"><span data-stu-id="0d521-160">You have the [finished version of the tests](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs) and the [complete implementation of the library](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-dotnet-test/PrimeService/PrimeService.cs).</span></span>

### <a name="additional-resources"></a><span data-ttu-id="0d521-161">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="0d521-161">Additional resources</span></span>

- [<span data-ttu-id="0d521-162">Sitio oficial de xUnit.net</span><span class="sxs-lookup"><span data-stu-id="0d521-162">xUnit.net official site</span></span>](https://xunit.github.io)
- [<span data-ttu-id="0d521-163">Probar la lógica del controlador en ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="0d521-163">Testing controller logic in ASP.NET Core</span></span>](/aspnet/core/mvc/controllers/testing)
