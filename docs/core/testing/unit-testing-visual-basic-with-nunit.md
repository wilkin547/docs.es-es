---
title: Prueba unitaria de Visual Basic en .NET Core con dotnet test y NUnit
description: 'Aprenda los conceptos de pruebas unitarias en .NET Core: cree una solución de Visual Basic de ejemplo paso a paso mediante NUnit.'
author: rprouse
ms.date: 10/04/2018
ms.openlocfilehash: 8f05d25a0add76f5c552f5b9ac1eb310c3d6407a
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715409"
---
# <a name="unit-testing-visual-basic-net-core-libraries-using-dotnet-test-and-nunit"></a><span data-ttu-id="45d23-103">Bibliotecas de .NET Core de prueba unitaria de Visual Basic con pruebas de dotnet y NUnit</span><span class="sxs-lookup"><span data-stu-id="45d23-103">Unit testing Visual Basic .NET Core libraries using dotnet test and NUnit</span></span>

<span data-ttu-id="45d23-104">Este tutorial le guía por una experiencia interactiva de creación de una solución de ejemplo paso a paso para aprender los conceptos de pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="45d23-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="45d23-105">Si prefiere seguir el tutorial con una solución precompilada, [vea o descargue el código de ejemplo](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-vb-nunit/) antes de comenzar.</span><span class="sxs-lookup"><span data-stu-id="45d23-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-vb-nunit/) before you begin.</span></span> <span data-ttu-id="45d23-106">Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="45d23-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

[!INCLUDE [testing an ASP.NET Core project from .NET Core](../../../includes/core-testing-note-aspnet.md)]

## <a name="prerequisites"></a><span data-ttu-id="45d23-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="45d23-107">Prerequisites</span></span>

- <span data-ttu-id="45d23-108">[SDK de .NET Core 2.1](https://dotnet.microsoft.com/download) o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="45d23-108">[.NET Core 2.1 SDK](https://dotnet.microsoft.com/download) or later versions.</span></span>
- <span data-ttu-id="45d23-109">Un editor de texto o un editor de código de su elección.</span><span class="sxs-lookup"><span data-stu-id="45d23-109">A text editor or code editor of your choice.</span></span>

## <a name="creating-the-source-project"></a><span data-ttu-id="45d23-110">Crear el proyecto de origen</span><span class="sxs-lookup"><span data-stu-id="45d23-110">Creating the source project</span></span>

<span data-ttu-id="45d23-111">Abra una ventana del Shell.</span><span class="sxs-lookup"><span data-stu-id="45d23-111">Open a shell window.</span></span> <span data-ttu-id="45d23-112">Cree un directorio llamado *unit-testing-vb-nunit* que contenga la solución.</span><span class="sxs-lookup"><span data-stu-id="45d23-112">Create a directory called *unit-testing-vb-nunit* to hold the solution.</span></span> <span data-ttu-id="45d23-113">En este directorio nuevo, ejecute el comando siguiente para crear un archivo de solución nuevo para la biblioteca de clases y el proyecto de prueba:</span><span class="sxs-lookup"><span data-stu-id="45d23-113">Inside this new directory, run the following command to create a new solution file for the class library and the test project:</span></span>

```dotnetcli
dotnet new sln
```

<span data-ttu-id="45d23-114">A continuación, cree un directorio *PrimeService*.</span><span class="sxs-lookup"><span data-stu-id="45d23-114">Next, create a *PrimeService* directory.</span></span> <span data-ttu-id="45d23-115">En el esquema siguiente se muestra la estructura de archivos hasta el momento:</span><span class="sxs-lookup"><span data-stu-id="45d23-115">The following outline shows the file structure so far:</span></span>

```console
/unit-testing-vb-nunit
    unit-testing-vb-nunit.sln
    /PrimeService
```

<span data-ttu-id="45d23-116">Convierta *PrimeService* en el directorio actual y ejecute el siguiente comando para crear el proyecto de origen:</span><span class="sxs-lookup"><span data-stu-id="45d23-116">Make *PrimeService* the current directory and run the following command to create the source project:</span></span>

```dotnetcli
dotnet new classlib -lang VB
```

<span data-ttu-id="45d23-117">Cambie el nombre de *Class1.VB* a *PrimeService.VB*.</span><span class="sxs-lookup"><span data-stu-id="45d23-117">Rename *Class1.VB* to *PrimeService.VB*.</span></span> <span data-ttu-id="45d23-118">Creará una implementación de errores de la clase `PrimeService`:</span><span class="sxs-lookup"><span data-stu-id="45d23-118">You create a failing implementation of the `PrimeService` class:</span></span>

```vb
Namespace Prime.Services
    Public Class PrimeService
        Public Function IsPrime(candidate As Integer) As Boolean
            Throw New NotImplementedException("Please create a test first.")
        End Function
    End Class
End Namespace
```

<span data-ttu-id="45d23-119">Cambien nuevamente el directorio al directorio *unit-testing-vb-using-mstest*.</span><span class="sxs-lookup"><span data-stu-id="45d23-119">Change the directory back to the *unit-testing-vb-using-mstest* directory.</span></span> <span data-ttu-id="45d23-120">Ejecute el siguiente comando para agregar el proyecto de biblioteca de clases a la solución:</span><span class="sxs-lookup"><span data-stu-id="45d23-120">Run the following command to add the class library project to the solution:</span></span>

```dotnetcli
dotnet sln add .\PrimeService\PrimeService.vbproj
```

## <a name="creating-the-test-project"></a><span data-ttu-id="45d23-121">Crear el proyecto de prueba</span><span class="sxs-lookup"><span data-stu-id="45d23-121">Creating the test project</span></span>

<span data-ttu-id="45d23-122">A continuación, cree el directorio *PrimeService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="45d23-122">Next, create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="45d23-123">En el esquema siguiente se muestra la estructura de directorios:</span><span class="sxs-lookup"><span data-stu-id="45d23-123">The following outline shows the directory structure:</span></span>

```console
/unit-testing-vb-nunit
    unit-testing-vb-nunit.sln
    /PrimeService
        Source Files
        PrimeService.vbproj
    /PrimeService.Tests
```

<span data-ttu-id="45d23-124">Convierta el directorio *PrimeService.Tests* en el directorio actual y cree un proyecto nuevo con el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="45d23-124">Make the *PrimeService.Tests* directory the current directory and create a new project using the following command:</span></span>

```dotnetcli
dotnet new nunit -lang VB
```

<span data-ttu-id="45d23-125">El comando [dotnet new](../tools/dotnet-new.md) crea un proyecto de prueba que usa NUnit como la biblioteca de pruebas.</span><span class="sxs-lookup"><span data-stu-id="45d23-125">The [dotnet new](../tools/dotnet-new.md) command creates a test project that uses NUnit as the test library.</span></span> <span data-ttu-id="45d23-126">La plantilla generada ha configurado el ejecutor de pruebas en el archivo *PrimeServiceTests.vbproj*:</span><span class="sxs-lookup"><span data-stu-id="45d23-126">The generated template configures the test runner in the *PrimeServiceTests.vbproj* file:</span></span>

[!code-xml[Packages](~/samples/core/getting-started/unit-testing-vb-nunit/PrimeService.Tests/PrimeService.Tests.vbproj#Packages)]

<span data-ttu-id="45d23-127">El proyecto de prueba requiere otros paquetes para crear y ejecutar pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="45d23-127">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="45d23-128">En el paso anterior, `dotnet new` agrega NUnit y el adaptador de prueba NUnit.</span><span class="sxs-lookup"><span data-stu-id="45d23-128">`dotnet new` in the previous step added NUnit and the NUnit test adapter.</span></span> <span data-ttu-id="45d23-129">Ahora, agregue la biblioteca de clases `PrimeService` como otra dependencia al proyecto.</span><span class="sxs-lookup"><span data-stu-id="45d23-129">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="45d23-130">Use el comando [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="45d23-130">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```dotnetcli
dotnet add reference ../PrimeService/PrimeService.vbproj
```

<span data-ttu-id="45d23-131">Puede ver todo el archivo en el [repositorio de muestras](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-nunit/PrimeService.Tests/PrimeService.Tests.vbproj) en GitHub.</span><span class="sxs-lookup"><span data-stu-id="45d23-131">You can see the entire file in the [samples repository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-nunit/PrimeService.Tests/PrimeService.Tests.vbproj) on GitHub.</span></span>

<span data-ttu-id="45d23-132">Tiene el diseño de solución final siguiente:</span><span class="sxs-lookup"><span data-stu-id="45d23-132">You have the following final solution layout:</span></span>

```console
/unit-testing-vb-nunit
    unit-testing-vb-nunit.sln
    /PrimeService
        Source Files
        PrimeService.vbproj
    /PrimeService.Tests
        Test Source Files
        PrimeService.Tests.vbproj
```

<span data-ttu-id="45d23-133">Ejecute el comando siguiente en el directorio *unit-testing-vb-nunit*:</span><span class="sxs-lookup"><span data-stu-id="45d23-133">Execute the following command in the *unit-testing-vb-nunit* directory:</span></span>

```dotnetcli
dotnet sln add .\PrimeService.Tests\PrimeService.Tests.vbproj
```

## <a name="creating-the-first-test"></a><span data-ttu-id="45d23-134">Crear la primera prueba</span><span class="sxs-lookup"><span data-stu-id="45d23-134">Creating the first test</span></span>

<span data-ttu-id="45d23-135">Escribirá una prueba de errores, la aprobará y, luego, repetirá el proceso.</span><span class="sxs-lookup"><span data-stu-id="45d23-135">You write one failing test, make it pass, then repeat the process.</span></span> <span data-ttu-id="45d23-136">En el directorio *PrimeService.Tests*, cambie el nombre del archivo *UnitTest1.vb* por *PrimeService_IsPrimeShould.VB* y reemplace todo su contenido por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="45d23-136">In the *PrimeService.Tests* directory, rename the *UnitTest1.vb* file to *PrimeService_IsPrimeShould.VB* and replace its entire contents with the following code:</span></span>

```vb
Imports NUnit.Framework

Namespace PrimeService.Tests
    <TestFixture>
    Public Class PrimeService_IsPrimeShould
        Private _primeService As Prime.Services.PrimeService = New Prime.Services.PrimeService()

        <Test>
        Sub IsPrime_InputIs1_ReturnFalse()
            Dim result As Boolean = _primeService.IsPrime(1)

            Assert.False(result, "1 should not be prime")
        End Sub

    End Class
End Namespace
```

<span data-ttu-id="45d23-137">El atributo `<TestFixture>` indica una clase que contiene pruebas.</span><span class="sxs-lookup"><span data-stu-id="45d23-137">The `<TestFixture>` attribute indicates a class that contains tests.</span></span> <span data-ttu-id="45d23-138">El atributo `<Test>` indica un método que el ejecutor de pruebas ejecuta.</span><span class="sxs-lookup"><span data-stu-id="45d23-138">The `<Test>` attribute denotes a method that is run by the test runner.</span></span> <span data-ttu-id="45d23-139">En *unit-testing-vb-nunit*, ejecute [`dotnet test`](../tools/dotnet-test.md) para compilar las pruebas y la biblioteca de clases y luego ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="45d23-139">From the *unit-testing-vb-nunit*, execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="45d23-140">El ejecutor de pruebas de NUnit tiene el punto de entrada del programa para ejecutar las pruebas desde la consola.</span><span class="sxs-lookup"><span data-stu-id="45d23-140">The NUnit test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="45d23-141">`dotnet test` inicia el ejecutor de pruebas con el proyecto de prueba unitaria que creó.</span><span class="sxs-lookup"><span data-stu-id="45d23-141">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="45d23-142">La prueba produce un error.</span><span class="sxs-lookup"><span data-stu-id="45d23-142">Your test fails.</span></span> <span data-ttu-id="45d23-143">Todavía no ha creado la implementación.</span><span class="sxs-lookup"><span data-stu-id="45d23-143">You haven't created the implementation yet.</span></span> <span data-ttu-id="45d23-144">Cree esta prueba que se supera escribiendo el código más simple en la clase `PrimeService` que funciona:</span><span class="sxs-lookup"><span data-stu-id="45d23-144">Make this test pass by writing the simplest code in the `PrimeService` class that works:</span></span>

```vb
Public Function IsPrime(candidate As Integer) As Boolean
    If candidate = 1 Then
        Return False
    End If
    Throw New NotImplementedException("Please create a test first.")
End Function
```

<span data-ttu-id="45d23-145">En el directorio *unit-testing-vb-nunit*, vuelva a ejecutar `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="45d23-145">In the *unit-testing-vb-nunit* directory, run `dotnet test` again.</span></span> <span data-ttu-id="45d23-146">El comando `dotnet test` ejecuta una compilación del proyecto `PrimeService` y luego del proyecto `PrimeService.Tests`.</span><span class="sxs-lookup"><span data-stu-id="45d23-146">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="45d23-147">Después de compilar ambos proyectos, se ejecuta esta única prueba.</span><span class="sxs-lookup"><span data-stu-id="45d23-147">After building both projects, it runs this single test.</span></span> <span data-ttu-id="45d23-148">Pasa.</span><span class="sxs-lookup"><span data-stu-id="45d23-148">It passes.</span></span>

## <a name="adding-more-features"></a><span data-ttu-id="45d23-149">Agregar más características</span><span class="sxs-lookup"><span data-stu-id="45d23-149">Adding more features</span></span>

<span data-ttu-id="45d23-150">Ahora que la prueba se ha superado, es el momento de escribir más.</span><span class="sxs-lookup"><span data-stu-id="45d23-150">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="45d23-151">Hay otros casos simples para números primos: 0, -1.</span><span class="sxs-lookup"><span data-stu-id="45d23-151">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="45d23-152">Puede agregar esos casos como nuevas pruebas con el atributo `<Test>`, pero enseguida este proceso se hace tedioso.</span><span class="sxs-lookup"><span data-stu-id="45d23-152">You could add those cases as new tests with the `<Test>` attribute, but that quickly becomes tedious.</span></span> <span data-ttu-id="45d23-153">Hay otros atributos de xUnit que le permiten escribir un conjunto de pruebas similares.</span><span class="sxs-lookup"><span data-stu-id="45d23-153">There are other xUnit attributes that enable you to write a suite of similar tests.</span></span>  <span data-ttu-id="45d23-154">Un atributo `<TestCase>` representa un conjunto de pruebas que ejecutan el mismo código, pero tienen diferentes argumentos de entrada.</span><span class="sxs-lookup"><span data-stu-id="45d23-154">A `<TestCase>` attribute represents a suite of tests that execute the same code but have different input arguments.</span></span> <span data-ttu-id="45d23-155">Puede usar el atributo `<TestCase>` para especificar valores para esas entradas.</span><span class="sxs-lookup"><span data-stu-id="45d23-155">You can use the `<TestCase>` attribute to specify values for those inputs.</span></span>

<span data-ttu-id="45d23-156">En lugar de crear pruebas, aplique estos dos atributos para crear un conjunto de pruebas que pruebe algunos valores inferiores a 2, que es el número primo más bajo:</span><span class="sxs-lookup"><span data-stu-id="45d23-156">Instead of creating new tests, apply these two attributes to create a series of tests that test several values less than two, which is the lowest prime number:</span></span>

[!code-vb[Sample_TestCode](../../../samples/core/getting-started/unit-testing-vb-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.vb?name=Sample_TestCode)]

<span data-ttu-id="45d23-157">Ejecute `dotnet test`, y dos de estas pruebas no se superarán.</span><span class="sxs-lookup"><span data-stu-id="45d23-157">Run `dotnet test`, and two of these tests fail.</span></span> <span data-ttu-id="45d23-158">Para superar todas las pruebas, cambie la cláusula `if` al principio del método `Main` en el archivo *PrimeService.cs*:</span><span class="sxs-lookup"><span data-stu-id="45d23-158">To make all of the tests pass, change the `if` clause at the beginning of the `Main` method in the *PrimeServices.cs* file:</span></span>

```vb
if candidate < 2
```

<span data-ttu-id="45d23-159">Puede continuar recorriendo en iteración agregando más pruebas, más teorías y más código en la biblioteca principal.</span><span class="sxs-lookup"><span data-stu-id="45d23-159">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="45d23-160">Ya tiene la [versión terminada de las pruebas](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.vb) y la [implementación completa de la biblioteca](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-nunit/PrimeService/PrimeService.vb).</span><span class="sxs-lookup"><span data-stu-id="45d23-160">You have the [finished version of the tests](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.vb) and the [complete implementation of the library](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-nunit/PrimeService/PrimeService.vb).</span></span>

<span data-ttu-id="45d23-161">Ha creado una biblioteca pequeña y un conjunto de pruebas unitarias para esa biblioteca.</span><span class="sxs-lookup"><span data-stu-id="45d23-161">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="45d23-162">Ha estructurado la solución, por lo que agregar pruebas y paquetes nuevos es parte del flujo de trabajo normal.</span><span class="sxs-lookup"><span data-stu-id="45d23-162">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="45d23-163">Ha centrado la mayor parte del tiempo y del esfuerzo en resolver los objetivos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="45d23-163">You've concentrated most of your time and effort on solving the goals of the application.</span></span>
