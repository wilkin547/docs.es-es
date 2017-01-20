---
title: Pruebas unitarias de .NET Core mediante pruebas de dotnet
description: Pruebas unitarias de .NET Core mediante pruebas de dotnet
keywords: .NET, .NET Core
author: ardalis
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: bdcdb812-6f13-4f20-9e90-0c0977937142
translationtype: Human Translation
ms.sourcegitcommit: 5687fc7ded899a478d1972ffea10a1e37d40124b
ms.openlocfilehash: f1f08f550d7484869e67fe705dc789ca5dae8e2f

---

# <a name="unit-testing-in-net-core-using-dotnet-test"></a>Pruebas unitarias de .NET Core mediante pruebas de dotnet

Por [Steve Smith](http://ardalis.com) y [Bill Wagner](https://github.com/BillWagner).

[Ver o descargar el código de ejemplo](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/unit-testing-using-dotnet-test)

> [!NOTE]
> Este tema atañe a .NET Core 1.0.

## <a name="creating-the-projects"></a>Crear los proyectos

El artículo sobre [cómo escribir bibliotecas con herramientas multiplataforma](../tutorials/libraries.md) contiene información sobre la organización de las soluciones para varios proyectos tanto para el origen como para las pruebas. Este artículo sigue estas convenciones. La estructura del proyecto final tendrá un aspecto similar al siguiente:

```
/unit-testing-using-dotnet-test
|__global.json
|__/src
   |__/PrimeService
      |__Source Files
      |__project.json
|__/test
   |__/PrimeService.Tests
      |__Test Files
      |__project.json
```

En el directorio raíz, debe crear un `global.json` que contiene los nombres de los directorios `src` y `test`:

```json
{
    "projects": [
        "src",
        "test"
    ]
}
```

### <a name="creating-the-source-project"></a>Crear el proyecto de origen

Después, en el directorio `src`, cree el directorio `PrimeService`.
Cambie a ese directorio y ejecute `dotnet new -t lib` para crear el proyecto de origen.


Cambie el nombre de `Library.cs` en `PrimeService.cs`. Para usar el desarrollo controlado por pruebas (TDD), tendrá que crear una implementación de errores de la clase `PrimeService`:

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

Después, cambie al directorio 'test' y cree el directorio `PrimeServices.Tests`.
Cambie al directorio `PrimeServices.Tests` y cree un nuevo proyecto con `dotnet new -t xunittest`. `dotnet new -t xunittest` crea un proyecto de prueba que usa xunit como biblioteca de pruebas. 

La plantilla generada configuró el ejecutor de pruebas en la raíz de `project.json`:

```json
{
  "version": "1.0.0-*",
  "testRunner": "xunit",
  // ...
}
```

La plantilla también establece el nodo de la plataforma que va a usar `netcoreapp1.0` e incluye las importaciones necesarias para obtener xUnit.net para que funcione con .NET Core RTM:

```json
  "frameworks": {
    "netcoreapp1.0": {
      "imports": [
        "dotnet54",
        "portable-net45+win8" 
      ]
    }
  }
```

El proyecto de prueba requiere otros paquetes para crear y ejecutar pruebas unitarias.
`dotnet new` agregó xunit y el ejecutor de xunit. Debe agregar el paquete PrimeService como otra dependencia al proyecto:

```json
"dependencies": {
  "xunit":"2.1.0",
  "dotnet-test-xunit": "1.0.0-rc2-192208-24",
  "PrimeService": {
    "target": "project"
  }
}
```

Observe que el proyecto `PrimeService` no incluye ninguna información de la ruta de acceso de directorio. Dado que creó la estructura del proyecto para que coincida con la organización esperada de `src` y `test`, y el archivo `global.json` lo indica, el sistema de compilación encontrará la ubicación correcta para el proyecto. Agregará el elemento `"target": "project"` para informar a NuGet que debe buscar en los directorios del proyecto, no de la fuente de NuGet. Sin esta clave, puede descargar un paquete con el mismo nombre que la biblioteca interna.

Puede ver todo el archivo en el [repositorio de muestras](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/test/PrimeService.Tests/project.json) en GitHub.

Una vez dispuesta esta estructura inicial, puede escribir la primera prueba.
Cuando haya comprobado esa primera prueba unitaria, todo estará configurado y deberá ejecutarse sin problemas a medida que agrega funciones y pruebas.

## <a name="creating-the-first-test"></a>Crear la primera prueba

El enfoque de TDD requiere la escritura de una prueba con errores, después la valida y finalmente repite el proceso. Por lo tanto, vamos a escribir esa prueba con errores. Quite `program.cs` en el directorio `PrimeService.Tests` y cree un nuevo archivo de C# con el siguiente contenido:

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
El ejecutor de pruebas de xunit tiene el punto de entrada del programa para ejecutar las pruebas desde la consola. `dotnet test` inicia el ejecutor de pruebas y proporciona un argumento de línea de comandos al ejecutor de pruebas que indica el ensamblado que contiene las pruebas.

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
Hay algunos otros casos simples para números primos: 0, -1. Puede agregarlo como nuevas pruebas con el atributo `[Fact]` pero rápidamente este proceso se hace tedioso. Hay otros atributos de xunit que le permiten escribir un conjunto de pruebas similares.  Un elemento `Theory` representa un conjunto de pruebas que ejecutan el mismo código, pero tienen diferentes argumentos de entrada.
Puede usar el atributo `[InlineData]` para especificar valores para esas entradas. 
 
 En lugar de crear nuevas pruebas, aproveche estos dos atributos para crear una teoría que prueba algunos valores inferiores a 2, que es el número primo más bajo:

```cs
[Theory]
[InlineData(-1)]
[InlineData(0)]
[InlineData(1)]
public void ReturnFalseGivenValuesLessThan2(int value)
{
    var result = _primeService.IsPrime(value);

    Assert.False(result, $"{value} should not be prime");
}
```

Ejecute `dotnet test` y verá que dos de estas pruebas producen un error.
Puede corregirlas modificando el servicio. Debe cambiar la cláusula `if` al principio del método:

```cs
if(candidate < 2)
```

Ahora, todas estas pruebas son correctas.

Puede continuar recorriendo en iteración al agregar más pruebas, más teorías y más código en la biblioteca principal. Rápidamente terminará con la [versión terminada de las pruebas](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/test/PrimeService.Tests/PrimeServie_IsPrimeShould.cs) y con la [implementación completa de la biblioteca](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/src/PrimeService/PrimeService.cs).

Ha creado una biblioteca pequeña y un conjunto de pruebas unitarias para esa biblioteca.
Ha estructurado esta solución para que agregar nuevos paquetes y pruebas sea un proceso muy sencillo y pueda concentrarse en el problema en cuestión. Las herramientas se ejecutarán automáticamente.
   
   > [!TIP]
   > En la plataforma Windows puede usar MSTest. Obtenga más información en el artículo [sobre el uso de MSTest en documentos de Windows](./using-mstest-on-windows.md).



<!--HONumber=Jan17_HO3-->


