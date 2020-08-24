---
title: Prueba unitaria de F# en .NET Core con dotnet test y MSTest
description: 'Aprenda los conceptos de pruebas unitarias para F# en .NET Core: cree paso a paso una solución de ejemplo mediante pruebas de dotnet y MSTest.'
author: billwagner
ms.author: wiwagn
ms.date: 08/30/2017
ms.openlocfilehash: 08aa0b4a36f399d4439a0f3b34e88a1b51e98215
ms.sourcegitcommit: c4a15c6c4ecbb8a46ad4e67d9b3ab9b8b031d849
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/20/2020
ms.locfileid: "88656545"
---
# <a name="unit-testing-f-libraries-in-net-core-using-dotnet-test-and-mstest"></a>Bibliotecas de F# de prueba unitaria en .NET Core con pruebas de dotnet y MSTest

Este tutorial le guía por una experiencia interactiva de creación de una solución de ejemplo paso a paso para aprender los conceptos de pruebas unitarias. Si prefiere seguir el tutorial con una solución precompilada, [vea o descargue el código de ejemplo](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-with-fsharp-mstest/) antes de comenzar. Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../../samples-and-tutorials/index.md#view-and-download-samples).

[!INCLUDE [testing an ASP.NET Core project from .NET Core](../../../includes/core-testing-note-aspnet.md)]

## <a name="creating-the-source-project"></a>Crear el proyecto de origen

Abra una ventana del Shell. Cree un directorio llamado *unit-testing-with-fsharp* que contenga la solución.
En este directorio nuevo, ejecute `dotnet new sln` para crear una solución nueva. Esto permite facilitar la administración de la biblioteca de clases y del proyecto de prueba unitaria.
En el directorio de la solución, cree un directorio *MathService*. Esta es la estructura de directorios y archivos hasta el momento:

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
```

Convierta *MathService* en el directorio actual y ejecute `dotnet new classlib -lang "F#"` para crear el proyecto de origen.  Creará una implementación de errores del servicio de matemáticas:

```fsharp
module MyMath =
    let squaresOfOdds xs = raise (System.NotImplementedException("You haven't written a test yet!"))
```

Cambie nuevamente el directorio al directorio *unit-testing-with-fsharp*. Ejecute `dotnet sln add .\MathService\MathService.fsproj` para agregar el proyecto de biblioteca de clases a la solución.

## <a name="creating-the-test-project"></a>Crear el proyecto de prueba

A continuación, cree el directorio *MathService.Tests*. En el esquema siguiente se muestra la estructura de directorios:

```console
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
        Source Files
        MathService.fsproj
    /MathService.Tests
```

Convierta el directorio *MathService.Tests* en el directorio actual y cree un proyecto nuevo con `dotnet new mstest -lang "F#"`. Esto crea un proyecto de prueba que usa MSTest como el marco de pruebas. La plantilla generada configura el ejecutor de pruebas en *MathServiceTests.fsproj*:

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.3.0-preview-20170628-02" />
  <PackageReference Include="MSTest.TestAdapter" Version="1.1.18" />
  <PackageReference Include="MSTest.TestFramework" Version="1.1.18" />
</ItemGroup>
```

El proyecto de prueba requiere otros paquetes para crear y ejecutar pruebas unitarias. `dotnet new` en el paso anterior agregó MSTest y el ejecutor de MSTest. Ahora, agregue la biblioteca de clases `MathService` como otra dependencia al proyecto. Use el comando `dotnet add reference`:

```dotnetcli
dotnet add reference ../MathService/MathService.fsproj
```

Puede ver todo el archivo en el [repositorio de muestras](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-with-fsharp/MathService.Tests/MathService.Tests.fsproj) en GitHub.

Tiene el diseño de solución final siguiente:

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
        Source Files
        MathService.fsproj
    /MathService.Tests
        Test Source Files
        MathServiceTests.fsproj
```

Ejecute `dotnet sln add .\MathService.Tests\MathService.Tests.fsproj` en el directorio *unit-testing-with-fsharp*.

## <a name="creating-the-first-test"></a>Crear la primera prueba

Escribirá una prueba de errores, la aprobará y, luego, repetirá el proceso. Abra *Tests.fs* y agregue el código siguiente:

```fsharp
namespace MathService.Tests

open System
open Microsoft.VisualStudio.TestTools.UnitTesting
open MathService

[<TestClass>]
type TestClass () =

    [<TestMethod>]
    member this.TestMethodPassing() =
        Assert.IsTrue(true)

    [<TestMethod>]
     member this.FailEveryTime() = Assert.IsTrue(false)
```

El atributo `[<TestClass>]` indica una clase que contiene pruebas. El atributo `[<TestMethod>]` indica un método de prueba que el ejecutor de pruebas ejecuta. En el directorio *unit-testing-with-fsharp*, ejecute `dotnet test` para compilar las pruebas y la biblioteca de clases y luego ejecutar las pruebas. El ejecutor de pruebas de MSTest tiene el punto de entrada del programa para ejecutar las pruebas desde la consola. `dotnet test` inicia el ejecutor de pruebas con el proyecto de prueba unitaria que creó.

Estas dos pruebas muestran las pruebas superadas y con errores más básicas. `My test` indica que se supera y `Fail every time` indica que no. Ahora, cree una prueba para el método `squaresOfOdds`. El método `squaresOfOdds` devuelve una lista de los cuadrados de todos los valores enteros impares que forman parte de la secuencia de entrada. En lugar de intentar escribir todas esas funciones a la vez, puede crear de forma iterativa pruebas que validen la funcionalidad. Hacer cada prueba superada significa crear la funcionalidad necesaria para el método.

La prueba más sencilla que se puede escribir es llamar a `squaresOfOdds` con todos los números impares, donde el resultado sea una secuencia de enteros vacía.  Aquí se muestra la prueba:

```fsharp
[<TestMethod>]
member this.TestEvenSequence() =
    let expected = Seq.empty<int> |> Seq.toList
    let actual = MyMath.squaresOfOdds [2; 4; 6; 8; 10]
    Assert.AreEqual(expected, actual)
```

Observe que la secuencia `expected` se convirtió en lista. La biblioteca de MSTest se basa en muchos tipos de .NET estándar. Esa dependencia significa que la interfaz pública y los resultados esperados admiten <xref:System.Collections.ICollection> en lugar de <xref:System.Collections.IEnumerable>.

Cuando ejecuta la prueba, se observa que no se supera la prueba. Todavía no ha creado la implementación. Cree esta prueba que se supera escribiendo el código más simple en la clase `Mathservice` que funciona:

```fsharp
let squaresOfOdds xs =
    Seq.empty<int> |> Seq.toList
```

En el directorio *unit-testing-with-fsharp*, vuelva a ejecutar `dotnet test`. El comando `dotnet test` ejecuta una compilación del proyecto `MathService` y luego del proyecto `MathService.Tests`. Después de compilar ambos proyectos, se ejecuta esta única prueba. Pasa.

## <a name="completing-the-requirements"></a>Finalización de los requisitos

Ahora que la prueba se ha superado, es el momento de escribir más. El próximo caso simple funciona con una secuencia cuyo único número impar es `1`. El número 1 es más simple, porque el cuadrado de 1 es 1. Aquí está la prueba siguiente:

```fsharp
[<TestMethod>]
member public this.TestOnesAndEvens() =
    let expected = [1; 1; 1; 1]
    let actual = MyMath.squaresOfOdds [2; 1; 4; 1; 6; 1; 8; 1; 10]
    Assert.AreEqual(expected, actual)
```

Si se ejecuta `dotnet test`, la prueba nueva se falla. Debe actualizar el método `squaresOfOdds` para controlar esta prueba nueva. Debe filtrar todos los números impares y quitarlos de la secuencia para que se supere esta prueba. Para hacerlo, escriba una función de filtro pequeña y use `Seq.filter`:

```fsharp
let private isOdd x = x % 2 <> 0

let squaresOfOdds xs =
    xs
    |> Seq.filter isOdd |> Seq.toList
```

Observe la llamada a `Seq.toList`. Esa acción crea una lista, que implemente la interfaz <xref:System.Collections.ICollection>.

Falta un paso todavía: el cuadrado de cada uno de los números impares. Comience escribiendo una prueba nueva:

```fsharp
[<TestMethod>]
member public this.TestSquaresOfOdds() =
    let expected = [1; 9; 25; 49; 81]
    let actual = MyMath.squaresOfOdds [1; 2; 3; 4; 5; 6; 7; 8; 9; 10]
    Assert.AreEqual(expected, actual)
```

Puede corregir la prueba si canaliza la secuencia filtrada a través de una operación de asignación para calcular el cuadrado de cada número impar:

```fsharp
let private square x = x * x
let private isOdd x = x % 2 <> 0

let squaresOfOdds xs =
    xs
    |> Seq.filter isOdd
    |> Seq.map square
    |> Seq.toList
```

Ha creado una biblioteca pequeña y un conjunto de pruebas unitarias para esa biblioteca. Ha estructurado la solución, por lo que agregar pruebas y paquetes nuevos es parte del flujo de trabajo normal. Ha centrado la mayor parte del tiempo y del esfuerzo en resolver los objetivos de la aplicación.

## <a name="see-also"></a>Vea también

- [dotnet new](../tools/dotnet-new.md)
- [dotnet sln](../tools/dotnet-sln.md)
- [dotnet add reference](../tools/dotnet-add-reference.md)
- [dotnet test](../tools/dotnet-test.md)
