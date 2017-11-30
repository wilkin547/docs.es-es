---
title: "Prueba unitaria del código C# en .NET Core mediante pruebas de dotnet y xUnit"
description: "Aprenda los conceptos de pruebas unitarias en C# y .NET Core: cree paso a paso una solución de ejemplo mediante pruebas de dotnet y xUnit."
author: ardalis
ms.author: wiwagn
ms.date: 09/08/2017
ms.topic: article
ms.prod: .net-core
ms.openlocfilehash: 6e986e89d47ba4de9b8563f1a95cb1ae89accc89
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="unit-testing-c-in-net-core-using-dotnet-test-and-xunit"></a><span data-ttu-id="cbc63-103">Prueba unitaria de C# en .NET Core mediante pruebas de dotnet y xUnit</span><span class="sxs-lookup"><span data-stu-id="cbc63-103">Unit testing C# in .NET Core using dotnet test and xUnit</span></span>

<span data-ttu-id="cbc63-104">Este tutorial le guía por una experiencia interactiva de creación de una solución de ejemplo paso a paso para aprender los conceptos de pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="cbc63-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="cbc63-105">Si prefiere seguir el tutorial con una solución precompilada, [vea o descargue el código de ejemplo](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/unit-testing-using-dotnet-test/) antes de comenzar.</span><span class="sxs-lookup"><span data-stu-id="cbc63-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/unit-testing-using-dotnet-test/) before you begin.</span></span> <span data-ttu-id="cbc63-106">Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="cbc63-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="creating-the-source-project"></a><span data-ttu-id="cbc63-107">Crear el proyecto de origen</span><span class="sxs-lookup"><span data-stu-id="cbc63-107">Creating the source project</span></span>

<span data-ttu-id="cbc63-108">Abra una ventana del Shell.</span><span class="sxs-lookup"><span data-stu-id="cbc63-108">Open a shell window.</span></span> <span data-ttu-id="cbc63-109">Cree un directorio denominado *unit-testing-using-dotnet-test* que contenga la solución.</span><span class="sxs-lookup"><span data-stu-id="cbc63-109">Create a directory called *unit-testing-using-dotnet-test* to hold the solution.</span></span>
<span data-ttu-id="cbc63-110">En este directorio nuevo, ejecute [`dotnet new sln`](../tools/dotnet-new.md) para crear una solución nueva.</span><span class="sxs-lookup"><span data-stu-id="cbc63-110">Inside this new directory, run [`dotnet new sln`](../tools/dotnet-new.md) to create a new solution.</span></span> <span data-ttu-id="cbc63-111">Esto permite facilitar la administración de la biblioteca de clases y del proyecto de prueba unitaria.</span><span class="sxs-lookup"><span data-stu-id="cbc63-111">This makes it easier to manage both the class library and the unit test project.</span></span>
<span data-ttu-id="cbc63-112">En el directorio de la solución, cree un directorio *PrimeService*.</span><span class="sxs-lookup"><span data-stu-id="cbc63-112">Inside the solution directory, create a *PrimeService* directory.</span></span> <span data-ttu-id="cbc63-113">Esta es la estructura de directorios y archivos hasta el momento:</span><span class="sxs-lookup"><span data-stu-id="cbc63-113">The directory and file structure thus far is shown below:</span></span>

```
/unit-testing-using-dotnet-test
    unit-testing-using-dotnet-test.sln
    /PrimeService
```

<span data-ttu-id="cbc63-114">Convierta *PrimeService* en el directorio actual y ejecute [`dotnet new classlib`](../tools/dotnet-new.md) para crear el proyecto de origen.</span><span class="sxs-lookup"><span data-stu-id="cbc63-114">Make *PrimeService* the current directory and run [`dotnet new classlib`](../tools/dotnet-new.md) to create the source project.</span></span> <span data-ttu-id="cbc63-115">Cambie el nombre de *Class1.cs* a *PrimeService.cs*.</span><span class="sxs-lookup"><span data-stu-id="cbc63-115">Rename *Class1.cs* to *PrimeService.cs*.</span></span> <span data-ttu-id="cbc63-116">Para usar el desarrollo controlado por pruebas (TDD), tendrá que crear una implementación de errores de la clase `PrimeService`:</span><span class="sxs-lookup"><span data-stu-id="cbc63-116">To use test-driven development (TDD), you'll create a failing implementation of the `PrimeService` class:</span></span>

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

<span data-ttu-id="cbc63-117">Cambie nuevamente el directorio al directorio *unit-testing-using-dotnet-test*.</span><span class="sxs-lookup"><span data-stu-id="cbc63-117">Change the directory back to the *unit-testing-using-dotnet-test* directory.</span></span> <span data-ttu-id="cbc63-118">Ejecute [`dotnet sln add .\PrimeService\PrimeService.csproj`](../tools/dotnet-sln.md) para agregar el proyecto de biblioteca de clases a la solución.</span><span class="sxs-lookup"><span data-stu-id="cbc63-118">Run [`dotnet sln add .\PrimeService\PrimeService.csproj`](../tools/dotnet-sln.md) to add the class library project to the solution.</span></span>

## <a name="creating-the-test-project"></a><span data-ttu-id="cbc63-119">Crear el proyecto de prueba</span><span class="sxs-lookup"><span data-stu-id="cbc63-119">Creating the test project</span></span>

<span data-ttu-id="cbc63-120">A continuación, cree el directorio *PrimeService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="cbc63-120">Next, create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="cbc63-121">En el esquema siguiente se muestra la estructura de directorios:</span><span class="sxs-lookup"><span data-stu-id="cbc63-121">The following outline shows the directory structure:</span></span>

```
/unit-testing-using-dotnet-test
    unit-testing-using-dotnet-test.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

<span data-ttu-id="cbc63-122">Convierta el directorio *PrimeService.Tests* en el directorio actual y cree un proyecto nuevo con [`dotnet new xunit`](../tools/dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="cbc63-122">Make the *PrimeService.Tests* directory the current directory and create a new project using [`dotnet new xunit`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="cbc63-123">Esto crea un proyecto de prueba que usa xUnit como biblioteca de pruebas.</span><span class="sxs-lookup"><span data-stu-id="cbc63-123">This creates a test project that uses xUnit as the test library.</span></span> <span data-ttu-id="cbc63-124">La plantilla generada ha configurado el ejecutor de pruebas en *PrimeServiceTests.csproj*:</span><span class="sxs-lookup"><span data-stu-id="cbc63-124">The generated template configures the test runner in the *PrimeServiceTests.csproj*:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.3.0-preview-20170628-02" />
  <PackageReference Include="xunit" Version="2.2.0" />
  <PackageReference Include="xunit.runner.visualstudio" Version="2.2.0" />
</ItemGroup>
```

<span data-ttu-id="cbc63-125">El proyecto de prueba requiere otros paquetes para crear y ejecutar pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="cbc63-125">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="cbc63-126">`dotnet new` en el paso anterior, agregó xUnit y el ejecutor de xUnit.</span><span class="sxs-lookup"><span data-stu-id="cbc63-126">`dotnet new` in the previous step added xUnit and the xUnit runner.</span></span> <span data-ttu-id="cbc63-127">Ahora, agregue la biblioteca de clases `PrimeService` como otra dependencia al proyecto.</span><span class="sxs-lookup"><span data-stu-id="cbc63-127">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="cbc63-128">Use el comando [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="cbc63-128">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```
dotnet add reference ../PrimeService/PrimeService.csproj
```

<span data-ttu-id="cbc63-129">Puede ver todo el archivo en el [repositorio de muestras](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService.Tests.csproj) en GitHub.</span><span class="sxs-lookup"><span data-stu-id="cbc63-129">You can see the entire file in the [samples repository](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService.Tests.csproj) on GitHub.</span></span>

<span data-ttu-id="cbc63-130">Aquí se muestra el diseño de solución final:</span><span class="sxs-lookup"><span data-stu-id="cbc63-130">The following shows the final solution layout:</span></span>

```
/unit-testing-using-dotnet-test
    unit-testing-using-dotnet-test.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
        Test Source Files
        PrimeServiceTests.csproj
```

<span data-ttu-id="cbc63-131">Ejecute [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.csproj`](../tools/dotnet-sln.md) en el directorio *unit-testing-using-dotnet-test*.</span><span class="sxs-lookup"><span data-stu-id="cbc63-131">Execute [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.csproj`](../tools/dotnet-sln.md) in the *unit-testing-using-dotnet-test* directory.</span></span> 

## <a name="creating-the-first-test"></a><span data-ttu-id="cbc63-132">Crear la primera prueba</span><span class="sxs-lookup"><span data-stu-id="cbc63-132">Creating the first test</span></span>

<span data-ttu-id="cbc63-133">El enfoque de TDD requiere la escritura de una prueba con errores, después la valida y finalmente repite el proceso.</span><span class="sxs-lookup"><span data-stu-id="cbc63-133">The TDD approach calls for writing one failing test, making it pass, then repeating the process.</span></span> <span data-ttu-id="cbc63-134">Quite *UnitTest1.cs* del directorio *PrimeService.Tests* y cree un archivo de C# nuevo denominado *PrimeService_IsPrimeShould.cs*.</span><span class="sxs-lookup"><span data-stu-id="cbc63-134">Remove *UnitTest1.cs* from the *PrimeService.Tests* directory and create a new C# file named *PrimeService_IsPrimeShould.cs*.</span></span> <span data-ttu-id="cbc63-135">Agregue el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="cbc63-135">Add the following code:</span></span>

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

            Assert.False(result, "1 should not be prime");
        }
    }
}
```

<span data-ttu-id="cbc63-136">El atributo `[Fact]` indica un método de prueba que el ejecutor de pruebas ejecuta.</span><span class="sxs-lookup"><span data-stu-id="cbc63-136">The `[Fact]` attribute indicates a test method that is run by the test runner.</span></span> <span data-ttu-id="cbc63-137">En *unit-testing-using-dotnet-test*, ejecute [`dotnet test`](../tools/dotnet-test.md) para compilar las pruebas y la biblioteca de clases y luego ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="cbc63-137">From the *unit-testing-using-dotnet-test*, execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="cbc63-138">El ejecutor de pruebas de xUnit tiene el punto de entrada del programa para ejecutar las pruebas desde la consola.</span><span class="sxs-lookup"><span data-stu-id="cbc63-138">The xUnit test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="cbc63-139">`dotnet test` inicia el ejecutor de pruebas con el proyecto de prueba unitaria que creó.</span><span class="sxs-lookup"><span data-stu-id="cbc63-139">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="cbc63-140">La prueba produce un error.</span><span class="sxs-lookup"><span data-stu-id="cbc63-140">Your test fails.</span></span> <span data-ttu-id="cbc63-141">Todavía no ha creado la implementación.</span><span class="sxs-lookup"><span data-stu-id="cbc63-141">You haven't created the implementation yet.</span></span> <span data-ttu-id="cbc63-142">Cree esta prueba escribiendo el código más simple en la clase `PrimeService` que funciona:</span><span class="sxs-lookup"><span data-stu-id="cbc63-142">Make this test by writing the simplest code in the `PrimeService` class that works:</span></span>

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

<span data-ttu-id="cbc63-143">En el directorio *unit-testing-using-dotnet-test*, vuelva a ejecutar `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="cbc63-143">In the *unit-testing-using-dotnet-test* directory, run `dotnet test` again.</span></span> <span data-ttu-id="cbc63-144">El comando `dotnet test` ejecuta una compilación del proyecto `PrimeService` y luego del proyecto `PrimeService.Tests`.</span><span class="sxs-lookup"><span data-stu-id="cbc63-144">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="cbc63-145">Después de compilar ambos proyectos, se ejecuta esta única prueba.</span><span class="sxs-lookup"><span data-stu-id="cbc63-145">After building both projects, it runs this single test.</span></span> <span data-ttu-id="cbc63-146">Pasa.</span><span class="sxs-lookup"><span data-stu-id="cbc63-146">It passes.</span></span>

## <a name="adding-more-features"></a><span data-ttu-id="cbc63-147">Agregar más características</span><span class="sxs-lookup"><span data-stu-id="cbc63-147">Adding more features</span></span>

<span data-ttu-id="cbc63-148">Ahora que la prueba se ha superado, es el momento de escribir más.</span><span class="sxs-lookup"><span data-stu-id="cbc63-148">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="cbc63-149">Hay algunos otros casos simples para números primos: 0, -1.</span><span class="sxs-lookup"><span data-stu-id="cbc63-149">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="cbc63-150">Puede agregar esos casos como nuevas pruebas con el atributo `[Fact]`, pero enseguida este proceso se hace tedioso.</span><span class="sxs-lookup"><span data-stu-id="cbc63-150">You could add those cases as new tests with the `[Fact]` attribute, but that quickly becomes tedious.</span></span> <span data-ttu-id="cbc63-151">Hay otros atributos de xUnit que le permiten escribir un conjunto de pruebas similares.</span><span class="sxs-lookup"><span data-stu-id="cbc63-151">There are other xUnit attributes that enable you to write a suite of similar tests.</span></span>  <span data-ttu-id="cbc63-152">Un atributo `[Theory]` representa un conjunto de pruebas que ejecutan el mismo código, pero tienen diferentes argumentos de entrada.</span><span class="sxs-lookup"><span data-stu-id="cbc63-152">A `[Theory]` attribute represents a suite of tests that execute the same code but have different input arguments.</span></span> <span data-ttu-id="cbc63-153">Puede usar el atributo `[InlineData]` para especificar valores para esas entradas.</span><span class="sxs-lookup"><span data-stu-id="cbc63-153">You can use the `[InlineData]` attribute to specify values for those inputs.</span></span>

<span data-ttu-id="cbc63-154">En lugar de crear pruebas nuevas, aplique estos dos atributos para crear una sola teoría.</span><span class="sxs-lookup"><span data-stu-id="cbc63-154">Instead of creating new tests, apply these two attributes to create a single theory.</span></span> <span data-ttu-id="cbc63-155">La teoría es un método que prueba varios valores menores que dos, que es el número primo menor:</span><span class="sxs-lookup"><span data-stu-id="cbc63-155">The theory is a method that tests several values less than two, which is the lowest prime number:</span></span>

[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]

<span data-ttu-id="cbc63-156">Ejecute `dotnet test`, y dos de estas pruebas no se superarán.</span><span class="sxs-lookup"><span data-stu-id="cbc63-156">Run `dotnet test`, and two of these tests fail.</span></span> <span data-ttu-id="cbc63-157">Para superar todas las pruebas, cambie la cláusula `if` al principio del método:</span><span class="sxs-lookup"><span data-stu-id="cbc63-157">To make all of the tests pass, change the `if` clause at the beginning of the method:</span></span>

```csharp
if (candidate < 2)
```

<span data-ttu-id="cbc63-158">Puede continuar recorriendo en iteración agregando más pruebas, más teorías y más código en la biblioteca principal.</span><span class="sxs-lookup"><span data-stu-id="cbc63-158">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="cbc63-159">Ya tiene la [versión terminada de las pruebas](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs) y la [implementación completa de la biblioteca](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService/PrimeService.cs).</span><span class="sxs-lookup"><span data-stu-id="cbc63-159">You have the [finished version of the tests](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs) and the [complete implementation of the library](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService/PrimeService.cs).</span></span>

### <a name="additional-resources"></a><span data-ttu-id="cbc63-160">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="cbc63-160">Additional resources</span></span>

[<span data-ttu-id="cbc63-161">Probar la lógica del controlador en ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="cbc63-161">Testing controller logic in ASP.NET Core</span></span>](https://docs.microsoft.com/aspnet/core/mvc/controllers/testing)
