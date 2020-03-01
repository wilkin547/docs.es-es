---
title: Prueba unitaria de C# con NUnit y .NET Core
description: 'Aprenda los conceptos de pruebas unitarias en C# y .NET Core: cree paso a paso una solución de ejemplo mediante pruebas de dotnet y NUnit.'
author: rprouse
ms.date: 08/31/2018
ms.openlocfilehash: 8c099695b48e96ac47e41794082cd8dccaa0457a
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78157276"
---
# <a name="unit-testing-c-with-nunit-and-net-core"></a><span data-ttu-id="b247c-103">Prueba unitaria de C# con NUnit y .NET Core</span><span class="sxs-lookup"><span data-stu-id="b247c-103">Unit testing C# with NUnit and .NET Core</span></span>

<span data-ttu-id="b247c-104">Este tutorial le guía por una experiencia interactiva de creación de una solución de ejemplo paso a paso para aprender los conceptos de pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="b247c-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="b247c-105">Si prefiere seguir el tutorial con una solución precompilada, [vea o descargue el código de ejemplo](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/) antes de comenzar.</span><span class="sxs-lookup"><span data-stu-id="b247c-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/) before you begin.</span></span> <span data-ttu-id="b247c-106">Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="b247c-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

[!INCLUDE [testing an ASP.NET Core project from .NET Core](../../../includes/core-testing-note-aspnet.md)]

## <a name="prerequisites"></a><span data-ttu-id="b247c-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="b247c-107">Prerequisites</span></span>

- <span data-ttu-id="b247c-108">[SDK de .NET Core 2.1](https://dotnet.microsoft.com/download) o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="b247c-108">[.NET Core 2.1 SDK](https://dotnet.microsoft.com/download) or later versions.</span></span>
- <span data-ttu-id="b247c-109">Un editor de texto o un editor de código de su elección.</span><span class="sxs-lookup"><span data-stu-id="b247c-109">A text editor or code editor of your choice.</span></span>

## <a name="creating-the-source-project"></a><span data-ttu-id="b247c-110">Crear el proyecto de origen</span><span class="sxs-lookup"><span data-stu-id="b247c-110">Creating the source project</span></span>

<span data-ttu-id="b247c-111">Abra una ventana del Shell.</span><span class="sxs-lookup"><span data-stu-id="b247c-111">Open a shell window.</span></span> <span data-ttu-id="b247c-112">Cree un directorio llamado *unit-testing-using-nunit* que contenga la solución.</span><span class="sxs-lookup"><span data-stu-id="b247c-112">Create a directory called *unit-testing-using-nunit* to hold the solution.</span></span> <span data-ttu-id="b247c-113">En este directorio nuevo, ejecute el comando siguiente para crear un archivo de solución nuevo para la biblioteca de clases y el proyecto de prueba:</span><span class="sxs-lookup"><span data-stu-id="b247c-113">Inside this new directory, run the following command to create a new solution file for the class library and the test project:</span></span>

```dotnetcli
dotnet new sln
```

<span data-ttu-id="b247c-114">A continuación, cree un directorio *PrimeService*.</span><span class="sxs-lookup"><span data-stu-id="b247c-114">Next, create a *PrimeService* directory.</span></span> <span data-ttu-id="b247c-115">En el esquema siguiente se muestra la estructura de directorios y archivos hasta el momento:</span><span class="sxs-lookup"><span data-stu-id="b247c-115">The following outline shows the directory and file structure so far:</span></span>

```console
/unit-testing-using-nunit
    unit-testing-using-nunit.sln
    /PrimeService
```

<span data-ttu-id="b247c-116">Convierta *PrimeService* en el directorio actual y ejecute el siguiente comando para crear el proyecto de origen:</span><span class="sxs-lookup"><span data-stu-id="b247c-116">Make *PrimeService* the current directory and run the following command to create the source project:</span></span>

```dotnetcli
dotnet new classlib
```

<span data-ttu-id="b247c-117">Cambie el nombre de *Class1.cs* a *PrimeService.cs*.</span><span class="sxs-lookup"><span data-stu-id="b247c-117">Rename *Class1.cs* to *PrimeService.cs*.</span></span> <span data-ttu-id="b247c-118">Creará una implementación de errores de la clase `PrimeService`:</span><span class="sxs-lookup"><span data-stu-id="b247c-118">You create a failing implementation of the `PrimeService` class:</span></span>

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

<span data-ttu-id="b247c-119">Cambie nuevamente el directorio a *unit-testing-using-nunit*.</span><span class="sxs-lookup"><span data-stu-id="b247c-119">Change the directory back to the *unit-testing-using-nunit* directory.</span></span> <span data-ttu-id="b247c-120">Ejecute el siguiente comando para agregar el proyecto de biblioteca de clases a la solución:</span><span class="sxs-lookup"><span data-stu-id="b247c-120">Run the following command to add the class library project to the solution:</span></span>

```dotnetcli
dotnet sln add PrimeService/PrimeService.csproj
```

## <a name="creating-the-test-project"></a><span data-ttu-id="b247c-121">Crear el proyecto de prueba</span><span class="sxs-lookup"><span data-stu-id="b247c-121">Creating the test project</span></span>

<span data-ttu-id="b247c-122">A continuación, cree el directorio *PrimeService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="b247c-122">Next, create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="b247c-123">En el esquema siguiente se muestra la estructura de directorios:</span><span class="sxs-lookup"><span data-stu-id="b247c-123">The following outline shows the directory structure:</span></span>

```console
/unit-testing-using-nunit
    unit-testing-using-nunit.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

<span data-ttu-id="b247c-124">Convierta el directorio *PrimeService.Tests* en el directorio actual y cree un proyecto nuevo con el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="b247c-124">Make the *PrimeService.Tests* directory the current directory and create a new project using the following command:</span></span>

```dotnetcli
dotnet new nunit
```

<span data-ttu-id="b247c-125">El comando [dotnet new](../tools/dotnet-new.md) crea un proyecto de prueba que usa NUnit como la biblioteca de pruebas.</span><span class="sxs-lookup"><span data-stu-id="b247c-125">The [dotnet new](../tools/dotnet-new.md) command creates a test project that uses NUnit as the test library.</span></span> <span data-ttu-id="b247c-126">La plantilla generada configura el ejecutor de pruebas en el archivo *PrimeService.Tests.csproj*:</span><span class="sxs-lookup"><span data-stu-id="b247c-126">The generated template configures the test runner in the *PrimeService.Tests.csproj* file:</span></span>

[!code-xml[Packages](~/samples/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService.Tests.csproj#Packages)]

<span data-ttu-id="b247c-127">El proyecto de prueba requiere otros paquetes para crear y ejecutar pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="b247c-127">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="b247c-128">En el paso anterior, `dotnet new` agrega el SDK de prueba de Microsoft, el marco de pruebas de NUnit y el adaptador de prueba de NUnit.</span><span class="sxs-lookup"><span data-stu-id="b247c-128">`dotnet new` in the previous step added the Microsoft test SDK, the NUnit test framework, and the NUnit test adapter.</span></span> <span data-ttu-id="b247c-129">Ahora, agregue la biblioteca de clases `PrimeService` como otra dependencia al proyecto.</span><span class="sxs-lookup"><span data-stu-id="b247c-129">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="b247c-130">Use el comando [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="b247c-130">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```dotnetcli
dotnet add reference ../PrimeService/PrimeService.csproj
```

<span data-ttu-id="b247c-131">Puede ver todo el archivo en el [repositorio de muestras](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService.Tests.csproj) en GitHub.</span><span class="sxs-lookup"><span data-stu-id="b247c-131">You can see the entire file in the [samples repository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService.Tests.csproj) on GitHub.</span></span>

<span data-ttu-id="b247c-132">En el esquema siguiente se muestra el diseño de solución final:</span><span class="sxs-lookup"><span data-stu-id="b247c-132">The following outline shows the final solution layout:</span></span>

```console
/unit-testing-using-nunit
    unit-testing-using-nunit.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
        Test Source Files
        PrimeService.Tests.csproj
```

<span data-ttu-id="b247c-133">Ejecute el comando siguiente en el directorio *unit-testing-using-nunit*:</span><span class="sxs-lookup"><span data-stu-id="b247c-133">Execute the following command in the *unit-testing-using-nunit* directory:</span></span>

```dotnetcli
dotnet sln add ./PrimeService.Tests/PrimeService.Tests.csproj
```

## <a name="creating-the-first-test"></a><span data-ttu-id="b247c-134">Crear la primera prueba</span><span class="sxs-lookup"><span data-stu-id="b247c-134">Creating the first test</span></span>

<span data-ttu-id="b247c-135">Escribirá una prueba de errores, la aprobará y, luego, repetirá el proceso.</span><span class="sxs-lookup"><span data-stu-id="b247c-135">You write one failing test, make it pass, then repeat the process.</span></span> <span data-ttu-id="b247c-136">En el directorio *PrimeService.Tests*, cambie el nombre del archivo *UnitTest1.cs* por *PrimeService_IsPrimeShould.cs* y reemplace todo su contenido por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="b247c-136">In the *PrimeService.Tests* directory, rename the *UnitTest1.cs* file to *PrimeService_IsPrimeShould.cs* and replace its entire contents with the following code:</span></span>

```csharp
using NUnit.Framework;
using Prime.Services;

namespace Prime.UnitTests.Services
{
    [TestFixture]
    public class PrimeService_IsPrimeShould
    {
        [Test]
        public void IsPrime_InputIs1_ReturnFalse()
        {
            PrimeService primeService = CreatePrimeService();
            var result = primeService.IsPrime(1);

            Assert.IsFalse(result, "1 should not be prime");
        }

        /*
        More tests
        */

        private PrimeService CreatePrimeService()
        {
             return new PrimeService();
        }
    }
}
```

<span data-ttu-id="b247c-137">El atributo `[TestFixture]` indica una clase que contiene pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="b247c-137">The `[TestFixture]` attribute denotes a class that contains unit tests.</span></span> <span data-ttu-id="b247c-138">El atributo `[Test]` indica que un método es un método de prueba.</span><span class="sxs-lookup"><span data-stu-id="b247c-138">The `[Test]` attribute indicates a method is a test method.</span></span>

<span data-ttu-id="b247c-139">Guarde este archivo y ejecute [`dotnet test`](../tools/dotnet-test.md) para compilar las pruebas y la biblioteca de clases y luego ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="b247c-139">Save this file and execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="b247c-140">El ejecutor de pruebas de NUnit tiene el punto de entrada del programa para ejecutar las pruebas desde la consola.</span><span class="sxs-lookup"><span data-stu-id="b247c-140">The NUnit test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="b247c-141">`dotnet test` inicia el ejecutor de pruebas con el proyecto de prueba unitaria que creó.</span><span class="sxs-lookup"><span data-stu-id="b247c-141">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="b247c-142">La prueba produce un error.</span><span class="sxs-lookup"><span data-stu-id="b247c-142">Your test fails.</span></span> <span data-ttu-id="b247c-143">Todavía no ha creado la implementación.</span><span class="sxs-lookup"><span data-stu-id="b247c-143">You haven't created the implementation yet.</span></span> <span data-ttu-id="b247c-144">Cree esta prueba que se supera escribiendo el código más simple en la clase `PrimeService` que funciona:</span><span class="sxs-lookup"><span data-stu-id="b247c-144">Make this test pass by writing the simplest code in the `PrimeService` class that works:</span></span>

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

<span data-ttu-id="b247c-145">En el directorio *unit-testing-using-nunit*, vuelva a ejecutar `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="b247c-145">In the *unit-testing-using-nunit* directory, run `dotnet test` again.</span></span> <span data-ttu-id="b247c-146">El comando `dotnet test` ejecuta una compilación del proyecto `PrimeService` y luego del proyecto `PrimeService.Tests`.</span><span class="sxs-lookup"><span data-stu-id="b247c-146">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="b247c-147">Después de compilar ambos proyectos, se ejecuta esta única prueba.</span><span class="sxs-lookup"><span data-stu-id="b247c-147">After building both projects, it runs this single test.</span></span> <span data-ttu-id="b247c-148">Pasa.</span><span class="sxs-lookup"><span data-stu-id="b247c-148">It passes.</span></span>

## <a name="adding-more-features"></a><span data-ttu-id="b247c-149">Agregar más características</span><span class="sxs-lookup"><span data-stu-id="b247c-149">Adding more features</span></span>

<span data-ttu-id="b247c-150">Ahora que la prueba se ha superado, es el momento de escribir más.</span><span class="sxs-lookup"><span data-stu-id="b247c-150">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="b247c-151">Hay otros casos simples para números primos: 0, -1.</span><span class="sxs-lookup"><span data-stu-id="b247c-151">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="b247c-152">Puede agregar pruebas nuevas con el atributo `[Test]`, pero enseguida este proceso se hace tedioso.</span><span class="sxs-lookup"><span data-stu-id="b247c-152">You could add new tests with the `[Test]` attribute, but that quickly becomes tedious.</span></span> <span data-ttu-id="b247c-153">Hay otros atributos de NUnit que le permiten escribir un conjunto de pruebas similares.</span><span class="sxs-lookup"><span data-stu-id="b247c-153">There are other NUnit attributes that enable you to write a suite of similar tests.</span></span>  <span data-ttu-id="b247c-154">Un atributo `[TestCase]` se usa para crear un conjunto de pruebas que ejecutan el mismo código pero tienen diferentes argumentos de entrada.</span><span class="sxs-lookup"><span data-stu-id="b247c-154">A `[TestCase]` attribute is used to create a suite of tests that execute the same code but have different input arguments.</span></span> <span data-ttu-id="b247c-155">Puede usar el atributo `[TestCase]` para especificar valores para esas entradas.</span><span class="sxs-lookup"><span data-stu-id="b247c-155">You can use the `[TestCase]` attribute to specify values for those inputs.</span></span>

<span data-ttu-id="b247c-156">En lugar de crear pruebas, aplique este atributo para crear una sola prueba controlada por datos.</span><span class="sxs-lookup"><span data-stu-id="b247c-156">Instead of creating new tests, apply this attribute to create a single data driven test.</span></span> <span data-ttu-id="b247c-157">La prueba controlada por datos es un método que prueba varios valores menores que dos, que es el número primo menor:</span><span class="sxs-lookup"><span data-stu-id="b247c-157">The data driven test is a method that tests several values less than two, which is the lowest prime number:</span></span>

[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]

<span data-ttu-id="b247c-158">Ejecute `dotnet test`, y dos de estas pruebas no se superarán.</span><span class="sxs-lookup"><span data-stu-id="b247c-158">Run `dotnet test`, and two of these tests fail.</span></span> <span data-ttu-id="b247c-159">Para superar todas las pruebas, cambie la cláusula `if` al principio del método `Main` en el archivo *PrimeService.cs*:</span><span class="sxs-lookup"><span data-stu-id="b247c-159">To make all of the tests pass, change the `if` clause at the beginning of the `Main` method in the *PrimeService.cs* file:</span></span>

```csharp
if (candidate < 2)
```

<span data-ttu-id="b247c-160">Puede continuar recorriendo en iteración agregando más pruebas, más teorías y más código en la biblioteca principal.</span><span class="sxs-lookup"><span data-stu-id="b247c-160">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="b247c-161">Ya tiene la [versión terminada de las pruebas](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.cs) y la [implementación completa de la biblioteca](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService/PrimeService.cs).</span><span class="sxs-lookup"><span data-stu-id="b247c-161">You have the [finished version of the tests](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.cs) and the [complete implementation of the library](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService/PrimeService.cs).</span></span>

<span data-ttu-id="b247c-162">Ha creado una biblioteca pequeña y un conjunto de pruebas unitarias para esa biblioteca.</span><span class="sxs-lookup"><span data-stu-id="b247c-162">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="b247c-163">Ha estructurado la solución, por lo que agregar pruebas y paquetes nuevos es parte del flujo de trabajo normal.</span><span class="sxs-lookup"><span data-stu-id="b247c-163">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="b247c-164">Ha centrado la mayor parte del tiempo y del esfuerzo en resolver los objetivos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b247c-164">You've concentrated most of your time and effort on solving the goals of the application.</span></span>
