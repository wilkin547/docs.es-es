---
title: Organización y prueba de proyectos con la CLI de .NET
description: En este tutorial se explica cómo organizar y probar proyectos .NET desde la línea de comandos.
author: cartermp
ms.date: 09/10/2018
ms.openlocfilehash: c668cff48a2418cc1bc34aef78ea26c863d9de6a
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104872683"
---
# <a name="organizing-and-testing-projects-with-the-net-cli"></a><span data-ttu-id="8cda1-103">Organización y prueba de proyectos con la CLI de .NET</span><span class="sxs-lookup"><span data-stu-id="8cda1-103">Organizing and testing projects with the .NET CLI</span></span>

<span data-ttu-id="8cda1-104">En este tutorial es una continuación de lo establecido en [Tutorial: Creación de una aplicación de consola con .NET en Visual Studio Code](with-visual-studio-code.md), por lo que le llevará más allá de la creación de una aplicación de consola simple para desarrollar aplicaciones avanzadas y bien organizadas.</span><span class="sxs-lookup"><span data-stu-id="8cda1-104">This tutorial follows [Tutorial: Create a console application with .NET using Visual Studio Code](with-visual-studio-code.md), taking you beyond the creation of a simple console app to develop advanced and well-organized applications.</span></span> <span data-ttu-id="8cda1-105">Después de mostrarle cómo usar carpetas para organizar su código, este tutorial le muestra cómo ampliar una aplicación de consola con el marco de pruebas de [xUnit](https://xunit.net/).</span><span class="sxs-lookup"><span data-stu-id="8cda1-105">After showing you how to use folders to organize your code, this tutorial shows you how to extend a console application with the [xUnit](https://xunit.net/) testing framework.</span></span>

## <a name="using-folders-to-organize-code"></a><span data-ttu-id="8cda1-106">Uso de carpetas para organizar el código</span><span class="sxs-lookup"><span data-stu-id="8cda1-106">Using folders to organize code</span></span>

<span data-ttu-id="8cda1-107">Si quiere introducir nuevos tipos en una aplicación de consola, puede hacerlo agregando archivos que contienen los tipos en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8cda1-107">If you want to introduce new types into a console app, you can do so by adding files containing the types to the app.</span></span> <span data-ttu-id="8cda1-108">Por ejemplo, si agrega archivos que contienen tipos `AccountInformation` y `MonthlyReportRecords` en su proyecto, la estructura del archivo del proyecto es plana y fácil desplazarse por él:</span><span class="sxs-lookup"><span data-stu-id="8cda1-108">For example if you add files containing `AccountInformation` and `MonthlyReportRecords` types to your project, the project file structure is flat and easy to navigate:</span></span>

```
/MyProject
|__AccountInformation.cs
|__MonthlyReportRecords.cs
|__MyProject.csproj
|__Program.cs
```

<span data-ttu-id="8cda1-109">En cambio, esto solo funciona bien cuando el tamaño del proyecto es relativamente pequeño.</span><span class="sxs-lookup"><span data-stu-id="8cda1-109">However, this only works well when the size of your project is relatively small.</span></span> <span data-ttu-id="8cda1-110">¿Puede imaginar qué pasará si agrega 20 tipos al proyecto?</span><span class="sxs-lookup"><span data-stu-id="8cda1-110">Can you imagine what will happen if you add 20 types to the project?</span></span> <span data-ttu-id="8cda1-111">Definitivamente no será fácil desplazarse por el proyecto ni mantenerlo con tantos archivos depositados en el directorio raíz del proyecto.</span><span class="sxs-lookup"><span data-stu-id="8cda1-111">The project definitely wouldn't be easy to navigate and maintain with that many files littering the project's root directory.</span></span>

<span data-ttu-id="8cda1-112">Para organizar el proyecto, cree una carpeta nueva y denomínela *Models* para contener los archivos de tipo.</span><span class="sxs-lookup"><span data-stu-id="8cda1-112">To organize the project, create a new folder and name it *Models* to hold the type files.</span></span> <span data-ttu-id="8cda1-113">Coloque los archivos de tipo en la carpeta *Models*:</span><span class="sxs-lookup"><span data-stu-id="8cda1-113">Place the type files into the *Models* folder:</span></span>

```
/MyProject
|__/Models
   |__AccountInformation.cs
   |__MonthlyReportRecords.cs
|__MyProject.csproj
|__Program.cs
```

<span data-ttu-id="8cda1-114">Es fácil desplazarse por los proyectos que agrupan archivos en carpetas de manera lógica, así como mantenerlos.</span><span class="sxs-lookup"><span data-stu-id="8cda1-114">Projects that logically group files into folders are easy to navigate and maintain.</span></span> <span data-ttu-id="8cda1-115">En la sección siguiente, creará un ejemplo más complejo con carpetas y pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="8cda1-115">In the next section, you create a more complex sample with folders and unit testing.</span></span>

## <a name="organizing-and-testing-using-the-newtypes-pets-sample"></a><span data-ttu-id="8cda1-116">Organizar y probar con el ejemplo de NewTypes Pets</span><span class="sxs-lookup"><span data-stu-id="8cda1-116">Organizing and testing using the NewTypes Pets Sample</span></span>

### <a name="prerequisites"></a><span data-ttu-id="8cda1-117">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="8cda1-117">Prerequisites</span></span>

* <span data-ttu-id="8cda1-118">[SDK de .NET 5.0](https://dotnet.microsoft.com/download) o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="8cda1-118">[.NET 5.0 SDK](https://dotnet.microsoft.com/download) or a later version.</span></span>

### <a name="building-the-sample"></a><span data-ttu-id="8cda1-119">Compilar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="8cda1-119">Building the sample</span></span>

<span data-ttu-id="8cda1-120">Para los pasos siguientes, puede seguir con el [ejemplo de NewTypes Pets](https://github.com/dotnet/samples/tree/main/core/console-apps/NewTypesMsBuild) o crear sus propios archivos y carpetas.</span><span class="sxs-lookup"><span data-stu-id="8cda1-120">For the following steps, you can either follow along using the [NewTypes Pets Sample](https://github.com/dotnet/samples/tree/main/core/console-apps/NewTypesMsBuild) or create your own files and folders.</span></span> <span data-ttu-id="8cda1-121">Los tipos se organizan de manera lógica en una estructura de carpetas que permite la adición de más tipos posteriormente, y las pruebas también se colocan de manera lógica en carpetas que permiten la adición de más pruebas después.</span><span class="sxs-lookup"><span data-stu-id="8cda1-121">The types are logically organized into a folder structure that permits the addition of more types later, and tests are also logically placed in folders permitting the addition of more tests later.</span></span>

<span data-ttu-id="8cda1-122">El ejemplo contiene dos tipos, `Dog` y `Cat`, y tiene implementada una interfaz común, `IPet`.</span><span class="sxs-lookup"><span data-stu-id="8cda1-122">The sample contains two types, `Dog` and `Cat`, and has them implement a common interface, `IPet`.</span></span> <span data-ttu-id="8cda1-123">Para el proyecto `NewTypes`, su objetivo es organizar los tipos relacionados con las mascotas en una carpeta *Pets*.</span><span class="sxs-lookup"><span data-stu-id="8cda1-123">For the `NewTypes` project, your goal is to organize the pet-related types into a *Pets* folder.</span></span> <span data-ttu-id="8cda1-124">Si se agrega después otro conjunto de tipos, *WildAnimals* por ejemplo, se colocan en la carpeta *NewTypes* junto a la carpeta *Pets*.</span><span class="sxs-lookup"><span data-stu-id="8cda1-124">If another set of types is added later, *WildAnimals* for example, they're placed in the *NewTypes* folder alongside the *Pets* folder.</span></span> <span data-ttu-id="8cda1-125">La carpeta *WildAnimals* puede contener tipos de animales que no son mascotas, como los tipos `Squirrel` y `Rabbit`.</span><span class="sxs-lookup"><span data-stu-id="8cda1-125">The *WildAnimals* folder may contain types for animals that aren't pets, such as `Squirrel` and `Rabbit` types.</span></span> <span data-ttu-id="8cda1-126">De la manera en que se agregan los tipos, el proyecto sigue estando bien organizado.</span><span class="sxs-lookup"><span data-stu-id="8cda1-126">In this way as types are added, the project remains well organized.</span></span>

<span data-ttu-id="8cda1-127">Cree la siguiente estructura de carpetas con el contenido del archivo indicado:</span><span class="sxs-lookup"><span data-stu-id="8cda1-127">Create the following folder structure with file content indicated:</span></span>

```
/NewTypes
|__/src
   |__/NewTypes
      |__/Pets
         |__Dog.cs
         |__Cat.cs
         |__IPet.cs
      |__Program.cs
      |__NewTypes.csproj
```

<span data-ttu-id="8cda1-128">*IPet.cs*:</span><span class="sxs-lookup"><span data-stu-id="8cda1-128">*IPet.cs*:</span></span>

[!code-csharp[IPet interface](../../../samples/snippets/core/tutorials/testing-with-cli/csharp/src/NewTypes/Pets/IPet.cs)]

<span data-ttu-id="8cda1-129">*Dog.cs*:</span><span class="sxs-lookup"><span data-stu-id="8cda1-129">*Dog.cs*:</span></span>

[!code-csharp[Dog class](../../../samples/snippets/core/tutorials/testing-with-cli/csharp/src/NewTypes/Pets/Dog.cs)]

<span data-ttu-id="8cda1-130">*Cat.cs*:</span><span class="sxs-lookup"><span data-stu-id="8cda1-130">*Cat.cs*:</span></span>

[!code-csharp[Cat class](../../../samples/snippets/core/tutorials/testing-with-cli/csharp/src/NewTypes/Pets/Cat.cs)]

<span data-ttu-id="8cda1-131">*Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="8cda1-131">*Program.cs*:</span></span>

[!code-csharp[Main](../../../samples/snippets/core/tutorials/testing-with-cli/csharp/src/NewTypes/Program.cs)]

<span data-ttu-id="8cda1-132">*NewTypes.csproj*:</span><span class="sxs-lookup"><span data-stu-id="8cda1-132">*NewTypes.csproj*:</span></span>

[!code-xml[NewTypes csproj](../../../samples/snippets/core/tutorials/testing-with-cli/csharp/src/NewTypes/NewTypes.csproj)]

<span data-ttu-id="8cda1-133">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="8cda1-133">Execute the following command:</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="8cda1-134">Obtenga el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="8cda1-134">Obtain the following output:</span></span>

```console
Woof!
Meow!
```

<span data-ttu-id="8cda1-135">Ejercicio opcional: puede agregar un nuevo tipo de mascota, como `Bird`, si amplía este proyecto.</span><span class="sxs-lookup"><span data-stu-id="8cda1-135">Optional exercise: You can add a new pet type, such as a `Bird`, by extending this project.</span></span> <span data-ttu-id="8cda1-136">Haga que el método `TalkToOwner` de las aves proporcione `Tweet!` al propietario.</span><span class="sxs-lookup"><span data-stu-id="8cda1-136">Make the bird's `TalkToOwner` method give a `Tweet!` to the owner.</span></span> <span data-ttu-id="8cda1-137">Ejecute la aplicación de nuevo.</span><span class="sxs-lookup"><span data-stu-id="8cda1-137">Run the app again.</span></span> <span data-ttu-id="8cda1-138">El resultado incluirá `Tweet!`.</span><span class="sxs-lookup"><span data-stu-id="8cda1-138">The output will include `Tweet!`</span></span>

### <a name="testing-the-sample"></a><span data-ttu-id="8cda1-139">Probar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="8cda1-139">Testing the sample</span></span>

<span data-ttu-id="8cda1-140">El proyecto `NewTypes` está en su lugar y lo ha organizado manteniendo los tipos relacionados con las mascotas en una carpeta.</span><span class="sxs-lookup"><span data-stu-id="8cda1-140">The `NewTypes` project is in place, and you've organized it by keeping the pets-related types in a folder.</span></span> <span data-ttu-id="8cda1-141">Después, cree su proyecto de prueba y comience a escribir pruebas con el marco de pruebas de [xUnit](https://xunit.net/).</span><span class="sxs-lookup"><span data-stu-id="8cda1-141">Next, create your test project and start writing tests with the [xUnit](https://xunit.net/) test framework.</span></span> <span data-ttu-id="8cda1-142">Las pruebas unitarias le permiten comprobar automáticamente el comportamiento de sus tipos de mascota para confirmar que están funcionando correctamente.</span><span class="sxs-lookup"><span data-stu-id="8cda1-142">Unit testing allows you to automatically check the behavior of your pet types to confirm that they're operating properly.</span></span>

<span data-ttu-id="8cda1-143">Vuelva a la carpeta *src* y cree una carpeta *test* con una carpeta *NewTypesTests* en su interior.</span><span class="sxs-lookup"><span data-stu-id="8cda1-143">Navigate back to the *src* folder and create a *test* folder with a *NewTypesTests* folder within it.</span></span> <span data-ttu-id="8cda1-144">En un símbolo del sistema desde la carpeta *NewTypesTests*, ejecute `dotnet new xunit`.</span><span class="sxs-lookup"><span data-stu-id="8cda1-144">At a command prompt from the *NewTypesTests* folder, execute `dotnet new xunit`.</span></span> <span data-ttu-id="8cda1-145">Esto genera dos archivos: *NewTypesTests.csproj* y *UnitTest1.cs*.</span><span class="sxs-lookup"><span data-stu-id="8cda1-145">This produces two files: *NewTypesTests.csproj* and *UnitTest1.cs*.</span></span>

<span data-ttu-id="8cda1-146">El proyecto de prueba no puede probar actualmente los tipos de `NewTypes` y necesita una referencia del proyecto para el proyecto `NewTypes`.</span><span class="sxs-lookup"><span data-stu-id="8cda1-146">The test project cannot currently test the types in `NewTypes` and requires a project reference to the `NewTypes` project.</span></span> <span data-ttu-id="8cda1-147">Para agregar una referencia del proyecto, use el comando [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="8cda1-147">To add a project reference, use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```dotnetcli
dotnet add reference ../../src/NewTypes/NewTypes.csproj
```

<span data-ttu-id="8cda1-148">O bien, también tiene la opción de agregar manualmente la referencia del proyecto si agrega un nodo `<ItemGroup>` al archivo *NewTypesTests.csproj*:</span><span class="sxs-lookup"><span data-stu-id="8cda1-148">Or, you also have the option of manually adding the project reference by adding an `<ItemGroup>` node to the *NewTypesTests.csproj* file:</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="../../src/NewTypes/NewTypes.csproj" />
</ItemGroup>
```

<span data-ttu-id="8cda1-149">*NewTypesTests.csproj*:</span><span class="sxs-lookup"><span data-stu-id="8cda1-149">*NewTypesTests.csproj*:</span></span>

[!code-xml[NewTypesTests csproj](../../../samples/snippets/core/tutorials/testing-with-cli/csharp/test/NewTypesTests/NewTypesTests.csproj)]

<span data-ttu-id="8cda1-150">El archivo *NewTypesTests.csproj* contiene lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8cda1-150">The *NewTypesTests.csproj* file contains the following:</span></span>

* <span data-ttu-id="8cda1-151">Referencia del paquete a `Microsoft.NET.Test.Sdk`, la infraestructura de pruebas de .NET</span><span class="sxs-lookup"><span data-stu-id="8cda1-151">Package reference to `Microsoft.NET.Test.Sdk`, the .NET testing infrastructure</span></span>
* <span data-ttu-id="8cda1-152">Referencia del paquete a `xunit`, el marco de pruebas de xUnit</span><span class="sxs-lookup"><span data-stu-id="8cda1-152">Package reference to `xunit`, the xUnit testing framework</span></span>
* <span data-ttu-id="8cda1-153">Referencia del paquete a `xunit.runner.visualstudio`, el ejecutor de pruebas</span><span class="sxs-lookup"><span data-stu-id="8cda1-153">Package reference to `xunit.runner.visualstudio`, the test runner</span></span>
* <span data-ttu-id="8cda1-154">Referencia del proyecto a `NewTypes`, el código que se va a probar</span><span class="sxs-lookup"><span data-stu-id="8cda1-154">Project reference to `NewTypes`, the code to test</span></span>

<span data-ttu-id="8cda1-155">Cambie el nombre de *UnitTest1.cs* a *PetTests.cs* y reemplace el código en el archivo por lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8cda1-155">Change the name of *UnitTest1.cs* to *PetTests.cs* and replace the code in the file with the following:</span></span>

```csharp
using System;
using Xunit;
using Pets;

public class PetTests
{
    [Fact]
    public void DogTalkToOwnerReturnsWoof()
    {
        string expected = "Woof!";
        string actual = new Dog().TalkToOwner();

        Assert.NotEqual(expected, actual);
    }

    [Fact]
    public void CatTalkToOwnerReturnsMeow()
    {
        string expected = "Meow!";
        string actual = new Cat().TalkToOwner();

        Assert.NotEqual(expected, actual);
    }
}
```

<span data-ttu-id="8cda1-156">Ejercicio opcional: si ha agregado un tipo `Bird` anteriormente que da como resultado `Tweet!` para el propietario, agregue un método de prueba al archivo *PetTests.cs*, `BirdTalkToOwnerReturnsTweet`, para comprobar que el método `TalkToOwner` funciona correctamente para el tipo `Bird`.</span><span class="sxs-lookup"><span data-stu-id="8cda1-156">Optional exercise: If you added a `Bird` type earlier that yields a `Tweet!` to the owner, add a test method to the *PetTests.cs* file, `BirdTalkToOwnerReturnsTweet`, to check that the `TalkToOwner` method works correctly for the `Bird` type.</span></span>

> [!NOTE]
> <span data-ttu-id="8cda1-157">Aunque espere que los valores `expected` y `actual` sean iguales, la aserción inicial con la comprobación `Assert.NotEqual` especifica que estos valores *no son iguales*.</span><span class="sxs-lookup"><span data-stu-id="8cda1-157">Although you expect that the `expected` and `actual` values are equal, an initial assertion with the `Assert.NotEqual` check specifies that these values are *not equal*.</span></span> <span data-ttu-id="8cda1-158">Cree siempre inicialmente una prueba que resulte fallida para comprobar la lógica de la prueba.</span><span class="sxs-lookup"><span data-stu-id="8cda1-158">Always initially create a test to fail in order to check the logic of the test.</span></span> <span data-ttu-id="8cda1-159">Después de confirmar que la prueba falla, ajuste la aserción para permitir que se supere la prueba.</span><span class="sxs-lookup"><span data-stu-id="8cda1-159">After you confirm that the test fails, adjust the assertion to allow the test to pass.</span></span>

<span data-ttu-id="8cda1-160">A continuación se muestra la estructura del proyecto completo:</span><span class="sxs-lookup"><span data-stu-id="8cda1-160">The following shows the complete project structure:</span></span>

```
/NewTypes
|__/src
   |__/NewTypes
      |__/Pets
         |__Dog.cs
         |__Cat.cs
         |__IPet.cs
      |__Program.cs
      |__NewTypes.csproj
|__/test
   |__NewTypesTests
      |__PetTests.cs
      |__NewTypesTests.csproj
```

<span data-ttu-id="8cda1-161">Comience en el directorio *test/NewTypesTests*.</span><span class="sxs-lookup"><span data-stu-id="8cda1-161">Start in the *test/NewTypesTests* directory.</span></span> <span data-ttu-id="8cda1-162">Ejecute las pruebas con el comando [`dotnet test`](../tools/dotnet-test.md).</span><span class="sxs-lookup"><span data-stu-id="8cda1-162">Run the tests with the [`dotnet test`](../tools/dotnet-test.md) command.</span></span> <span data-ttu-id="8cda1-163">Este comando inicia el ejecutor de pruebas especificado en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="8cda1-163">This command starts the test runner specified in the project file.</span></span>

<span data-ttu-id="8cda1-164">Como se esperaba, se producen errores en las pruebas y la consola muestra el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="8cda1-164">As expected, testing fails, and the console displays the following output:</span></span>

```output
Test run for C:\Source\dotnet\docs\samples\snippets\core\tutorials\testing-with-cli\csharp\test\NewTypesTests\bin\Debug\net5.0\NewTypesTests.dll (.NETCoreApp,Version=v5.0)
Microsoft (R) Test Execution Command Line Tool Version 16.8.1
Copyright (c) Microsoft Corporation.  All rights reserved.

Starting test execution, please wait...
A total of 1 test files matched the specified pattern.
[xUnit.net 00:00:00.50]     PetTests.DogTalkToOwnerReturnsWoof [FAIL]
  Failed PetTests.DogTalkToOwnerReturnsWoof [6 ms]
  Error Message:
   Assert.NotEqual() Failure
Expected: Not "Woof!"
Actual:   "Woof!"
  Stack Trace:
     at PetTests.DogTalkToOwnerReturnsWoof() in C:\Source\dotnet\docs\samples\snippets\core\tutorials\testing-with-cli\csharp\test\NewTypesTests\PetTests.cs:line 13

Failed!  - Failed:     1, Passed:     1, Skipped:     0, Total:     2, Duration: 8 ms - NewTypesTests.dll (net5.0)
```

<span data-ttu-id="8cda1-165">Cambie las aserciones de sus pruebas de `Assert.NotEqual` a `Assert.Equal`:</span><span class="sxs-lookup"><span data-stu-id="8cda1-165">Change the assertions of your tests from `Assert.NotEqual` to `Assert.Equal`:</span></span>

[!code-csharp[PetTests class](../../../samples/snippets/core/tutorials/testing-with-cli/csharp/test/NewTypesTests/PetTests.cs)]

<span data-ttu-id="8cda1-166">Vuelva a ejecutar las pruebas con el comando `dotnet test` y obtenga el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="8cda1-166">Re-run the tests with the `dotnet test` command and obtain the following output:</span></span>

```output
Test run for C:\Source\dotnet\docs\samples\snippets\core\tutorials\testing-with-cli\csharp\test\NewTypesTests\bin\Debug\net5.0\NewTypesTests.dll (.NETCoreApp,Version=v5.0)
Microsoft (R) Test Execution Command Line Tool Version 16.8.1
Copyright (c) Microsoft Corporation.  All rights reserved.

Starting test execution, please wait...
A total of 1 test files matched the specified pattern.

Passed!  - Failed:     0, Passed:     2, Skipped:     0, Total:     2, Duration: 2 ms - NewTypesTests.dll (net5.0)
```

<span data-ttu-id="8cda1-167">Se pasan las pruebas.</span><span class="sxs-lookup"><span data-stu-id="8cda1-167">Testing passes.</span></span> <span data-ttu-id="8cda1-168">Los métodos de los tipos de mascota devuelven los valores correctos al dirigirse al propietario.</span><span class="sxs-lookup"><span data-stu-id="8cda1-168">The pet types' methods return the correct values when talking to the owner.</span></span>

<span data-ttu-id="8cda1-169">Ha obtenido información sobre las técnicas para organizar y probar proyectos con xUnit.</span><span class="sxs-lookup"><span data-stu-id="8cda1-169">You've learned techniques for organizing and testing projects using xUnit.</span></span> <span data-ttu-id="8cda1-170">Continúe con estas técnicas aplicándolas en sus propios proyectos.</span><span class="sxs-lookup"><span data-stu-id="8cda1-170">Go forward with these techniques applying them in your own projects.</span></span> <span data-ttu-id="8cda1-171">*Disfrute programando.*</span><span class="sxs-lookup"><span data-stu-id="8cda1-171">*Happy coding!*</span></span>
