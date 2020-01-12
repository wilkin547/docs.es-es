---
title: Organización y prueba de proyectos con la línea de comandos de .NET Core
description: En este tutorial se explica cómo organizar y probar proyectos .NET Core desde la línea de comandos.
author: cartermp
ms.date: 09/10/2018
ms.openlocfilehash: fdaa42be4d3b8872a3119f97f253ce277564339e
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715339"
---
# <a name="organizing-and-testing-projects-with-the-net-core-command-line"></a>Organización y prueba de proyectos con la línea de comandos de .NET Core

Este tutorial sigue al tutorial [Introducción a .NET Core en Windows, Linux y macOS con la línea de comandos](cli-create-console-app.md) dirigiéndole más allá de la creación de una aplicación de consola sencilla para desarrollar aplicaciones más avanzadas y bien organizadas. Después de mostrarle cómo usar carpetas para organizar su código, este tutorial le muestra cómo ampliar una aplicación de consola con el marco de pruebas de [xUnit](https://xunit.github.io/).

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

Para los pasos siguientes, puede seguir con el [ejemplo de NewTypes Pets](https://github.com/dotnet/samples/tree/master/core/console-apps/NewTypesMsBuild) o crear sus propios archivos y carpetas. Los tipos se organizan de manera lógica en una estructura de carpetas que permite la adición de más tipos posteriormente, y las pruebas también se colocan de manera lógica en carpetas que permiten la adición de más pruebas después.

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

Ejecute el siguiente comando:

```dotnetcli
dotnet run
```

Obtenga el siguiente resultado:

```console
Woof!
Meow!
```

Ejercicio opcional: puede agregar un nuevo tipo de mascota, como `Bird`, si amplía este proyecto. Haga que el método `TalkToOwner` de las aves proporcione `Tweet!` al propietario. Ejecute la aplicación de nuevo. El resultado incluirá `Tweet!`.

### <a name="testing-the-sample"></a>Probar el ejemplo

El proyecto `NewTypes` está en su lugar y lo ha organizado manteniendo los tipos relacionados con las mascotas en una carpeta. Después, cree su proyecto de prueba y comience a escribir pruebas con el marco de pruebas de [xUnit](https://xunit.github.io/). Las pruebas unitarias le permiten comprobar automáticamente el comportamiento de sus tipos de mascota para confirmar que están funcionando correctamente.

Vuelva a la carpeta *src* y cree una carpeta *test* con una carpeta *NewTypesTests* en su interior. En un símbolo del sistema desde la carpeta *NewTypesTests*, ejecute `dotnet new xunit`. Esto genera dos archivos: *NewTypesTests.csproj* y *UnitTest1.cs*.

El proyecto de prueba no puede probar actualmente los tipos de `NewTypes` y necesita una referencia del proyecto para el proyecto `NewTypes`. Para agregar una referencia del proyecto, use el comando [`dotnet add reference`](../tools/dotnet-add-reference.md):

```dotnetcli
dotnet add reference ../../src/NewTypes/NewTypes.csproj
```

O bien, también tiene la opción de agregar manualmente la referencia del proyecto si agrega un nodo `<ItemGroup>` al archivo *NewTypesTests.csproj*:

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
> Aunque espere que los valores `expected` y `actual` sean iguales, la aserción inicial con la comprobación `Assert.NotEqual` especifica que estos valores *no son iguales*. Cree siempre inicialmente una prueba que resulte fallida para comprobar la lógica de la prueba. Después de confirmar que la prueba falla, ajuste la aserción para permitir que se supere la prueba.

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

```output
Test run for c:\Users\ronpet\repos\samples\core\console-apps\NewTypesMsBuild\test\NewTypesTests\bin\Debug\netcoreapp2.1\NewTypesTests.dll(.NETCoreApp,Version=v2.1)
Microsoft (R) Test Execution Command Line Tool Version 15.8.0
Copyright (c) Microsoft Corporation.  All rights reserved.

Starting test execution, please wait...
[xUnit.net 00:00:00.77]     PetTests.DogTalkToOwnerReturnsWoof [FAIL]
[xUnit.net 00:00:00.78]     PetTests.CatTalkToOwnerReturnsMeow [FAIL]
Failed   PetTests.DogTalkToOwnerReturnsWoof
Error Message:
 Assert.NotEqual() Failure
Expected: Not "Woof!"
Actual:   "Woof!"
Stack Trace:
   at PetTests.DogTalkToOwnerReturnsWoof() in c:\Users\ronpet\repos\samples\core\console-apps\NewTypesMsBuild\test\NewTypesTests\PetTests.cs:line 13
Failed   PetTests.CatTalkToOwnerReturnsMeow
Error Message:
 Assert.NotEqual() Failure
Expected: Not "Meow!"
Actual:   "Meow!"
Stack Trace:
   at PetTests.CatTalkToOwnerReturnsMeow() in c:\Users\ronpet\repos\samples\core\console-apps\NewTypesMsBuild\test\NewTypesTests\PetTests.cs:line 22

Total tests: 2. Passed: 0. Failed: 2. Skipped: 0.
Test Run Failed.
Test execution time: 1.7000 Seconds
```

Cambie las aserciones de sus pruebas de `Assert.NotEqual` a `Assert.Equal`:

[!code-csharp[PetTests class](../../../samples/core/console-apps/NewTypesMsBuild/test/NewTypesTests/PetTests.cs)]

Vuelva a ejecutar las pruebas con el comando `dotnet test` y obtenga el siguiente resultado:

```output
Test run for c:\Users\ronpet\repos\samples\core\console-apps\NewTypesMsBuild\test\NewTypesTests\bin\Debug\netcoreapp2.1\NewTypesTests.dll(.NETCoreApp,Version=v2.1)
Microsoft (R) Test Execution Command Line Tool Version 15.8.0
Copyright (c) Microsoft Corporation.  All rights reserved.

Starting test execution, please wait...

Total tests: 2. Passed: 2. Failed: 0. Skipped: 0.
Test Run Successful.
Test execution time: 1.6029 Seconds
```

Se pasan las pruebas. Los métodos de los tipos de mascota devuelven los valores correctos al dirigirse al propietario.

Ha obtenido información sobre las técnicas para organizar y probar proyectos con xUnit. Continúe con estas técnicas aplicándolas en sus propios proyectos. *Disfrute programando.*
