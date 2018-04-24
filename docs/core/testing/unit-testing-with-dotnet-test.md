---
title: Prueba unitaria del código C# en .NET Core mediante pruebas de dotnet y xUnit
description: 'Aprenda los conceptos de pruebas unitarias en C# y .NET Core: cree paso a paso una solución de ejemplo mediante pruebas de dotnet y xUnit.'
author: ardalis
ms.author: wiwagn
ms.date: 11/29/2017
ms.topic: article
ms.prod: .net-core
ms.workload:
- dotnetcore
ms.openlocfilehash: 382b5b5e8bafccbcaaa5ef247d894506c1b0b172
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2018
---
# <a name="unit-testing-c-in-net-core-using-dotnet-test-and-xunit"></a>Prueba unitaria de C# en .NET Core mediante pruebas de dotnet y xUnit

Este tutorial le guía por una experiencia interactiva de creación de una solución de ejemplo paso a paso para aprender los conceptos de pruebas unitarias. Si prefiere seguir el tutorial con una solución precompilada, [vea o descargue el código de ejemplo](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-using-dotnet-test/) antes de comenzar. Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

## <a name="creating-the-source-project"></a>Crear el proyecto de origen

Abra una ventana del Shell. Cree un directorio denominado *unit-testing-using-dotnet-test* que contenga la solución.
En este directorio nuevo, ejecute [`dotnet new sln`](../tools/dotnet-new.md) para crear una solución nueva. El hecho de contar con una solución facilita la administración de la biblioteca de clases y del proyecto de prueba unitaria.
En el directorio de la solución, cree un directorio *PrimeService*. La estructura de directorios y archivos hasta el momento sería la siguiente:

```
/unit-testing-using-dotnet-test
    unit-testing-using-dotnet-test.sln
    /PrimeService
```

Convierta *PrimeService* en el directorio actual y ejecute [`dotnet new classlib`](../tools/dotnet-new.md) para crear el proyecto de origen. Cambie el nombre de *Class1.cs* a *PrimeService.cs*. Para usar el desarrollo controlado por pruebas (TDD), tiene que crear primero una implementación de errores de la clase `PrimeService`:

```csharp
using System;

namespace Prime.Services
{
    public class PrimeService
    {
        public bool IsPrime(int candidate)
        {
            throw new NotImplementedException("Please create a test first");
        }
    }
}
```

Cambie nuevamente el directorio al directorio *unit-testing-using-dotnet-test*.

Ejecute el comando [dotnet sln](../tools/dotnet-sln.md) para agregar el proyecto de biblioteca de clases a la solución:

```
dotnet sln add .\PrimeService\PrimeService.csproj
```

## <a name="creating-the-test-project"></a>Crear el proyecto de prueba

A continuación, cree el directorio *PrimeService.Tests*. En el esquema siguiente se muestra la estructura de directorios:

```
/unit-testing-using-dotnet-test
    unit-testing-using-dotnet-test.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

Convierta el directorio *PrimeService.Tests* en el directorio actual y cree un proyecto nuevo con [`dotnet new xunit`](../tools/dotnet-new.md). Este comando crea un proyecto de prueba que usa xUnit como biblioteca de pruebas. La plantilla generada configura el ejecutor de pruebas en el archivo *PrimeServiceTests.csproj* similar al código siguiente:

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.3.0" />
  <PackageReference Include="xunit" Version="2.2.0" />
  <PackageReference Include="xunit.runner.visualstudio" Version="2.2.0" />
</ItemGroup>
```

El proyecto de prueba requiere otros paquetes para crear y ejecutar pruebas unitarias. `dotnet new` en el paso anterior, agregó xUnit y el ejecutor de xUnit. Ahora, agregue la biblioteca de clases `PrimeService` como otra dependencia al proyecto. Use el comando [`dotnet add reference`](../tools/dotnet-add-reference.md):

```
dotnet add reference ../PrimeService/PrimeService.csproj
```

Puede ver todo el archivo en el [repositorio de muestras](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService.Tests.csproj) en GitHub.

Aquí se muestra el diseño de solución final:

```
/unit-testing-using-dotnet-test
    unit-testing-using-dotnet-test.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
        Test Source Files
        PrimeServiceTests.csproj
```

Para agregar el proyecto de pruebas a la solución, ejecute el comando [dotnet sln](../tools/dotnet-sln.md) en el directorio *unit-testing-using-dotnet-test*:

```
dotnet sln add .\PrimeService.Tests\PrimeService.Tests.csproj
```

## <a name="creating-the-first-test"></a>Crear la primera prueba

El enfoque de TDD requiere la escritura de una prueba con errores, después la valida y finalmente repite el proceso. Quite *UnitTest1.cs* del directorio *PrimeService.Tests* y cree un archivo de C# nuevo denominado *PrimeService_IsPrimeShould.cs*. Agregue el código siguiente:

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
        public void ReturnFalseGivenValueOf1()
        {
            var result = _primeService.IsPrime(1);

            Assert.False(result, "1 should not be prime");
        }
    }
}
```

El atributo `[Fact]` indica un método de prueba que el ejecutor de pruebas ejecuta. Para la carpeta *PrimeService.Tests*, ejecute [`dotnet test`](../tools/dotnet-test.md) para compilar las pruebas y la biblioteca de clases y luego ejecutar las pruebas. El ejecutor de pruebas de xUnit tiene el punto de entrada del programa para ejecutar las pruebas desde la consola. `dotnet test` inicia el ejecutor de pruebas con el proyecto de prueba unitaria que creó.

La prueba produce un error. Todavía no ha creado la implementación. Cree esta prueba escribiendo el código más simple en la clase `PrimeService` que funciona. Reemplace la implementación de método existente de `IsPrime` por el código siguiente:

```csharp
public bool IsPrime(int candidate)
{
    if (candidate == 1)
    {
        return false;
    }
    throw new NotImplementedException("Please create a test first");
}
```

En el directorio *PrimeService.Tests*, ejecute `dotnet test` de nuevo. El comando `dotnet test` ejecuta una compilación del proyecto `PrimeService` y luego del proyecto `PrimeService.Tests`. Después de compilar ambos proyectos, se ejecuta esta única prueba. Pasa.

## <a name="adding-more-features"></a>Agregar más características

Ahora que la prueba se ha superado, es el momento de escribir más. Hay algunos otros casos simples para números primos: 0, -1. Puede agregar esos casos como nuevas pruebas con el atributo `[Fact]`, pero enseguida este proceso se hace tedioso. Hay otros atributos de xUnit que le permiten escribir un conjunto de pruebas similares:

- Un elemento `[Theory]` representa un conjunto de pruebas que ejecutan el mismo código, pero tienen diferentes argumentos de entrada.

- Un atributo `[InlineData]` especifica valores para esas entradas.

En lugar de crear pruebas nuevas, aplique estos dos atributos, `[Theory]` y `[InlineData]`, para crear una sola teoría en el archivo *PrimeService_IsPrimeShould.cs*. La teoría es un método que prueba varios valores menores que dos, que es el número primo menor:

[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]

Ejecute `dotnet test` de nuevo, y dos de estas pruebas deben generar un error. Para superar todas las pruebas, cambie la cláusula `if` al principio del método `IsPrime` en el archivo *PrimeService.cs*:

```csharp
if (candidate < 2)
```

Puede continuar recorriendo en iteración agregando más pruebas, más teorías y más código en la biblioteca principal. Ya tiene la [versión terminada de las pruebas](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs) y la [implementación completa de la biblioteca](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-dotnet-test/PrimeService/PrimeService.cs).

### <a name="additional-resources"></a>Recursos adicionales

[Probar la lógica del controlador en ASP.NET Core](/aspnet/core/mvc/controllers/testing)
