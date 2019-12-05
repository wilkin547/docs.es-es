---
title: Opciones de valores
description: Obtenga información sobre F# el tipo de opción Value, que es una versión de struct del tipo de opción.
ms.date: 12/04/2019
ms.openlocfilehash: 0e9882ab4acdf2757705ef6022516d3572d87ef2
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837121"
---
# <a name="value-options"></a>Opciones de valores

El tipo de opción Value F# en se usa cuando se mantienen las dos circunstancias siguientes:

1. Un escenario es adecuado para una [ F# opción](options.md).
2. El uso de una estructura proporciona una ventaja de rendimiento en su escenario.

No todos los escenarios sensibles al rendimiento se "resuelven" mediante el uso de Structs. Debe tener en cuenta el costo adicional de copia cuando se usan en lugar de los tipos de referencia. Sin embargo, F# los programas de gran tamaño suelen crear instancias de muchos tipos opcionales que fluyen a través de rutas de acceso activas y, en tales casos, los Structs pueden obtener un mejor rendimiento general a lo largo de la duración de un programa.

## <a name="definition"></a>de esquema JSON

La opción Value se define como una [Unión discriminada de struct](discriminated-unions.md#struct-discriminated-unions) que es similar al tipo de opción de referencia. Su definición se puede considerar de esta manera:

```fsharp
[<StructuralEquality; StructuralComparison>]
[<Struct>]
type ValueOption<'T> =
    | ValueNone
    | ValueSome of 'T
```

La opción Value se ajusta a la igualdad estructural y a la comparación. La principal diferencia es que el nombre compilado, el nombre de tipo y los nombres de caso indican que se trata de un tipo de valor.

## <a name="using-value-options"></a>Usar opciones de valor

Las opciones de valor se usan de la misma manera que [las opciones](options.md). `ValueSome` se utiliza para indicar que un valor está presente y `ValueNone` se utiliza cuando un valor no está presente:

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

Como con [las opciones](options.md), la Convención de nomenclatura para una función que devuelve `ValueOption` es prefijarla con `try`.

## <a name="value-option-properties-and-methods"></a>Propiedades y métodos de la opción Value

En este momento hay una propiedad para las opciones de valor: `Value`. Se produce una <xref:System.InvalidOperationException> si no hay ningún valor presente cuando se invoca esta propiedad.

## <a name="value-option-functions"></a>Funciones de opción de valor

El módulo `ValueOption` de FSharp. Core contiene una funcionalidad equivalente al módulo `Option`. Hay algunas diferencias en el nombre, como `defaultValueArg`:

```fsharp
val defaultValueArg : arg:'T voption -> defaultValue:'T -> 'T
```

Esto actúa como `defaultArg` en el módulo de `Option`, pero funciona en una opción de valor en su lugar.

## <a name="see-also"></a>Vea también

- [Opciones](options.md)
