---
title: Prueba unitaria de C# con NUnit y .NET Core
description: "Aprenda los conceptos de pruebas unitarias en C# y .NET Core: cree paso a paso una solución de ejemplo mediante pruebas de dotnet y NUnit."
keywords: NUnit,. NET y .NET Core
author: rprouse
ms.date: 12/01/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.openlocfilehash: ad410497adc641e89bd9845ed69c063692ad2f73
ms.sourcegitcommit: 401c4427a3ec0d1263543033b3084039278509dc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2017
---
# <a name="unit-testing-c-with-nunit-and-net-core"></a><span data-ttu-id="08ab1-104">Prueba unitaria de C# con NUnit y .NET Core</span><span class="sxs-lookup"><span data-stu-id="08ab1-104">Unit testing C# with NUnit and .NET Core</span></span>

<span data-ttu-id="08ab1-105">Este tutorial le guía por una experiencia interactiva de creación de una solución de ejemplo paso a paso para aprender los conceptos de pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="08ab1-105">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="08ab1-106">Si prefiere seguir el tutorial con una solución precompilada, [vea o descargue el código de ejemplo](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-nunit/) antes de comenzar.</span><span class="sxs-lookup"><span data-stu-id="08ab1-106">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-nunit/) before you begin.</span></span> <span data-ttu-id="08ab1-107">Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="08ab1-107">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="creating-the-source-project"></a><span data-ttu-id="08ab1-108">Crear el proyecto de origen</span><span class="sxs-lookup"><span data-stu-id="08ab1-108">Creating the source project</span></span>

<span data-ttu-id="08ab1-109">Abra una ventana del Shell.</span><span class="sxs-lookup"><span data-stu-id="08ab1-109">Open a shell window.</span></span> <span data-ttu-id="08ab1-110">Cree un directorio llamado *unit-testing-using-nunit* que contenga la solución.</span><span class="sxs-lookup"><span data-stu-id="08ab1-110">Create a directory called *unit-testing-using-nunit* to hold the solution.</span></span> <span data-ttu-id="08ab1-111">En este directorio nuevo, ejecute [`dotnet new sln`](../tools/dotnet-new.md) para crear un archivo de solución nuevo para la biblioteca de clases y el proyecto de prueba.</span><span class="sxs-lookup"><span data-stu-id="08ab1-111">Inside this new directory, run [`dotnet new sln`](../tools/dotnet-new.md) to create a new solution file for the class library and the test project.</span></span> <span data-ttu-id="08ab1-112">A continuación, cree un directorio *PrimeService*.</span><span class="sxs-lookup"><span data-stu-id="08ab1-112">Next, create a *PrimeService* directory.</span></span> <span data-ttu-id="08ab1-113">En el esquema siguiente se muestra la estructura de directorios y archivos hasta el momento:</span><span class="sxs-lookup"><span data-stu-id="08ab1-113">The following outline shows the directory and file structure thus far:</span></span>

```
/unit-testing-using-nunit
    unit-testing-using-nunit.sln
    /PrimeService
```

<span data-ttu-id="08ab1-114">Convierta *PrimeService* en el directorio actual y ejecute [`dotnet new classlib`](../tools/dotnet-new.md) para crear el proyecto de origen.</span><span class="sxs-lookup"><span data-stu-id="08ab1-114">Make *PrimeService* the current directory and run [`dotnet new classlib`](../tools/dotnet-new.md) to create the source project.</span></span> <span data-ttu-id="08ab1-115">Cambie el nombre de *Class1.cs* a *PrimeService.cs*.</span><span class="sxs-lookup"><span data-stu-id="08ab1-115">Rename *Class1.cs* to *PrimeService.cs*.</span></span> <span data-ttu-id="08ab1-116">Para usar el desarrollo controlado por pruebas (TDD), tiene que crear una implementación de errores de la clase `PrimeService`:</span><span class="sxs-lookup"><span data-stu-id="08ab1-116">To use test-driven development (TDD), you create a failing implementation of the `PrimeService` class:</span></span>

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

<span data-ttu-id="08ab1-117">Cambie nuevamente el directorio a *unit-testing-using-nunit*.</span><span class="sxs-lookup"><span data-stu-id="08ab1-117">Change the directory back to the *unit-testing-using-nunit* directory.</span></span> <span data-ttu-id="08ab1-118">Ejecute [`dotnet sln add PrimeService/PrimeService.csproj`](../tools/dotnet-sln.md) para agregar el proyecto de biblioteca de clases a la solución.</span><span class="sxs-lookup"><span data-stu-id="08ab1-118">Run [`dotnet sln add PrimeService/PrimeService.csproj`](../tools/dotnet-sln.md) to add the class library project to the solution.</span></span>

## <a name="install-the-nunit-project-template"></a><span data-ttu-id="08ab1-119">Instalación de la plantilla de proyecto NUnit</span><span class="sxs-lookup"><span data-stu-id="08ab1-119">Install the NUnit project template</span></span>

<span data-ttu-id="08ab1-120">Debe instalar las plantillas de proyecto de prueba NUnit para poder crear un proyecto de prueba.</span><span class="sxs-lookup"><span data-stu-id="08ab1-120">The NUnit test project templates need to be installed before creating a test project.</span></span> <span data-ttu-id="08ab1-121">Solo deberá hacerlo una vez en cada máquina de desarrollador en la que creará proyectos NUnit.</span><span class="sxs-lookup"><span data-stu-id="08ab1-121">This only needs to be done once on each developer machine where you'll create new NUnit projects.</span></span> <span data-ttu-id="08ab1-122">Ejecute [`dotnet new -i NUnit3.DotNetNew.Template`](../tools/dotnet-new.md) para instalar las plantillas NUnit.</span><span class="sxs-lookup"><span data-stu-id="08ab1-122">Run [`dotnet new -i NUnit3.DotNetNew.Template`](../tools/dotnet-new.md) to install the NUnit templates.</span></span>

```
dotnet new -i NUnit3.DotNetNew.Template
```

### <a name="creating-the-test-project"></a><span data-ttu-id="08ab1-123">Crear el proyecto de prueba</span><span class="sxs-lookup"><span data-stu-id="08ab1-123">Creating the test project</span></span>

<span data-ttu-id="08ab1-124">A continuación, cree el directorio *PrimeService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="08ab1-124">Next, create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="08ab1-125">En el esquema siguiente se muestra la estructura de directorios:</span><span class="sxs-lookup"><span data-stu-id="08ab1-125">The following outline shows the directory structure:</span></span>

```
/unit-testing-using-nunit
    unit-testing-using-nunit.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

<span data-ttu-id="08ab1-126">Convierta el directorio *PrimeService.Tests* en el directorio actual y cree un proyecto nuevo con [`dotnet new nunit`](../tools/dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="08ab1-126">Make the *PrimeService.Tests* directory the current directory and create a new project using [`dotnet new nunit`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="08ab1-127">Este comando de dotnet nuevo crea un proyecto de prueba que usa NUnit como la biblioteca de pruebas.</span><span class="sxs-lookup"><span data-stu-id="08ab1-127">The dotnet new command creates a test project that uses NUnit as the test library.</span></span> <span data-ttu-id="08ab1-128">La plantilla generada configura el ejecutor de pruebas en el archivo *PrimeServiceTests.csproj*:</span><span class="sxs-lookup"><span data-stu-id="08ab1-128">The generated template configures the test runner in the *PrimeServiceTests.csproj* file:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.5.0" />
  <PackageReference Include="NUnit" Version="3.9.0" />
  <PackageReference Include="NUnit3TestAdapter" Version="3.9.0" />
</ItemGroup>
```

<span data-ttu-id="08ab1-129">El proyecto de prueba requiere otros paquetes para crear y ejecutar pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="08ab1-129">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="08ab1-130">En el paso anterior, `dotnet new` agrega el SDK de prueba de Microsoft, el marco de pruebas de NUnit y el adaptador de prueba de NUnit.</span><span class="sxs-lookup"><span data-stu-id="08ab1-130">`dotnet new` in the previous step added the Microsoft test SDK, the NUnit test framework, and the NUnit test adapter.</span></span> <span data-ttu-id="08ab1-131">Ahora, agregue la biblioteca de clases `PrimeService` como otra dependencia al proyecto.</span><span class="sxs-lookup"><span data-stu-id="08ab1-131">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="08ab1-132">Use el comando [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="08ab1-132">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```
dotnet add reference ../PrimeService/PrimeService.csproj
```

<span data-ttu-id="08ab1-133">Puede ver todo el archivo en el [repositorio de muestras](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService.Tests.csproj) en GitHub.</span><span class="sxs-lookup"><span data-stu-id="08ab1-133">You can see the entire file in the [samples repository](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService.Tests.csproj) on GitHub.</span></span>

<span data-ttu-id="08ab1-134">En el esquema siguiente se muestra el diseño de solución final:</span><span class="sxs-lookup"><span data-stu-id="08ab1-134">The following outline shows the final solution layout:</span></span>

```
/unit-testing-using-nunit
    unit-testing-using-nunit.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
        Test Source Files
        PrimeServiceTests.csproj
```

<span data-ttu-id="08ab1-135">Ejecute [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.csproj`](../tools/dotnet-sln.md) en el directorio *unit-testing-using-dotnet-test*.</span><span class="sxs-lookup"><span data-stu-id="08ab1-135">Execute [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.csproj`](../tools/dotnet-sln.md) in the *unit-testing-using-dotnet-test* directory.</span></span>

## <a name="creating-the-first-test"></a><span data-ttu-id="08ab1-136">Crear la primera prueba</span><span class="sxs-lookup"><span data-stu-id="08ab1-136">Creating the first test</span></span>

<span data-ttu-id="08ab1-137">El enfoque de TDD requiere la escritura de una prueba con errores, después la valida y finalmente repite el proceso.</span><span class="sxs-lookup"><span data-stu-id="08ab1-137">The TDD approach calls for writing one failing test, making it pass, then repeating the process.</span></span> <span data-ttu-id="08ab1-138">Quite *UnitTest1.cs* del directorio *PrimeService.Tests* y cree un nuevo archivo de C# denominado *PrimeService_IsPrimeShould.cs* con el siguiente contenido:</span><span class="sxs-lookup"><span data-stu-id="08ab1-138">Remove *UnitTest1.cs* from the *PrimeService.Tests* directory and create a new C# file named *PrimeService_IsPrimeShould.cs* with the following content:</span></span>

```csharp
using NUnit.Framework;
using Prime.Services;

namespace Prime.UnitTests.Services
{
    [TestFixture]
    public class PrimeService_IsPrimeShould
    {
        private readonly PrimeService _primeService;

        public PrimeService_IsPrimeShould()
        {
            _primeService = new PrimeService();
        }

        [Test]
        public void ReturnFalseGivenValueOf1()
        {
            var result = _primeService.IsPrime(1);

            Assert.IsFalse(result, "1 should not be prime");
        }
    }
}
```

<span data-ttu-id="08ab1-139">El atributo `[TestFixture]` indica una clase que contiene pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="08ab1-139">The `[TestFixture]` attribute denotes a class that contains unit tests.</span></span> <span data-ttu-id="08ab1-140">El atributo `[Test]` indica que un método es un método de prueba.</span><span class="sxs-lookup"><span data-stu-id="08ab1-140">The `[Test]` attribute indicates a method is a test method.</span></span>

<span data-ttu-id="08ab1-141">Guarde este archivo y ejecute [`dotnet test`](../tools/dotnet-test.md) para compilar las pruebas y la biblioteca de clases y luego ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="08ab1-141">Save this file and execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="08ab1-142">El ejecutor de pruebas de NUnit tiene el punto de entrada del programa para ejecutar las pruebas desde la consola.</span><span class="sxs-lookup"><span data-stu-id="08ab1-142">The NUnit test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="08ab1-143">`dotnet test` inicia el ejecutor de pruebas con el proyecto de prueba unitaria que creó.</span><span class="sxs-lookup"><span data-stu-id="08ab1-143">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="08ab1-144">La prueba produce un error.</span><span class="sxs-lookup"><span data-stu-id="08ab1-144">Your test fails.</span></span> <span data-ttu-id="08ab1-145">Todavía no ha creado la implementación.</span><span class="sxs-lookup"><span data-stu-id="08ab1-145">You haven't created the implementation yet.</span></span> <span data-ttu-id="08ab1-146">Cree esta prueba que se supera escribiendo el código más simple en la clase `PrimeService` que funciona:</span><span class="sxs-lookup"><span data-stu-id="08ab1-146">Make this test pass by writing the simplest code in the `PrimeService` class that works:</span></span>

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

<span data-ttu-id="08ab1-147">En el directorio *unit-testing-using-nunit*, vuelva a ejecutar `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="08ab1-147">In the *unit-testing-using-nunit* directory, run `dotnet test` again.</span></span> <span data-ttu-id="08ab1-148">El comando `dotnet test` ejecuta una compilación del proyecto `PrimeService` y luego del proyecto `PrimeService.Tests`.</span><span class="sxs-lookup"><span data-stu-id="08ab1-148">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="08ab1-149">Después de compilar ambos proyectos, se ejecuta esta única prueba.</span><span class="sxs-lookup"><span data-stu-id="08ab1-149">After building both projects, it runs this single test.</span></span> <span data-ttu-id="08ab1-150">Pasa.</span><span class="sxs-lookup"><span data-stu-id="08ab1-150">It passes.</span></span>

## <a name="adding-more-features"></a><span data-ttu-id="08ab1-151">Agregar más características</span><span class="sxs-lookup"><span data-stu-id="08ab1-151">Adding more features</span></span>

<span data-ttu-id="08ab1-152">Ahora que la prueba se ha superado, es el momento de escribir más.</span><span class="sxs-lookup"><span data-stu-id="08ab1-152">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="08ab1-153">Hay algunos otros casos simples para números primos: 0, -1.</span><span class="sxs-lookup"><span data-stu-id="08ab1-153">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="08ab1-154">Puede agregar pruebas nuevas con el atributo `[Test]`, pero enseguida este proceso se hace tedioso.</span><span class="sxs-lookup"><span data-stu-id="08ab1-154">You could add new tests with the `[Test]` attribute, but that quickly becomes tedious.</span></span> <span data-ttu-id="08ab1-155">Hay otros atributos de NUnit que le permiten escribir un conjunto de pruebas similares.</span><span class="sxs-lookup"><span data-stu-id="08ab1-155">There are other NUnit attributes that enable you to write a suite of similar tests.</span></span>  <span data-ttu-id="08ab1-156">Un atributo `[TestCase]` se usa para crear un conjunto de pruebas que ejecutan el mismo código pero tienen diferentes argumentos de entrada.</span><span class="sxs-lookup"><span data-stu-id="08ab1-156">A `[TestCase]` attribute is used to create a suite of tests that execute the same code but have different input arguments.</span></span> <span data-ttu-id="08ab1-157">Puede usar el atributo `[TestCase]` para especificar valores para esas entradas.</span><span class="sxs-lookup"><span data-stu-id="08ab1-157">You can use the `[TestCase]` attribute to specify values for those inputs.</span></span>

<span data-ttu-id="08ab1-158">En lugar de crear pruebas, aplique este atributo para crear una sola prueba controlada por datos.</span><span class="sxs-lookup"><span data-stu-id="08ab1-158">Instead of creating new tests, apply this attribute to create a single data driven test.</span></span> <span data-ttu-id="08ab1-159">La prueba controlada por datos es un método que prueba varios valores menores que dos, que es el número primo menor:</span><span class="sxs-lookup"><span data-stu-id="08ab1-159">The data driven test is a method that tests several values less than two, which is the lowest prime number:</span></span>

[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]

<span data-ttu-id="08ab1-160">Ejecute `dotnet test`, y dos de estas pruebas no se superarán.</span><span class="sxs-lookup"><span data-stu-id="08ab1-160">Run `dotnet test`, and two of these tests fail.</span></span> <span data-ttu-id="08ab1-161">Para superar todas las pruebas, cambie la cláusula `if` al principio del método:</span><span class="sxs-lookup"><span data-stu-id="08ab1-161">To make all of the tests pass, change the `if` clause at the beginning of the method:</span></span>

```csharp
if (candidate < 2)
```

<span data-ttu-id="08ab1-162">Puede continuar recorriendo en iteración agregando más pruebas, más teorías y más código en la biblioteca principal.</span><span class="sxs-lookup"><span data-stu-id="08ab1-162">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="08ab1-163">Ya tiene la [versión terminada de las pruebas](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.cs) y la [implementación completa de la biblioteca](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-nunit/PrimeService/PrimeService.cs).</span><span class="sxs-lookup"><span data-stu-id="08ab1-163">You have the [finished version of the tests](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.cs) and the [complete implementation of the library](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-nunit/PrimeService/PrimeService.cs).</span></span>

<span data-ttu-id="08ab1-164">Ha creado una biblioteca pequeña y un conjunto de pruebas unitarias para esa biblioteca.</span><span class="sxs-lookup"><span data-stu-id="08ab1-164">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="08ab1-165">Ha estructurado la solución, por lo que agregar pruebas y paquetes nuevos es parte del flujo de trabajo normal.</span><span class="sxs-lookup"><span data-stu-id="08ab1-165">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="08ab1-166">Ha centrado la mayor parte del tiempo y del esfuerzo en resolver los objetivos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="08ab1-166">You've concentrated most of your time and effort on solving the goals of the application.</span></span>
