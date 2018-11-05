---
title: Prueba unitaria de C# con MSTest y .NET Core
description: 'Aprenda los conceptos de pruebas unitarias en C# y .NET Core: cree paso a paso una solución de ejemplo mediante pruebas de dotnet y MSTest.'
author: ncarandini
ms.author: wiwagn
ms.date: 09/08/2017
ms.openlocfilehash: 1c2b0bdd4bf76a17217db0c98b8f951f7d58f2ea
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50183781"
---
# <a name="unit-testing-c-with-mstest-and-net-core"></a><span data-ttu-id="18f9c-103">Prueba unitaria de C# con MSTest y .NET Core</span><span class="sxs-lookup"><span data-stu-id="18f9c-103">Unit testing C# with MSTest and .NET Core</span></span>

<span data-ttu-id="18f9c-104">Este tutorial le guía por una experiencia interactiva de creación de una solución de ejemplo paso a paso para aprender los conceptos de pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="18f9c-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="18f9c-105">Si prefiere seguir el tutorial con una solución precompilada, [vea o descargue el código de ejemplo](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/) antes de comenzar.</span><span class="sxs-lookup"><span data-stu-id="18f9c-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/) before you begin.</span></span> <span data-ttu-id="18f9c-106">Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="18f9c-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

### <a name="creating-the-source-project"></a><span data-ttu-id="18f9c-107">Crear el proyecto de origen</span><span class="sxs-lookup"><span data-stu-id="18f9c-107">Creating the source project</span></span>

<span data-ttu-id="18f9c-108">Abra una ventana del Shell.</span><span class="sxs-lookup"><span data-stu-id="18f9c-108">Open a shell window.</span></span> <span data-ttu-id="18f9c-109">Cree un directorio llamado *unit-testing-using-mstest* que contenga la solución.</span><span class="sxs-lookup"><span data-stu-id="18f9c-109">Create a directory called *unit-testing-using-mstest* to hold the solution.</span></span> <span data-ttu-id="18f9c-110">En este directorio nuevo, ejecute [`dotnet new sln`](../tools/dotnet-new.md) para crear un archivo de solución nuevo para la biblioteca de clases y el proyecto de prueba.</span><span class="sxs-lookup"><span data-stu-id="18f9c-110">Inside this new directory, run [`dotnet new sln`](../tools/dotnet-new.md) to create a new solution file for the class library and the test project.</span></span> <span data-ttu-id="18f9c-111">A continuación, cree un directorio *PrimeService*.</span><span class="sxs-lookup"><span data-stu-id="18f9c-111">Next, create a *PrimeService* directory.</span></span> <span data-ttu-id="18f9c-112">En el esquema siguiente se muestra la estructura de directorios y archivos hasta el momento:</span><span class="sxs-lookup"><span data-stu-id="18f9c-112">The following outline shows the directory and file structure thus far:</span></span>

```
/unit-testing-using-mstest
    unit-testing-using-mstest.sln
    /PrimeService
```

<span data-ttu-id="18f9c-113">Convierta *PrimeService* en el directorio actual y ejecute [`dotnet new classlib`](../tools/dotnet-new.md) para crear el proyecto de origen.</span><span class="sxs-lookup"><span data-stu-id="18f9c-113">Make *PrimeService* the current directory and run [`dotnet new classlib`](../tools/dotnet-new.md) to create the source project.</span></span> <span data-ttu-id="18f9c-114">Cambie el nombre de *Class1.cs* a *PrimeService.cs*.</span><span class="sxs-lookup"><span data-stu-id="18f9c-114">Rename *Class1.cs* to *PrimeService.cs*.</span></span> <span data-ttu-id="18f9c-115">Para usar el desarrollo controlado por pruebas (TDD), tiene que crear una implementación de errores de la clase `PrimeService`:</span><span class="sxs-lookup"><span data-stu-id="18f9c-115">To use test-driven development (TDD), you create a failing implementation of the `PrimeService` class:</span></span>

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

<span data-ttu-id="18f9c-116">Cambie nuevamente el directorio al directorio *unit-testing-using-mstest*.</span><span class="sxs-lookup"><span data-stu-id="18f9c-116">Change the directory back to the *unit-testing-using-mstest* directory.</span></span> <span data-ttu-id="18f9c-117">Ejecute [`dotnet sln add PrimeService/PrimeService.csproj`](../tools/dotnet-sln.md) para agregar el proyecto de biblioteca de clases a la solución.</span><span class="sxs-lookup"><span data-stu-id="18f9c-117">Run [`dotnet sln add PrimeService/PrimeService.csproj`](../tools/dotnet-sln.md) to add the class library project to the solution.</span></span> 

### <a name="creating-the-test-project"></a><span data-ttu-id="18f9c-118">Crear el proyecto de prueba</span><span class="sxs-lookup"><span data-stu-id="18f9c-118">Creating the test project</span></span>

<span data-ttu-id="18f9c-119">A continuación, cree el directorio *PrimeService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="18f9c-119">Next, create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="18f9c-120">En el esquema siguiente se muestra la estructura de directorios:</span><span class="sxs-lookup"><span data-stu-id="18f9c-120">The following outline shows the directory structure:</span></span>

```
/unit-testing-using-mstest
    unit-testing-using-mstest.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

<span data-ttu-id="18f9c-121">Convierta el directorio *PrimeService.Tests* en el directorio actual y cree un proyecto nuevo con [`dotnet new mstest`](../tools/dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="18f9c-121">Make the *PrimeService.Tests* directory the current directory and create a new project using [`dotnet new mstest`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="18f9c-122">Este comando de dotnet nuevo crea un proyecto de prueba que usa MSTest como la biblioteca de pruebas.</span><span class="sxs-lookup"><span data-stu-id="18f9c-122">The dotnet new command creates a test project that uses MStest as the test library.</span></span> <span data-ttu-id="18f9c-123">La plantilla generada configura el ejecutor de pruebas en el archivo *PrimeServiceTests.csproj*:</span><span class="sxs-lookup"><span data-stu-id="18f9c-123">The generated template configures the test runner in the *PrimeServiceTests.csproj* file:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.3.0" />
  <PackageReference Include="MSTest.TestAdapter" Version="1.1.18" />
  <PackageReference Include="MSTest.TestFramework" Version="1.1.18" />
</ItemGroup>
```

<span data-ttu-id="18f9c-124">El proyecto de prueba requiere otros paquetes para crear y ejecutar pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="18f9c-124">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="18f9c-125">`dotnet new` en el paso anterior agregó el SDK de MSTest, el marco de prueba de MSTest y el ejecutor de MSTest.</span><span class="sxs-lookup"><span data-stu-id="18f9c-125">`dotnet new` in the previous step added the MSTest SDK, the MSTest test framework, and the MSTest runner.</span></span> <span data-ttu-id="18f9c-126">Ahora, agregue la biblioteca de clases `PrimeService` como otra dependencia al proyecto.</span><span class="sxs-lookup"><span data-stu-id="18f9c-126">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="18f9c-127">Use el comando [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="18f9c-127">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```
dotnet add reference ../PrimeService/PrimeService.csproj
```

<span data-ttu-id="18f9c-128">Puede ver todo el archivo en el [repositorio de muestras](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService.Tests.csproj) en GitHub.</span><span class="sxs-lookup"><span data-stu-id="18f9c-128">You can see the entire file in the [samples repository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService.Tests.csproj) on GitHub.</span></span>

<span data-ttu-id="18f9c-129">En el esquema siguiente se muestra el diseño de solución final:</span><span class="sxs-lookup"><span data-stu-id="18f9c-129">The following outline shows the final solution layout:</span></span>

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

<span data-ttu-id="18f9c-130">Ejecute [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.csproj`](../tools/dotnet-sln.md) en el directorio *unit-testing-using-mstest*.</span><span class="sxs-lookup"><span data-stu-id="18f9c-130">Execute [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.csproj`](../tools/dotnet-sln.md) in the *unit-testing-using-mstest* directory.</span></span> 

## <a name="creating-the-first-test"></a><span data-ttu-id="18f9c-131">Crear la primera prueba</span><span class="sxs-lookup"><span data-stu-id="18f9c-131">Creating the first test</span></span>

<span data-ttu-id="18f9c-132">El enfoque de TDD requiere la escritura de una prueba con errores, después la valida y finalmente repite el proceso.</span><span class="sxs-lookup"><span data-stu-id="18f9c-132">The TDD approach calls for writing one failing test, making it pass, then repeating the process.</span></span> <span data-ttu-id="18f9c-133">Quite *UnitTest1.cs* del directorio *PrimeService.Tests* y cree un nuevo archivo de C# denominado *PrimeService_IsPrimeShould.cs* con el siguiente contenido:</span><span class="sxs-lookup"><span data-stu-id="18f9c-133">Remove *UnitTest1.cs* from the *PrimeService.Tests* directory and create a new C# file named *PrimeService_IsPrimeShould.cs* with the following content:</span></span>

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

<span data-ttu-id="18f9c-134">El atributo `[TestClass]` indica una clase que contiene pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="18f9c-134">The `[TestClass]` attribute denotes a class that contains unit tests.</span></span> <span data-ttu-id="18f9c-135">El atributo `[TestMethod]` indica que un método es un método de prueba.</span><span class="sxs-lookup"><span data-stu-id="18f9c-135">The `[TestMethod]` attribute indicates a method is a test method.</span></span> 

<span data-ttu-id="18f9c-136">Guarde este archivo y ejecute [`dotnet test`](../tools/dotnet-test.md) para compilar las pruebas y la biblioteca de clases y luego ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="18f9c-136">Save this file and execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="18f9c-137">El ejecutor de pruebas de MSTest tiene el punto de entrada del programa para ejecutar las pruebas desde la consola.</span><span class="sxs-lookup"><span data-stu-id="18f9c-137">The MSTest test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="18f9c-138">`dotnet test` inicia el ejecutor de pruebas con el proyecto de prueba unitaria que creó.</span><span class="sxs-lookup"><span data-stu-id="18f9c-138">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="18f9c-139">La prueba produce un error.</span><span class="sxs-lookup"><span data-stu-id="18f9c-139">Your test fails.</span></span> <span data-ttu-id="18f9c-140">Todavía no ha creado la implementación.</span><span class="sxs-lookup"><span data-stu-id="18f9c-140">You haven't created the implementation yet.</span></span> <span data-ttu-id="18f9c-141">Cree esta prueba que se supera escribiendo el código más simple en la clase `PrimeService` que funciona:</span><span class="sxs-lookup"><span data-stu-id="18f9c-141">Make this test pass by writing the simplest code in the `PrimeService` class that works:</span></span>

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

<span data-ttu-id="18f9c-142">En el directorio *unit-testing-using-mstest*, vuelva a ejecutar `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="18f9c-142">In the *unit-testing-using-mstest* directory, run `dotnet test` again.</span></span> <span data-ttu-id="18f9c-143">El comando `dotnet test` ejecuta una compilación del proyecto `PrimeService` y luego del proyecto `PrimeService.Tests`.</span><span class="sxs-lookup"><span data-stu-id="18f9c-143">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="18f9c-144">Después de compilar ambos proyectos, se ejecuta esta única prueba.</span><span class="sxs-lookup"><span data-stu-id="18f9c-144">After building both projects, it runs this single test.</span></span> <span data-ttu-id="18f9c-145">Pasa.</span><span class="sxs-lookup"><span data-stu-id="18f9c-145">It passes.</span></span>

## <a name="adding-more-features"></a><span data-ttu-id="18f9c-146">Agregar más características</span><span class="sxs-lookup"><span data-stu-id="18f9c-146">Adding more features</span></span>

<span data-ttu-id="18f9c-147">Ahora que la prueba se ha superado, es el momento de escribir más.</span><span class="sxs-lookup"><span data-stu-id="18f9c-147">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="18f9c-148">Hay algunos otros casos simples para números primos: 0, -1.</span><span class="sxs-lookup"><span data-stu-id="18f9c-148">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="18f9c-149">Puede agregar pruebas nuevas con el atributo `[TestMethod]`, pero enseguida este proceso se hace tedioso.</span><span class="sxs-lookup"><span data-stu-id="18f9c-149">You could add new tests with the `[TestMethod]` attribute, but that quickly becomes tedious.</span></span> <span data-ttu-id="18f9c-150">Hay otros atributos de MSTest que le permiten escribir un conjunto de pruebas similares.</span><span class="sxs-lookup"><span data-stu-id="18f9c-150">There are other MSTest attributes that enable you to write a suite of similar tests.</span></span>  <span data-ttu-id="18f9c-151">Un atributo `[DataTestMethod]` representa un conjunto de pruebas que ejecutan el mismo código, pero que tienen diferentes argumentos de entrada.</span><span class="sxs-lookup"><span data-stu-id="18f9c-151">A `[DataTestMethod]`attribute represents a suite of tests that execute the same code but have different input arguments.</span></span> <span data-ttu-id="18f9c-152">Puede usar el atributo `[DataRow]` para especificar valores para esas entradas.</span><span class="sxs-lookup"><span data-stu-id="18f9c-152">You can use the `[DataRow]` attribute to specify values for those inputs.</span></span>

<span data-ttu-id="18f9c-153">En lugar de crear pruebas nuevas, aplique estos dos atributos para crear una sola prueba controlada por datos.</span><span class="sxs-lookup"><span data-stu-id="18f9c-153">Instead of creating new tests, apply these two attributes to create a single data driven test.</span></span> <span data-ttu-id="18f9c-154">La prueba controlada por datos es un método que prueba varios valores menores que dos, que es el número primo menor:</span><span class="sxs-lookup"><span data-stu-id="18f9c-154">The data driven test is a method that tests several values less than two, which is the lowest prime number:</span></span>

[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]

<span data-ttu-id="18f9c-155">Ejecute `dotnet test`, y dos de estas pruebas no se superarán.</span><span class="sxs-lookup"><span data-stu-id="18f9c-155">Run `dotnet test`, and two of these tests fail.</span></span> <span data-ttu-id="18f9c-156">Para superar todas las pruebas, cambie la cláusula `if` al principio del método:</span><span class="sxs-lookup"><span data-stu-id="18f9c-156">To make all of the tests pass, change the `if` clause at the beginning of the method:</span></span>

```csharp
if (candidate < 2)
```

<span data-ttu-id="18f9c-157">Puede continuar recorriendo en iteración agregando más pruebas, más teorías y más código en la biblioteca principal.</span><span class="sxs-lookup"><span data-stu-id="18f9c-157">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="18f9c-158">Ya tiene la [versión terminada de las pruebas](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs) y la [implementación completa de la biblioteca](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/PrimeService/PrimeService.cs).</span><span class="sxs-lookup"><span data-stu-id="18f9c-158">You have the [finished version of the tests](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs) and the [complete implementation of the library](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/PrimeService/PrimeService.cs).</span></span>

<span data-ttu-id="18f9c-159">Ha creado una biblioteca pequeña y un conjunto de pruebas unitarias para esa biblioteca.</span><span class="sxs-lookup"><span data-stu-id="18f9c-159">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="18f9c-160">Ha estructurado la solución, por lo que agregar pruebas y paquetes nuevos es parte del flujo de trabajo normal.</span><span class="sxs-lookup"><span data-stu-id="18f9c-160">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="18f9c-161">Ha centrado la mayor parte del tiempo y del esfuerzo en resolver los objetivos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="18f9c-161">You've concentrated most of your time and effort on solving the goals of the application.</span></span>
