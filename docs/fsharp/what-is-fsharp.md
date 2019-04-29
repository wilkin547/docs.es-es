---
title: Qué esF#
description: Conozca los aspectos del F# lenguaje de programación es y qué F# programación es similar a. Obtenga información sobre los tipos de datos enriquecidos, funciones y cómo encajan entre sí.
ms.date: 08/03/2018
ms.openlocfilehash: ea82147e4e6d3c980fb224eeafd805c7ed53f8f2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756343"
---
# <a name="what-is-f"></a>¿Qué es F\#

F#es un lenguaje de programación funcional que resulta muy fácil escribir código correcto y fácil de mantener.

F#programación principalmente implica la definición de tipos y funciones que son de tipo deduce y generalizadas automáticamente. Esto permite que el enfoque a permanecer en el dominio del problema y manipular los datos, en lugar de los detalles de la programación.

```fsharp
open System // Gets access to functionality in System namespace.

// Defines a function that takes a name and produces a greeting.
let getGreeting name =
    sprintf "Hello, %s! Isn't F# great?" name

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

F#tiene numerosas características, incluidos:

* Sintaxis ligera
* Inmutables de manera predeterminada
* Generalización automática y la inferencia de tipos
* Funciones de primera clase
* Tipos de datos eficaces
* Detección de patrones
* Programación asincrónica

Un conjunto completo de características se documentan en el [ F# referencia del lenguaje](language-reference/index.md).

## <a name="rich-data-types"></a>Tipos de datos enriquecido

Tipos de datos como [registros](language-reference/records.md) y [uniones discriminadas](language-reference/discriminated-unions.md) le permite representar datos complejos y dominios.

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

F#registros y uniones discriminadas son distintos de null, inmutable y comparable de forma predeterminada, haciéndolos muy fácil de usar.

## <a name="enforced-correctness-with-functions-and-pattern-matching"></a>Corrección impuesto con funciones y coincidencia de patrones

F#las funciones son eficaces en la práctica y fácil declarar. Cuando se combina con [coincidencia de patrones](language-reference/pattern-matching.md), le permiten definir comportamiento cuya corrección se aplica por el compilador.

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

F#las funciones también son de primera clase, lo que significa que se pueden pasar como parámetros y devueltos por otras funciones.

## <a name="functions-to-define-operations-on-objects"></a>Funciones para definir las operaciones en objetos

F#es totalmente compatible con objetos, que son tipos de datos útiles cuando es necesario combinar datos y la funcionalidad. F#las funciones se usan para manipular objetos.

```fsharp
type Set<[<EqualityConditionOn>] ‘T when ‘T: comparison>(elements: seq<'T>) =
    member s.IsEmpty = // Implementation elided
    member s.Contains (value) =// Implementation elided
    member s.Add (value) = // Implementation elided
    // ...
    // Further Implementation elided
    // ...
    interface IEnumerable<‘T>
    interface IReadOnlyCollection<‘T>

[<RequireQualifiedAccess>]
module Set =
    let isEmpty (set: Set<'T>) = set.IsEmpty

    let contains element (set: Set<'T>) = set.Contains(element)

    let add value (set: Set<'T>) = set.Add(value)
```

En lugar de escribir código que está orientada a objetos, en F#, a menudo escribirá código que se trata como otro tipo de datos para las funciones para manipular los objetos. Características como [interfaces genéricas](language-reference/interfaces.md), [expresiones de objeto](language-reference/object-expressions.md)y un uso razonable de [miembros](language-reference/members/index.md) son comunes en mayor F# programas.

## <a name="next-steps"></a>Pasos siguientes

Para obtener más información sobre un conjunto mayor de F# características, consulte el [ F# paseo](tour.md).