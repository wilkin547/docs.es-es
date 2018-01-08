---
title: Prueba unitaria de C# con MSTest y .NET Core
description: "Aprenda los conceptos de pruebas unitarias en C# y .NET Core: cree paso a paso una solución de ejemplo mediante pruebas de dotnet y MSTest."
keywords: MSTest, .NET, .NET Core
author: ncarandini
ms.author: wiwagn
ms.date: 09/08/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: ed447641-3e85-4e50-b7ed-004630048a3e
ms.workload: dotnetcore
ms.openlocfilehash: 827f17a347a1a6c3830b2e7feb4de7781369a203
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="unit-testing-c-with-mstest-and-net-core"></a><span data-ttu-id="57e05-104">Prueba unitaria de C# con MSTest y .NET Core</span><span class="sxs-lookup"><span data-stu-id="57e05-104">Unit testing C# with MSTest and .NET Core</span></span>

<span data-ttu-id="57e05-105">Este tutorial le guía por una experiencia interactiva de creación de una solución de ejemplo paso a paso para aprender los conceptos de pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="57e05-105">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="57e05-106">Si prefiere seguir el tutorial con una solución precompilada, [vea o descargue el código de ejemplo](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/) antes de comenzar.</span><span class="sxs-lookup"><span data-stu-id="57e05-106">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/) before you begin.</span></span> <span data-ttu-id="57e05-107">Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="57e05-107">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

### <a name="creating-the-source-project"></a><span data-ttu-id="57e05-108">Crear el proyecto de origen</span><span class="sxs-lookup"><span data-stu-id="57e05-108">Creating the source project</span></span>

<span data-ttu-id="57e05-109">Abra una ventana del Shell.</span><span class="sxs-lookup"><span data-stu-id="57e05-109">Open a shell window.</span></span> <span data-ttu-id="57e05-110">Cree un directorio denominado *unit-testing-using-dotnet-test* que contenga la solución.</span><span class="sxs-lookup"><span data-stu-id="57e05-110">Create a directory called *unit-testing-using-dotnet-test* to hold the solution.</span></span> <span data-ttu-id="57e05-111">En este directorio nuevo, ejecute [`dotnet new sln`](../tools/dotnet-new.md) para crear un archivo de solución nuevo para la biblioteca de clases y el proyecto de prueba.</span><span class="sxs-lookup"><span data-stu-id="57e05-111">Inside this new directory, run [`dotnet new sln`](../tools/dotnet-new.md) to create a new solution file for the class library and the test project.</span></span> <span data-ttu-id="57e05-112">A continuación, cree un directorio *PrimeService*.</span><span class="sxs-lookup"><span data-stu-id="57e05-112">Next, create a *PrimeService* directory.</span></span> <span data-ttu-id="57e05-113">En el esquema siguiente se muestra la estructura de directorios y archivos hasta el momento:</span><span class="sxs-lookup"><span data-stu-id="57e05-113">The following outline shows the directory and file structure thus far:</span></span>

```
/unit-testing-using-mstest
    unit-testing-using-mstest.sln
    /PrimeService
```

<span data-ttu-id="57e05-114">Convierta *PrimeService* en el directorio actual y ejecute [`dotnet new classlib`](../tools/dotnet-new.md) para crear el proyecto de origen.</span><span class="sxs-lookup"><span data-stu-id="57e05-114">Make *PrimeService* the current directory and run [`dotnet new classlib`](../tools/dotnet-new.md) to create the source project.</span></span> <span data-ttu-id="57e05-115">Cambie el nombre de *Class1.cs* a *PrimeService.cs*.</span><span class="sxs-lookup"><span data-stu-id="57e05-115">Rename *Class1.cs* to *PrimeService.cs*.</span></span> <span data-ttu-id="57e05-116">Para usar el desarrollo controlado por pruebas (TDD), tiene que crear una implementación de errores de la clase `PrimeService`:</span><span class="sxs-lookup"><span data-stu-id="57e05-116">To use test-driven development (TDD), you create a failing implementation of the `PrimeService` class:</span></span>

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

<span data-ttu-id="57e05-117">Cambie nuevamente el directorio al directorio *unit-testing-using-mstest*.</span><span class="sxs-lookup"><span data-stu-id="57e05-117">Change the directory back to the *unit-testing-using-mstest* directory.</span></span> <span data-ttu-id="57e05-118">Ejecute [`dotnet sln add PrimeService/PrimeService.csproj`](../tools/dotnet-sln.md) para agregar el proyecto de biblioteca de clases a la solución.</span><span class="sxs-lookup"><span data-stu-id="57e05-118">Run [`dotnet sln add PrimeService/PrimeService.csproj`](../tools/dotnet-sln.md) to add the class library project to the solution.</span></span> 

### <a name="creating-the-test-project"></a><span data-ttu-id="57e05-119">Crear el proyecto de prueba</span><span class="sxs-lookup"><span data-stu-id="57e05-119">Creating the test project</span></span>

<span data-ttu-id="57e05-120">A continuación, cree el directorio *PrimeService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="57e05-120">Next, create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="57e05-121">En el esquema siguiente se muestra la estructura de directorios:</span><span class="sxs-lookup"><span data-stu-id="57e05-121">The following outline shows the directory structure:</span></span>

```
/unit-testing-using-mstest
    unit-testing-using-mstest.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

<span data-ttu-id="57e05-122">Convierta el directorio *PrimeService.Tests* en el directorio actual y cree un proyecto nuevo con [`dotnet new mstest`](../tools/dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="57e05-122">Make the *PrimeService.Tests* directory the current directory and create a new project using [`dotnet new mstest`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="57e05-123">Este comando de dotnet nuevo crea un proyecto de prueba que usa MSTest como la biblioteca de pruebas.</span><span class="sxs-lookup"><span data-stu-id="57e05-123">The dotnet new command creates a test project that uses MStest as the test library.</span></span> <span data-ttu-id="57e05-124">La plantilla generada configura el ejecutor de pruebas en el archivo *PrimeServiceTests.csproj*:</span><span class="sxs-lookup"><span data-stu-id="57e05-124">The generated template configures the test runner in the *PrimeServiceTests.csproj* file:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.3.0" />
  <PackageReference Include="MSTest.TestAdapter" Version="1.1.18" />
  <PackageReference Include="MSTest.TestFramework" Version="1.1.18" />
</ItemGroup>
```

<span data-ttu-id="57e05-125">El proyecto de prueba requiere otros paquetes para crear y ejecutar pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="57e05-125">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="57e05-126">`dotnet new` en el paso anterior agregó el SDK de MSTest, el marco de prueba de MSTest y el ejecutor de MSTest.</span><span class="sxs-lookup"><span data-stu-id="57e05-126">`dotnet new` in the previous step added the MSTest SDK, the MSTest test framework, and the MSTest runner.</span></span> <span data-ttu-id="57e05-127">Ahora, agregue la biblioteca de clases `PrimeService` como otra dependencia al proyecto.</span><span class="sxs-lookup"><span data-stu-id="57e05-127">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="57e05-128">Use el comando [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="57e05-128">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```
dotnet add reference ../PrimeService/PrimeService.csproj
```

<span data-ttu-id="57e05-129">Puede ver todo el archivo en el [repositorio de muestras](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService.Tests.csproj) en GitHub.</span><span class="sxs-lookup"><span data-stu-id="57e05-129">You can see the entire file in the [samples repository](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService.Tests.csproj) on GitHub.</span></span>

<span data-ttu-id="57e05-130">En el esquema siguiente se muestra el diseño de solución final:</span><span class="sxs-lookup"><span data-stu-id="57e05-130">The following outline shows the final solution layout:</span></span>

```
/unit-testing-using-mstest
    unit-testing-using-mstest.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
        Test Source Files
        PrimeServiceTests.csproj
```

<span data-ttu-id="57e05-131">Ejecute [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.csproj`](../tools/dotnet-sln.md) en el directorio *unit-testing-using-dotnet-test*.</span><span class="sxs-lookup"><span data-stu-id="57e05-131">Execute [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.csproj`](../tools/dotnet-sln.md) in the *unit-testing-using-dotnet-test* directory.</span></span> 

## <a name="creating-the-first-test"></a><span data-ttu-id="57e05-132">Crear la primera prueba</span><span class="sxs-lookup"><span data-stu-id="57e05-132">Creating the first test</span></span>

<span data-ttu-id="57e05-133">El enfoque de TDD requiere la escritura de una prueba con errores, después la valida y finalmente repite el proceso.</span><span class="sxs-lookup"><span data-stu-id="57e05-133">The TDD approach calls for writing one failing test, making it pass, then repeating the process.</span></span> <span data-ttu-id="57e05-134">Quite *UnitTest1.cs* del directorio *PrimeService.Tests* y cree un nuevo archivo de C# denominado *PrimeService_IsPrimeShould.cs* con el siguiente contenido:</span><span class="sxs-lookup"><span data-stu-id="57e05-134">Remove *UnitTest1.cs* from the *PrimeService.Tests* directory and create a new C# file named *PrimeService_IsPrimeShould.cs* with the following content:</span></span>

```csharp
using Microsoft.VisualStudio.TestTools.UnitTesting;
using Prime.Services;

namespace Prime.UnitTests.Services
{
    [TestClass]
    public class PrimeService_IsPrimeShould
    {
        private readonly PrimeService _primeService;

        public PrimeService_IsPrimeShould()
        {
            _primeService = new PrimeService();
        }

        [TestMethod]
        public void ReturnFalseGivenValueOf1()
        {
            var result = _primeService.IsPrime(1);

            Assert.IsFalse(result, "1 should not be prime");
        }
    }
}
```

<span data-ttu-id="57e05-135">El atributo `[TestClass]` indica una clase que contiene pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="57e05-135">The `[TestClass]` attribute denotes a class that contains unit tests.</span></span> <span data-ttu-id="57e05-136">El atributo `[TestMethod]` indica que un método es un método de prueba.</span><span class="sxs-lookup"><span data-stu-id="57e05-136">The `[TestMethod]` attribute indicates a method is a test method.</span></span> 

<span data-ttu-id="57e05-137">Guarde este archivo y ejecute [`dotnet test`](../tools/dotnet-test.md) para compilar las pruebas y la biblioteca de clases y luego ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="57e05-137">Save this file and execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="57e05-138">El ejecutor de pruebas de MSTest tiene el punto de entrada del programa para ejecutar las pruebas desde la consola.</span><span class="sxs-lookup"><span data-stu-id="57e05-138">The MSTest test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="57e05-139">`dotnet test` inicia el ejecutor de pruebas con el proyecto de prueba unitaria que creó.</span><span class="sxs-lookup"><span data-stu-id="57e05-139">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="57e05-140">La prueba produce un error.</span><span class="sxs-lookup"><span data-stu-id="57e05-140">Your test fails.</span></span> <span data-ttu-id="57e05-141">Todavía no ha creado la implementación.</span><span class="sxs-lookup"><span data-stu-id="57e05-141">You haven't created the implementation yet.</span></span> <span data-ttu-id="57e05-142">Cree esta prueba que se supera escribiendo el código más simple en la clase `PrimeService` que funciona:</span><span class="sxs-lookup"><span data-stu-id="57e05-142">Make this test pass by writing the simplest code in the `PrimeService` class that works:</span></span>

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

<span data-ttu-id="57e05-143">En el directorio *unit-testing-using-mstest*, vuelva a ejecutar `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="57e05-143">In the *unit-testing-using-mstest* directory, run `dotnet test` again.</span></span> <span data-ttu-id="57e05-144">El comando `dotnet test` ejecuta una compilación del proyecto `PrimeService` y luego del proyecto `PrimeService.Tests`.</span><span class="sxs-lookup"><span data-stu-id="57e05-144">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="57e05-145">Después de compilar ambos proyectos, se ejecuta esta única prueba.</span><span class="sxs-lookup"><span data-stu-id="57e05-145">After building both projects, it runs this single test.</span></span> <span data-ttu-id="57e05-146">Pasa.</span><span class="sxs-lookup"><span data-stu-id="57e05-146">It passes.</span></span>

## <a name="adding-more-features"></a><span data-ttu-id="57e05-147">Agregar más características</span><span class="sxs-lookup"><span data-stu-id="57e05-147">Adding more features</span></span>

<span data-ttu-id="57e05-148">Ahora que la prueba se ha superado, es el momento de escribir más.</span><span class="sxs-lookup"><span data-stu-id="57e05-148">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="57e05-149">Hay algunos otros casos simples para números primos: 0, -1.</span><span class="sxs-lookup"><span data-stu-id="57e05-149">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="57e05-150">Puede agregar pruebas nuevas con el atributo `[TestMethod]`, pero enseguida este proceso se hace tedioso.</span><span class="sxs-lookup"><span data-stu-id="57e05-150">You could add new tests with the `[TestMethod]` attribute, but that quickly becomes tedious.</span></span> <span data-ttu-id="57e05-151">Hay otros atributos de MSTest que le permiten escribir un conjunto de pruebas similares.</span><span class="sxs-lookup"><span data-stu-id="57e05-151">There are other MSTest attributes that enable you to write a suite of similar tests.</span></span>  <span data-ttu-id="57e05-152">Un atributo `[DataTestMethod]` representa un conjunto de pruebas que ejecutan el mismo código, pero que tienen diferentes argumentos de entrada.</span><span class="sxs-lookup"><span data-stu-id="57e05-152">A `[DataTestMethod]`attribute represents a suite of tests that execute the same code but have different input arguments.</span></span> <span data-ttu-id="57e05-153">Puede usar el atributo `[DataRow]` para especificar valores para esas entradas.</span><span class="sxs-lookup"><span data-stu-id="57e05-153">You can use the `[DataRow]` attribute to specify values for those inputs.</span></span>

<span data-ttu-id="57e05-154">En lugar de crear pruebas nuevas, aplique estos dos atributos para crear una sola prueba controlada por datos.</span><span class="sxs-lookup"><span data-stu-id="57e05-154">Instead of creating new tests, apply these two attributes to create a single data driven test.</span></span> <span data-ttu-id="57e05-155">La prueba controlada por datos es un método que prueba varios valores menores que dos, que es el número primo menor:</span><span class="sxs-lookup"><span data-stu-id="57e05-155">The data driven test is a method that tests several values less than two, which is the lowest prime number: :</span></span>

[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]

<span data-ttu-id="57e05-156">Ejecute `dotnet test`, y dos de estas pruebas no se superarán.</span><span class="sxs-lookup"><span data-stu-id="57e05-156">Run `dotnet test`, and two of these tests fail.</span></span> <span data-ttu-id="57e05-157">Para superar todas las pruebas, cambie la cláusula `if` al principio del método:</span><span class="sxs-lookup"><span data-stu-id="57e05-157">To make all of the tests pass, change the `if` clause at the beginning of the method:</span></span>

```csharp
if (candidate < 2)
```

<span data-ttu-id="57e05-158">Puede continuar recorriendo en iteración agregando más pruebas, más teorías y más código en la biblioteca principal.</span><span class="sxs-lookup"><span data-stu-id="57e05-158">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="57e05-159">Ya tiene la [versión terminada de las pruebas](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs) y la [implementación completa de la biblioteca](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService/PrimeService.cs).</span><span class="sxs-lookup"><span data-stu-id="57e05-159">You have the [finished version of the tests](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs) and the [complete implementation of the library](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService/PrimeService.cs).</span></span>

<span data-ttu-id="57e05-160">Ha creado una biblioteca pequeña y un conjunto de pruebas unitarias para esa biblioteca.</span><span class="sxs-lookup"><span data-stu-id="57e05-160">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="57e05-161">Ha estructurado la solución, por lo que agregar pruebas y paquetes nuevos es parte del flujo de trabajo normal.</span><span class="sxs-lookup"><span data-stu-id="57e05-161">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="57e05-162">Ha centrado la mayor parte del tiempo y del esfuerzo en resolver los objetivos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="57e05-162">You've concentrated most of your time and effort on solving the goals of the application.</span></span>
