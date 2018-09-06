---
title: 'Opciones de valores (F #)'
description: 'Obtenga información sobre el tipo de opción de valor de F #, que es una versión de la estructura del tipo de opción.'
ms.date: 06/16/2018
ms.openlocfilehash: 5647ef61725401b10a6045b14eef11f5b041e3e9
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2018
ms.locfileid: "43747505"
---
# <a name="value-options"></a>Opciones de valor

El tipo de opción de valor en F # se utiliza cuando mantiene los siguientes dos casos:

1. Un escenario es adecuado para un [opción F #](options.md).
2. Uso de un struct mejora el rendimiento en su escenario.

No todos los escenarios sensibles al rendimiento se "solucionar" mediante el uso de estructuras. Debe tener en cuenta el costo adicional de copia cuando se usan en lugar de tipos de referencia. Sin embargo, programas de gran tamaño F # crear una instancia normalmente muchos tipos opcionales que fluyen a través de las rutas de acceso frecuente, porque structs a veces puede producir el mejor rendimiento general durante la vigencia de un programa.

## <a name="definition"></a>de esquema JSON

Opción de valor se define como un [unión discriminada de struct](discriminated-unions.md#struct-discriminated-unions) que es similar al tipo de opción de referencia:

```fsharp
[<StructuralEquality; StructuralComparison>]
[<CompiledName("FSharpValueOption`1")>]
[<Struct>]
type ValueOption<'T> =
    | ValueNone: 'T voption
    | ValueSome: 'T -> 'T voption

    member Value : 'T

and 'T voption = ValueOption<'T>
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