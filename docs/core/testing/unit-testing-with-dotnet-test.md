---
title: Prueba unitaria del código C# en .NET Core mediante pruebas de dotnet y xUnit
description: 'Aprenda los conceptos de pruebas unitarias en C# y .NET Core: cree paso a paso una solución de ejemplo mediante pruebas de dotnet y xUnit.'
author: ardalis
ms.author: wiwagn
ms.date: 12/04/2019
ms.openlocfilehash: d8cf0e29c8a482b39bd7e99bcde1fd60301f046f
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83702949"
---
# <a name="unit-testing-c-in-net-core-using-dotnet-test-and-xunit"></a>Prueba unitaria de C# en .NET Core mediante pruebas de dotnet y xUnit

En este tutorial se muestra cómo compilar una solución que contiene un proyecto de prueba unitaria y un proyecto de código fuente. Para seguir el tutorial con una solución precompilada, [vea o descargue el código de ejemplo](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-using-dotnet-test/). Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

## <a name="create-the-solution"></a>Creación de la solución

En esta sección, se crea una solución que contiene los proyectos de prueba y origen. La solución completada tiene la siguiente estructura de directorios:

```
/unit-testing-using-dotnet-test
    unit-testing-using-dotnet-test.sln
    /PrimeService
        PrimeService.cs
        PrimeService.csproj
    /PrimeService.Tests
        PrimeService_IsPrimeShould.cs
        PrimeServiceTests.csproj
```

Las instrucciones siguientes proporcionan los pasos para crear la solución de prueba. Consulte la sección sobre [comandos para crear la solución de prueba](#create-test-cmd) a fin de obtener instrucciones para crear la solución de prueba en un paso.

* Abra una ventana del Shell.
* Ejecute el siguiente comando:

  ```dotnetcli
  dotnet new sln -o unit-testing-using-dotnet-test
  ```

  El comando [`dotnet new sln`](../tools/dotnet-new.md) crea una nueva solución en el directorio *unit-testing-using-dotnet-test*.
* Cambie el directorio a la carpeta *unit-testing-using-dotnet-test*.
* Ejecute el siguiente comando:

  ```dotnetcli
  dotnet new classlib -o PrimeService
  ```

   El comando [`dotnet new classlib`](../tools/dotnet-new.md) crea un nuevo proyecto de biblioteca de clases en la carpeta *PrimeService*. La nueva biblioteca de clases contendrá el código que se va a probar.
* Cambie el nombre de *Class1.cs* a *PrimeService.cs*.
* Reemplace el código de *PrimeService.cs* por el código siguiente:
  
  ```csharp
  using System;

  namespace Prime.Services
  {
      public class PrimeService
      {
          public bool IsPrime(int candidate)
          {
              throw new NotImplementedException("Not implemented.");
          }
      }
  }
  ```

* El código anterior:
  * Produce una excepción <xref:System.NotImplementedException> con un mensaje que indica que no se ha implementado.
  * Se actualiza más adelante en el tutorial.

<!-- preceding code shows an english bias. Message makes no sense outside english -->

* En el directorio *unit-testing-using-dotnet-test*, ejecute el comando siguiente para agregar el proyecto de biblioteca de clases a la solución:

  ```dotnetcli
  dotnet sln add ./PrimeService/PrimeService.csproj
  ```

* Cree el proyecto *PrimeService.Tests* ejecutando el comando siguiente:

  ```dotnetcli
  dotnet new xunit -o PrimeService.Tests
  ```

* El comando anterior:
  * Crea el proyecto *PrimeService.Tests* en el directorio *PrimeService.Tests*. El proyecto de prueba usa [xUnit](https://xunit.net/) como biblioteca de pruebas.
  * Configura el ejecutor de pruebas agregando los siguientes `<PackageReference />`elementos al archivo del proyecto:
    * "Microsoft.NET.Test.Sdk"
    * "xunit"
    * "xunit.runner.visualstudio"

* Agregue el proyecto de prueba al archivo de solución ejecutando el siguiente comando:

  ```dotnetcli
  dotnet sln add ./PrimeService.Tests/PrimeService.Tests.csproj
  ```

* Agregue la biblioteca de clases `PrimeService` como dependencia al proyecto *PrimeService.Tests*:

  ```dotnetcli
  dotnet add ./PrimeService.Tests/PrimeService.Tests.csproj reference ./PrimeService/PrimeService.csproj  
  ```

<a name="create-test-cmd"></a>

### <a name="commands-to-create-the-solution"></a>Comandos para crear la solución

En esta sección se resumen todos los comandos de la sección anterior. Omita esta sección si ha completado los pasos en la sección anterior.

Los siguientes comandos crean la solución de prueba en una máquina Windows. Para macOS y Unix, actualice el comando `ren` a la versión del SO de `ren` para cambiar el nombre de un archivo:

```dotnetcli
dotnet new sln -o unit-testing-using-dotnet-test
cd unit-testing-using-dotnet-test
dotnet new classlib -o PrimeService
ren .\PrimeService\Class1.cs PrimeService.cs
dotnet sln add ./PrimeService/PrimeService.csproj
dotnet new xunit -o PrimeService.Tests
dotnet add ./PrimeService.Tests/PrimeService.Tests.csproj reference ./PrimeService/PrimeService.csproj
dotnet sln add ./PrimeService.Tests/PrimeService.Tests.csproj
```

Siga las instrucciones de "Reemplace el código de *PrimeService.cs* por el siguiente código" de la sección anterior.

## <a name="create-a-test"></a>Creación de una prueba

Un enfoque popular en el desarrollo controlado por pruebas (TDD) consiste en escribir una prueba antes de implementar un código de destino. En este tutorial se usa el enfoque TDD. Se puede llamar al método `IsPrime`, pero sin implementar. Se produce un error en una llamada de prueba a `IsPrime`. Con TDD, se escribe una prueba a sabiendas de que en esta se produce un error. El código de destino se actualiza para conseguir que se supere la prueba. Siga repitiendo este enfoque, escribiendo una prueba con errores y, a continuación, actualizando el código de destino que se va a pasar.

Actualice el proyecto *PrimeService.Tests*:

* Elimine *PrimeService.Tests/UnitTest1.cs*.
* Cree un archivo *PrimeService.Tests/PrimeService_IsPrimeShould.cs*.
* Reemplace el código de *PrimeService_IsPrimeShould.cs* por el código siguiente:

```csharp
using Xunit;
using Prime.Services;

namespace Prime.UnitTests.Services
{
    public class PrimeService_IsPrimeShould
    {
        private readonly PrimeService _primeService;

        public PrimeService_IsPrimeShould()
        {
            _primeService = new PrimeService();
        }

        [Fact]
        public void IsPrime_InputIs1_ReturnFalse()
        {
            var result = _primeService.IsPrime(1);

            Assert.False(result, "1 should not be prime");
        }
    }
}
```

El atributo `[Fact]` declara un método de prueba que el ejecutor de pruebas ejecuta. En la carpeta *PrimeService.Tests*, ejecute `dotnet test`. El comando [dotnet test](../tools/dotnet-test.md) compila ambos proyectos y ejecuta las pruebas. El ejecutor de pruebas de xUnit tiene el punto de entrada del programa para ejecutar las pruebas. `dotnet test` inicia el ejecutor de pruebas con el proyecto de prueba unitaria.

Se produce un error en la prueba porque no se ha implementado `IsPrime`. Con el enfoque TDD, solo tiene que escribir código suficiente para que se supere esta prueba. Actualice `IsPrime` con el siguiente código:

```csharp
public bool IsPrime(int candidate)
{
    if (candidate == 1)
    {
        return false;
    }
    throw new NotImplementedException("Not fully implemented.");
}
```

Ejecute `dotnet test`. La prueba se supera.

### <a name="add-more-tests"></a>Incorporación de más pruebas

Agregue pruebas de números primos para 0 y -1. Podría copiar la prueba anterior y cambiar el siguiente código para usar 0 y -1:

```csharp
var result = _primeService.IsPrime(1);

Assert.False(result, "1 should not be prime");
```

La copia de código de prueba cuando solamente es un parámetro el que cambia da lugar a la duplicación de código y al sobredimensionamiento de pruebas. Los siguientes atributos de xUnit habilitan la escritura de un conjunto de pruebas similares:

- Un elemento `[Theory]` representa un conjunto de pruebas que ejecutan el mismo código, pero tienen diferentes argumentos de entrada.
- Un atributo `[InlineData]` especifica valores para esas entradas.

En lugar de crear pruebas nuevas, aplique los atributos de xUnit anteriores para crear una sola teoría. Reemplace el código siguiente:

```csharp
[Fact]
public void IsPrime_InputIs1_ReturnFalse()
{
    var result = _primeService.IsPrime(1);

    Assert.False(result, "1 should not be prime");
}
```

por el siguiente código:

[!code-csharp[Sample_TestCode](../../../samples/snippets/core/testing/unit-testing-using-dotnet-test/csharp/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]

En el código anterior, `[Theory]` y `[InlineData]` habilitan la prueba de varios valores inferiores a dos. Dos es el número primo más pequeño.

Al ejecutar `dotnet test`, se produce un error en dos de las pruebas. Para que se superen todas las pruebas, actualice el método `IsPrime` con el siguiente código:

```csharp
public bool IsPrime(int candidate)
{
    if (candidate < 2)
    {
        return false;
    }
    throw new NotImplementedException("Not fully implemented.");
}
```

Siguiendo el enfoque TDD, agregue más pruebas con errores y, a continuación, actualice el código de destino. Consulte la [versión terminada de las pruebas](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs) y la [implementación completa de la biblioteca](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-dotnet-test/PrimeService/PrimeService.cs).

El método `IsPrime` completado no es un algoritmo eficaz para probar los números primos.

### <a name="additional-resources"></a>Recursos adicionales

- [Sitio oficial de xUnit.net](https://xunit.net)
- [Probar la lógica del controlador en ASP.NET Core](/aspnet/core/mvc/controllers/testing)
- [`dotnet add reference`](../tools/dotnet-add-reference.md)
