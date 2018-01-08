---
title: "Organización y prueba de proyectos con la línea de comandos de .NET Core"
description: "En este tutorial se explica cómo organizar y probar proyectos .NET Core desde la línea de comandos."
keywords: .NET, .NET Core, unit testing, .NET Core CLI, xUnit
author: cartermp
ms.author: mairaw
ms.date: 05/16/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 52ff1be3-d92e-4477-9c84-8c1771e87ab5
ms.workload: dotnetcore
ms.openlocfilehash: 4b8728a175d67cc532866d4de41d412e459f0291
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="organizing-and-testing-projects-with-the-net-core-command-line"></a><span data-ttu-id="c2cdf-104">Organización y prueba de proyectos con la línea de comandos de .NET Core</span><span class="sxs-lookup"><span data-stu-id="c2cdf-104">Organizing and testing projects with the .NET Core command line</span></span>

<span data-ttu-id="c2cdf-105">Este tutorial sigue al tutorial [Introducción a .NET Core en Windows, Linux y macOS con la línea de comandos](using-with-xplat-cli.md) dirigiéndole más allá de la creación de una aplicación de consola sencilla para desarrollar aplicaciones más avanzadas y bien organizadas.</span><span class="sxs-lookup"><span data-stu-id="c2cdf-105">This tutorial follows [Getting started with .NET Core on Windows/Linux/macOS using the command line](using-with-xplat-cli.md), taking you beyond the creation of a simple console app to develop advanced and well-organized applications.</span></span> <span data-ttu-id="c2cdf-106">Después de mostrarle cómo usar carpetas para organizar su código, este tutorial le muestra cómo ampliar una aplicación de consola con el marco de pruebas de [xUnit](https://xunit.github.io/).</span><span class="sxs-lookup"><span data-stu-id="c2cdf-106">After showing you how to use folders to organize your code, this tutorial shows you how to extend a console application with the [xUnit](https://xunit.github.io/) testing framework.</span></span>

## <a name="using-folders-to-organize-code"></a><span data-ttu-id="c2cdf-107">Uso de carpetas para organizar el código</span><span class="sxs-lookup"><span data-stu-id="c2cdf-107">Using folders to organize code</span></span>

<span data-ttu-id="c2cdf-108">Si quiere introducir nuevos tipos en una aplicación de consola, puede hacerlo agregando archivos que contienen los tipos en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c2cdf-108">If you want to introduce new types into a console app, you can do so by adding files containing the types to the app.</span></span> <span data-ttu-id="c2cdf-109">Por ejemplo, si agrega archivos que contienen tipos `AccountInformation` y `MonthlyReportRecords` en su proyecto, la estructura del archivo del proyecto es plana y fácil desplazarse por él:</span><span class="sxs-lookup"><span data-stu-id="c2cdf-109">For example if you add files containing `AccountInformation` and `MonthlyReportRecords` types to your project, the project file structure is flat and easy to navigate:</span></span>

```
/MyProject
|__AccountInformation.cs
|__MonthlyReportRecords.cs
|__MyProject.csproj
|__Program.cs
```

<span data-ttu-id="c2cdf-110">En cambio, esto solo funciona bien cuando el tamaño del proyecto es relativamente pequeño.</span><span class="sxs-lookup"><span data-stu-id="c2cdf-110">However, this only works well when the size of your project is relatively small.</span></span> <span data-ttu-id="c2cdf-111">¿Puede imaginar qué pasará si agrega 20 tipos al proyecto?</span><span class="sxs-lookup"><span data-stu-id="c2cdf-111">Can you imagine what will happen if you add 20 types to the project?</span></span> <span data-ttu-id="c2cdf-112">Definitivamente no será fácil desplazarse por el proyecto ni mantenerlo con tantos archivos depositados en el directorio raíz del proyecto.</span><span class="sxs-lookup"><span data-stu-id="c2cdf-112">The project definitely wouldn't be easy to navigate and maintain with that many files littering the project's root directory.</span></span>

<span data-ttu-id="c2cdf-113">Para organizar el proyecto, cree una carpeta nueva y denomínela *Models* para contener los archivos de tipo.</span><span class="sxs-lookup"><span data-stu-id="c2cdf-113">To organize the project, create a new folder and name it *Models* to hold the type files.</span></span> <span data-ttu-id="c2cdf-114">Coloque los archivos de tipo en la carpeta *Models*:</span><span class="sxs-lookup"><span data-stu-id="c2cdf-114">Place the type files into the *Models* folder:</span></span>

```
/MyProject
|__/Models
   |__AccountInformation.cs
   |__MonthlyReportRecords.cs
|__MyProject.csproj
|__Program.cs
```

<span data-ttu-id="c2cdf-115">Es fácil desplazarse por los proyectos que agrupan archivos en carpetas de manera lógica, así como mantenerlos.</span><span class="sxs-lookup"><span data-stu-id="c2cdf-115">Projects that logically group files into folders are easy to navigate and maintain.</span></span> <span data-ttu-id="c2cdf-116">En la sección siguiente, creará un ejemplo más complejo con carpetas y pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="c2cdf-116">In the next section, you create a more complex sample with folders and unit testing.</span></span>

## <a name="organizing-and-testing-using-the-newtypes-pets-sample"></a><span data-ttu-id="c2cdf-117">Organizar y probar con el ejemplo de NewTypes Pets</span><span class="sxs-lookup"><span data-stu-id="c2cdf-117">Organizing and testing using the NewTypes Pets Sample</span></span>

### <a name="building-the-sample"></a><span data-ttu-id="c2cdf-118">Compilar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="c2cdf-118">Building the sample</span></span>

<span data-ttu-id="c2cdf-119">Para los pasos siguientes, puede seguir con el [ejemplo de NewTypes Pets](https://github.com/dotnet/docs/tree/master/samples/core/console-apps/NewTypesMsBuild) o crear sus propios archivos y carpetas.</span><span class="sxs-lookup"><span data-stu-id="c2cdf-119">For the following steps, you can either follow along using the [NewTypes Pets Sample](https://github.com/dotnet/docs/tree/master/samples/core/console-apps/NewTypesMsBuild) or create your own files and folders.</span></span> <span data-ttu-id="c2cdf-120">Los tipos se organizan de manera lógica en una estructura de carpetas que permite la adición de más tipos posteriormente, y las pruebas también se colocan de manera lógica en carpetas que permiten la adición de más pruebas después.</span><span class="sxs-lookup"><span data-stu-id="c2cdf-120">The types are logically organized into a folder structure that permits the addition of more types later, and tests are also logically placed in folders permitting the addition of more tests later.</span></span>

<span data-ttu-id="c2cdf-121">El ejemplo contiene dos tipos, `Dog` y `Cat`, y tiene implementada una interfaz común, `IPet`.</span><span class="sxs-lookup"><span data-stu-id="c2cdf-121">The sample contains two types, `Dog` and `Cat`, and has them implement a common interface, `IPet`.</span></span> <span data-ttu-id="c2cdf-122">Para el proyecto `NewTypes`, su objetivo es organizar los tipos relacionados con las mascotas en una carpeta *Pets*.</span><span class="sxs-lookup"><span data-stu-id="c2cdf-122">For the `NewTypes` project, your goal is to organize the pet-related types into a *Pets* folder.</span></span> <span data-ttu-id="c2cdf-123">Si se agrega después otro conjunto de tipos, *WildAnimals* por ejemplo, se colocan en la carpeta *NewTypes* junto a la carpeta *Pets*.</span><span class="sxs-lookup"><span data-stu-id="c2cdf-123">If another set of types is added later, *WildAnimals* for example, they're placed in the *NewTypes* folder alongside the *Pets* folder.</span></span> <span data-ttu-id="c2cdf-124">La carpeta *WildAnimals* puede contener tipos de animales que no son mascotas, como los tipos `Squirrel` y `Rabbit`.</span><span class="sxs-lookup"><span data-stu-id="c2cdf-124">The *WildAnimals* folder may contain types for animals that aren't pets, such as `Squirrel` and `Rabbit` types.</span></span> <span data-ttu-id="c2cdf-125">De la manera en que se agregan los tipos, el proyecto sigue estando bien organizado.</span><span class="sxs-lookup"><span data-stu-id="c2cdf-125">In this way as types are added, the project remains well organized.</span></span> 

<span data-ttu-id="c2cdf-126">Cree la siguiente estructura de carpetas con el contenido del archivo indicado:</span><span class="sxs-lookup"><span data-stu-id="c2cdf-126">Create the following folder structure with file content indicated:</span></span>

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

<span data-ttu-id="c2cdf-127">*IPet.cs*:</span><span class="sxs-lookup"><span data-stu-id="c2cdf-127">*IPet.cs*:</span></span>

[!code-csharp[IPet interface](../../../samples/core/console-apps/NewTypesMsBuild/src/NewTypes/Pets/IPet.cs)]

<span data-ttu-id="c2cdf-128">*Dog.cs*:</span><span class="sxs-lookup"><span data-stu-id="c2cdf-128">*Dog.cs*:</span></span>

[!code-csharp[Dog class](../../../samples/core/console-apps/NewTypesMsBuild/src/NewTypes/Pets/Dog.cs)]

<span data-ttu-id="c2cdf-129">*Cat.cs*:</span><span class="sxs-lookup"><span data-stu-id="c2cdf-129">*Cat.cs*:</span></span>

[!code-csharp[Cat class](../../../samples/core/console-apps/NewTypesMsBuild/src/NewTypes/Pets/Cat.cs)]

<span data-ttu-id="c2cdf-130">*Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="c2cdf-130">*Program.cs*:</span></span>

[!code-csharp[Main](../../../samples/core/console-apps/NewTypesMsBuild/src/NewTypes/Program.cs)]

<span data-ttu-id="c2cdf-131">*NewTypes.csproj*:</span><span class="sxs-lookup"><span data-stu-id="c2cdf-131">*NewTypes.csproj*:</span></span>

[!code-xml[NewTypes csproj](../../../samples/core/console-apps/NewTypesMsBuild/src/NewTypes/NewTypes.csproj)]

<span data-ttu-id="c2cdf-132">Ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="c2cdf-132">Execute the following commands:</span></span>

```console
dotnet run
```

<span data-ttu-id="c2cdf-133">Obtenga el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="c2cdf-133">Obtain the following output:</span></span>

```console
Woof!
Meow!
```

<span data-ttu-id="c2cdf-134">Ejercicio opcional: puede agregar un nuevo tipo de mascota, como `Bird`, ampliando este proyecto.</span><span class="sxs-lookup"><span data-stu-id="c2cdf-134">Optional exercise: You can add a new pet type, such as a `Bird`, by extending this project.</span></span> <span data-ttu-id="c2cdf-135">Haga que el método `TalkToOwner` de las aves proporcione `Tweet!` al propietario.</span><span class="sxs-lookup"><span data-stu-id="c2cdf-135">Make the bird's `TalkToOwner` method give a `Tweet!` to the owner.</span></span> <span data-ttu-id="c2cdf-136">Ejecute la aplicación de nuevo.</span><span class="sxs-lookup"><span data-stu-id="c2cdf-136">Run the app again.</span></span> <span data-ttu-id="c2cdf-137">El resultado incluirá `Tweet!`.</span><span class="sxs-lookup"><span data-stu-id="c2cdf-137">The output will include `Tweet!`</span></span>

### <a name="testing-the-sample"></a><span data-ttu-id="c2cdf-138">Probar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="c2cdf-138">Testing the sample</span></span>

<span data-ttu-id="c2cdf-139">El proyecto `NewTypes` está en su lugar y lo ha organizado manteniendo los tipos relacionados con las mascotas en una carpeta.</span><span class="sxs-lookup"><span data-stu-id="c2cdf-139">The `NewTypes` project is in place, and you've organized it by keeping the pets-related types in a folder.</span></span> <span data-ttu-id="c2cdf-140">Después, cree su proyecto de prueba y comience a escribir pruebas con el marco de pruebas de [xUnit](https://xunit.github.io/).</span><span class="sxs-lookup"><span data-stu-id="c2cdf-140">Next, create your test project and start writing tests with the [xUnit](https://xunit.github.io/) test framework.</span></span> <span data-ttu-id="c2cdf-141">Las pruebas unitarias le permiten comprobar automáticamente el comportamiento de sus tipos de mascota para confirmar que están funcionando correctamente.</span><span class="sxs-lookup"><span data-stu-id="c2cdf-141">Unit testing allows you to automatically check the bevahior of your pet types to confirm that they're operating properly.</span></span>

<span data-ttu-id="c2cdf-142">Cree una carpeta *test* con una carpeta *NewTypesTests* en su interior.</span><span class="sxs-lookup"><span data-stu-id="c2cdf-142">Create a *test* folder with a *NewTypesTests* folder within it.</span></span> <span data-ttu-id="c2cdf-143">En un símbolo del sistema desde la carpeta *NewTypesTests*, ejecute `dotnet new xunit`.</span><span class="sxs-lookup"><span data-stu-id="c2cdf-143">At a command prompt from the *NewTypesTests* folder, execute `dotnet new xunit`.</span></span> <span data-ttu-id="c2cdf-144">Esto genera dos archivos: *NewTypesTests.csproj* y *UnitTest1.cs*.</span><span class="sxs-lookup"><span data-stu-id="c2cdf-144">This produces two files: *NewTypesTests.csproj* and *UnitTest1.cs*.</span></span>

<span data-ttu-id="c2cdf-145">El proyecto de prueba no puede probar actualmente los tipos de `NewTypes` y necesita una referencia del proyecto para el proyecto `NewTypes`.</span><span class="sxs-lookup"><span data-stu-id="c2cdf-145">The test project cannot currently test the types in `NewTypes` and requires a project reference to the `NewTypes` project.</span></span> <span data-ttu-id="c2cdf-146">Para agregar una referencia del proyecto, use el comando [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="c2cdf-146">To add a project reference, use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```
dotnet add reference ../../src/NewTypes/NewTypes.csproj
```

<span data-ttu-id="c2cdf-147">También tiene la opción de agregar manualmente la referencia del proyecto agregando un nodo `<ItemGroup>` al archivo *NewTypesTests.csproj*:</span><span class="sxs-lookup"><span data-stu-id="c2cdf-147">You also have the option of manually adding the project reference by adding an `<ItemGroup>` node to the *NewTypesTests.csproj* file:</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="../../src/NewTypes/NewTypes.csproj" />
</ItemGroup>
```

<span data-ttu-id="c2cdf-148">*NewTypesTests.csproj*:</span><span class="sxs-lookup"><span data-stu-id="c2cdf-148">*NewTypesTests.csproj*:</span></span>

[!code-xml[NewTypesTests csproj](../../../samples/core/console-apps/NewTypesMsBuild/test/NewTypesTests/NewTypesTests.csproj)]

<span data-ttu-id="c2cdf-149">El archivo *NewTypesTests.csproj* contiene lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c2cdf-149">The *NewTypesTests.csproj* file contains the following:</span></span>

* <span data-ttu-id="c2cdf-150">Referencia del paquete a `Microsoft.NET.Test.Sdk`, la infraestructura de pruebas de .NET</span><span class="sxs-lookup"><span data-stu-id="c2cdf-150">Package reference to `Microsoft.NET.Test.Sdk`, the .NET testing infrastructure</span></span>
* <span data-ttu-id="c2cdf-151">Referencia del paquete a `xunit`, el marco de pruebas de xUnit</span><span class="sxs-lookup"><span data-stu-id="c2cdf-151">Package reference to `xunit`, the xUnit testing framework</span></span>
* <span data-ttu-id="c2cdf-152">Referencia del paquete a `xunit.runner.visualstudio`, el ejecutor de pruebas</span><span class="sxs-lookup"><span data-stu-id="c2cdf-152">Package reference to `xunit.runner.visualstudio`, the test runner</span></span>
* <span data-ttu-id="c2cdf-153">Referencia del proyecto a `NewTypes`, el código que se va a probar</span><span class="sxs-lookup"><span data-stu-id="c2cdf-153">Project reference to `NewTypes`, the code to test</span></span>

<span data-ttu-id="c2cdf-154">Cambie el nombre de *UnitTest1.cs* a *PetTests.cs* y reemplace el código en el archivo por lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c2cdf-154">Change the name of *UnitTest1.cs* to *PetTests.cs* and replace the code in the file with the following:</span></span>

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

<span data-ttu-id="c2cdf-155">Ejercicio opcional: si ha agregado un tipo `Bird` anteriormente que da como resultado `Tweet!` para el propietario, agregue un método de prueba al archivo *PetTests.cs*, `BirdTalkToOwnerReturnsTweet`, para comprobar que el método `TalkToOwner` funciona correctamente para el tipo `Bird`.</span><span class="sxs-lookup"><span data-stu-id="c2cdf-155">Optional exercise: If you added a `Bird` type earlier that yields a `Tweet!` to the owner, add a test method to the *PetTests.cs* file, `BirdTalkToOwnerReturnsTweet`, to check that the `TalkToOwner` method works correctly for the `Bird` type.</span></span>

> [!NOTE]
> <span data-ttu-id="c2cdf-156">Aunque espere que los valores `expected` y `actual` sean iguales, las aserciones iniciales con las comprobaciones `Assert.NotEqual` especifican que *no son iguales*.</span><span class="sxs-lookup"><span data-stu-id="c2cdf-156">Although you expect that the `expected` and `actual` values are equal, the initial assertions with the `Assert.NotEqual` checks specify that they are *not equal*.</span></span> <span data-ttu-id="c2cdf-157">Cree siempre inicialmente sus pruebas para que produzcan un error una vez para comprobar la lógica de las pruebas.</span><span class="sxs-lookup"><span data-stu-id="c2cdf-157">Always initially create your tests to fail once in order to check the logic of the tests.</span></span> <span data-ttu-id="c2cdf-158">Este es un paso importante en la metodología de diseño controlado por pruebas (TDD).</span><span class="sxs-lookup"><span data-stu-id="c2cdf-158">This is an important step in test-driven design (TDD) methodology.</span></span> <span data-ttu-id="c2cdf-159">Después de que confirme que las pruebas producen errores, ajuste las aserciones para permitir que las puedan pasar.</span><span class="sxs-lookup"><span data-stu-id="c2cdf-159">After you confirm the tests fail, you adjust the assertions to allow them to pass.</span></span>

<span data-ttu-id="c2cdf-160">A continuación se muestra la estructura del proyecto completo:</span><span class="sxs-lookup"><span data-stu-id="c2cdf-160">The following shows the complete project structure:</span></span>

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

<span data-ttu-id="c2cdf-161">Comience en el directorio *test/NewTypesTests*.</span><span class="sxs-lookup"><span data-stu-id="c2cdf-161">Start in the *test/NewTypesTests* directory.</span></span> <span data-ttu-id="c2cdf-162">Restaure el proyecto de prueba con el comando [`dotnet restore`](../tools/dotnet-restore.md).</span><span class="sxs-lookup"><span data-stu-id="c2cdf-162">Restore the test project with the [`dotnet restore`](../tools/dotnet-restore.md) command.</span></span> <span data-ttu-id="c2cdf-163">Ejecute las pruebas con el comando [`dotnet test`](../tools/dotnet-test.md).</span><span class="sxs-lookup"><span data-stu-id="c2cdf-163">Run the tests with the [`dotnet test`](../tools/dotnet-test.md) command.</span></span> <span data-ttu-id="c2cdf-164">Este comando inicia el ejecutor de pruebas especificado en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="c2cdf-164">This command starts the test runner specified in the project file.</span></span>

 [!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

 
<span data-ttu-id="c2cdf-165">Como se esperaba, se producen errores en las pruebas y la consola muestra el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="c2cdf-165">As expected, testing fails, and the console displays the following output:</span></span>
 
```
Test run for C:\NewTypesMsBuild\test\NewTypesTests\bin\Debug\netcoreapp1.1\NewTypesTests.dll(.NETCoreApp,Version=v1.1)
Microsoft (R) Test Execution Command Line Tool Version 15.0.0.0
Copyright (c) Microsoft Corporation.  All rights reserved.

Starting test execution, please wait...
[xUnit.net 00:00:00.7271827]   Discovering: NewTypesTests
[xUnit.net 00:00:00.8258687]   Discovered:  NewTypesTests
[xUnit.net 00:00:00.8663545]   Starting:    NewTypesTests
[xUnit.net 00:00:01.0109236]     PetTests.CatTalkToOwnerReturnsMeow [FAIL]
[xUnit.net 00:00:01.0119107]       Assert.NotEqual() Failure
[xUnit.net 00:00:01.0120278]       Expected: Not "Meow!"
[xUnit.net 00:00:01.0120968]       Actual:   "Meow!"
[xUnit.net 00:00:01.0130500]       Stack Trace:
[xUnit.net 00:00:01.0141240]         C:\NewTypesMsBuild\test\NewTypesTests\PetTests.cs(22,0): at PetTests.CatTalkToOwnerReturnsMeow()
[xUnit.net 00:00:01.0272364]     PetTests.DogTalkToOwnerReturnsWoof [FAIL]
[xUnit.net 00:00:01.0273649]       Assert.NotEqual() Failure
[xUnit.net 00:00:01.0274166]       Expected: Not "Woof!"
[xUnit.net 00:00:01.0274690]       Actual:   "Woof!"
[xUnit.net 00:00:01.0275264]       Stack Trace:
[xUnit.net 00:00:01.0275960]         C:\NewTypesMsBuild\test\NewTypesTests\PetTests.cs(13,0): at PetTests.DogTalkToOwnerReturnsWoof()
[xUnit.net 00:00:01.0294509]   Finished:    NewTypesTests
Failed   PetTests.CatTalkToOwnerReturnsMeow
Error Message:
 Assert.NotEqual() Failure
Expected: Not "Meow!"
Actual:   "Meow!"
Stack Trace:
   at PetTests.CatTalkToOwnerReturnsMeow() in C:\NewTypesMsBuild\test\NewTypesTests\PetTests.cs:line 22
Failed   PetTests.DogTalkToOwnerReturnsWoof
Error Message:
 Assert.NotEqual() Failure
Expected: Not "Woof!"
Actual:   "Woof!"
Stack Trace:
   at PetTests.DogTalkToOwnerReturnsWoof() in C:\NewTypesMsBuild\test\NewTypesTests\PetTests.cs:line 13

Total tests: 2. Passed: 0. Failed: 2. Skipped: 0.
Test Run Failed.
Test execution time: 2.1371 Seconds
```

<span data-ttu-id="c2cdf-166">Cambie las aserciones de sus pruebas de `Assert.NotEqual` a `Assert.Equal`:</span><span class="sxs-lookup"><span data-stu-id="c2cdf-166">Change the assertions of your tests from `Assert.NotEqual` to `Assert.Equal`:</span></span>

[!code-csharp[PetTests class](../../../samples/core/console-apps/NewTypesMsBuild/test/NewTypesTests/PetTests.cs)]

<span data-ttu-id="c2cdf-167">Vuelva a ejecutar las pruebas con el comando `dotnet test` y obtenga el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="c2cdf-167">Re-run the tests with the `dotnet test` command and obtain the following output:</span></span>

```
Microsoft (R) Test Execution Command Line Tool Version 15.0.0.0
Copyright (c) Microsoft Corporation.  All rights reserved.

Starting test execution, please wait...
[xUnit.net 00:00:01.3882374]   Discovering: NewTypesTests
[xUnit.net 00:00:01.4767970]   Discovered:  NewTypesTests
[xUnit.net 00:00:01.5157667]   Starting:    NewTypesTests
[xUnit.net 00:00:01.6408870]   Finished:    NewTypesTests

Total tests: 2. Passed: 2. Failed: 0. Skipped: 0.
Test Run Successful.
Test execution time: 1.6634 Seconds
```

<span data-ttu-id="c2cdf-168">Se pasan las pruebas.</span><span class="sxs-lookup"><span data-stu-id="c2cdf-168">Testing passes.</span></span> <span data-ttu-id="c2cdf-169">Los métodos de los tipos de mascota devuelven los valores correctos al dirigirse al propietario.</span><span class="sxs-lookup"><span data-stu-id="c2cdf-169">The pet types' methods return the correct values when talking to the owner.</span></span>

<span data-ttu-id="c2cdf-170">Ha obtenido información sobre las técnicas para organizar y probar proyectos con xUnit.</span><span class="sxs-lookup"><span data-stu-id="c2cdf-170">You've learned techniques for organizing and testing projects using xUnit.</span></span> <span data-ttu-id="c2cdf-171">Continúe con estas técnicas aplicándolas en sus propios proyectos.</span><span class="sxs-lookup"><span data-stu-id="c2cdf-171">Go forward with these techniques applying them in your own projects.</span></span> <span data-ttu-id="c2cdf-172">*Disfrute programando.*</span><span class="sxs-lookup"><span data-stu-id="c2cdf-172">*Happy coding!*</span></span>

