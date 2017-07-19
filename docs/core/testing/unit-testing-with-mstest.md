---
title: Pruebas unitarias con MSTest y .NET Core | Microsoft Docs
description: "Cómo usar MSTest con .NET Core"
keywords: MSTest, .NET, .NET Core
author: ncarandini
ms.author: wiwagn
ms.date: 03/21/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: ed447641-3e85-4e50-b7ed-004630048a3e
ms.translationtype: Human Translation
ms.sourcegitcommit: fe32676f0e39ed109a68f39584cf41aec5f5ce90
ms.openlocfilehash: 5c6382ee0de3cba950b4585b05f10b4682f9a797
ms.contentlocale: es-es
ms.lasthandoff: 05/10/2017

---

# <a name="unit-testing-with-mstest-and-net-core"></a>Pruebas unitarias con MSTest y .NET Core

Este tutorial le guía por una experiencia interactiva de creación de una solución de ejemplo paso a paso para aprender los conceptos de pruebas unitarias. Si prefiere seguir el tutorial con una solución precompilada, [vea o descargue el código de ejemplo](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/) antes de comenzar. Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

### <a name="creating-the-source-project"></a>Crear el proyecto de origen

Abra una ventana del Shell. Cree un directorio denominado *unit-testing-using-dotnet-test* que contenga la solución. Dentro de este nuevo directorio, cree un directorio *PrimeService*. Esta es la estructura de directorios hasta el momento:

```
/unit-testing-using-mstest
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

Cambie el directorio de nuevo al directorio *unit-testing-using-mstest* y cree el directorio *PrimeService.Tests*. Esta es la estructura de directorios:

```
/unit-testing-using-mstest
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

Convierta el directorio *PrimeService.Tests* en el directorio actual y cree un proyecto nuevo con [`dotnet new mstest`](../tools/dotnet-new.md). Esto crea un proyecto de prueba que usa MStest como la biblioteca de pruebas. La plantilla generada configura el ejecutor de pruebas en el archivo *PrimeServiceTests.csproj*:

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.0.0" />
  <PackageReference Include="MSTest.TestAdapter" Version="1.1.11" />
  <PackageReference Include="MSTest.TestFramework" Version="1.1.11" />
</ItemGroup>
```

El proyecto de prueba requiere otros paquetes para crear y ejecutar pruebas unitarias. `dotnet new` en el paso anterior agregó el SDK de MSTest, el marco de prueba de MSTest y el ejecutor de MSTest. Ahora, agregue la biblioteca de clases `PrimeService` como otra dependencia al proyecto. Use el comando [`dotnet add reference`](../tools/dotnet-add-reference.md):

```
dotnet add reference ../PrimeService/PrimeService.csproj
```

Otra opción consiste en editar el archivo *PrimeService.Tests.csproj*. Directamente en el primer nodo `<ItemGroup>`, agregue otro nodo `<ItemGroup>` con una referencia al proyecto de biblioteca:

```xml
<ItemGroup>
  <ProjectReference Include="..\PrimeService\PrimeService.csproj" />
</ItemGroup>
```

Puede ver todo el archivo en el [repositorio de muestras](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService.Tests.csproj) en GitHub.

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
using Microsoft.VisualStudio.TestTools.UnitTesting;
using Prime.Services;

namespace Prime.UnitTests.Services
{
    [TestClass]
    public class PrimeService_IsPrimeShould
    {
        private readonly PrimeService _primeService;

        public PrimeService_IsPrimeShould()
        {
            _primeService = new PrimeService();
        }

        [TestMethod]
        public void ReturnFalseGivenValueOf1()
        {
            var result = _primeService.IsPrime(1);

            Assert.IsFalse(result, $"1 should not be prime");
        }
    }
}
```

El atributo `[TestClass]` indica una clase que contiene pruebas unitarias. El atributo `[TestMethod]` indica un método como una única prueba. 

Guarde este archivo y ejecute [`dotnet test`](../tools/dotnet-test.md) para compilar las pruebas y la biblioteca de clases y luego ejecutar las pruebas. El ejecutor de pruebas de MSTest tiene el punto de entrada del programa para ejecutar las pruebas desde la consola. `dotnet test` inicia el ejecutor de pruebas y proporciona un argumento de línea de comandos al ejecutor de pruebas que indica el ensamblado que contiene las pruebas.

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

## <a name="adding-more-features"></a>Agregar más características

Ahora que la prueba se ha superado, es el momento de escribir más. Hay algunos otros casos simples para números primos: 0, -1. Puede agregarlas como nuevas pruebas con el atributo `[TestMethod]`, pero enseguida este proceso se hace tedioso. Hay otros atributos de MSTest que le permiten escribir un conjunto de pruebas similares.  Un atributo `[DataTestMethod]` representa un conjunto de pruebas que ejecutan el mismo código, pero que tienen diferentes argumentos de entrada. Puede usar el atributo `[DataRow]` para especificar valores para esas entradas. 
 
En lugar de crear nuevas pruebas, aproveche estos dos atributos para crear un método de prueba de datos único que pruebe algunos valores inferiores a 2, que es el número primo más bajo:

[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]

Ejecute `dotnet test`, y dos de estas pruebas no se superarán. Para superar todas las pruebas, cambie la cláusula `if` al principio del método:

```csharp
if (candidate < 2)
```

Puede continuar recorriendo en iteración agregando más pruebas, más teorías y más código en la biblioteca principal. Acabará con la [versión terminada de las pruebas](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs) y con la [implementación completa de la biblioteca](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService/PrimeService.cs).

Ha creado una biblioteca pequeña y un conjunto de pruebas unitarias para esa biblioteca. Ha estructurado la solución para que el proceso de agregar nuevos paquetes y pruebas sea continuo y pueda concentrar la mayor parte de su tiempo y esfuerzo en solucionar los objetivos de la aplicación.

