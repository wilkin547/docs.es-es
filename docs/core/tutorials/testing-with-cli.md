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
ms.openlocfilehash: 62c81bf070a435f6105c313ae95340a5504233df
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="organizing-and-testing-projects-with-the-net-core-command-line"></a>Organización y prueba de proyectos con la línea de comandos de .NET Core

Este tutorial sigue al tutorial [Introducción a .NET Core en Windows, Linux y macOS con la línea de comandos](using-with-xplat-cli.md) dirigiéndole más allá de la creación de una aplicación de consola sencilla para desarrollar aplicaciones más avanzadas y bien organizadas. Después de mostrarle cómo usar carpetas para organizar su código, este tutorial le muestra cómo ampliar una aplicación de consola con el marco de pruebas de [xUnit](https://xunit.github.io/).

## <a name="using-folders-to-organize-code"></a>Uso de carpetas para organizar el código

Si quiere introducir nuevos tipos en una aplicación de consola, puede hacerlo agregando archivos que contienen los tipos en la aplicación. Por ejemplo, si agrega archivos que contienen tipos `AccountInformation` y `MonthlyReportRecords` en su proyecto, la estructura del archivo del proyecto es plana y fácil desplazarse por él:

```
/MyProject
|__AccountInformation.cs
|__MonthlyReportRecords.cs
|__MyProject.csproj
|__Program.cs
```

En cambio, esto solo funciona bien cuando el tamaño del proyecto es relativamente pequeño. ¿Puede imaginar qué pasará si agrega 20 tipos al proyecto? Definitivamente no será fácil desplazarse por el proyecto ni mantenerlo con tantos archivos depositados en el directorio raíz del proyecto.

Para organizar el proyecto, cree una carpeta nueva y denomínela *Models* para contener los archivos de tipo. Coloque los archivos de tipo en la carpeta *Models*:

```
/MyProject
|__/Models
   |__AccountInformation.cs
   |__MonthlyReportRecords.cs
|__MyProject.csproj
|__Program.cs
```

Es fácil desplazarse por los proyectos que agrupan archivos en carpetas de manera lógica, así como mantenerlos. En la sección siguiente, creará un ejemplo más complejo con carpetas y pruebas unitarias.

## <a name="organizing-and-testing-using-the-newtypes-pets-sample"></a>Organizar y probar con el ejemplo de NewTypes Pets

### <a name="building-the-sample"></a>Compilar el ejemplo

Para los pasos siguientes, puede seguir con el [ejemplo de NewTypes Pets](https://github.com/dotnet/docs/tree/master/samples/core/console-apps/NewTypesMsBuild) o crear sus propios archivos y carpetas. Los tipos se organizan de manera lógica en una estructura de carpetas que permite la adición de más tipos posteriormente, y las pruebas también se colocan de manera lógica en carpetas que permiten la adición de más pruebas después.

El ejemplo contiene dos tipos, `Dog` y `Cat`, y tiene implementada una interfaz común, `IPet`. Para el proyecto `NewTypes`, su objetivo es organizar los tipos relacionados con las mascotas en una carpeta *Pets*. Si se agrega después otro conjunto de tipos, *WildAnimals* por ejemplo, se colocan en la carpeta *NewTypes* junto a la carpeta *Pets*. La carpeta *WildAnimals* puede contener tipos de animales que no son mascotas, como los tipos `Squirrel` y `Rabbit`. De la manera en que se agregan los tipos, el proyecto sigue estando bien organizado. 

Cree la siguiente estructura de carpetas con el contenido del archivo indicado:

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

*IPet.cs*:

[!code-csharp[IPet interface](../../../samples/core/console-apps/NewTypesMsBuild/src/NewTypes/Pets/IPet.cs)]

*Dog.cs*:

[!code-csharp[Dog class](../../../samples/core/console-apps/NewTypesMsBuild/src/NewTypes/Pets/Dog.cs)]

*Cat.cs*:

[!code-csharp[Cat class](../../../samples/core/console-apps/NewTypesMsBuild/src/NewTypes/Pets/Cat.cs)]

*Program.cs*:

[!code-csharp[Main](../../../samples/core/console-apps/NewTypesMsBuild/src/NewTypes/Program.cs)]

*NewTypes.csproj*:

[!code-xml[NewTypes csproj](../../../samples/core/console-apps/NewTypesMsBuild/src/NewTypes/NewTypes.csproj)]

Ejecute los siguientes comandos:

```console
dotnet run
```

Obtenga el siguiente resultado:

```console
Woof!
Meow!
```

Ejercicio opcional: puede agregar un nuevo tipo de mascota, como `Bird`, ampliando este proyecto. Haga que el método `TalkToOwner` de las aves proporcione `Tweet!` al propietario. Ejecute la aplicación de nuevo. El resultado incluirá `Tweet!`.

### <a name="testing-the-sample"></a>Probar el ejemplo

El proyecto `NewTypes` está en su lugar y lo ha organizado manteniendo los tipos relacionados con las mascotas en una carpeta. Después, cree su proyecto de prueba y comience a escribir pruebas con el marco de pruebas de [xUnit](https://xunit.github.io/). Las pruebas unitarias le permiten comprobar automáticamente el comportamiento de sus tipos de mascota para confirmar que están funcionando correctamente.

Cree una carpeta *test* con una carpeta *NewTypesTests* en su interior. En un símbolo del sistema desde la carpeta *NewTypesTests*, ejecute `dotnet new xunit`. Esto genera dos archivos: *NewTypesTests.csproj* y *UnitTest1.cs*.

El proyecto de prueba no puede probar actualmente los tipos de `NewTypes` y necesita una referencia del proyecto para el proyecto `NewTypes`. Para agregar una referencia del proyecto, use el comando [`dotnet add reference`](../tools/dotnet-add-reference.md):

```
dotnet add reference ../../src/NewTypes/NewTypes.csproj
```

También tiene la opción de agregar manualmente la referencia del proyecto agregando un nodo `<ItemGroup>` al archivo *NewTypesTests.csproj*:

```xml
<ItemGroup>
  <ProjectReference Include="../../src/NewTypes/NewTypes.csproj" />
</ItemGroup>
```

*NewTypesTests.csproj*:

[!code-xml[NewTypesTests csproj](../../../samples/core/console-apps/NewTypesMsBuild/test/NewTypesTests/NewTypesTests.csproj)]

El archivo *NewTypesTests.csproj* contiene lo siguiente:

* Referencia del paquete a `Microsoft.NET.Test.Sdk`, la infraestructura de pruebas de .NET
* Referencia del paquete a `xunit`, el marco de pruebas de xUnit
* Referencia del paquete a `xunit.runner.visualstudio`, el ejecutor de pruebas
* Referencia del proyecto a `NewTypes`, el código que se va a probar

Cambie el nombre de *UnitTest1.cs* a *PetTests.cs* y reemplace el código en el archivo por lo siguiente:

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

Ejercicio opcional: si ha agregado un tipo `Bird` anteriormente que da como resultado `Tweet!` para el propietario, agregue un método de prueba al archivo *PetTests.cs*, `BirdTalkToOwnerReturnsTweet`, para comprobar que el método `TalkToOwner` funciona correctamente para el tipo `Bird`.

> [!NOTE]
> Aunque espere que los valores `expected` y `actual` sean iguales, las aserciones iniciales con las comprobaciones `Assert.NotEqual` especifican que *no son iguales*. Cree siempre inicialmente sus pruebas para que produzcan un error una vez para comprobar la lógica de las pruebas. Este es un paso importante en la metodología de diseño controlado por pruebas (TDD). Después de que confirme que las pruebas producen errores, ajuste las aserciones para permitir que las puedan pasar.

A continuación se muestra la estructura del proyecto completo:

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

Comience en el directorio *test/NewTypesTests*. Restaure el proyecto de prueba con el comando [`dotnet restore`](../tools/dotnet-restore.md). Ejecute las pruebas con el comando [`dotnet test`](../tools/dotnet-test.md). Este comando inicia el ejecutor de pruebas especificado en el archivo del proyecto.

 [!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

 
Como se esperaba, se producen errores en las pruebas y la consola muestra el siguiente resultado:
 
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

Cambie las aserciones de sus pruebas de `Assert.NotEqual` a `Assert.Equal`:

[!code-csharp[PetTests class](../../../samples/core/console-apps/NewTypesMsBuild/test/NewTypesTests/PetTests.cs)]

Vuelva a ejecutar las pruebas con el comando `dotnet test` y obtenga el siguiente resultado:

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

Se pasan las pruebas. Los métodos de los tipos de mascota devuelven los valores correctos al dirigirse al propietario.

Ha obtenido información sobre las técnicas para organizar y probar proyectos con xUnit. Continúe con estas técnicas aplicándolas en sus propios proyectos. *Disfrute programando.*

