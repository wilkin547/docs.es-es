---
title: Nameof
description: Obtenga información sobre el operador de nombre, una característica de metaprogramaciones que le permite generar el nombre de cualquier símbolo en el código fuente.
ms.date: 11/12/2020
ms.openlocfilehash: 9947d7172d1b73db5c181297ec8b1131382e1f5e
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "94688641"
---
# <a name="nameof"></a>Nameof

La `nameof` expresión genera una constante de cadena que coincide con el nombre en el origen para prácticamente cualquier construcción de F # en el código fuente.

## <a name="syntax"></a>Sintaxis

```fsharp
nameof symbol
nameof<'TGeneric>
```

## <a name="remarks"></a>Comentarios

`nameof` funciona resolviendo el símbolo que se le ha pasado y genera el nombre de ese símbolo tal y como se declara en el código fuente. Esto resulta útil en varios escenarios, como el registro, y protege el registro de los cambios en el código fuente.

```fsharp
let months =
    [
        "January"; "February"; "March"; "April";
        "May"; "June"; "July"; "August"; "September";
        "October"; "November"; "December"
    ]

let lookupMonth month =
    if (month > 12 || month < 1) then
        invalidArg (nameof month) ($"Value passed in was %d{month}.")

    months.[month-1]

printfn "%s" (lookupMonth 12)
printfn "%s" (lookupMonth 1)
printfn "%s" (lookupMonth 13)
```

La última línea producirá una excepción y se `"month"` mostrará en el mensaje de error.

Puede tomar un nombre de casi todas las construcciones de F #:

```fsharp
module M =
    let f x = nameof x

printfn $"{(M.f 12)]}"
printfn $"{(nameof M)}"
printfn $"{(nameof M.f)}"
```

`nameof` no es una función de primera clase y no se puede usar como tal. Esto significa que no se puede aplicar parcialmente y los valores no se pueden canalizar a él a través de los operadores de canalización de F #.

## <a name="nameof-on-operators"></a>Nombre en operadores

Los operadores de F # se pueden usar de dos maneras, como un texto de operador, o un símbolo que representa el formulario compilado. `nameof` en un operador, se generará el nombre del operador tal y como se declara en el origen. Para obtener el nombre compilado, use el nombre compilado en el origen:

```fsharp
nameof(+) // "+"
nameof op_Addition // "op_Addition"
```

## <a name="nameof-on-generics"></a>Nombre en genéricos

También puede tomar el nombre de un parámetro de tipo genérico, pero la sintaxis es diferente:

```fsharp
let f<'a> () = nameof<'a>
f() // "a"
```

`nameof<'TGeneric>` tomará el nombre del símbolo tal y como se define en el origen, no el nombre del tipo que se sustituye en un sitio de llamada.

El motivo por el que la sintaxis es diferente es alinear con otros operadores intrínsecos de F # como `typeof<>` y `typedefof<>` . Esto hace que F # sea coherente con respecto a los operadores que actúan en tipos genéricos y en cualquier otro elemento de origen.

## <a name="nameof-in-pattern-matching"></a>Nombre en coincidencia de patrones

El [ `nameof` patrón](pattern-matching.md#nameof-pattern) le permite usar `nameof` en una expresión de coincidencia de patrones como la siguiente:

```fsharp
let f (str: string) =
    match str with
    | nameof str -> "It's 'str'!"
    | _ -> "It is not 'str'!"

f "str" // matches
f "asdf" // does not match
```
