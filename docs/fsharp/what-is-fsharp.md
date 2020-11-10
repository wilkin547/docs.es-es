---
title: ¿Qué es F#?
description: 'Obtenga información sobre el lenguaje de programación de F # y la programación de F #. Obtenga información sobre los tipos de datos enriquecidos, las funciones y cómo encajan entre sí.'
ms.date: 08/03/2018
ms.openlocfilehash: 37dc2f472d65a046e4bf67e672e2a96f4d4afded
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2020
ms.locfileid: "94439667"
---
# <a name="what-is-f"></a>Qué es F\#

F # es un lenguaje de programación funcional que facilita la escritura de código correcto y fácil de mantener.

La programación en F # implica principalmente la definición de tipos y funciones que se infieren de tipo y se generalizan automáticamente. Esto permite que el foco permanezca en el dominio del problema y manipule sus datos, en lugar de los detalles de la programación.

```fsharp
open System // Gets access to functionality in System namespace.

// Defines a function that takes a name and produces a greeting.
let getGreeting name = $"Hello, {name}! Isn't F# great?"

[<EntryPoint>]
let main args =
    // Defines a list of names
    let names = [ "Don"; "Julia"; "Xi" ]

    // Prints a greeting for each name!
    names
    |> List.map getGreeting
    |> List.iter (fun greeting -> printfn "%s" greeting)

    0
```

F # tiene numerosas características, entre las que se incluyen:

* Sintaxis ligera
* Inmutable de forma predeterminada
* Inferencia de tipos y generalización automática
* Funciones de primera clase
* Tipos de datos eficaces
* Detección de patrones
* Programación asincrónica

En la [Referencia del lenguaje F #](./language-reference/index.md)se documenta un conjunto completo de características.

## <a name="rich-data-types"></a>Tipos de datos enriquecidos

Los tipos de datos como [registros](./language-reference/records.md) y [uniones discriminadas](./language-reference/discriminated-unions.md) permiten representar dominios y datos complejos.

```fsharp
// Group data with Records
type SuccessfulWithdrawal = {
    Amount: decimal
    Balance: decimal
}

type FailedWithdrawal = {
    Amount: decimal
    Balance: decimal
    IsOverdraft: bool
}

// Use discriminated unions to represent data of 1 or more forms
type WithdrawalResult =
    | Success of SuccessfulWithdrawal
    | InsufficientFunds of FailedWithdrawal
    | CardExpired of System.DateTime
    | UndisclosedFailure
```

Los registros de F # y las uniones discriminadas son no NULL, inmutables y comparables de forma predeterminada, lo que facilita su uso.

## <a name="enforced-correctness-with-functions-and-pattern-matching"></a>Aplicación de corrección con funciones y coincidencia de patrones

Las funciones de F # son fáciles de declarar y eficaces en la práctica. Cuando se combina con la [coincidencia de patrones](./language-reference/pattern-matching.md), permiten definir el comportamiento cuya corrección se aplica mediante el compilador.

```fsharp
// Returns a WithdrawalResult
let withdrawMoney amount = // Implementation elided

let handleWithdrawal amount =
    let w = withdrawMoney amount

    // The F# compiler enforces accounting for each case!
    match w with
    | Success s -> printfn "Successfully withdrew %f" s.Amount
    | InsufficientFunds f -> printfn "Failed: balance is %f" f.Balance
    | CardExpired d -> printfn "Failed: card expired on %O" d
    | UndisclosedFailure -> printfn "Failed: unknown :("
```

Las funciones de F # son también de primera clase, lo que significa que se pueden pasar como parámetros y devolverse desde otras funciones.

## <a name="functions-to-define-operations-on-objects"></a>Funciones para definir operaciones en objetos

F # es totalmente compatible con objetos, que son tipos de datos útiles cuando es necesario combinar datos y funcionalidad. Las funciones de F # se utilizan para manipular objetos.

```fsharp
type Set<'T when 'T: comparison>(elements: seq<'T>) =
    member s.IsEmpty = // Implementation elided
    member s.Contains (value) =// Implementation elided
    member s.Add (value) = // Implementation elided
    // ...
    // Further Implementation elided
    // ...
    interface IEnumerable<‘T>
    interface IReadOnlyCollection<‘T>

module Set =
    let isEmpty (set: Set<'T>) = set.IsEmpty

    let contains element (set: Set<'T>) = set.Contains(element)

    let add value (set: Set<'T>) = set.Add(value)
```

En lugar de escribir código orientado a objetos, en F #, a menudo escribirá código que trata los objetos como otro tipo de datos para las funciones que se van a manipular. Las características como las [interfaces genéricas](./language-reference/interfaces.md), las [expresiones de objeto](./language-reference/object-expressions.md)y el uso prudente de [los miembros](./language-reference/members/index.md) son comunes en los programas de F # más grandes.

## <a name="next-steps"></a>Pasos siguientes

Para obtener más información sobre un conjunto mayor de características de F #, consulte el [paseo por f #](tour.md).
