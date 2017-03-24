---
title: Uso de MSTest con .NET Core | Microsoft Docs
description: "Cómo usar MSTest con .NET Core"
keywords: MSTest, .NET, .NET Core
author: ncarandini
ms.author: wiwagn
ms.date: 02/10/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: ed447641-3e85-4e50-b7ed-004630048a3e
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: 4ffc7dd4e11820a3c50ca83847a7ab418bf2faf3
ms.lasthandoff: 03/07/2017

---

# <a name="unit-testing-with-mstest-and-net-core"></a>Pruebas unitarias con MSTest y .NET Core

## <a name="creating-the-projects"></a>Crear los proyectos

El artículo sobre [cómo escribir bibliotecas con herramientas multiplataforma](../tutorials/libraries.md) contiene información sobre la organización de las soluciones para varios proyectos tanto para el origen como para las pruebas. Este artículo sigue estas convenciones. La estructura del proyecto final tendrá un aspecto similar al siguiente:

```
/unit-testing-using-mstest
|__/PrimeService
   |__Source Files
   |__PrimeService.csproj
|__/PrimeService.Tests
   |__Test Files
   |__PrimeService.csproj
```

### <a name="creating-the-source-project"></a>Crear el proyecto de origen

Abra una ventana del Shell. Comience en el directorio *unit-testing-using-mstest* y cree el directorio *PrimeService*.
Haga que *PrimeService* sea el directorio actual y ejecute `dotnet new classlib` para crear el proyecto de origen.

Cambie el nombre de *Class1.cs* a *PrimeService.cs*. Para usar el desarrollo controlado por pruebas (TDD), tendrá que crear una implementación de errores de la clase `PrimeService`:

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

Después, cambie el directorio de nuevo al directorio *unit-testing-using-mstest* y cree el directorio *PrimeServices.Tests*.
Haga que el directorio *PrimeService.Tests* sea el directorio actual y cree un proyecto nuevo con `dotnet new mstest`. Esto crea un proyecto de prueba que usa MStest como la biblioteca de pruebas. 

La plantilla generada ha configurado el ejecutor de pruebas en el archivo *PrimeServiceTests.csproj*:

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.0.0-preview-20170123-02" />
  <PackageReference Include="MSTest.TestAdapter" Version="1.1.10-rc2" />
  <PackageReference Include="MSTest.TestFramework" Version="1.0.8-rc2" />
</ItemGroup>
```

El proyecto de prueba requiere otros paquetes para crear y ejecutar pruebas unitarias.
`dotnet new` ha agregado el SDK de MSTest, el marco de prueba de MSTest y el ejecutor de MSTest. Debe agregar el paquete PrimeService como otra dependencia al proyecto. Puede hacerlo mediante la CLI `dotnet`:

```
dotnet add reference ../PrimeService/PrimeService.csproj
```

O puede editar manualmente el archivo *PrimeService.Tests.csproj*.
Directamente en el primer nodo `<ItemGroup>`, agregue otro nodo `<ItemGroup>` con una referencia al proyecto de biblioteca:

```xml
  <ItemGroup>
    <ProjectReference Include="..\PrimeService\PrimeService.csproj" />
  </ItemGroup>
```

Puede ver todo el archivo en el [repositorio de muestras](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService.Tests.csproj) en GitHub.

Una vez dispuesta esta estructura inicial, puede escribir la primera prueba.
Cuando haya comprobado esa primera prueba unitaria, todo estará configurado y deberá ejecutarse sin problemas a medida que agrega funciones y pruebas.

## <a name="creating-the-first-test"></a>Crear la primera prueba

Antes de crear la biblioteca o las pruebas, necesita ejecutar `dotnet restore` en los directorios *PrimeService* y *PrimeService.Tests*. Este comando restaura todos los paquetes de NuGet necesarios para cada proyecto.

El enfoque de TDD requiere la escritura de una prueba con errores, después la valida y finalmente repite el proceso. Por lo tanto, vamos a escribir esa prueba con errores. Quite *UnitTest1.cs* del directorio *PrimeService.Tests* y cree un nuevo archivo de C# denominado *PrimeService_IsPrimeShould.cs* con el siguiente contenido:

```cs
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

Guarde este archivo y ejecute `dotnet build` para compilar el proyecto de prueba.
Si no ha creado ya el proyecto `PrimeService`, el sistema de compilación lo detectará y lo compilará porque es una dependencia del proyecto de prueba.

Ahora, ejecute `dotnet test` para ejecutar las pruebas desde la consola.
El ejecutor de pruebas de MSTest tiene el punto de entrada del programa para ejecutar las pruebas desde la consola. `dotnet test` inicia el ejecutor de pruebas y proporciona un argumento de línea de comandos al ejecutor de pruebas que indica el ensamblado que contiene las pruebas.

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

En el directorio *PrimeService.Tests*, ejecute `dotnet test` de nuevo. El comando `dotnet test` ejecutará primero una compilación para el proyecto Prime.Services y, después, para el proyecto PrimeService.Tests. Después de compilar ambos proyectos, ejecutará esta prueba única. Pasa.

## <a name="adding-more-features"></a>Agregar más características

Ahora, que ha realizado una prueba correcta, es el momento de escribir más.
Hay algunos otros casos simples para números primos: 0, -1. Puede agregarlo como nuevas pruebas con el atributo `[TestMethod]` pero rápidamente este proceso se hace tedioso. Hay otros atributos de MSTest que le permiten escribir un conjunto de pruebas similares.  Un elemento `DataTestMethod` representa un conjunto de pruebas que ejecutan el mismo código, pero tienen diferentes argumentos de entrada.
Puede usar el atributo `[DataRow]` para especificar valores para esas entradas. 
 
 En lugar de crear nuevas pruebas, aproveche estos dos atributos para crear un método de prueba de datos único que pruebe algunos valores inferiores a 2, que es el número primo más bajo:

[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs#Sample_TestCode "Primeras pruebas")]

Ejecute `dotnet test` y verá que dos de estas pruebas producen un error.
Puede corregirlas modificando el servicio. Debe cambiar la cláusula `if` al principio del método:

```cs
if(candidate < 2)
```

Ahora, todas estas pruebas son correctas.

Puede continuar recorriendo en iteración al agregar más pruebas, más teorías y más código en la biblioteca principal. Rápidamente terminará con la [versión terminada de las pruebas](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs) y con la [implementación completa de la biblioteca](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService/PrimeService.cs).

Ha creado una biblioteca pequeña y un conjunto de pruebas unitarias para esa biblioteca.
Ha estructurado esta solución para que agregar nuevos paquetes y pruebas sea un proceso muy sencillo y pueda concentrarse en el problema en cuestión. Las herramientas se ejecutarán automáticamente.
