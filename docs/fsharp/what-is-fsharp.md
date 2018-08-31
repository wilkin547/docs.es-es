---
title: '¿Qué es F #'
description: 'Obtenga información sobre lo que el lenguaje F # programación es y qué programación en F # como. Obtenga información sobre los tipos de datos enriquecidos, funciones y cómo encajan entre sí.'
ms.date: 08/03/2018
ms.openlocfilehash: 193747f380c61a387ed79ecca6abbcd90ee74376
ms.sourcegitcommit: fe02afbc39e78afd78cc6050e4a9c12a75f579f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2018
ms.locfileid: "43256715"
---
# <a name="what-is-f"></a>¿Qué es F # #

F # es un lenguaje de programación funcional que resulta muy fácil escribir código correcto y fácil de mantener.

Programación en F # principalmente implica definir tipos y funciones que son de tipo deduce y generalizadas automáticamente. Esto permite que el enfoque a permanecer en el dominio del problema y manipular los datos, en lugar de los detalles de la programación.

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

F # tiene numerosas características, incluidos:

* Sintaxis ligera
* Inmutables de manera predeterminada
* Generalización automática y la inferencia de tipos
* Funciones de primera clase
* Tipos de datos eficaces
* Detección de patrones
* Programación asincrónica

Un conjunto completo de características se documentan en el [referencia del lenguaje F #](language-reference/index.md).

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

F # registros y uniones discriminadas son distintos de null, inmutable y comparable de forma predeterminada, haciéndolos muy fácil de usar.

## <a name="enforced-correctness-with-functions-and-pattern-matching"></a>Corrección impuesto con funciones y coincidencia de patrones

Las funciones de F # son eficaces en la práctica y fácil declarar. Cuando se combina con [coincidencia de patrones](language-reference/pattern-matching.md), le permiten definir comportamiento cuya corrección se aplica por el compilador.

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

Las funciones de F # también son de primera clase, lo que significa que se pueden pasar como parámetros y devueltos por otras funciones.

## <a name="functions-to-define-operations-on-objects"></a>Funciones para definir las operaciones en objetos

F # es totalmente compatible con objetos, que son tipos de datos útiles cuando es necesario combinar datos y la funcionalidad. Las funciones de F # se usan para manipular objetos.

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

En lugar de escribir código que está orientada a objetos, en F #, a menudo escribirá código que trata los objetos como otro tipo de datos para las funciones para manipular. Características como [interfaces genéricas](language-reference/interfaces.md), [expresiones de objeto](language-reference/object-expressions.md)y un uso razonable de [miembros](language-reference/members/index.md) son comunes en F # programas más grandes.

## <a name="next-steps"></a>Pasos siguientes

Para obtener más información sobre un conjunto mayor de características de F #, consulte el [paseo por F #](tour.md).