---
title: ¿Qué es F#?
description: Obtenga información sobre qué F# es el lenguaje de programación F# y qué programación es como. Obtenga información sobre los tipos de datos enriquecidos, las funciones y cómo encajan entre sí.
ms.date: 08/03/2018
ms.openlocfilehash: 3cba509f59a8e81e1a0264de7451e9d80304d768
ms.sourcegitcommit: 8b8dd14dde727026fd0b6ead1ec1df2e9d747a48
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "71332730"
---
# <a name="what-is-f"></a><span data-ttu-id="ce163-104">Qué es F\#</span><span class="sxs-lookup"><span data-stu-id="ce163-104">What is F\#</span></span>

<span data-ttu-id="ce163-105">F#es un lenguaje de programación funcional que facilita la escritura de código correcto y fácil de mantener.</span><span class="sxs-lookup"><span data-stu-id="ce163-105">F# is a functional programming language that makes it easy to write correct and maintainable code.</span></span>

<span data-ttu-id="ce163-106">F#la programación implica principalmente definir tipos y funciones que se infieren de tipo y se generalizan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="ce163-106">F# programming primarily involves defining types and functions that are type-inferred and generalized automatically.</span></span> <span data-ttu-id="ce163-107">Esto permite que el foco permanezca en el dominio del problema y manipule sus datos, en lugar de los detalles de la programación.</span><span class="sxs-lookup"><span data-stu-id="ce163-107">This allows your focus to remain on the problem domain and manipulating its data, rather than the details of programming.</span></span>

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

<span data-ttu-id="ce163-108">F#tiene numerosas características, entre las que se incluyen:</span><span class="sxs-lookup"><span data-stu-id="ce163-108">F# has numerous features, including:</span></span>

* <span data-ttu-id="ce163-109">Sintaxis ligera</span><span class="sxs-lookup"><span data-stu-id="ce163-109">Lightweight syntax</span></span>
* <span data-ttu-id="ce163-110">Inmutable de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="ce163-110">Immutable by default</span></span>
* <span data-ttu-id="ce163-111">Inferencia de tipos y generalización automática</span><span class="sxs-lookup"><span data-stu-id="ce163-111">Type inference and automatic generalization</span></span>
* <span data-ttu-id="ce163-112">Funciones de primera clase</span><span class="sxs-lookup"><span data-stu-id="ce163-112">First-class functions</span></span>
* <span data-ttu-id="ce163-113">Tipos de datos eficaces</span><span class="sxs-lookup"><span data-stu-id="ce163-113">Powerful data types</span></span>
* <span data-ttu-id="ce163-114">Detección de patrones</span><span class="sxs-lookup"><span data-stu-id="ce163-114">Pattern matching</span></span>
* <span data-ttu-id="ce163-115">Programación asincrónica</span><span class="sxs-lookup"><span data-stu-id="ce163-115">Async programming</span></span>

<span data-ttu-id="ce163-116">En la [ F# referencia del lenguaje](./language-reference/index.md)se documenta un conjunto completo de características.</span><span class="sxs-lookup"><span data-stu-id="ce163-116">A full set of features are documented in the [F# language reference](./language-reference/index.md).</span></span>

## <a name="rich-data-types"></a><span data-ttu-id="ce163-117">Tipos de datos enriquecidos</span><span class="sxs-lookup"><span data-stu-id="ce163-117">Rich data types</span></span>

<span data-ttu-id="ce163-118">Los tipos de datos como [registros](./language-reference/records.md) y [uniones discriminadas](./language-reference/discriminated-unions.md) permiten representar dominios y datos complejos.</span><span class="sxs-lookup"><span data-stu-id="ce163-118">Data types such as [Records](./language-reference/records.md) and [Discriminated Unions](./language-reference/discriminated-unions.md) let you represent complex data and domains.</span></span>

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

<span data-ttu-id="ce163-119">F#los registros y las uniones discriminadas son no NULL, inmutables y comparables de forma predeterminada, lo que facilita su uso.</span><span class="sxs-lookup"><span data-stu-id="ce163-119">F# records and discriminated unions are non-null, immutable, and comparable by default, making them very easy to use.</span></span>

## <a name="enforced-correctness-with-functions-and-pattern-matching"></a><span data-ttu-id="ce163-120">Aplicación de corrección con funciones y coincidencia de patrones</span><span class="sxs-lookup"><span data-stu-id="ce163-120">Enforced correctness with functions and pattern matching</span></span>

<span data-ttu-id="ce163-121">F#las funciones son fáciles de declarar y eficaces en la práctica.</span><span class="sxs-lookup"><span data-stu-id="ce163-121">F# functions are easy to declare and powerful in practice.</span></span> <span data-ttu-id="ce163-122">Cuando se combina con la [coincidencia de patrones](./language-reference/pattern-matching.md), permiten definir el comportamiento cuya corrección se aplica mediante el compilador.</span><span class="sxs-lookup"><span data-stu-id="ce163-122">When combined with [pattern matching](./language-reference/pattern-matching.md), they allow you to define behavior whose correctness is enforced by the compiler.</span></span>

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

<span data-ttu-id="ce163-123">F#las funciones son también de primera clase, lo que significa que se pueden pasar como parámetros y devolverse desde otras funciones.</span><span class="sxs-lookup"><span data-stu-id="ce163-123">F# functions are also first-class, meaning they can be passed as parameters and returned from other functions.</span></span>

## <a name="functions-to-define-operations-on-objects"></a><span data-ttu-id="ce163-124">Funciones para definir operaciones en objetos</span><span class="sxs-lookup"><span data-stu-id="ce163-124">Functions to define operations on objects</span></span>

<span data-ttu-id="ce163-125">F#tiene compatibilidad total con objetos, que son tipos de datos útiles cuando es necesario combinar datos y funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="ce163-125">F# has full support for objects, which are useful data types when you need to blend data and functionality.</span></span> <span data-ttu-id="ce163-126">F#las funciones se usan para manipular objetos.</span><span class="sxs-lookup"><span data-stu-id="ce163-126">F# functions are used to manipulate objects.</span></span>

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

<span data-ttu-id="ce163-127">En lugar de escribir código orientado a objetos, en F#, a menudo escribirá código que trata los objetos como otro tipo de datos para las funciones que se van a manipular.</span><span class="sxs-lookup"><span data-stu-id="ce163-127">Rather than writing code that is object-oriented, in F#, you will often write code that treats objects as another data type for functions to manipulate.</span></span> <span data-ttu-id="ce163-128">Las características como las [interfaces genéricas](./language-reference/interfaces.md), las [expresiones de objeto](./language-reference/object-expressions.md)y el uso prudente de [los miembros](./language-reference/members/index.md) son comunes en los programas más grandes. F#</span><span class="sxs-lookup"><span data-stu-id="ce163-128">Features such as [generic interfaces](./language-reference/interfaces.md), [object expressions](./language-reference/object-expressions.md), and judicious use of [members](./language-reference/members/index.md) are common in larger F# programs.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ce163-129">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="ce163-129">Next steps</span></span>

<span data-ttu-id="ce163-130">Para obtener más información acerca de un conjunto F# mayor de características, consulte el [ F# paseo](tour.md).</span><span class="sxs-lookup"><span data-stu-id="ce163-130">To learn more about a larger set of F# features, check out the [F# Tour](tour.md).</span></span>
