---
title: Pruebas unitarias con MSTest y .NET Core
description: "Cómo usar MSTest con .NET Core"
keywords: MSTest, .NET, .NET Core
author: ncarandini
ms.author: wiwagn
ms.date: 03/21/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: ed447641-3e85-4e50-b7ed-004630048a3e
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: d1cb9f6667e1317e74d246988ef1257d0712c431
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---

# <a name="unit-testing-with-mstest-and-net-core"></a><span data-ttu-id="599ba-104">Pruebas unitarias con MSTest y .NET Core</span><span class="sxs-lookup"><span data-stu-id="599ba-104">Unit testing with MSTest and .NET Core</span></span>

<span data-ttu-id="599ba-105">Este tutorial le guía por una experiencia interactiva de creación de una solución de ejemplo paso a paso para aprender los conceptos de pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="599ba-105">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="599ba-106">Si prefiere seguir el tutorial con una solución precompilada, [vea o descargue el código de ejemplo](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/) antes de comenzar.</span><span class="sxs-lookup"><span data-stu-id="599ba-106">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/) before you begin.</span></span> <span data-ttu-id="599ba-107">Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="599ba-107">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

### <a name="creating-the-source-project"></a><span data-ttu-id="599ba-108">Crear el proyecto de origen</span><span class="sxs-lookup"><span data-stu-id="599ba-108">Creating the source project</span></span>

<span data-ttu-id="599ba-109">Abra una ventana del Shell.</span><span class="sxs-lookup"><span data-stu-id="599ba-109">Open a shell window.</span></span> <span data-ttu-id="599ba-110">Cree un directorio denominado *unit-testing-using-dotnet-test* que contenga la solución.</span><span class="sxs-lookup"><span data-stu-id="599ba-110">Create a directory called *unit-testing-using-dotnet-test* to hold the solution.</span></span> <span data-ttu-id="599ba-111">Dentro de este nuevo directorio, cree un directorio *PrimeService*.</span><span class="sxs-lookup"><span data-stu-id="599ba-111">Inside this new directory, create a *PrimeService* directory.</span></span> <span data-ttu-id="599ba-112">Esta es la estructura de directorios hasta el momento:</span><span class="sxs-lookup"><span data-stu-id="599ba-112">The directory structure thus far is shown below:</span></span>

```
/unit-testing-using-mstest
    /PrimeService
```

<span data-ttu-id="599ba-113">Convierta *PrimeService* en el directorio actual y ejecute [`dotnet new classlib`](../tools/dotnet-new.md) para crear el proyecto de origen.</span><span class="sxs-lookup"><span data-stu-id="599ba-113">Make *PrimeService* the current directory and run [`dotnet new classlib`](../tools/dotnet-new.md) to create the source project.</span></span> <span data-ttu-id="599ba-114">Cambie el nombre de *Class1.cs* a *PrimeService.cs*.</span><span class="sxs-lookup"><span data-stu-id="599ba-114">Rename *Class1.cs* to *PrimeService.cs*.</span></span> <span data-ttu-id="599ba-115">Para usar el desarrollo controlado por pruebas (TDD), tendrá que crear una implementación de errores de la clase `PrimeService`:</span><span class="sxs-lookup"><span data-stu-id="599ba-115">To use test-driven development (TDD), you'll create a failing implementation of the `PrimeService` class:</span></span>

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

### <a name="creating-the-test-project"></a><span data-ttu-id="599ba-116">Crear el proyecto de prueba</span><span class="sxs-lookup"><span data-stu-id="599ba-116">Creating the test project</span></span>

<span data-ttu-id="599ba-117">Cambie el directorio de nuevo al directorio *unit-testing-using-mstest* y cree el directorio *PrimeService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="599ba-117">Change the directory back to the *unit-testing-using-mstest* directory and create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="599ba-118">Esta es la estructura de directorios:</span><span class="sxs-lookup"><span data-stu-id="599ba-118">The directory structure is shown below:</span></span>

```
/unit-testing-using-mstest
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

<span data-ttu-id="599ba-119">Convierta el directorio *PrimeService.Tests* en el directorio actual y cree un proyecto nuevo con [`dotnet new mstest`](../tools/dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="599ba-119">Make the *PrimeService.Tests* directory the current directory and create a new project using [`dotnet new mstest`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="599ba-120">Esto crea un proyecto de prueba que usa MStest como la biblioteca de pruebas.</span><span class="sxs-lookup"><span data-stu-id="599ba-120">This creates a test project that uses MStest as the test library.</span></span> <span data-ttu-id="599ba-121">La plantilla generada configura el ejecutor de pruebas en el archivo *PrimeServiceTests.csproj*:</span><span class="sxs-lookup"><span data-stu-id="599ba-121">The generated template configures the test runner in the *PrimeServiceTests.csproj* file:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.0.0" />
  <PackageReference Include="MSTest.TestAdapter" Version="1.1.11" />
  <PackageReference Include="MSTest.TestFramework" Version="1.1.11" />
</ItemGroup>
```

<span data-ttu-id="599ba-122">El proyecto de prueba requiere otros paquetes para crear y ejecutar pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="599ba-122">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="599ba-123">`dotnet new` en el paso anterior agregó el SDK de MSTest, el marco de prueba de MSTest y el ejecutor de MSTest.</span><span class="sxs-lookup"><span data-stu-id="599ba-123">`dotnet new` in the previous step added the MSTest SDK, the MSTest test framework, and the MSTest runner.</span></span> <span data-ttu-id="599ba-124">Ahora, agregue la biblioteca de clases `PrimeService` como otra dependencia al proyecto.</span><span class="sxs-lookup"><span data-stu-id="599ba-124">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="599ba-125">Use el comando [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="599ba-125">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```
dotnet add reference ../PrimeService/PrimeService.csproj
```

<span data-ttu-id="599ba-126">Otra opción consiste en editar el archivo *PrimeService.Tests.csproj*.</span><span class="sxs-lookup"><span data-stu-id="599ba-126">Another option is to edit the *PrimeService.Tests.csproj* file.</span></span> <span data-ttu-id="599ba-127">Directamente en el primer nodo `<ItemGroup>`, agregue otro nodo `<ItemGroup>` con una referencia al proyecto de biblioteca:</span><span class="sxs-lookup"><span data-stu-id="599ba-127">Directly under the first `<ItemGroup>` node, add another `<ItemGroup>` node with a reference to the library project:</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="..\PrimeService\PrimeService.csproj" />
</ItemGroup>
```

<span data-ttu-id="599ba-128">Puede ver todo el archivo en el [repositorio de muestras](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService.Tests.csproj) en GitHub.</span><span class="sxs-lookup"><span data-stu-id="599ba-128">You can see the entire file in the [samples repository](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService.Tests.csproj) on GitHub.</span></span>

<span data-ttu-id="599ba-129">A continuación se muestra el diseño de la solución final:</span><span class="sxs-lookup"><span data-stu-id="599ba-129">The final solution layout is shown below:</span></span>

```
/unit-testing-using-mstest
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
        PrimeService
        PrimeServiceTests.csproj
```

## <a name="creating-the-first-test"></a><span data-ttu-id="599ba-130">Crear la primera prueba</span><span class="sxs-lookup"><span data-stu-id="599ba-130">Creating the first test</span></span>

<span data-ttu-id="599ba-131">Antes de compilar la biblioteca o las pruebas, ejecute [`dotnet restore`](../tools/dotnet-restore.md) en el directorio *PrimeService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="599ba-131">Before building the library or the tests, execute [`dotnet restore`](../tools/dotnet-restore.md) in the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="599ba-132">Este comando restaura todos los paquetes de NuGet necesarios para cada proyecto.</span><span class="sxs-lookup"><span data-stu-id="599ba-132">This command restores all the necessary NuGet packages for each project.</span></span>

<span data-ttu-id="599ba-133">El enfoque de TDD requiere la escritura de una prueba con errores, después la valida y finalmente repite el proceso.</span><span class="sxs-lookup"><span data-stu-id="599ba-133">The TDD approach calls for writing one failing test, making it pass, then repeating the process.</span></span> <span data-ttu-id="599ba-134">Quite *UnitTest1.cs* del directorio *PrimeService.Tests* y cree un nuevo archivo de C# denominado *PrimeService_IsPrimeShould.cs* con el siguiente contenido:</span><span class="sxs-lookup"><span data-stu-id="599ba-134">Remove *UnitTest1.cs* from the *PrimeService.Tests* directory and create a new C# file named *PrimeService_IsPrimeShould.cs* with the following content:</span></span>

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

            Assert.IsFalse(result, $"1 should not be prime");
        }
    }
}
```

<span data-ttu-id="599ba-135">El atributo `[TestClass]` indica una clase que contiene pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="599ba-135">The `[TestClass]` attribute denotes a class that contains unit tests.</span></span> <span data-ttu-id="599ba-136">El atributo `[TestMethod]` indica un método como una única prueba.</span><span class="sxs-lookup"><span data-stu-id="599ba-136">The `[TestMethod]` attribute denotes a method as a single test.</span></span> 

<span data-ttu-id="599ba-137">Guarde este archivo y ejecute [`dotnet test`](../tools/dotnet-test.md) para compilar las pruebas y la biblioteca de clases y luego ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="599ba-137">Save this file and execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="599ba-138">El ejecutor de pruebas de MSTest tiene el punto de entrada del programa para ejecutar las pruebas desde la consola.</span><span class="sxs-lookup"><span data-stu-id="599ba-138">The MSTest test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="599ba-139">`dotnet test` inicia el ejecutor de pruebas y proporciona un argumento de línea de comandos al ejecutor de pruebas que indica el ensamblado que contiene las pruebas.</span><span class="sxs-lookup"><span data-stu-id="599ba-139">`dotnet test` starts the test runner and provides a command-line argument to the test runner indicating the assembly that contains your tests.</span></span>

<span data-ttu-id="599ba-140">La prueba produce un error.</span><span class="sxs-lookup"><span data-stu-id="599ba-140">Your test fails.</span></span> <span data-ttu-id="599ba-141">Todavía no ha creado la implementación.</span><span class="sxs-lookup"><span data-stu-id="599ba-141">You haven't created the implementation yet.</span></span> <span data-ttu-id="599ba-142">Escriba el código más simple en la clase `PrimeService` para pasar esta prueba:</span><span class="sxs-lookup"><span data-stu-id="599ba-142">Write the simplest code in the `PrimeService` class to make this test pass:</span></span>

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

<span data-ttu-id="599ba-143">En el directorio *PrimeService.Tests*, ejecute `dotnet test` de nuevo.</span><span class="sxs-lookup"><span data-stu-id="599ba-143">In the *PrimeService.Tests* directory, run `dotnet test` again.</span></span> <span data-ttu-id="599ba-144">El comando `dotnet test` ejecuta una compilación del proyecto `PrimeService` y luego del proyecto `PrimeService.Tests`.</span><span class="sxs-lookup"><span data-stu-id="599ba-144">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="599ba-145">Después de compilar ambos proyectos, se ejecuta esta única prueba.</span><span class="sxs-lookup"><span data-stu-id="599ba-145">After building both projects, it runs this single test.</span></span> <span data-ttu-id="599ba-146">Pasa.</span><span class="sxs-lookup"><span data-stu-id="599ba-146">It passes.</span></span>

## <a name="adding-more-features"></a><span data-ttu-id="599ba-147">Agregar más características</span><span class="sxs-lookup"><span data-stu-id="599ba-147">Adding more features</span></span>

<span data-ttu-id="599ba-148">Ahora que la prueba se ha superado, es el momento de escribir más.</span><span class="sxs-lookup"><span data-stu-id="599ba-148">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="599ba-149">Hay algunos otros casos simples para números primos: 0, -1.</span><span class="sxs-lookup"><span data-stu-id="599ba-149">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="599ba-150">Puede agregarlas como nuevas pruebas con el atributo `[TestMethod]`, pero enseguida este proceso se hace tedioso.</span><span class="sxs-lookup"><span data-stu-id="599ba-150">You could add those as new tests with the `[TestMethod]` attribute, but that quickly becomes tedious.</span></span> <span data-ttu-id="599ba-151">Hay otros atributos de MSTest que le permiten escribir un conjunto de pruebas similares.</span><span class="sxs-lookup"><span data-stu-id="599ba-151">There are other MSTest attributes that enable you to write a suite of similar tests.</span></span>  <span data-ttu-id="599ba-152">Un atributo `[DataTestMethod]` representa un conjunto de pruebas que ejecutan el mismo código, pero que tienen diferentes argumentos de entrada.</span><span class="sxs-lookup"><span data-stu-id="599ba-152">A `[DataTestMethod]`attribute represents a suite of tests that execute the same code but have different input arguments.</span></span> <span data-ttu-id="599ba-153">Puede usar el atributo `[DataRow]` para especificar valores para esas entradas.</span><span class="sxs-lookup"><span data-stu-id="599ba-153">You can use the `[DataRow]` attribute to specify values for those inputs.</span></span> 
 
<span data-ttu-id="599ba-154">En lugar de crear nuevas pruebas, aproveche estos dos atributos para crear un método de prueba de datos único que pruebe algunos valores inferiores a 2, que es el número primo más bajo:</span><span class="sxs-lookup"><span data-stu-id="599ba-154">Instead of creating new tests, leverage these two attributes to create a single data test method that tests several values less than two, which is the lowest prime number:</span></span>

<span data-ttu-id="599ba-155">[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]</span><span class="sxs-lookup"><span data-stu-id="599ba-155">[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]</span></span>

<span data-ttu-id="599ba-156">Ejecute `dotnet test`, y dos de estas pruebas no se superarán.</span><span class="sxs-lookup"><span data-stu-id="599ba-156">Run `dotnet test`, and two of these tests fail.</span></span> <span data-ttu-id="599ba-157">Para superar todas las pruebas, cambie la cláusula `if` al principio del método:</span><span class="sxs-lookup"><span data-stu-id="599ba-157">To make all of the tests pass, change the `if` clause at the beginning of the method:</span></span>

```csharp
if (candidate < 2)
```

<span data-ttu-id="599ba-158">Puede continuar recorriendo en iteración agregando más pruebas, más teorías y más código en la biblioteca principal.</span><span class="sxs-lookup"><span data-stu-id="599ba-158">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="599ba-159">Acabará con la [versión terminada de las pruebas](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs) y con la [implementación completa de la biblioteca](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService/PrimeService.cs).</span><span class="sxs-lookup"><span data-stu-id="599ba-159">You'll end up with the [finished version of the tests](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs) and the [complete implementation of the library](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService/PrimeService.cs).</span></span>

<span data-ttu-id="599ba-160">Ha creado una biblioteca pequeña y un conjunto de pruebas unitarias para esa biblioteca.</span><span class="sxs-lookup"><span data-stu-id="599ba-160">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="599ba-161">Ha estructurado la solución para que el proceso de agregar nuevos paquetes y pruebas sea continuo y pueda concentrar la mayor parte de su tiempo y esfuerzo en solucionar los objetivos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="599ba-161">You've structured the solution so that adding new packages and tests is seamless, and you can concentrate most of your time and effort on solving the goals of the applicaiton.</span></span>

