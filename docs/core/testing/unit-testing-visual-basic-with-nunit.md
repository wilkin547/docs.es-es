---
title: Prueba unitaria de Visual Basic en .NET Core con pruebas de dotnet y NUnit
description: "Aprenda los conceptos de pruebas unitarias en .NET Core: cree una solución de Visual Basic de ejemplo paso a paso mediante NUnit."
author: rprouse
ms.date: 12/01/2017
ms.topic: article
dev_langs: vb
ms.prod: .net-core
ms.openlocfilehash: 2166da36fe9d0297f03e7c38249135d281b9a5d6
ms.sourcegitcommit: 401c4427a3ec0d1263543033b3084039278509dc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2017
---
# <a name="unit-testing-visual-basic-net-core-libraries-using-dotnet-test-and-nunit"></a><span data-ttu-id="118c3-103">Bibliotecas de .NET Core de prueba unitaria de Visual Basic con pruebas de dotnet y NUnit</span><span class="sxs-lookup"><span data-stu-id="118c3-103">Unit testing Visual Basic .NET Core libraries using dotnet test and NUnit</span></span>

<span data-ttu-id="118c3-104">Este tutorial le guía por una experiencia interactiva de creación de una solución de ejemplo paso a paso para aprender los conceptos de pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="118c3-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="118c3-105">Si prefiere seguir el tutorial con una solución precompilada, [vea o descargue el código de ejemplo](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/unit-testing-vb-nunit/) antes de comenzar.</span><span class="sxs-lookup"><span data-stu-id="118c3-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/unit-testing-vb-nunit/) before you begin.</span></span> <span data-ttu-id="118c3-106">Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="118c3-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="creating-the-source-project"></a><span data-ttu-id="118c3-107">Crear el proyecto de origen</span><span class="sxs-lookup"><span data-stu-id="118c3-107">Creating the source project</span></span>

<span data-ttu-id="118c3-108">Abra una ventana del Shell.</span><span class="sxs-lookup"><span data-stu-id="118c3-108">Open a shell window.</span></span> <span data-ttu-id="118c3-109">Cree un directorio llamado *unit-testing-vb-nunit* que contenga la solución.</span><span class="sxs-lookup"><span data-stu-id="118c3-109">Create a directory called *unit-testing-vb-nunit* to hold the solution.</span></span> <span data-ttu-id="118c3-110">En este directorio nuevo, ejecute [`dotnet new sln`](../tools/dotnet-new.md) para crear una solución nueva.</span><span class="sxs-lookup"><span data-stu-id="118c3-110">Inside this new directory, run [`dotnet new sln`](../tools/dotnet-new.md) to create a new solution.</span></span> <span data-ttu-id="118c3-111">Esta práctica permite facilitar la administración de la biblioteca de clases y del proyecto de prueba unitaria.</span><span class="sxs-lookup"><span data-stu-id="118c3-111">This practice makes it easier to manage both the class library and the unit test project.</span></span> <span data-ttu-id="118c3-112">En el directorio de la solución, cree un directorio *PrimeService*.</span><span class="sxs-lookup"><span data-stu-id="118c3-112">Inside the solution directory, create a *PrimeService* directory.</span></span> <span data-ttu-id="118c3-113">Hasta el momento, esta es la estructura de directorios y archivos:</span><span class="sxs-lookup"><span data-stu-id="118c3-113">You have the following directory and file structure thus far:</span></span>

```
/unit-testing-vb-nunit
    unit-testing-vb-nunit.sln
    /PrimeService
```

<span data-ttu-id="118c3-114">Convierta *PrimeService* en el directorio actual y ejecute [`dotnet new classlib -lang VB`](../tools/dotnet-new.md) para crear el proyecto de origen.</span><span class="sxs-lookup"><span data-stu-id="118c3-114">Make *PrimeService* the current directory and run [`dotnet new classlib -lang VB`](../tools/dotnet-new.md) to create the source project.</span></span> <span data-ttu-id="118c3-115">Cambie el nombre de *Class1.VB* a *PrimeService.VB*.</span><span class="sxs-lookup"><span data-stu-id="118c3-115">Rename *Class1.VB* to *PrimeService.VB*.</span></span> <span data-ttu-id="118c3-116">Para usar el desarrollo controlado por pruebas (TDD), tiene que crear una implementación de errores de la clase `PrimeService`:</span><span class="sxs-lookup"><span data-stu-id="118c3-116">To use test-driven development (TDD), you create a failing implementation of the `PrimeService` class:</span></span>

```vb
Imports System

Namespace Prime.Services
    Public Class PrimeService
        Public Function IsPrime(candidate As Integer) As Boolean
            Throw New NotImplementedException("Please create a test first")
        End Function
    End Class
End Namespace
```

<span data-ttu-id="118c3-117">Cambien nuevamente el directorio al directorio *unit-testing-vb-using-stest*.</span><span class="sxs-lookup"><span data-stu-id="118c3-117">Change the directory back to the *unit-testing-vb-using-stest* directory.</span></span> <span data-ttu-id="118c3-118">Ejecute [`dotnet sln add .\PrimeService\PrimeService.vbproj`](../tools/dotnet-sln.md) para agregar el proyecto de biblioteca de clases a la solución.</span><span class="sxs-lookup"><span data-stu-id="118c3-118">Run [`dotnet sln add .\PrimeService\PrimeService.vbproj`](../tools/dotnet-sln.md) to add the class library project to the solution.</span></span>

## <a name="install-the-nunit-project-template"></a><span data-ttu-id="118c3-119">Instalación de la plantilla de proyecto NUnit</span><span class="sxs-lookup"><span data-stu-id="118c3-119">Install the NUnit project template</span></span>

<span data-ttu-id="118c3-120">Debe instalar las plantillas de proyecto de prueba NUnit para poder crear un proyecto de prueba.</span><span class="sxs-lookup"><span data-stu-id="118c3-120">The NUnit test project templates need to be installed before creating a test project.</span></span> <span data-ttu-id="118c3-121">Solo deberá hacerlo una vez en cada máquina de desarrollador en la que creará proyectos NUnit.</span><span class="sxs-lookup"><span data-stu-id="118c3-121">This only needs to be done once on each developer machine where you'll create new NUnit projects.</span></span> <span data-ttu-id="118c3-122">Ejecute [`dotnet new -i NUnit3.DotNetNew.Template`](../tools/dotnet-new.md) para instalar las plantillas NUnit.</span><span class="sxs-lookup"><span data-stu-id="118c3-122">Run [`dotnet new -i NUnit3.DotNetNew.Template`](../tools/dotnet-new.md) to install the NUnit templates.</span></span>

 ```
 dotnet new -i NUnit3.DotNetNew.Template
 ```

## <a name="creating-the-test-project"></a><span data-ttu-id="118c3-123">Crear el proyecto de prueba</span><span class="sxs-lookup"><span data-stu-id="118c3-123">Creating the test project</span></span>

<span data-ttu-id="118c3-124">A continuación, cree el directorio *PrimeService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="118c3-124">Next, create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="118c3-125">En el esquema siguiente se muestra la estructura de directorios:</span><span class="sxs-lookup"><span data-stu-id="118c3-125">The following outline shows the directory structure:</span></span>

```
/unit-testing-vb-nunit
    unit-testing-vb-nunit.sln
    /PrimeService
        Source Files
        PrimeService.vbproj
    /PrimeService.Tests
```

<span data-ttu-id="118c3-126">Convierta el directorio *PrimeService.Tests* en el directorio actual y cree un proyecto nuevo con [`dotnet new nunit -lang VB`](../tools/dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="118c3-126">Make the *PrimeService.Tests* directory the current directory and create a new project using [`dotnet new nunit -lang VB`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="118c3-127">Este comando crea un proyecto de prueba que usa NUnit como biblioteca de pruebas.</span><span class="sxs-lookup"><span data-stu-id="118c3-127">This command creates a test project that uses NUnit as the test library.</span></span> <span data-ttu-id="118c3-128">La plantilla generada ha configurado el ejecutor de pruebas en *PrimeServiceTests.vbproj*:</span><span class="sxs-lookup"><span data-stu-id="118c3-128">The generated template configures the test runner in the *PrimeServiceTests.vbproj*:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.5.0" />
  <PackageReference Include="NUnit" Version="3.9.0" />
  <PackageReference Include="NUnit3TestAdapter" Version="3.9.0" />
</ItemGroup>
```

<span data-ttu-id="118c3-129">El proyecto de prueba requiere otros paquetes para crear y ejecutar pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="118c3-129">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="118c3-130">En el paso anterior, `dotnet new` agrega NUnit y el adaptador de prueba NUnit.</span><span class="sxs-lookup"><span data-stu-id="118c3-130">`dotnet new` in the previous step added NUnit and the NUnit test adapter.</span></span> <span data-ttu-id="118c3-131">Ahora, agregue la biblioteca de clases `PrimeService` como otra dependencia al proyecto.</span><span class="sxs-lookup"><span data-stu-id="118c3-131">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="118c3-132">Use el comando [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="118c3-132">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```
dotnet add reference ../PrimeService/PrimeService.vbproj
```

<span data-ttu-id="118c3-133">Puede ver todo el archivo en el [repositorio de muestras](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-vb-nunit/PrimeService.Tests/PrimeService.Tests.vbproj) en GitHub.</span><span class="sxs-lookup"><span data-stu-id="118c3-133">You can see the entire file in the [samples repository](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-vb-nunit/PrimeService.Tests/PrimeService.Tests.vbproj) on GitHub.</span></span>

<span data-ttu-id="118c3-134">Tiene el diseño de solución final siguiente:</span><span class="sxs-lookup"><span data-stu-id="118c3-134">You have the following final solution layout:</span></span>

```
/unit-testing-vb-nunit
    unit-testing-vb-nunit.sln
    /PrimeService
        Source Files
        PrimeService.vbproj
    /PrimeService.Tests
        Test Source Files
        PrimeServiceTests.vbproj
```

<span data-ttu-id="118c3-135">Ejecute [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.vbproj`](../tools/dotnet-sln.md) en el directorio *unit-testing-vb-nunit*.</span><span class="sxs-lookup"><span data-stu-id="118c3-135">Execute [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.vbproj`](../tools/dotnet-sln.md) in the *unit-testing-vb-nunit* directory.</span></span>

## <a name="creating-the-first-test"></a><span data-ttu-id="118c3-136">Crear la primera prueba</span><span class="sxs-lookup"><span data-stu-id="118c3-136">Creating the first test</span></span>

<span data-ttu-id="118c3-137">El enfoque de TDD requiere la escritura de una prueba con errores, después la valida y finalmente repite el proceso.</span><span class="sxs-lookup"><span data-stu-id="118c3-137">The TDD approach calls for writing one failing test, making it pass, then repeating the process.</span></span> <span data-ttu-id="118c3-138">Quite *UnitTest1.vb* del directorio *PrimeService.Tests* y cree un archivo de Visual Basic nuevo denominado *PrimeService_IsPrimeShould.VB*.</span><span class="sxs-lookup"><span data-stu-id="118c3-138">Remove *UnitTest1.vb* from the *PrimeService.Tests* directory and create a new Visual Basic file named *PrimeService_IsPrimeShould.VB*.</span></span> <span data-ttu-id="118c3-139">Agregue el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="118c3-139">Add the following code:</span></span>

```vb
Imports NUnit.Framework

Namespace PrimeService.Tests
    <TestFixture>
    Public Class PrimeService_IsPrimeShould
        Private _primeService As Prime.Services.PrimeService = New Prime.Services.PrimeService()

        <Test>
        Sub ReturnFalseGivenValueOf1()
            Dim result As Boolean = _primeService.IsPrime(1)

            Assert.False(result, "1 should not be prime")
        End Sub

    End Class
End Namespace
```

<span data-ttu-id="118c3-140">El atributo `<TestFixture>` indica una clase que contiene pruebas.</span><span class="sxs-lookup"><span data-stu-id="118c3-140">The `<TestFixture>` attribute indicates a class that contains tests.</span></span> <span data-ttu-id="118c3-141">El atributo `<Test>` indica un método que el ejecutor de pruebas ejecuta.</span><span class="sxs-lookup"><span data-stu-id="118c3-141">The `<Test>` attribute denotes a method that is run by the test runner.</span></span> <span data-ttu-id="118c3-142">En *unit-testing-vb-nunit*, ejecute [`dotnet test`](../tools/dotnet-test.md) para compilar las pruebas y la biblioteca de clases y luego ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="118c3-142">From the *unit-testing-vb-nunit*, execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="118c3-143">El ejecutor de pruebas de NUnit tiene el punto de entrada del programa para ejecutar las pruebas desde la consola.</span><span class="sxs-lookup"><span data-stu-id="118c3-143">The NUnit test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="118c3-144">`dotnet test` inicia el ejecutor de pruebas con el proyecto de prueba unitaria que creó.</span><span class="sxs-lookup"><span data-stu-id="118c3-144">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="118c3-145">La prueba produce un error.</span><span class="sxs-lookup"><span data-stu-id="118c3-145">Your test fails.</span></span> <span data-ttu-id="118c3-146">Todavía no ha creado la implementación.</span><span class="sxs-lookup"><span data-stu-id="118c3-146">You haven't created the implementation yet.</span></span> <span data-ttu-id="118c3-147">Cree esta prueba escribiendo el código más simple en la clase `PrimeService` que funciona:</span><span class="sxs-lookup"><span data-stu-id="118c3-147">Make this test by writing the simplest code in the `PrimeService` class that works:</span></span>

```vb
Public Function IsPrime(candidate As Integer) As Boolean
    If candidate = 1 Then
        Return False
    End If
    Throw New NotImplementedException("Please create a test first")
End Function
```

<span data-ttu-id="118c3-148">En el directorio *unit-testing-vb-nunit*, vuelva a ejecutar `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="118c3-148">In the *unit-testing-vb-nunit* directory, run `dotnet test` again.</span></span> <span data-ttu-id="118c3-149">El comando `dotnet test` ejecuta una compilación del proyecto `PrimeService` y luego del proyecto `PrimeService.Tests`.</span><span class="sxs-lookup"><span data-stu-id="118c3-149">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="118c3-150">Después de compilar ambos proyectos, se ejecuta esta única prueba.</span><span class="sxs-lookup"><span data-stu-id="118c3-150">After building both projects, it runs this single test.</span></span> <span data-ttu-id="118c3-151">Pasa.</span><span class="sxs-lookup"><span data-stu-id="118c3-151">It passes.</span></span>

## <a name="adding-more-features"></a><span data-ttu-id="118c3-152">Agregar más características</span><span class="sxs-lookup"><span data-stu-id="118c3-152">Adding more features</span></span>

<span data-ttu-id="118c3-153">Ahora que la prueba se ha superado, es el momento de escribir más.</span><span class="sxs-lookup"><span data-stu-id="118c3-153">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="118c3-154">Hay algunos otros casos simples para números primos: 0, -1.</span><span class="sxs-lookup"><span data-stu-id="118c3-154">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="118c3-155">Puede agregar esos casos como nuevas pruebas con el atributo `<Test>`, pero enseguida este proceso se hace tedioso.</span><span class="sxs-lookup"><span data-stu-id="118c3-155">You could add those cases as new tests with the `<Test>` attribute, but that quickly becomes tedious.</span></span> <span data-ttu-id="118c3-156">Hay otros atributos de xUnit que le permiten escribir un conjunto de pruebas similares.</span><span class="sxs-lookup"><span data-stu-id="118c3-156">There are other xUnit attributes that enable you to write a suite of similar tests.</span></span>  <span data-ttu-id="118c3-157">Un atributo `<TestCase>` representa un conjunto de pruebas que ejecutan el mismo código, pero tienen diferentes argumentos de entrada.</span><span class="sxs-lookup"><span data-stu-id="118c3-157">A `<TestCase>` attribute represents a suite of tests that execute the same code but have different input arguments.</span></span> <span data-ttu-id="118c3-158">Puede usar el atributo `<TestCase>` para especificar valores para esas entradas.</span><span class="sxs-lookup"><span data-stu-id="118c3-158">You can use the `<TestCase>` attribute to specify values for those inputs.</span></span>

<span data-ttu-id="118c3-159">En lugar de crear pruebas, aplique estos dos atributos para crear un conjunto de pruebas que pruebe algunos valores inferiores a 2, que es el número primo más bajo:</span><span class="sxs-lookup"><span data-stu-id="118c3-159">Instead of creating new tests, apply these two attributes to create a series of tests that test several values less than two, which is the lowest prime number:</span></span>

[!code-vb[Sample_TestCode](../../../samples/core/getting-started/unit-testing-vb-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.vb?name=Sample_TestCode)]

<span data-ttu-id="118c3-160">Ejecute `dotnet test`, y dos de estas pruebas no se superarán.</span><span class="sxs-lookup"><span data-stu-id="118c3-160">Run `dotnet test`, and two of these tests fail.</span></span> <span data-ttu-id="118c3-161">Para superar todas las pruebas, cambie la cláusula `if` al principio del método:</span><span class="sxs-lookup"><span data-stu-id="118c3-161">To make all of the tests pass, change the `if` clause at the beginning of the method:</span></span>

```vb
if candidate < 2
```

<span data-ttu-id="118c3-162">Puede continuar recorriendo en iteración agregando más pruebas, más teorías y más código en la biblioteca principal.</span><span class="sxs-lookup"><span data-stu-id="118c3-162">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="118c3-163">Ya tiene la [versión terminada de las pruebas](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-vb-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.vb) y la [implementación completa de la biblioteca](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-vb-nunit/PrimeService/PrimeService.vb).</span><span class="sxs-lookup"><span data-stu-id="118c3-163">You have the [finished version of the tests](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-vb-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.vb) and the [complete implementation of the library](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-vb-nunit/PrimeService/PrimeService.vb).</span></span>

<span data-ttu-id="118c3-164">Ha creado una biblioteca pequeña y un conjunto de pruebas unitarias para esa biblioteca.</span><span class="sxs-lookup"><span data-stu-id="118c3-164">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="118c3-165">Ha estructurado la solución, por lo que agregar pruebas y paquetes nuevos es parte del flujo de trabajo normal.</span><span class="sxs-lookup"><span data-stu-id="118c3-165">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="118c3-166">Ha centrado la mayor parte del tiempo y del esfuerzo en resolver los objetivos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="118c3-166">You've concentrated most of your time and effort on solving the goals of the application.</span></span>
