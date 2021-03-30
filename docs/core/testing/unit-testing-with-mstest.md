---
title: Prueba unitaria de C# con MSTest y .NET Core
description: 'Aprenda los conceptos de pruebas unitarias en C# y .NET Core: cree paso a paso una solución de ejemplo mediante pruebas de dotnet y MSTest.'
author: ncarandini
ms.author: wiwagn
ms.date: 10/21/2020
ms.openlocfilehash: e2c3326778d7fc1a492062cff4f2d2ad4a61ac18
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104874893"
---
# <a name="unit-testing-c-with-mstest-and-net-core"></a><span data-ttu-id="57fd8-103">Prueba unitaria de C# con MSTest y .NET Core</span><span class="sxs-lookup"><span data-stu-id="57fd8-103">Unit testing C# with MSTest and .NET Core</span></span>

<span data-ttu-id="57fd8-104">Este tutorial le guía por una experiencia interactiva de creación de una solución de ejemplo paso a paso para aprender los conceptos de pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="57fd8-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="57fd8-105">Si prefiere seguir el tutorial con una solución precompilada, [vea o descargue el código de ejemplo](https://github.com/dotnet/samples/blob/main/core/getting-started/unit-testing-using-mstest/) antes de comenzar.</span><span class="sxs-lookup"><span data-stu-id="57fd8-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/samples/blob/main/core/getting-started/unit-testing-using-mstest/) before you begin.</span></span> <span data-ttu-id="57fd8-106">Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../../samples-and-tutorials/index.md#view-and-download-samples).</span><span class="sxs-lookup"><span data-stu-id="57fd8-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#view-and-download-samples).</span></span>

[!INCLUDE [testing an ASP.NET Core project from .NET Core](../../../includes/core-testing-note-aspnet.md)]

## <a name="create-the-source-project"></a><span data-ttu-id="57fd8-107">Creación del proyecto de origen</span><span class="sxs-lookup"><span data-stu-id="57fd8-107">Create the source project</span></span>

<span data-ttu-id="57fd8-108">Abra una ventana del Shell.</span><span class="sxs-lookup"><span data-stu-id="57fd8-108">Open a shell window.</span></span> <span data-ttu-id="57fd8-109">Cree un directorio llamado *unit-testing-using-mstest* que contenga la solución.</span><span class="sxs-lookup"><span data-stu-id="57fd8-109">Create a directory called *unit-testing-using-mstest* to hold the solution.</span></span> <span data-ttu-id="57fd8-110">En este directorio nuevo, ejecute [`dotnet new sln`](../tools/dotnet-new.md) para crear un archivo de solución nuevo para la biblioteca de clases y el proyecto de prueba.</span><span class="sxs-lookup"><span data-stu-id="57fd8-110">Inside this new directory, run [`dotnet new sln`](../tools/dotnet-new.md) to create a new solution file for the class library and the test project.</span></span> <span data-ttu-id="57fd8-111">A continuación, cree un directorio *PrimeService*.</span><span class="sxs-lookup"><span data-stu-id="57fd8-111">Next, create a *PrimeService* directory.</span></span> <span data-ttu-id="57fd8-112">En el esquema siguiente se muestra la estructura de directorios y archivos hasta el momento:</span><span class="sxs-lookup"><span data-stu-id="57fd8-112">The following outline shows the directory and file structure thus far:</span></span>

```console
/unit-testing-using-mstest
    unit-testing-using-mstest.sln
    /PrimeService
```

<span data-ttu-id="57fd8-113">Convierta *PrimeService* en el directorio actual y ejecute [`dotnet new classlib`](../tools/dotnet-new.md) para crear el proyecto de origen.</span><span class="sxs-lookup"><span data-stu-id="57fd8-113">Make *PrimeService* the current directory and run [`dotnet new classlib`](../tools/dotnet-new.md) to create the source project.</span></span> <span data-ttu-id="57fd8-114">Cambie el nombre de *Class1.cs* a *PrimeService.cs*.</span><span class="sxs-lookup"><span data-stu-id="57fd8-114">Rename *Class1.cs* to *PrimeService.cs*.</span></span> <span data-ttu-id="57fd8-115">Creará una implementación de errores de la clase `PrimeService`:</span><span class="sxs-lookup"><span data-stu-id="57fd8-115">You create a failing implementation of the `PrimeService` class:</span></span>

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

<span data-ttu-id="57fd8-116">Cambie nuevamente el directorio al directorio *unit-testing-using-mstest*.</span><span class="sxs-lookup"><span data-stu-id="57fd8-116">Change the directory back to the *unit-testing-using-mstest* directory.</span></span> <span data-ttu-id="57fd8-117">Ejecute [`dotnet sln add PrimeService/PrimeService.csproj`](../tools/dotnet-sln.md) para agregar el proyecto de biblioteca de clases a la solución.</span><span class="sxs-lookup"><span data-stu-id="57fd8-117">Run [`dotnet sln add PrimeService/PrimeService.csproj`](../tools/dotnet-sln.md) to add the class library project to the solution.</span></span>

## <a name="create-the-test-project"></a><span data-ttu-id="57fd8-118">Crear el proyecto de prueba</span><span class="sxs-lookup"><span data-stu-id="57fd8-118">Create the test project</span></span>

<span data-ttu-id="57fd8-119">A continuación, cree el directorio *PrimeService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="57fd8-119">Next, create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="57fd8-120">En el esquema siguiente se muestra la estructura de directorios:</span><span class="sxs-lookup"><span data-stu-id="57fd8-120">The following outline shows the directory structure:</span></span>

```console
/unit-testing-using-mstest
    unit-testing-using-mstest.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

<span data-ttu-id="57fd8-121">Convierta el directorio *PrimeService.Tests* en el directorio actual y cree un proyecto nuevo con [`dotnet new mstest`](../tools/dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="57fd8-121">Make the *PrimeService.Tests* directory the current directory and create a new project using [`dotnet new mstest`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="57fd8-122">Este comando de dotnet nuevo crea un proyecto de prueba que usa MSTest como la biblioteca de pruebas.</span><span class="sxs-lookup"><span data-stu-id="57fd8-122">The dotnet new command creates a test project that uses MSTest as the test library.</span></span> <span data-ttu-id="57fd8-123">La plantilla generada configura el ejecutor de pruebas en el archivo *PrimeServiceTests.csproj*:</span><span class="sxs-lookup"><span data-stu-id="57fd8-123">The generated template configures the test runner in the *PrimeServiceTests.csproj* file:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.3.0" />
  <PackageReference Include="MSTest.TestAdapter" Version="1.1.18" />
  <PackageReference Include="MSTest.TestFramework" Version="1.1.18" />
</ItemGroup>
```

<span data-ttu-id="57fd8-124">El proyecto de prueba requiere otros paquetes para crear y ejecutar pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="57fd8-124">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="57fd8-125">`dotnet new` en el paso anterior agregó el SDK de MSTest, el marco de prueba de MSTest y el ejecutor de MSTest.</span><span class="sxs-lookup"><span data-stu-id="57fd8-125">`dotnet new` in the previous step added the MSTest SDK, the MSTest test framework, and the MSTest runner.</span></span> <span data-ttu-id="57fd8-126">Ahora, agregue la biblioteca de clases `PrimeService` como otra dependencia al proyecto.</span><span class="sxs-lookup"><span data-stu-id="57fd8-126">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="57fd8-127">Use el comando [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="57fd8-127">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```dotnetcli
dotnet add reference ../PrimeService/PrimeService.csproj
```

<span data-ttu-id="57fd8-128">Puede ver todo el archivo en el [repositorio de muestras](https://github.com/dotnet/samples/blob/main/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService.Tests.csproj) en GitHub.</span><span class="sxs-lookup"><span data-stu-id="57fd8-128">You can see the entire file in the [samples repository](https://github.com/dotnet/samples/blob/main/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService.Tests.csproj) on GitHub.</span></span>

<span data-ttu-id="57fd8-129">En el esquema siguiente se muestra el diseño de solución final:</span><span class="sxs-lookup"><span data-stu-id="57fd8-129">The following outline shows the final solution layout:</span></span>

```console
/unit-testing-using-mstest
    unit-testing-using-mstest.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
        Test Source Files
        PrimeServiceTests.csproj
```

<span data-ttu-id="57fd8-130">Ejecute [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.csproj`](../tools/dotnet-sln.md) en el directorio *unit-testing-using-mstest*.</span><span class="sxs-lookup"><span data-stu-id="57fd8-130">Execute [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.csproj`](../tools/dotnet-sln.md) in the *unit-testing-using-mstest* directory.</span></span>

## <a name="create-the-first-test"></a><span data-ttu-id="57fd8-131">Creación de la primera prueba</span><span class="sxs-lookup"><span data-stu-id="57fd8-131">Create the first test</span></span>

<span data-ttu-id="57fd8-132">Escribirá una prueba de errores, la aprobará y, luego, repetirá el proceso.</span><span class="sxs-lookup"><span data-stu-id="57fd8-132">You write one failing test, make it pass, then repeat the process.</span></span> <span data-ttu-id="57fd8-133">Quite *UnitTest1.cs* del directorio *PrimeService.Tests* y cree un nuevo archivo de C# denominado *PrimeService_IsPrimeShould.cs* con el siguiente contenido:</span><span class="sxs-lookup"><span data-stu-id="57fd8-133">Remove *UnitTest1.cs* from the *PrimeService.Tests* directory and create a new C# file named *PrimeService_IsPrimeShould.cs* with the following content:</span></span>

```csharp
using Microsoft.VisualStudio.TestTools.UnitTesting;
using Prime.Services;

namespace Prime.UnitTests.Services
{
    [TestClass]
    public class PrimeService_IsPrimeShould
    {
        [TestMethod]
        public void IsPrime_InputIs1_ReturnFalse()
        {
            var primeService = new PrimeService();
            bool result = primeService.IsPrime(1);

            Assert.IsFalse(result, "1 should not be prime");
        }
    }
}
```

<span data-ttu-id="57fd8-134">El [atributo TestClass](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) indica una clase que contiene pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="57fd8-134">The [TestClass attribute](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) denotes a class that contains unit tests.</span></span> <span data-ttu-id="57fd8-135">El [atributo TestMethod](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) indica que un método es un método de prueba.</span><span class="sxs-lookup"><span data-stu-id="57fd8-135">The [TestMethod attribute](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) indicates a method is a test method.</span></span>

<span data-ttu-id="57fd8-136">Guarde este archivo y ejecute [`dotnet test`](../tools/dotnet-test.md) para compilar las pruebas y la biblioteca de clases y luego ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="57fd8-136">Save this file and execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="57fd8-137">El ejecutor de pruebas de MSTest tiene el punto de entrada del programa para ejecutar las pruebas desde la consola.</span><span class="sxs-lookup"><span data-stu-id="57fd8-137">The MSTest test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="57fd8-138">`dotnet test` inicia el ejecutor de pruebas con el proyecto de prueba unitaria que creó.</span><span class="sxs-lookup"><span data-stu-id="57fd8-138">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="57fd8-139">La prueba produce un error.</span><span class="sxs-lookup"><span data-stu-id="57fd8-139">Your test fails.</span></span> <span data-ttu-id="57fd8-140">Todavía no ha creado la implementación.</span><span class="sxs-lookup"><span data-stu-id="57fd8-140">You haven't created the implementation yet.</span></span> <span data-ttu-id="57fd8-141">Cree esta prueba que se supera escribiendo el código más simple en la clase `PrimeService` que funciona:</span><span class="sxs-lookup"><span data-stu-id="57fd8-141">Make this test pass by writing the simplest code in the `PrimeService` class that works:</span></span>

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

<span data-ttu-id="57fd8-142">En el directorio *unit-testing-using-mstest*, vuelva a ejecutar `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="57fd8-142">In the *unit-testing-using-mstest* directory, run `dotnet test` again.</span></span> <span data-ttu-id="57fd8-143">El comando `dotnet test` ejecuta una compilación del proyecto `PrimeService` y luego del proyecto `PrimeService.Tests`.</span><span class="sxs-lookup"><span data-stu-id="57fd8-143">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="57fd8-144">Después de compilar ambos proyectos, se ejecuta esta única prueba.</span><span class="sxs-lookup"><span data-stu-id="57fd8-144">After building both projects, it runs this single test.</span></span> <span data-ttu-id="57fd8-145">Pasa.</span><span class="sxs-lookup"><span data-stu-id="57fd8-145">It passes.</span></span>

## <a name="add-more-features"></a><span data-ttu-id="57fd8-146">Adición de más características</span><span class="sxs-lookup"><span data-stu-id="57fd8-146">Add more features</span></span>

<span data-ttu-id="57fd8-147">Ahora que la prueba se ha superado, es el momento de escribir más.</span><span class="sxs-lookup"><span data-stu-id="57fd8-147">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="57fd8-148">Hay algunos otros casos simples para números primos: 0, -1.</span><span class="sxs-lookup"><span data-stu-id="57fd8-148">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="57fd8-149">Puede agregar pruebas nuevas con el [atributo TestMethod](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute), pero este proceso enseguida se hace tedioso.</span><span class="sxs-lookup"><span data-stu-id="57fd8-149">You could add new tests with the [TestMethod attribute](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute), but that quickly becomes tedious.</span></span> <span data-ttu-id="57fd8-150">Hay otros atributos de MSTest que le permiten escribir un conjunto de pruebas similares.</span><span class="sxs-lookup"><span data-stu-id="57fd8-150">There are other MSTest attributes that enable you to write a suite of similar tests.</span></span>  <span data-ttu-id="57fd8-151">Un [atributo DataTestMethod](xref:Microsoft.VisualStudio.TestTools.UnitTesting.DataTestMethodAttribute) representa un conjunto de pruebas que ejecutan el mismo código, pero tienen diferentes argumentos de entrada.</span><span class="sxs-lookup"><span data-stu-id="57fd8-151">A [DataTestMethod attribute](xref:Microsoft.VisualStudio.TestTools.UnitTesting.DataTestMethodAttribute) represents a suite of tests that execute the same code but have different input arguments.</span></span> <span data-ttu-id="57fd8-152">Puede usar el [atributo DataRow](xref:Microsoft.VisualStudio.TestTools.UnitTesting.DataRowAttribute) para especificar valores para esas entradas.</span><span class="sxs-lookup"><span data-stu-id="57fd8-152">You can use the [DataRow attribute](xref:Microsoft.VisualStudio.TestTools.UnitTesting.DataRowAttribute) to specify values for those inputs.</span></span>

<span data-ttu-id="57fd8-153">En lugar de crear pruebas nuevas, aplique estos dos atributos para crear una sola prueba controlada por datos.</span><span class="sxs-lookup"><span data-stu-id="57fd8-153">Instead of creating new tests, apply these two attributes to create a single data driven test.</span></span> <span data-ttu-id="57fd8-154">La prueba controlada por datos es un método que prueba varios valores menores que dos, que es el número primo menor:</span><span class="sxs-lookup"><span data-stu-id="57fd8-154">The data driven test is a method that tests several values less than two, which is the lowest prime number:</span></span>

[!code-csharp[Sample_TestCode](../../../samples/snippets/core/testing/unit-testing-using-mstest/csharp/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]

<span data-ttu-id="57fd8-155">Ejecute `dotnet test`, y dos de estas pruebas no se superarán.</span><span class="sxs-lookup"><span data-stu-id="57fd8-155">Run `dotnet test`, and two of these tests fail.</span></span> <span data-ttu-id="57fd8-156">Para superar todas las pruebas, cambie la cláusula `if` al principio del método:</span><span class="sxs-lookup"><span data-stu-id="57fd8-156">To make all of the tests pass, change the `if` clause at the beginning of the method:</span></span>

```csharp
if (candidate < 2)
```

<span data-ttu-id="57fd8-157">Puede continuar recorriendo en iteración agregando más pruebas, más teorías y más código en la biblioteca principal.</span><span class="sxs-lookup"><span data-stu-id="57fd8-157">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="57fd8-158">Ya tiene la [versión terminada de las pruebas](https://github.com/dotnet/samples/blob/main/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs) y la [implementación completa de la biblioteca](https://github.com/dotnet/samples/blob/main/core/getting-started/unit-testing-using-mstest/PrimeService/PrimeService.cs).</span><span class="sxs-lookup"><span data-stu-id="57fd8-158">You have the [finished version of the tests](https://github.com/dotnet/samples/blob/main/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs) and the [complete implementation of the library](https://github.com/dotnet/samples/blob/main/core/getting-started/unit-testing-using-mstest/PrimeService/PrimeService.cs).</span></span>

<span data-ttu-id="57fd8-159">Ha creado una biblioteca pequeña y un conjunto de pruebas unitarias para esa biblioteca.</span><span class="sxs-lookup"><span data-stu-id="57fd8-159">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="57fd8-160">Ha estructurado la solución, por lo que agregar pruebas y paquetes nuevos es parte del flujo de trabajo normal.</span><span class="sxs-lookup"><span data-stu-id="57fd8-160">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="57fd8-161">Ha centrado la mayor parte del tiempo y del esfuerzo en resolver los objetivos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="57fd8-161">You've concentrated most of your time and effort on solving the goals of the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="57fd8-162">Consulte también</span><span class="sxs-lookup"><span data-stu-id="57fd8-162">See also</span></span>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting>
- [<span data-ttu-id="57fd8-163">Usar el marco de trabajo MSTest en pruebas unitarias</span><span class="sxs-lookup"><span data-stu-id="57fd8-163">Use the MSTest framework in unit tests</span></span>](/visualstudio/test/using-microsoft-visualstudio-testtools-unittesting-members-in-unit-tests)
- [<span data-ttu-id="57fd8-164">Documentos del marco de pruebas de MSTest V2</span><span class="sxs-lookup"><span data-stu-id="57fd8-164">MSTest V2 test framework docs</span></span>](https://github.com/Microsoft/testfx-docs)
