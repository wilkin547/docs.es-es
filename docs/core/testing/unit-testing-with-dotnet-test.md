---
title: Pruebas unitarias de .NET Core mediante pruebas de dotnet | Microsoft Docs
description: Pruebas unitarias de .NET Core mediante pruebas de dotnet
keywords: .NET, .NET Core
author: ardalis
ms.author: wiwagn
ms.date: 002/02/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: bdcdb812-6f13-4f20-9e90-0c0977937142
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: cd860241f5f20b6a4f1ccfec60e0c9cd5079152a
ms.lasthandoff: 03/07/2017

---

# <a name="unit-testing-in-net-core-using-dotnet-test"></a>Pruebas unitarias de .NET Core mediante pruebas de dotnet

Por [Steve Smith](http://ardalis.com) y [Bill Wagner](https://github.com/BillWagner).

[Ver o descargar el código de ejemplo](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/unit-testing-using-dotnet-test)

## <a name="creating-the-projects"></a>Crear los proyectos

El artículo sobre [cómo escribir bibliotecas con herramientas multiplataforma](../tutorials/libraries.md) contiene información sobre la organización de las soluciones para varios proyectos tanto para el origen como para las pruebas. Este artículo sigue estas convenciones. La estructura del proyecto final tendrá un aspecto similar al siguiente:

```
/unit-testing-using-dotnet-test
|__/PrimeService
   |__Source Files
   |__PrimeService.csproj
|__/PrimeService.Tests
   |__Test Files
   |__PrimeService.csproj
```

### <a name="creating-the-source-project"></a>Crear el proyecto de origen

Comience en el directorio `unit-testing-using-dotnet-test` y cree el directorio `PrimeService`.
Cambie a ese directorio y ejecute `dotnet new classib` para crear el proyecto de origen.


Cambie el nombre de `Class1.cs` en `PrimeService.cs`. Para usar el desarrollo controlado por pruebas (TDD), tendrá que crear una implementación de errores de la clase `PrimeService`:

```cs
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

Después, vuelva al directorio "unit-testing-using-dotnet-test" y cree el directorio `PrimeServices.Tests`.
Cambie al directorio `PrimeService.Tests` y cree un nuevo proyecto con `dotnet new xunit`. `dotnet xunit` crea un proyecto de prueba que usa xUnit como biblioteca de pruebas. 

La plantilla generada ha configurado el ejecutor de pruebas en PrimeServiceTests.csproj:

```xml
  <ItemGroup>
    <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.0.0-preview-20170125-04" />
    <PackageReference Include="xunit" Version="2.2.0-beta5-build3474" />
    <PackageReference Include="xunit.runner.visualstudio" Version="2.2.0-beta5-build1225" />
  </ItemGroup>
```

El proyecto de prueba requiere otros paquetes para crear y ejecutar pruebas unitarias.
`dotnet new` ha agregado xUnit y el ejecutor de xUnit. Debe agregar el paquete PrimeService como otra dependencia al proyecto. Puede hacerlo mediante la CLI `dotnet`:

```
dotnet add reference ../PrimeService/PrimeService.csproj
```

O puede editar directamente el archivo `PrimeService.Tests.csproj`.
Directamente en el primer nodo `<ItemGroup>`, agregue otro nodo `<ItemGroup>` con una referencia al proyecto de biblioteca:

```xml
  <ItemGroup>
    <ProjectReference Include="..\PrimeService\PrimeService.csproj" />
  </ItemGroup>
```

Puede ver todo el archivo en el [repositorio de muestras](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService.Tests.csproj) en GitHub.

Una vez dispuesta esta estructura inicial, puede escribir la primera prueba.
Cuando haya comprobado esa primera prueba unitaria, todo estará configurado y deberá ejecutarse sin problemas a medida que agrega funciones y pruebas.

## <a name="creating-the-first-test"></a>Crear la primera prueba

Antes de crear la biblioteca o las pruebas, necesita ejecutar `dotnet restore` en los directorios `PrimeService` y `PrimeService.Tests`. Este comando restaura todos los paquetes de NuGet necesarios para cada proyecto.

El enfoque de TDD requiere la escritura de una prueba con errores, después la valida y finalmente repite el proceso. Por lo tanto, vamos a escribir esa prueba con errores. Quite `UnitTest1.cs` del directorio `PrimeService.Tests` y cree un nuevo archivo de C# denominado `PrimeService_IsPrimeShould.cs` con el siguiente contenido:

```cs
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

El atributo `[Fact]` indica un método como una única prueba. 

Guarde este archivo y ejecute `dotnet build` para compilar el proyecto de prueba.
Si no ha creado ya el proyecto `PrimeService`, el sistema de compilación lo detectará y lo compilará porque es una dependencia del proyecto de prueba.

Ahora, ejecute `dotnet test` para ejecutar las pruebas desde la consola.
El ejecutor de pruebas de xUnit tiene el punto de entrada del programa para ejecutar las pruebas desde la consola. `dotnet test` inicia el ejecutor de pruebas y proporciona un argumento de línea de comandos al ejecutor de pruebas que indica el ensamblado que contiene las pruebas.

La prueba produce un error. Todavía no ha creado la implementación.
Escriba el código más sencillo para validar esta prueba:

```cs
public bool IsPrime(int candidate) 
{
    if(candidate == 1) 
    { 
        return false;
    } 
    throw new NotImplementedException("Please create a test first");
} 
```

### <a name="adding-more-features"></a>Agregar más características

Ahora, que ha realizado una prueba correcta, es el momento de escribir más.
Hay algunos otros casos simples para números primos: 0, -1. Puede agregarlo como nuevas pruebas con el atributo `[Fact]` pero rápidamente este proceso se hace tedioso. Hay otros atributos de xUnit que le permiten escribir un conjunto de pruebas similares.  Un elemento `Theory` representa un conjunto de pruebas que ejecutan el mismo código, pero tienen diferentes argumentos de entrada.
Puede usar el atributo `[InlineData]` para especificar valores para esas entradas. 
 
 En lugar de crear nuevas pruebas, aproveche estos dos atributos para crear una teoría que prueba algunos valores inferiores a 2, que es el número primo más bajo:

[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs#Sample_TestCode "Primeras pruebas")]
```

Run `dotnet test` and you'll see that two of these tests fail.
You can make them pass by changing the service. You need to change
the `if` clause at the beginning of the method:

```cs
if(candidate < 2)
```

Ahora, todas estas pruebas son correctas.

Puede continuar recorriendo en iteración al agregar más pruebas, más teorías y más código en la biblioteca principal. Rápidamente terminará con la [versión terminada de las pruebas](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/test/PrimeService.Tests/PrimeService_IsPrimeShould.cs) y con la [implementación completa de la biblioteca](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/src/PrimeService/PrimeService.cs).

Ha creado una biblioteca pequeña y un conjunto de pruebas unitarias para esa biblioteca.
Ha estructurado esta solución para que agregar nuevos paquetes y pruebas sea un proceso muy sencillo y pueda concentrarse en el problema en cuestión. Las herramientas se ejecutarán automáticamente.

