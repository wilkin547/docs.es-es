---
title: Opciones de valor
description: Obtenga información sobre la F# tipo de opción de valor, que es una versión de la estructura del tipo de opción.
ms.date: 02/06/2019
ms.openlocfilehash: e1036c83189c853b3704d94ca245e4818acc98c1
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/07/2019
ms.locfileid: "55828038"
---
# <a name="value-options"></a>Opciones de valor

El tipo de opción de valor F# se utiliza cuando mantiene los siguientes dos casos:

1. Un escenario es adecuado para un [ F# opción](options.md).
2. Uso de un struct mejora el rendimiento en su escenario.

No todos los escenarios sensibles al rendimiento se "solucionar" mediante el uso de estructuras. Debe tener en cuenta el costo adicional de copia cuando se usan en lugar de tipos de referencia. Sin embargo, gran F# programas suelen crear instancias de muchos tipos opcionales que fluyen a través de rutas de acceso activas y en estos casos, structs, es posible obtener un mejor rendimiento general durante la vigencia de un programa.

## <a name="definition"></a>de esquema JSON

Opción de valor se define como un [unión discriminada de struct](discriminated-unions.md#struct-discriminated-unions) que es similar al tipo de opción de referencia. De esta manera, se puede considerar su definición:

```fsharp
[<StructuralEquality; StructuralComparison>]
[<Struct>]
type ValueOption<'T> =
    | ValueNone
    | ValueSome of 'T
```

Opción de valor se ajusta a la comparación e igualdad estructural. La principal diferencia es que el nombre compilado, nombre de tipo y los nombres de casos indican que es un tipo de valor.

## <a name="using-value-options"></a>Uso de las opciones de valor

Opciones de valores se usan como [opciones](options.md). `ValueSome` se utiliza para indicar que un valor está presente, y `ValueNone` se usa cuando un valor no está presente:

```fsharp
let tryParseDateTime (s: string) =
    match System.DateTime.TryParse(s) with
    | (true, dt) -> ValueSome dt
    | (false, _) -> ValueNone

let possibleDateString1 = "1990-12-25"
let possibleDateString2 = "This is not a date"

let result1 = tryParseDateTime possibleDateString1
let result2 = tryParseDateTime possibleDateString2

match (result1, result2) with
| ValueSome d1, ValueSome d2 -> printfn "Both are dates!"
| ValueSome d1, ValueNone -> printfn "Only the first is a date!"
| ValueNone, ValueSome d2 -> printfn "Only the second is a date!"
| ValueNone, ValueNone -> printfn "None of them are dates!"
```

Igual que con [opciones](options.md), la convención de nomenclatura para una función que devuelve `ValueOption` es un prefijo con `try`.

## <a name="value-option-properties-and-methods"></a>Métodos y propiedades de la opción de valor

En este momento no hay una propiedad para las opciones de valor: `Value`. Un <xref:System.InvalidOperationException> se produce si ningún valor está presente cuando se invoca esta propiedad.

## <a name="value-option-functions"></a>Funciones con valores de opción

Actualmente hay una función de módulo enlazados para las opciones de valor, `defaultValueArg`:

```fsharp
val defaultValueArg : arg:'T voption -> defaultValue:'T -> 'T 
```

Igual que con el `defaultArg` función, `defaultValueArg` devuelve el valor subyacente de la opción de valor determinado si existe; de lo contrario, devuelve el valor predeterminado especificado.

En este momento, no hay ningún otras funciones de módulo enlazados para las opciones de valor.

## <a name="see-also"></a>Vea también

- [Opciones](options.md)
