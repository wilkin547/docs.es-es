---
title: Resultados
description: Obtenga información sobre cómo usar F# el tipo ' result ' para ayudarle a escribir código tolerante a errores.
ms.date: 04/24/2017
ms.openlocfilehash: 187aa26ccbaac7e0ec998756377bb7b0489eb1ab
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424852"
---
# <a name="results"></a><span data-ttu-id="c25c8-103">Resultados</span><span class="sxs-lookup"><span data-stu-id="c25c8-103">Results</span></span>

<span data-ttu-id="c25c8-104">A partir F# de 4,1, hay un tipo de `Result<'T,'TFailure>` que puede usar para escribir código tolerante a errores que se puede componer.</span><span class="sxs-lookup"><span data-stu-id="c25c8-104">Starting with F# 4.1, there is a `Result<'T,'TFailure>` type which you can use for writing error-tolerant code which can be composed.</span></span>

## <a name="syntax"></a><span data-ttu-id="c25c8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c25c8-105">Syntax</span></span>

```fsharp
// The definition of Result in FSharp.Core
[<StructuralEquality; StructuralComparison>]
[<CompiledName("FSharpResult`2")>]
[<Struct>]
type Result<'T,'TError> =
    | Ok of ResultValue:'T
    | Error of ErrorValue:'TError
```

## <a name="remarks"></a><span data-ttu-id="c25c8-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c25c8-106">Remarks</span></span>

<span data-ttu-id="c25c8-107">Tenga en cuenta que el tipo de resultado es una [Unión discriminada de struct](discriminated-unions.md#struct-discriminated-unions), que es F# otra característica presentada en 4,1.</span><span class="sxs-lookup"><span data-stu-id="c25c8-107">Note that the result type is a [struct discriminated union](discriminated-unions.md#struct-discriminated-unions), which is another feature introduced in F# 4.1.</span></span>  <span data-ttu-id="c25c8-108">La semántica de igualdad estructural se aplica aquí.</span><span class="sxs-lookup"><span data-stu-id="c25c8-108">Structural equality semantics apply here.</span></span>

<span data-ttu-id="c25c8-109">El tipo de `Result` se usa normalmente en el control de errores de Monad, que a menudo se conoce como [programación orientada a ferrocarriles](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/posts/recipe-part2.html) dentro de la F# comunidad.</span><span class="sxs-lookup"><span data-stu-id="c25c8-109">The `Result` type is typically used in monadic error-handling, which is often referred to as [Railway-oriented Programming](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/posts/recipe-part2.html) within the F# community.</span></span>  <span data-ttu-id="c25c8-110">En el siguiente ejemplo trivial se muestra este enfoque.</span><span class="sxs-lookup"><span data-stu-id="c25c8-110">The following trivial example demonstrates this approach.</span></span>

```fsharp
// Define a simple type which has fields that can be validated
type Request =
    { Name: string
      Email: string }

// Define some logic for what defines a valid name.
//
// Generates a Result which is an Ok if the name validates;
// otherwise, it generates a Result which is an Error.
let validateName req =
    match req.Name with
    | null -> Error "No name found."
    | "" -> Error "Name is empty."
    | "bananas" -> Error "Bananas is not a name."
    | _ -> Ok req

// Similarly, define some email validation logic.
let validateEmail req =
    match req.Email with
    | null -> Error "No email found."
    | "" -> Error "Email is empty."
    | s when s.EndsWith("bananas.com") -> Error "No email from bananas.com is allowed."
    | _ -> Ok req

let validateRequest reqResult =
    reqResult
    |> Result.bind validateName
    |> Result.bind validateEmail

let test() =
    // Now, create a Request and pattern match on the result.
    let req1 = { Name = "Phillip"; Email = "phillip@contoso.biz" }
    let res1 = validateRequest (Ok req1)
    match res1 with
    | Ok req -> printfn "My request was valid! Name: %s Email %s" req.Name req.Email
    | Error e -> printfn "Error: %s" e
    // Prints: "My request was valid!  Name: Phillip Email: phillip@consoto.biz"

    let req2 = { Name = "Phillip"; Email = "phillip@bananas.com" }
    let res2 = validateRequest (Ok req2)
    match res2 with
    | Ok req -> printfn "My request was valid! Name: %s Email %s" req.Name req.Email
    | Error e -> printfn "Error: %s" e
    // Prints: "Error: No email from bananas.com is allowed."

test()
```

<span data-ttu-id="c25c8-111">Como puede ver, es muy fácil encadenar varias funciones de validación si las obliga a que devuelvan un `Result`.</span><span class="sxs-lookup"><span data-stu-id="c25c8-111">As you can see, it's quite easy to chain together various validation functions if you force them all to return a `Result`.</span></span>  <span data-ttu-id="c25c8-112">Esto le permite dividir la funcionalidad como esta en pequeñas piezas que son comparables según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="c25c8-112">This lets you break up functionality like this into small pieces which are as composable as you need them to be.</span></span>  <span data-ttu-id="c25c8-113">También tiene el valor agregado de *exigir* el uso de la [coincidencia de patrones](pattern-matching.md) al final de una ronda de validación, que a su vez exige un mayor grado de corrección del programa.</span><span class="sxs-lookup"><span data-stu-id="c25c8-113">This also has the added value of *enforcing* the use of [pattern matching](pattern-matching.md) at the end of a round of validation, which in turns enforces a higher degree of program correctness.</span></span>

## <a name="see-also"></a><span data-ttu-id="c25c8-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="c25c8-114">See also</span></span>

- [<span data-ttu-id="c25c8-115">Uniones discriminadas</span><span class="sxs-lookup"><span data-stu-id="c25c8-115">Discriminated Unions</span></span>](discriminated-unions.md)
- [<span data-ttu-id="c25c8-116">Coincidencia de patrones</span><span class="sxs-lookup"><span data-stu-id="c25c8-116">Pattern Matching</span></span>](pattern-matching.md)
