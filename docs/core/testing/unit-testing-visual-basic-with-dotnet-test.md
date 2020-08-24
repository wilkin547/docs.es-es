---
title: Prueba unitaria de Visual Basic en .NET Core con dotnet test y xUnit
description: 'Aprenda los conceptos de pruebas unitarias en .NET Core: cree paso a paso una solución de Visual Basic de ejemplo mediante pruebas de dotnet y xUnit.'
author: billwagner
ms.author: wiwagn
ms.date: 05/18/2020
ms.openlocfilehash: d384bf08f0b6031a519a8430c876eafc05d03a2e
ms.sourcegitcommit: c4a15c6c4ecbb8a46ad4e67d9b3ab9b8b031d849
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/20/2020
ms.locfileid: "88656428"
---
# <a name="unit-testing-visual-basic-net-core-libraries-using-dotnet-test-and-xunit"></a><span data-ttu-id="2aebb-103">Bibliotecas de .NET Core de prueba unitaria de Visual Basic con pruebas de dotnet y xUnit</span><span class="sxs-lookup"><span data-stu-id="2aebb-103">Unit testing Visual Basic .NET Core libraries using dotnet test and xUnit</span></span>

<span data-ttu-id="2aebb-104">En este tutorial se muestra cómo compilar una solución que contiene un proyecto de prueba unitaria y un proyecto de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="2aebb-104">This tutorial shows how to build a solution containing a unit test project and library project.</span></span> <span data-ttu-id="2aebb-105">Para seguir el tutorial con una solución precompilada, [vea o descargue el código de ejemplo](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-using-dotnet-test/).</span><span class="sxs-lookup"><span data-stu-id="2aebb-105">To follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-using-dotnet-test/).</span></span> <span data-ttu-id="2aebb-106">Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../../samples-and-tutorials/index.md#view-and-download-samples).</span><span class="sxs-lookup"><span data-stu-id="2aebb-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#view-and-download-samples).</span></span>

## <a name="create-the-solution"></a><span data-ttu-id="2aebb-107">Creación de la solución</span><span class="sxs-lookup"><span data-stu-id="2aebb-107">Create the solution</span></span>

<span data-ttu-id="2aebb-108">En esta sección, se crea una solución que contiene los proyectos de prueba y origen.</span><span class="sxs-lookup"><span data-stu-id="2aebb-108">In this section, a solution is created that contains the source and test projects.</span></span> <span data-ttu-id="2aebb-109">La solución completada tiene la siguiente estructura de directorios:</span><span class="sxs-lookup"><span data-stu-id="2aebb-109">The completed solution has the following directory structure:</span></span>

```
/unit-testing-using-dotnet-test
    unit-testing-using-dotnet-test.sln
    /PrimeService
        PrimeService.vb
        PrimeService.vbproj
    /PrimeService.Tests
        PrimeService_IsPrimeShould.vb
        PrimeServiceTests.vbproj
```

<span data-ttu-id="2aebb-110">Las instrucciones siguientes proporcionan los pasos para crear la solución de prueba.</span><span class="sxs-lookup"><span data-stu-id="2aebb-110">The following instructions provide the steps to create the test solution.</span></span> <span data-ttu-id="2aebb-111">Consulte la sección sobre [comandos para crear la solución de prueba](#create-test-cmd) a fin de obtener instrucciones para crear la solución de prueba en un paso.</span><span class="sxs-lookup"><span data-stu-id="2aebb-111">See [Commands to create test solution](#create-test-cmd) for instructions to create the test solution in one step.</span></span>

* <span data-ttu-id="2aebb-112">Abra una ventana del Shell.</span><span class="sxs-lookup"><span data-stu-id="2aebb-112">Open a shell window.</span></span>
* <span data-ttu-id="2aebb-113">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="2aebb-113">Run the following command:</span></span>

  ```dotnetcli
  dotnet new sln -o unit-testing-using-dotnet-test
  ```

  <span data-ttu-id="2aebb-114">El comando [`dotnet new sln`](../tools/dotnet-new.md) crea una nueva solución en el directorio *unit-testing-using-dotnet-test*.</span><span class="sxs-lookup"><span data-stu-id="2aebb-114">The [`dotnet new sln`](../tools/dotnet-new.md) command creates a new solution in the *unit-testing-using-dotnet-test* directory.</span></span>
* <span data-ttu-id="2aebb-115">Cambie el directorio a la carpeta *unit-testing-using-dotnet-test*.</span><span class="sxs-lookup"><span data-stu-id="2aebb-115">Change directory to the *unit-testing-using-dotnet-test* folder.</span></span>
* <span data-ttu-id="2aebb-116">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="2aebb-116">Run the following command:</span></span>

  ```dotnetcli
  dotnet new classlib -o PrimeService --lang VB
  ```

   <span data-ttu-id="2aebb-117">El comando [`dotnet new classlib`](../tools/dotnet-new.md) crea un nuevo proyecto de biblioteca de clases en la carpeta *PrimeService*.</span><span class="sxs-lookup"><span data-stu-id="2aebb-117">The [`dotnet new classlib`](../tools/dotnet-new.md) command creates a new class library project  in the *PrimeService* folder.</span></span> <span data-ttu-id="2aebb-118">La nueva biblioteca de clases contendrá el código que se va a probar.</span><span class="sxs-lookup"><span data-stu-id="2aebb-118">The new class library will contain the code to be tested.</span></span>
* <span data-ttu-id="2aebb-119">Cambie el nombre de *Class1.vb* a *PrimeService.vb*.</span><span class="sxs-lookup"><span data-stu-id="2aebb-119">Rename *Class1.vb* to *PrimeService.vb*.</span></span>
* <span data-ttu-id="2aebb-120">Reemplace el código de *PrimeService.vb* por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="2aebb-120">Replace the code in *PrimeService.vb* with the following code:</span></span>
  
  ```vb
  Imports System
  
  Namespace Prime.Services
      Public Class PrimeService
          Public Function IsPrime(candidate As Integer) As Boolean
              Throw New NotImplementedException("Not implemented.")
          End Function
      End Class
  End Namespace
  ```

* <span data-ttu-id="2aebb-121">El código anterior:</span><span class="sxs-lookup"><span data-stu-id="2aebb-121">The preceding code:</span></span>
  * <span data-ttu-id="2aebb-122">Produce una excepción <xref:System.NotImplementedException> con un mensaje que indica que no se ha implementado.</span><span class="sxs-lookup"><span data-stu-id="2aebb-122">Throws a <xref:System.NotImplementedException> with a message indicating it's not implemented.</span></span>
  * <span data-ttu-id="2aebb-123">Se actualiza más adelante en el tutorial.</span><span class="sxs-lookup"><span data-stu-id="2aebb-123">Is updated later in the tutorial.</span></span>

<!-- preceding code shows an english bias. Message makes no sense outside english -->

* <span data-ttu-id="2aebb-124">En el directorio *unit-testing-using-dotnet-test*, ejecute el comando siguiente para agregar el proyecto de biblioteca de clases a la solución:</span><span class="sxs-lookup"><span data-stu-id="2aebb-124">In the *unit-testing-using-dotnet-test* directory, run the following command to add the class library project to the solution:</span></span>

  ```dotnetcli
  dotnet sln add ./PrimeService/PrimeService.vbproj
  ```

* <span data-ttu-id="2aebb-125">Cree el proyecto *PrimeService.Tests* ejecutando el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="2aebb-125">Create the *PrimeService.Tests* project by running the following command:</span></span>

  ```dotnetcli
  dotnet new xunit -o PrimeService.Tests
  ```

* <span data-ttu-id="2aebb-126">El comando anterior:</span><span class="sxs-lookup"><span data-stu-id="2aebb-126">The preceding command:</span></span>
  * <span data-ttu-id="2aebb-127">Crea el proyecto *PrimeService.Tests* en el directorio *PrimeService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="2aebb-127">Creates the *PrimeService.Tests* project in the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="2aebb-128">El proyecto de prueba usa [xUnit](https://xunit.net/) como biblioteca de pruebas.</span><span class="sxs-lookup"><span data-stu-id="2aebb-128">The test project uses [xUnit](https://xunit.net/) as the test library.</span></span>
  * <span data-ttu-id="2aebb-129">Configura el ejecutor de pruebas agregando los siguientes `<PackageReference />`elementos al archivo del proyecto:</span><span class="sxs-lookup"><span data-stu-id="2aebb-129">Configures the test runner by adding the following `<PackageReference />`elements to the project file:</span></span>
    * <span data-ttu-id="2aebb-130">"Microsoft.NET.Test.Sdk"</span><span class="sxs-lookup"><span data-stu-id="2aebb-130">"Microsoft.NET.Test.Sdk"</span></span>
    * <span data-ttu-id="2aebb-131">"xunit"</span><span class="sxs-lookup"><span data-stu-id="2aebb-131">"xunit"</span></span>
    * <span data-ttu-id="2aebb-132">"xunit.runner.visualstudio"</span><span class="sxs-lookup"><span data-stu-id="2aebb-132">"xunit.runner.visualstudio"</span></span>

* <span data-ttu-id="2aebb-133">Agregue el proyecto de prueba al archivo de solución ejecutando el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="2aebb-133">Add the test project to the solution file by running the following command:</span></span>

  ```dotnetcli
  dotnet sln add ./PrimeService.Tests/PrimeService.Tests.vbproj
  ```

* <span data-ttu-id="2aebb-134">Agregue la biblioteca de clases `PrimeService` como dependencia al proyecto *PrimeService.Tests*:</span><span class="sxs-lookup"><span data-stu-id="2aebb-134">Add the `PrimeService` class library as a dependency to the *PrimeService.Tests* project:</span></span>

  ```dotnetcli
  dotnet add ./PrimeService.Tests/PrimeService.Tests.vbproj reference ./PrimeService/PrimeService.vbproj  
  ```

<a name="create-test-cmd"></a>

### <a name="commands-to-create-the-solution"></a><span data-ttu-id="2aebb-135">Comandos para crear la solución</span><span class="sxs-lookup"><span data-stu-id="2aebb-135">Commands to create the solution</span></span>

<span data-ttu-id="2aebb-136">En esta sección se resumen todos los comandos de la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="2aebb-136">This section summarizes all the commands in the previous section.</span></span> <span data-ttu-id="2aebb-137">Omita esta sección si ha completado los pasos en la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="2aebb-137">Skip this section if you've completed the steps in the previous section.</span></span>

<span data-ttu-id="2aebb-138">Los siguientes comandos crean la solución de prueba en una máquina Windows.</span><span class="sxs-lookup"><span data-stu-id="2aebb-138">The following commands create the test solution on a windows machine.</span></span> <span data-ttu-id="2aebb-139">Para macOS y Unix, actualice el comando `ren` a la versión del SO de `ren` para cambiar el nombre de un archivo:</span><span class="sxs-lookup"><span data-stu-id="2aebb-139">For macOS and Unix, update the `ren` command to the OS version of `ren` to rename a file:</span></span>

```dotnetcli
dotnet new sln -o unit-testing-using-dotnet-test
cd unit-testing-using-dotnet-test
dotnet new classlib -o PrimeService
ren .\PrimeService\Class1.vb PrimeService.vb
dotnet sln add ./PrimeService/PrimeService.vbproj
dotnet new xunit -o PrimeService.Tests
dotnet add ./PrimeService.Tests/PrimeService.Tests.vbproj reference ./PrimeService/PrimeService.vbproj
dotnet sln add ./PrimeService.Tests/PrimeService.Tests.vbproj
```

<span data-ttu-id="2aebb-140">Siga las instrucciones de "Reemplace el código de *PrimeService.vb* por el código siguiente" de la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="2aebb-140">Follow the instructions for "Replace the code in *PrimeService.vb* with the following code" in the previous section.</span></span>

## <a name="create-a-test"></a><span data-ttu-id="2aebb-141">Creación de una prueba</span><span class="sxs-lookup"><span data-stu-id="2aebb-141">Create a test</span></span>

<span data-ttu-id="2aebb-142">Un enfoque popular en el desarrollo controlado por pruebas (TDD) consiste en escribir una prueba antes de implementar un código de destino.</span><span class="sxs-lookup"><span data-stu-id="2aebb-142">A popular approach in test driven development (TDD) is to write a test before implementing the target code.</span></span> <span data-ttu-id="2aebb-143">En este tutorial se usa el enfoque TDD.</span><span class="sxs-lookup"><span data-stu-id="2aebb-143">This tutorial uses the TDD approach.</span></span> <span data-ttu-id="2aebb-144">Se puede llamar al método `IsPrime`, pero sin implementar.</span><span class="sxs-lookup"><span data-stu-id="2aebb-144">The `IsPrime` method is callable, but not implemented.</span></span> <span data-ttu-id="2aebb-145">Se produce un error en una llamada de prueba a `IsPrime`.</span><span class="sxs-lookup"><span data-stu-id="2aebb-145">A test call to `IsPrime` fails.</span></span> <span data-ttu-id="2aebb-146">Con TDD, se escribe una prueba a sabiendas de que en esta se produce un error.</span><span class="sxs-lookup"><span data-stu-id="2aebb-146">With TDD, a test is written that is known to fail.</span></span> <span data-ttu-id="2aebb-147">El código de destino se actualiza para conseguir que se supere la prueba.</span><span class="sxs-lookup"><span data-stu-id="2aebb-147">The target code is updated to make the test pass.</span></span> <span data-ttu-id="2aebb-148">Siga repitiendo este enfoque, escribiendo una prueba con errores y, a continuación, actualizando el código de destino que se va a pasar.</span><span class="sxs-lookup"><span data-stu-id="2aebb-148">You keep repeating this approach, writing a failing test and then updating the target code to pass.</span></span>

<span data-ttu-id="2aebb-149">Actualice el proyecto *PrimeService.Tests*:</span><span class="sxs-lookup"><span data-stu-id="2aebb-149">Update the *PrimeService.Tests* project:</span></span>

* <span data-ttu-id="2aebb-150">Elimine *PrimeService.Tests/UnitTest1.vb*.</span><span class="sxs-lookup"><span data-stu-id="2aebb-150">Delete *PrimeService.Tests/UnitTest1.vb*.</span></span>
* <span data-ttu-id="2aebb-151">Cree un archivo *PrimeService.Tests/PrimeService_IsPrimeShould.vb*.</span><span class="sxs-lookup"><span data-stu-id="2aebb-151">Create a *PrimeService.Tests/PrimeService_IsPrimeShould.vb*  file.</span></span>
* <span data-ttu-id="2aebb-152">Reemplace el código de *PrimeService_IsPrimeShould.vb* por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="2aebb-152">Replace the code in *PrimeService_IsPrimeShould.vb* with the following code:</span></span>

```vb
Imports Xunit

Namespace PrimeService.Tests
    Public Class PrimeService_IsPrimeShould
        Private ReadOnly _primeService As Prime.Services.PrimeService

        Public Sub New()
            _primeService = New Prime.Services.PrimeService()
        End Sub


        <Fact>
        Sub IsPrime_InputIs1_ReturnFalse()
            Dim result As Boolean = _primeService.IsPrime(1)

            Assert.False(result, "1 should not be prime")
        End Sub

    End Class
End Namespace
```

<span data-ttu-id="2aebb-153">El atributo `[Fact]` declara un método de prueba que el ejecutor de pruebas ejecuta.</span><span class="sxs-lookup"><span data-stu-id="2aebb-153">The `[Fact]` attribute declares a test method that's run by the test runner.</span></span> <span data-ttu-id="2aebb-154">En la carpeta *PrimeService.Tests*, ejecute `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="2aebb-154">From the *PrimeService.Tests* folder, run `dotnet test`.</span></span> <span data-ttu-id="2aebb-155">El comando [dotnet test](../tools/dotnet-test.md) compila ambos proyectos y ejecuta las pruebas.</span><span class="sxs-lookup"><span data-stu-id="2aebb-155">The [dotnet test](../tools/dotnet-test.md) command builds both projects and runs the tests.</span></span> <span data-ttu-id="2aebb-156">El ejecutor de pruebas de xUnit tiene el punto de entrada del programa para ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="2aebb-156">The xUnit test runner contains the program entry point to run the tests.</span></span> <span data-ttu-id="2aebb-157">`dotnet test` inicia el ejecutor de pruebas con el proyecto de prueba unitaria.</span><span class="sxs-lookup"><span data-stu-id="2aebb-157">`dotnet test` starts the test runner using the unit test project.</span></span>

<span data-ttu-id="2aebb-158">Se produce un error en la prueba porque no se ha implementado `IsPrime`.</span><span class="sxs-lookup"><span data-stu-id="2aebb-158">The test fails because `IsPrime` hasn't been implemented.</span></span> <span data-ttu-id="2aebb-159">Con el enfoque TDD, solo tiene que escribir código suficiente para que se supere esta prueba.</span><span class="sxs-lookup"><span data-stu-id="2aebb-159">Using the TDD approach, write only enough code so this test passes.</span></span> <span data-ttu-id="2aebb-160">Actualice `IsPrime` con el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="2aebb-160">Update `IsPrime` with the following code:</span></span>

```vb
Public Function IsPrime(candidate As Integer) As Boolean
    If candidate = 1 Then
        Return False
    End If
    Throw New NotImplementedException("Not implemented.")
End Function
```

<span data-ttu-id="2aebb-161">Ejecute `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="2aebb-161">Run `dotnet test`.</span></span> <span data-ttu-id="2aebb-162">La prueba se supera.</span><span class="sxs-lookup"><span data-stu-id="2aebb-162">The test passes.</span></span>

### <a name="add-more-tests"></a><span data-ttu-id="2aebb-163">Incorporación de más pruebas</span><span class="sxs-lookup"><span data-stu-id="2aebb-163">Add more tests</span></span>

<span data-ttu-id="2aebb-164">Agregue pruebas de números primos para 0 y -1.</span><span class="sxs-lookup"><span data-stu-id="2aebb-164">Add prime number tests for 0 and -1.</span></span> <span data-ttu-id="2aebb-165">Podría copiar la prueba anterior y cambiar el siguiente código para usar 0 y -1:</span><span class="sxs-lookup"><span data-stu-id="2aebb-165">You could copy the preceding test and change the following code to use 0 and -1:</span></span>

```vb
Dim result As Boolean = _primeService.IsPrime(1)

Assert.False(result, "1 should not be prime")
```

<span data-ttu-id="2aebb-166">La copia de código de prueba cuando solamente es un parámetro el que cambia da lugar a la duplicación de código y al sobredimensionamiento de pruebas.</span><span class="sxs-lookup"><span data-stu-id="2aebb-166">Copying test code when only a parameter changes results in code duplication and test bloat.</span></span> <span data-ttu-id="2aebb-167">Los siguientes atributos de xUnit habilitan la escritura de un conjunto de pruebas similares:</span><span class="sxs-lookup"><span data-stu-id="2aebb-167">The following xUnit attributes enable writing a suite of similar tests:</span></span>

- <span data-ttu-id="2aebb-168">Un elemento `[Theory]` representa un conjunto de pruebas que ejecutan el mismo código, pero tienen diferentes argumentos de entrada.</span><span class="sxs-lookup"><span data-stu-id="2aebb-168">`[Theory]` represents a suite of tests that execute the same code but have different input arguments.</span></span>
- <span data-ttu-id="2aebb-169">Un atributo `[InlineData]` especifica valores para esas entradas.</span><span class="sxs-lookup"><span data-stu-id="2aebb-169">`[InlineData]` attribute specifies values for those inputs.</span></span>

<span data-ttu-id="2aebb-170">En lugar de crear pruebas nuevas, aplique los atributos de xUnit anteriores para crear una sola teoría.</span><span class="sxs-lookup"><span data-stu-id="2aebb-170">Rather than creating new tests, apply the preceding xUnit attributes to create a single theory.</span></span> <span data-ttu-id="2aebb-171">Reemplace el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="2aebb-171">Replace the following code:</span></span>

```vb
<Fact>
Sub IsPrime_InputIs1_ReturnFalse()
    Dim result As Boolean = _primeService.IsPrime(1)

    Assert.False(result, "1 should not be prime")
End Sub
```

<span data-ttu-id="2aebb-172">por el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="2aebb-172">with the following code:</span></span>

```vb
<Theory>
<InlineData(-1)>
<InlineData(0)>
<InlineData(1)>
Sub IsPrime_ValuesLessThan2_ReturnFalse(ByVal value As Integer)
    Dim result As Boolean = _primeService.IsPrime(value)

    Assert.False(result, $"{value} should not be prime")
End Sub
```

<span data-ttu-id="2aebb-173">En el código anterior, `[Theory]` y `[InlineData]` habilitan la prueba de varios valores inferiores a dos.</span><span class="sxs-lookup"><span data-stu-id="2aebb-173">In the preceding code, `[Theory]` and `[InlineData]` enable testing several values less than two.</span></span> <span data-ttu-id="2aebb-174">Dos es el número primo más pequeño.</span><span class="sxs-lookup"><span data-stu-id="2aebb-174">Two is the smallest prime number.</span></span>

<span data-ttu-id="2aebb-175">Al ejecutar `dotnet test`, se produce un error en dos de las pruebas.</span><span class="sxs-lookup"><span data-stu-id="2aebb-175">Run `dotnet test`, two of the tests fail.</span></span> <span data-ttu-id="2aebb-176">Para que se superen todas las pruebas, actualice el método `IsPrime` con el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="2aebb-176">To make all of the tests pass, update the `IsPrime` method with the following code:</span></span>

```vb
Public Function IsPrime(candidate As Integer) As Boolean
    If candidate < 2 Then
        Return False
    End If
    Throw New NotImplementedException("Not fully implemented.")
End Function
```

<span data-ttu-id="2aebb-177">Siguiendo el enfoque TDD, agregue más pruebas con errores y, a continuación, actualice el código de destino.</span><span class="sxs-lookup"><span data-stu-id="2aebb-177">Following the TDD approach, add more failing tests, then update the target code.</span></span> <span data-ttu-id="2aebb-178">Consulte la [versión terminada de las pruebas](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.vb) y la [implementación completa de la biblioteca](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-dotnet-test/PrimeService/PrimeService.vb).</span><span class="sxs-lookup"><span data-stu-id="2aebb-178">See the [finished version of the tests](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.vb) and the [complete implementation of the library](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-dotnet-test/PrimeService/PrimeService.vb).</span></span>

<span data-ttu-id="2aebb-179">El método `IsPrime` completado no es un algoritmo eficaz para probar los números primos.</span><span class="sxs-lookup"><span data-stu-id="2aebb-179">The completed `IsPrime` method is not an efficient algorithm for testing primality.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="2aebb-180">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="2aebb-180">Additional resources</span></span>

- [<span data-ttu-id="2aebb-181">Sitio oficial de xUnit.net</span><span class="sxs-lookup"><span data-stu-id="2aebb-181">xUnit.net official site</span></span>](https://xunit.net/)
- [<span data-ttu-id="2aebb-182">Probar la lógica del controlador en ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="2aebb-182">Testing controller logic in ASP.NET Core</span></span>](/aspnet/core/mvc/controllers/testing)
- [`dotnet add reference`](../tools/dotnet-add-reference.md)
