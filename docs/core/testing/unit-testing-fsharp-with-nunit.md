---
title: Bibliotecas de F# de prueba unitaria en .NET Core con pruebas de dotnet y NUnit
description: "Aprenda los conceptos de pruebas unitarias para F# en .NET Core: cree paso a paso una solución de ejemplo mediante pruebas de dotnet y NUnit."
author: rprouse
ms.date: 12/01/2017
ms.topic: article
dev_langs: fsharp
ms.prod: .net-core
ms.openlocfilehash: 27a7bb889fd736294252da39b1839b2197b8df03
ms.sourcegitcommit: 401c4427a3ec0d1263543033b3084039278509dc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2017
---
# <a name="unit-testing-f-libraries-in-net-core-using-dotnet-test-and-nunit"></a>Bibliotecas de F# de prueba unitaria en .NET Core con pruebas de dotnet y NUnit

Este tutorial le guía por una experiencia interactiva de creación de una solución de ejemplo paso a paso para aprender los conceptos de pruebas unitarias. Si prefiere seguir el tutorial con una solución precompilada, [vea o descargue el código de ejemplo](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/unit-testing-with-fsharp-nunit/) antes de comenzar. Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

## <a name="creating-the-source-project"></a>Crear el proyecto de origen

Abra una ventana del Shell. Cree un directorio llamado *unit-testing-with-fsharp* que contenga la solución.
En este directorio nuevo, ejecute [`dotnet new sln`](../tools/dotnet-new.md) para crear una solución nueva. Esto permite facilitar la administración de la biblioteca de clases y del proyecto de prueba unitaria.
En el directorio de la solución, cree un directorio *MathService*. Esta es la estructura de directorios y archivos hasta el momento:

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
```

Make *MathService* the current directory and run [`dotnet new classlib -lang F#`](../tools/dotnet-new.md) to create the source project.  Para usar el desarrollo controlado por pruebas (TDD), tendrá que crear una implementación de errores del servicio de matemáticas:

```fsharp
module MyMath =
    let sumOfSquares xs = raise (System.NotImplementedException("You haven't written a test yet!"))
```

Cambie nuevamente el directorio al directorio *unit-testing-with-fsharp*. Ejecute [`dotnet sln add .\MathService\MathService.fsproj`](../tools/dotnet-sln.md) para agregar el proyecto de biblioteca de clases a la solución.

## <a name="install-the-nunit-project-template"></a>Instalación de la plantilla de proyecto NUnit

Debe instalar las plantillas de proyecto de prueba NUnit para poder crear un proyecto de prueba. Solo deberá hacerlo una vez en cada máquina de desarrollador en la que creará proyectos NUnit. Ejecute [`dotnet new -i NUnit3.DotNetNew.Template`](../tools/dotnet-new.md) para instalar las plantillas NUnit.

 ```
 dotnet new -i NUnit3.DotNetNew.Template
 ```

## <a name="creating-the-test-project"></a>Crear el proyecto de prueba

A continuación, cree el directorio *MathService.Tests*. En el esquema siguiente se muestra la estructura de directorios:

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
        Source Files
        MathService.fsproj
    /MathService.Tests
```

Convierta el directorio *MathService.Tests* en el directorio actual y cree un proyecto nuevo con [`dotnet new nunit -lang F#`](../tools/dotnet-new.md). Esto crea un proyecto de prueba que usa NUnit como el marco de pruebas. La plantilla generada configura el ejecutor de pruebas en *MathServiceTests.fsproj*:

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.5.0" />
  <PackageReference Include="NUnit" Version="3.9.0" />
  <PackageReference Include="NUnit3TestAdapter" Version="3.9.0" />
</ItemGroup>
```

El proyecto de prueba requiere otros paquetes para crear y ejecutar pruebas unitarias. En el paso anterior, `dotnet new` agrega NUnit y el adaptador de prueba NUnit. Ahora, agregue la biblioteca de clases `MathService` como otra dependencia al proyecto. Use el comando [`dotnet add reference`](../tools/dotnet-add-reference.md):

```
dotnet add reference ../MathService/MathService.fsproj
```

Puede ver todo el archivo en el [repositorio de muestras](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-with-fsharp/MathService.Tests/MathService.Tests.fsproj) en GitHub.

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

Ejecute [`dotnet sln add .\MathService.Tests\MathService.Tests.fsproj`](../tools/dotnet-sln.md) en el directorio *unit-testing-with-fsharp*.

## <a name="creating-the-first-test"></a>Crear la primera prueba

El enfoque de TDD requiere la escritura de una prueba con errores, después la valida y finalmente repite el proceso. Abra *Tests.fs* y agregue el código siguiente:

```fsharp
namespace MathService.Tests

open System
open NUnit.Framework
open MathService

[<TestFixture>]
type TestClass () =

    [<Test>]
    member this.TestMethodPassing() =
        Assert.True(true)

    [<Test>]
     member this.FailEveryTime() = Assert.True(false)
```

El atributo `[<TestFixture>]` indica una clase que contiene pruebas. El atributo `[<Test>]` indica un método de prueba que el ejecutor de pruebas ejecuta. En el directorio *unit-testing-with-fsharp*, ejecute [`dotnet test`](../tools/dotnet-test.md) para compilar las pruebas y la biblioteca de clases y luego ejecutar las pruebas. El ejecutor de pruebas de NUnit tiene el punto de entrada del programa para ejecutar las pruebas desde la consola. `dotnet test` inicia el ejecutor de pruebas con el proyecto de prueba unitaria que creó.

Estas dos pruebas muestran las pruebas superadas y con errores más básicas. `My test` indica que se supera y `Fail every time` indica que no. Ahora, cree una prueba para el método `sumOfSquares`. El método `sumOfSquares` devuelve la suma de los cuadrados de todos los valores enteros impares que forman parte de la secuencia de entrada. En lugar de intentar escribir todas esas funciones a la vez, puede crear de forma iterativa pruebas que validen la funcionalidad. Hacer cada prueba superada significa crear la funcionalidad necesaria para el método.

La prueba más sencilla que se puede escribir es llamar a `sumOfSquares` con todos los números impares, donde el resultado sea una secuencia de enteros vacía.  Aquí se muestra la prueba:

```fsharp
[<Test>]
member this.TestEvenSequence() =
    let expected = Seq.empty<int> |> Seq.toList
    let actual = MyMath.sumOfSquares [2; 4; 6; 8; 10]
    Assert.That(actual, Is.EqualTo(expected))
```

Observe que la secuencia `expected` se convirtió en lista. El marco de NUnit se basa en muchos tipos de .NET estándar. Esa dependencia significa que la interfaz pública y los resultados esperados admiten <xref:System.Collections.ICollection> en lugar de <xref:System.Collections.IEnumerable>.

Cuando ejecuta la prueba, se observa que no se supera la prueba. Todavía no ha creado la implementación. Cree esta prueba escribiendo el código más simple en la clase `Mathservice` que funciona:

```csharp
let sumOfSquares xs =
    Seq.empty<int> |> Seq.toList
```

En el directorio *unit-testing-with-fsharp*, vuelva a ejecutar `dotnet test`. El comando `dotnet test` ejecuta una compilación del proyecto `MathService` y luego del proyecto `MathService.Tests`. Después de compilar ambos proyectos, se ejecuta esta única prueba. Pasa.

## <a name="completing-the-requirements"></a>Finalización de los requisitos

Ahora que la prueba se ha superado, es el momento de escribir más. El próximo caso simple funciona con una secuencia cuyo único número impar es `1`. El número 1 es más simple, porque el cuadrado de 1 es 1. Aquí está la prueba siguiente:

```fsharp
[<Test>]
member public this.SumOnesAndEvens() =
    let expected = [1; 1; 1; 1]
    let actual = MyMath.sumOfSquares [2; 1; 4; 1; 6; 1; 8; 1; 10]
    Assert.That(actual, Is.EqualTo(expected))
```

Si se ejecuta `dotnet test`, la prueba nueva se falla. Debe actualizar el método `sumOfSquares` para controlar esta prueba nueva. Debe filtrar todos los números impares y quitarlos de la secuencia para que se supere esta prueba. Para hacerlo, escriba una función de filtro pequeña y use `Seq.filter`:

```fsharp
let private isOdd x = x % 2 <> 0

let sumOfSquares xs =
    xs
    |> Seq.filter isOdd
    |> Seq.toList
```

Observe la llamada a `Seq.toList`. Esa acción crea una lista, que implemente la interfaz <xref:System.Collections.ICollection>.

Falta un paso todavía: el cuadrado de cada uno de los números impares. Comience escribiendo una prueba nueva:

```fsharp
[<Test>]
member public this.TestSquaresOfOdds() =
    let expected = [1; 9; 25; 49; 81]
    let actual = MyMath.sumOfSquares [1; 2; 3; 4; 5; 6; 7; 8; 9; 10]
    Assert.That(actual, Is.EqualTo(expected))
```

Puede corregir la prueba si canaliza la secuencia filtrada a través de una operación de asignación para calcular el cuadrado de cada número impar:

```fsharp
let private square x = x * x
let private isOdd x = x % 2 <> 0

let sumOfSquares xs =
    xs
    |> Seq.filter isOdd
    |> Seq.map square
    |> Seq.toList
```

Ha creado una biblioteca pequeña y un conjunto de pruebas unitarias para esa biblioteca. Ha estructurado la solución, por lo que agregar pruebas y paquetes nuevos es parte del flujo de trabajo normal. Ha centrado la mayor parte del tiempo y del esfuerzo en resolver los objetivos de la aplicación.
