---
title: Registros anónimos
description: Aprenda a usar los registros anónimos de construcción y uso, una característica de lenguaje que ayuda a la manipulación de datos.
ms.date: 06/12/2019
ms.openlocfilehash: 061fd3279c84b9a3161c687d9392947ee7ce9c83
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77453031"
---
# <a name="anonymous-records"></a>Registros anónimos

Los registros anónimos son agregados simples de valores con nombre que no es necesario declarar antes de su uso. Puede declararlos como Structs o tipos de referencia. Son tipos de referencia de forma predeterminada.

## <a name="syntax"></a>Sintaxis

En los siguientes ejemplos se muestra la sintaxis de registros anónimos. Los elementos delimitados como `[item]` son opcionales.

```fsharp
// Construct an anonymous record
let value-name = [struct] {| Label1: Type1; Label2: Type2; ...|}

// Use an anonymous record as a type parameter
let value-name = Type-Name<[struct] {| Label1: Type1; Label2: Type2; ...|}>

// Define a parameter with an anonymous record as input
let function-name (arg-name: [struct] {| Label1: Type1; Label2: Type2; ...|}) ...
```

## <a name="basic-usage"></a>Uso básico

Los registros anónimos se consideran como F# tipos de registro que no es necesario declarar antes de la creación de instancias.

Por ejemplo, aquí puede interactuar con una función que genera un registro anónimo:

```fsharp
open System

let getCircleStats radius =
    let d = radius * 2.0
    let a = Math.PI * (radius ** 2.0)
    let c = 2.0 * Math.PI * radius

    {| Diameter = d; Area = a; Circumference = c |}

let r = 2.0
let stats = getCircleStats r
printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
    r stats.Diameter stats.Area stats.Circumference
```

En el ejemplo siguiente se expande el anterior con una función `printCircleStats` que toma un registro anónimo como entrada:

```fsharp
open System

let getCircleStats radius =
    let d = radius * 2.0
    let a = Math.PI * (radius ** 2.0)
    let c = 2.0 * Math.PI * radius

    {| Diameter = d; Area = a; Circumference = c |}

let printCircleStats r (stats: {| Area: float; Circumference: float; Diameter: float |}) =
    printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
        r stats.Diameter stats.Area stats.Circumference

let r = 2.0
let stats = getCircleStats r
printCircleStats r stats
```

La llamada a `printCircleStats` con cualquier tipo de registro anónimo que no tenga la misma "forma" que el tipo de entrada no se compilará:

```fsharp
printCircleStats r {| Diameter = 2.0; Area = 4.0; MyCircumference = 12.566371 |}
// Two anonymous record types have mismatched sets of field names
// '["Area"; "Circumference"; "Diameter"]' and '["Area"; "Diameter"; "MyCircumference"]'
```

## <a name="struct-anonymous-records"></a>Struct de registros anónimos

Los registros anónimos también se pueden definir como struct con la palabra clave `struct` opcional. En el ejemplo siguiente se aumenta el anterior generando y consumiendo un registro anónimo de struct:

```fsharp
open System

let getCircleStats radius =
    let d = radius * 2.0
    let a = Math.PI * (radius ** 2.0)
    let c = 2.0 * Math.PI * radius

    // Note that the keyword comes before the '{| |}' brace pair
    struct {| Area = a; Circumference = c; Diameter = d |}

// the 'struct' keyword also comes before the '{| |}' brace pair when declaring the parameter type
let printCircleStats r (stats: struct {| Area: float; Circumference: float; Diameter: float |}) =
    printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
        r stats.Diameter stats.Area stats.Circumference

let r = 2.0
let stats = getCircleStats r
printCircleStats r stats
```

### <a name="structness-inference"></a>Inferencia de Structs

Los registros anónimos de struct también permiten la "inferencia de la estructura", donde no es necesario especificar la palabra clave `struct` en el sitio de llamada. En este ejemplo, Elide la palabra clave `struct` al llamar a `printCircleStats`:

```fsharp

let printCircleStats r (stats: struct {| Area: float; Circumference: float; Diameter: float |}) =
    printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
        r stats.Diameter stats.Area stats.Circumference

printCircleStats r {| Area = 4.0; Circumference = 12.6; Diameter = 12.6 |}
```

El patrón inverso, que especifica `struct` cuando el tipo de entrada no es un registro anónimo de struct, no se compilará.

## <a name="embedding-anonymous-records-within-other-types"></a>Incrustar registros anónimos dentro de otros tipos

Resulta útil declarar [uniones discriminadas](discriminated-unions.md) cuyos casos son registros. Pero si los datos de los registros son del mismo tipo que la Unión discriminada, debe definir todos los tipos como recursivos mutuamente. El uso de registros anónimos evita esta restricción. A continuación se muestra un tipo y una función de ejemplo que coincide con el patrón:

```fsharp
type FullName = { FirstName: string; LastName: string }

// Note that using a named for Manager and Executive would require mutually recursive definitions.
type Employee =
    | Engineer of FullName
    | Manager of {| Name: FullName; Reports: Employee list |}
    | Executive of {| Name: FullName; Reports: Employee list; Assistant: Employee |}

let getFirstName e =
    match e with
    | Engineer fullName -> fullName.FirstName
    | Manager m -> m.Name.FirstName
    | Executive ex -> ex.Name.FirstName
```

## <a name="copy-and-update-expressions"></a>Expresiones de copia y actualización

Los registros anónimos admiten la construcción con [expresiones de copia y actualización](copy-and-update-record-expressions.md). Por ejemplo, aquí se muestra cómo se puede crear una nueva instancia de un registro anónimo que copie los datos de una existente:

```fsharp
let data = {| X = 1; Y = 2 |}
let data' = {| data with Y = 3 |}
```

Sin embargo, a diferencia de los registros con nombre, los registros anónimos le permiten crear formularios totalmente diferentes con expresiones de copia y actualización. En el ejemplo siguiente se toma el mismo registro anónimo del ejemplo anterior y se expande en un nuevo registro anónimo:

```fsharp
let data = {| X = 1; Y = 2 |}
let expandedData = {| data with Z = 3 |} // Gives {| X=1; Y=2; Z=3 |}
```

También es posible construir registros anónimos a partir de instancias de registros con nombre:

```fsharp
type R = { X: int }
let data = { X = 1 }
let data' = {| data with Y = 2 |} // Gives {| X=1; Y=2 |}
```

También puede copiar datos a y desde los registros anónimos de referencia y de struct:

```fsharp
// Copy data from a reference record into a struct anonymous record
type R1 = { X: int }
let r1 = { X = 1 }

let data1 = struct {| r1 with Y = 1 |}

// Copy data from a struct record into a reference anonymous record
[<Struct>]
type R2 = { X: int }
let r2 = { X = 1 }

let data2 = {| r1 with Y = 1 |}

// Copy the reference anonymous record data into a struct anonymous record
let data3 = struct {| data2 with Z = r2.X |}
```

## <a name="properties-of-anonymous-records"></a>Propiedades de los registros anónimos

Los registros anónimos tienen una serie de características que son esenciales para comprender mejor cómo se pueden usar.

### <a name="anonymous-records-are-nominal"></a>Los registros anónimos son nominales

Los registros anónimos son [tipos nominales](https://en.wikipedia.org/wiki/Nominal_type_system). Se consideran mejores como tipos de [registros](records.md) con nombre (que también son nominales) que no requieren una declaración inicial.

Considere el ejemplo siguiente con dos declaraciones de registros anónimos:

```fsharp
let x = {| X = 1 |}
let y = {| Y = 1 |}
```

Los valores `x` y `y` tienen tipos diferentes y no son compatibles entre sí. No son equiparables y no son comparables. Para ilustrar esto, considere un equivalente de registro con nombre:

```fsharp
type X = { X: int }
type Y = { Y: int }

let x = { X = 1 }
let y = { Y = 1 }
```

No hay nada inherentemente diferente sobre los registros anónimos cuando se compara con sus equivalentes de registro con nombre cuando se trata de una comparación o equivalencia de tipos.

### <a name="anonymous-records-use-structural-equality-and-comparison"></a>Los registros anónimos usan comparación y igualdad estructural

Al igual que los tipos de registro, los registros anónimos son estructuralmente equiparables y comparables. Esto solo es cierto si todos los tipos constituyentes admiten la igualdad y la comparación, como sucede con los tipos de registro. Para admitir la igualdad o la comparación, dos registros anónimos deben tener la misma "forma".

```fsharp
{| a = 1+1 |} = {| a = 2 |} // true
{| a = 1+1 |} > {| a = 1 |} // true

// error FS0001: Two anonymous record types have mismatched sets of field names '["a"]' and '["a"; "b"]'
{| a = 1 + 1 |} = {| a = 2;  b = 1|}
```

### <a name="anonymous-records-are-serializable"></a>Los registros anónimos son serializables

Puede serializar los registros anónimos del mismo modo que con los registros con nombre. Este es un ejemplo de uso de [Newtonsoft. JSON](https://www.nuget.org/packages/Newtonsoft.Json/):

```fsharp
open Newtonsoft.Json

let phillip' = {| name="Phillip"; age=28 |}
let philStr = JsonConvert.SerializeObject(phillip') 

let phillip = JsonConvert.DeserializeObject<{|name: string; age: int|}>(philStr)
printfn "Name: %s Age: %d" phillip.name phillip.age
```

Los registros anónimos son útiles para enviar datos ligeros a través de una red sin necesidad de definir por adelantado un dominio para los tipos serializados y deserializados.

### <a name="anonymous-records-interoperate-with-c-anonymous-types"></a>Los registros anónimos interoperan con C# tipos anónimos

Es posible usar una API de .net que requiera el uso de [ C# tipos anónimos](../../csharp/programming-guide/classes-and-structs/anonymous-types.md). C#los tipos anónimos son triviales para interoperar con mediante registros anónimos. En el ejemplo siguiente se muestra cómo usar registros anónimos para llamar a una sobrecarga de [LINQ](../../csharp/programming-guide/concepts/linq/index.md) que requiere un tipo anónimo:

```fsharp
open System.Linq

let names = [ "Ana"; "Felipe"; "Emilia"]
let nameGrouping = names.Select(fun n -> {| Name = n; FirstLetter = n.[0] |})
for ng in nameGrouping do
    printfn "%s has first letter %c" ng.Name ng.FirstLetter
```

Hay muchas otras API usadas en .NET que requieren el uso del paso de un tipo anónimo. Los registros anónimos son la herramienta para trabajar con ellos.

## <a name="limitations"></a>Limitaciones

Los registros anónimos tienen algunas restricciones en su uso. Algunos son inherentes a su diseño, pero otros pueden cambiar.

### <a name="limitations-with-pattern-matching"></a>Limitaciones con la coincidencia de patrones

Los registros anónimos no admiten la coincidencia de patrones, a diferencia de los registros con nombre. Existen tres razones:

1. Un patrón tendría que tener en cuenta cada campo de un registro anónimo, a diferencia de los tipos de registro con nombre. Esto se debe a que los registros anónimos no admiten el subtipo estructural, sino que son tipos nominales.
2. Debido a (1), no hay ninguna posibilidad de tener patrones adicionales en una expresión de coincidencia de patrones, ya que cada patrón distinto implicaría un tipo de registro anónimo diferente.
3. Debido a (3), cualquier patrón de registro anónimo sería más detallado que el uso de la notación "punto".

Hay una sugerencia de lenguaje abierto para [permitir la coincidencia de patrones en contextos limitados](https://github.com/fsharp/fslang-suggestions/issues/713).

### <a name="limitations-with-mutability"></a>Limitaciones con mutabilidad

En la actualidad, no es posible definir un registro anónimo con datos de `mutable`. Hay una [sugerencia de lenguaje abierto](https://github.com/fsharp/fslang-suggestions/issues/732) para permitir datos mutables.

### <a name="limitations-with-struct-anonymous-records"></a>Limitaciones de los registros anónimos de struct

No es posible declarar registros anónimos de struct como `IsByRefLike` o `IsReadOnly`. Hay una [sugerencia de lenguaje abierto](https://github.com/fsharp/fslang-suggestions/issues/712) para `IsByRefLike` y `IsReadOnly` registros anónimos.
