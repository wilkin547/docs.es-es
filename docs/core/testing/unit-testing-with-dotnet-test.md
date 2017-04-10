---
title: Pruebas unitarias de .NET Core mediante pruebas de dotnet | Microsoft Docs
description: Pruebas unitarias de .NET Core mediante pruebas de dotnet
keywords: .NET, .NET Core
author: ardalis
ms.author: wiwagn
ms.date: 03/21/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: bdcdb812-6f13-4f20-9e90-0c0977937142
translationtype: Human Translation
ms.sourcegitcommit: 4a1f0c88fb1ccd6694f8d4f5687431646adbe000
ms.openlocfilehash: 3ca312509d7ba7a7759d1ac294f79cc359419c52
ms.lasthandoff: 03/22/2017

---

# <a name="unit-testing-in-net-core-using-dotnet-test"></a>Pruebas unitarias de .NET Core mediante pruebas de dotnet

Este tutorial le guía por una experiencia interactiva de creación de una solución de ejemplo paso a paso para aprender los conceptos de pruebas unitarias. Si prefiere seguir el tutorial con una solución precompilada, [vea o descargue el código de ejemplo](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/unit-testing-using-dotnet-test/) antes de comenzar.

### <a name="creating-the-source-project"></a>Crear el proyecto de origen

Abra una ventana del Shell. Cree un directorio denominado *unit-testing-using-dotnet-test* que contenga la solución. Dentro de este nuevo directorio, cree un directorio *PrimeService*. Esta es la estructura de directorios hasta el momento:

```
/unit-testing-using-dotnet-test
    /PrimeService
```

Convierta *PrimeService* en el directorio actual y ejecute [`dotnet new classlib`](../tools/dotnet-new.md) para crear el proyecto de origen. Cambie el nombre de *Class1.cs* a *PrimeService.cs*. Para usar el desarrollo controlado por pruebas (TDD), tendrá que crear una implementación de errores de la clase `PrimeService`:

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

### <a name="creating-the-test-project"></a>Crear el proyecto de prueba

Cambie el directorio de nuevo al directorio *unit-testing-using-mstest* y cree el directorio *PrimeServices.Test*. Esta es la estructura de directorios:

```
/unit-testing-using-dotnet-test
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

Convierta el directorio *PrimeService.Tests* en el directorio actual y cree un proyecto nuevo con [`dotnet new xunit`](../tools/dotnet-new.md). Esto crea un proyecto de prueba que usa xUnit como biblioteca de pruebas. La plantilla generada ha configurado el ejecutor de pruebas en *PrimeServiceTests.csproj*:

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.0.0" />
  <PackageReference Include="xunit" Version="2.2.0" />
  <PackageReference Include="xunit.runner.visualstudio" Version="2.2.0" />
</ItemGroup>
```

El proyecto de prueba requiere otros paquetes para crear y ejecutar pruebas unitarias. `dotnet new` en el paso anterior, agregó xUnit y el ejecutor de xUnit. Ahora, agregue la biblioteca de clases `PrimeService` como otra dependencia al proyecto. Use el comando [`dotnet add reference`](../tools/dotnet-add-reference.md):

```
dotnet add reference ../PrimeService/PrimeService.csproj
```

Otra opción consiste en editar el archivo *PrimeService.Tests.csproj*. Directamente en el primer nodo `<ItemGroup>`, agregue otro nodo `<ItemGroup>` con una referencia al proyecto de biblioteca:

```xml
<ItemGroup>
  <ProjectReference Include="..\PrimeService\PrimeService.csproj" />
</ItemGroup>
```

Puede ver todo el archivo en el [repositorio de muestras](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService.Tests.csproj) en GitHub.

A continuación se muestra el diseño de la solución final:

```
/unit-testing-using-mstest
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
        PrimeService
        PrimeServiceTests.csproj
```

## <a name="creating-the-first-test"></a>Crear la primera prueba

Antes de compilar la biblioteca o las pruebas, ejecute [`dotnet restore`](../tools/dotnet-restore.md) en el directorio *PrimeService.Tests*. Este comando restaura todos los paquetes de NuGet necesarios para cada proyecto.

El enfoque de TDD requiere la escritura de una prueba con errores, después la valida y finalmente repite el proceso. Quite *UnitTest1.cs* del directorio *PrimeService.Tests* y cree un nuevo archivo de C# denominado *PrimeService_IsPrimeShould.cs* con el siguiente contenido:

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

            Assert.False(result, $"1 should not be prime");
        }
    }
}
```

El atributo `[Fact]` indica un método como una única prueba. Ejecute [`dotnet test`](../tools/dotnet-test.md) para generar las pruebas y la biblioteca de clases y, a continuación, ejecute las pruebas. El ejecutor de pruebas de xUnit tiene el punto de entrada del programa para ejecutar las pruebas desde la consola. `dotnet test` inicia el ejecutor de pruebas y proporciona un argumento de línea de comandos al ejecutor de pruebas que indica el ensamblado que contiene las pruebas.

La prueba produce un error. Todavía no ha creado la implementación. Escriba el código más simple en la clase `PrimeService` para pasar esta prueba:

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

### <a name="adding-more-features"></a>Agregar más características

Ahora que la prueba se ha superado, es el momento de escribir más. Hay algunos otros casos simples para números primos: 0, -1. Puede agregarlas como nuevas pruebas con el atributo `[Fact]`, pero enseguida este proceso se hace tedioso. Hay otros atributos de xUnit que le permiten escribir un conjunto de pruebas similares.  Un atributo `[Theory]` representa un conjunto de pruebas que ejecutan el mismo código, pero tienen diferentes argumentos de entrada. Puede usar el atributo `[InlineData]` para especificar valores para esas entradas. 
 
En lugar de crear nuevas pruebas, aproveche estos dos atributos para crear una teoría que prueba algunos valores inferiores a 2, que es el número primo más bajo:

[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]

Ejecute `dotnet test`, y dos de estas pruebas no se superarán. Para superar todas las pruebas, cambie la cláusula `if` al principio del método:

```csharp
if (candidate < 2)
```

Puede continuar recorriendo en iteración agregando más pruebas, más teorías y más código en la biblioteca principal. Acabará con la [versión terminada de las pruebas](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs) y con la [implementación completa de la biblioteca](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService/PrimeService.cs).

Ha creado una biblioteca pequeña y un conjunto de pruebas unitarias para esa biblioteca. Ha estructurado la solución para que el proceso de agregar nuevos paquetes y pruebas sea continuo y pueda concentrar la mayor parte de su tiempo y esfuerzo en solucionar los objetivos de la aplicación.

