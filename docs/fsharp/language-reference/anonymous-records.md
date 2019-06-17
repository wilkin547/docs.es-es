---
title: Registros anónimos
description: Obtenga información sobre cómo usar la construcción y use registros anónimos, una característica del lenguaje que ayuda en la manipulación de datos.
ms.date: 06/12/2019
ms.openlocfilehash: e576210d4fb76ccfd09f8feb157ef4542aa94ccf
ms.sourcegitcommit: c4dfe37032c64a1fba2cc3d5947550d79f95e3b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/13/2019
ms.locfileid: "67041809"
---
# <a name="anonymous-records"></a>Registros anónimos

Registros anónimos son agregados simples de valores con nombre que no es necesario declarar antes de utilizarlo. Se puede declarar como tipos de structs o referencia. Son tipos de referencia de forma predeterminada.

## <a name="syntax"></a>Sintaxis

Los ejemplos siguientes muestran la sintaxis de registro anónimo. Los elementos delimitados como `[item]` son opcionales.

```fsharp
// Construct an anonymous record
let value-name = [struct] {| Label1: Type1; Label2: Type2; ...|}

// Use an anonymous record as a type parameter
let value-name = Type-Name<[struct] {| Label1: Type1; Label2: Type2; ...|}>

// Define a parameter with an anonymous record as input
let function-name (arg-name: [struct] {| Label1: Type1; Label2: Type2; ...|}) ...
```

## <a name="basic-usage"></a>Uso básico

Registros anónimos mejor están pensados como F# tipos que no necesitan declararse antes de la creación de instancias de registros.

Por ejemplo, aquí cómo pueden interactuar con una función que genera un registro anónimo:

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

El ejemplo siguiente se expande en el anterior con un `printCircleStats` función que toma un registro anónimo como entrada:

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

Una llamada a `printCircleStats` con cualquier tipo de registro anónimo que no tiene la misma "forma" como el tipo de entrada no se compilará:

```fsharp
printCircleStats r {| Diameter = 2.0; Area = 4.0; MyCircumference = 12.566371 |}
// Two anonymous record types have mismatched sets of field names
// '["Area"; "Circumference"; "Diameter"]' and '["Area"; "Diameter"; "MyCircumference"]'
```

## <a name="struct-anonymous-records"></a>Registros de struct anónimos

Registros anónimos también pueden definirse como struct con el elemento opcional `struct` palabra clave. El ejemplo siguiente aumenta lo anterior al producir y consumir un registro de struct anónimo:

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

### <a name="structness-inference"></a>Inferencia Structness

Registros de struct anónimos también permiten "structness inferencia" donde no es necesario especificar el `struct` palabra clave en el sitio de llamada. En este ejemplo, elide el `struct` palabra clave al llamar a `printCircleStats`:

```fsharp

let printCircleStats r (stats: struct {| Area: float; Circumference: float; Diameter: float |}) =
    printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
        r stats.Diameter stats.Area stats.Circumference

printCircleStats r {| Area = 4.0; Circumference = 12.6; Diameter = 12.6 |}
```

El orden inverso de patrón - especificar `struct` cuando el tipo de entrada no es un registro struct anónimo: no se compilará.

## <a name="embedding-anonymous-records-within-other-types"></a>Insertar registros anónimos dentro de otros tipos

Es útil declarar [uniones discriminadas](discriminated-unions.md) cuyos casos son los registros. Pero si los datos de los registros son el mismo tipo que la unión discriminada, debe definir todos los tipos como mutuamente recursivas. Uso de registros anónimos evita esta restricción. Lo que sigue es un ejemplo de tipo y función coincide con ese patrón encima de él:

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

## <a name="copy-and-update-expressions"></a>Copiar y actualizar las expresiones

Registros anónimos admiten una construcción con [copiar y actualizar las expresiones](copy-and-update-record-expressions.md). Por ejemplo, mostramos cómo puede crear una nueva instancia de un registro anónimo que copia existente de datos:

```fsharp
let data = {| X = 1; Y = 2 |}
let data' = {| data with Y = 3 |}
```

Sin embargo, a diferencia de los registros con nombre, registros anónimos le permiten construir formularios completamente diferentes con copia y actualizar las expresiones. El ejemplo siguiente toma el mismo registro anónimo del ejemplo anterior y expande en un nuevo registro anónimo:

```fsharp
let data = {| X = 1; Y = 2 |}
let expandedData = {| data with Z = 3 |} // Gives {| X=1; Y=2; Z=3 |}
```

También es posible crear registros anónimos de instancias de registros con nombre:

```fsharp
type R = { X: int }
let data = { X = 1 }
let data' = {| data with Y = 2 |} // Gives {| X=1; Y=2 |}
```

También puede copiar datos hacia y desde registros anónimos de referencia y struct:

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

## <a name="properties-of-anonymous-records"></a>Propiedades de registros anónimos

Registros anónimos tienen un número de características que son esenciales para entender cómo se puede usar.

### <a name="anonymous-records-are-nominal"></a>Registros anónimos son nominales

Registros anónimos son [tipos nominales](https://en.wikipedia.org/wiki/Nominal_type_system). Como con nombre son entiende mejor [registro](records.md) tipos (que también son nominales) que no requieren una declaración por adelantado.

Considere el siguiente ejemplo con dos declaraciones de registro anónimo:

```fsharp
let x = {| X = 1 |}
let y = {| Y = 1 |}
```

El `x` y `y` tienen distintos tipos de valores y no son compatibles entre sí. No son equivalentes y no son comparables. Para ilustrar esto, considere la posibilidad de un registro con nombre equivalente:

```fsharp
type X = { X: int }
type Y = { Y: int }

let x = { X = 1 }
let y = { Y = 1 }
```

No hay nada esencialmente distinto en registros anónimos cuando se comparan con sus equivalentes de registro con nombre cuando relativas a la equivalencia de tipos o comparación.

### <a name="anonymous-records-use-structural-equality-and-comparison"></a>Registros anónimos, use comparación e igualdad estructural

Al igual que los tipos de registros, registros anónimos son estructuralmente equivalentes y comparable. Esto solo es true si todos los tipos constituyentes admiten igualdad y comparación, al igual que con los tipos de registros. Para admitir la comparación o igualdad, dos registros anónimos deben tener la misma "forma".

```fsharp
{| a = 1+1 |} = {| a = 2 |} // true
{| a = 1+1 |} > {| a = 1 |} // true

// error FS0001: Two anonymous record types have mismatched sets of field names '["a"]' and '["a"; "b"]'
{| a = 1 + 1 |} = {| a = 2;  b = 1|}
```

### <a name="anonymous-records-are-serializable"></a>Registros anónimos son serializables

Puede serializar registros anónimos se puede hacer con registros con nombre. Este es un ejemplo con [Newtonsoft.Json](https://www.nuget.org/packages/Newtonsoft.Json/):

```fsharp
open Newtonsoft.Json

let phillip = {| name="Phillip"; age=28 |}
JsonConvert.SerializeObject(phillip)

let phillip = JsonConvert.DeserializeObject<{|name: string; age: int|}>(str)
printfn "Name: %s Age: %d" phillip.name phillip.age
```

Registros anónimos son útiles para el envío de datos ligero a través de una red sin necesidad de definir un dominio para los tipos serializa y deserializa por adelantado.

### <a name="anonymous-records-interoperate-with-c-anonymous-types"></a>Registros anónimos interoperan con C# tipos anónimos

Es posible usar una API de .NET que requiere el uso de [ C# tipos anónimos](../../csharp/programming-guide/classes-and-structs/anonymous-types.md). C#tipos anónimos son triviales para interoperar con registros anónimos. En el ejemplo siguiente se muestra cómo utilizar registros anónimos para llamar a un [LINQ](../../csharp/programming-guide/concepts/linq/index.md) sobrecarga que requiere un tipo anónimo:

```fsharp
open System.Linq

let names = [ "Ana"; "Felipe"; "Emilia"]
let nameGrouping = names.Select(fun n -> {| Name = n; FirstLetter = n.[0] |})
for ng in nameGrouping do
    printfn "%s has first letter %c" ng.Name ng.FirstLetter
```

Hay una gran cantidad de otra API que se usan a lo largo de .NET que requieren el uso de cómo pasar un tipo anónimo. Registros anónimos son la herramienta para trabajar con ellos.

## <a name="limitations"></a>Limitaciones

Registros anónimos tienen algunas restricciones de su uso. Algunas son inherentes a su diseño, pero otras son susceptibles de cambiar.

### <a name="limitations-with-pattern-matching"></a>Limitaciones de coincidencia de patrones

Registros anónimos no admiten la coincidencia de patrones, a diferencia de los registros con nombre. Existen tres razones:

1. Tendría un patrón para tener en cuenta todos los campos de un registro anónimo, a diferencia de los tipos de registros con nombre. Esto es porque no admiten registros anónimos subtipo estructural, sino que son tipos nominales.
2. Debido a (1), no hay ninguna posibilidad de ver patrones adicionales en una expresión de coincidencia de patrón, como cada patrón distinto implicaría un tipo de registro anónimo diferentes.
3. Debido a (3), cualquier modelo de registro anónimo sería más detallado que el uso de la notación "punto".

Hay una sugerencia de lenguaje abierto para [permiten la coincidencia de patrones limitada en contextos](https://github.com/fsharp/fslang-suggestions/issues/713).

### <a name="limitations-with-mutability"></a>Limitaciones con mutabilidad

No es actualmente posible definir un registro anónimo con `mutable` datos. Hay un [abrir sugerencia lenguaje](https://github.com/fsharp/fslang-suggestions/issues/732) para permitir que los datos mutables.

### <a name="limitations-with-struct-anonymous-records"></a>Limitaciones de los registros de struct anónimos

No es posible declarar struct registros anónimos como `IsByRefLike` o `IsReadOnly`. Hay un [abrir sugerencia lenguaje](https://github.com/fsharp/fslang-suggestions/issues/712) a para `IsByRefLike` y `IsReadOnly` registros anónimos.
