---
title: Results
description: 'Obtenga información sobre cómo usar el tipo de "resultado" de F # para ayudarle a escribir código tolerante a errores.'
ms.date: 08/13/2020
ms.openlocfilehash: 53b1db0c9224ae032d58c06cd3c58e3dbed03f7b
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "96740229"
---
# <a name="results"></a><span data-ttu-id="aa2d6-103">Results</span><span class="sxs-lookup"><span data-stu-id="aa2d6-103">Results</span></span>

<span data-ttu-id="aa2d6-104">El `Result<'T,'TFailure>` tipo le permite escribir código tolerante a errores que se puede componer.</span><span class="sxs-lookup"><span data-stu-id="aa2d6-104">The `Result<'T,'TFailure>` type lets you write error-tolerant code that can be composed.</span></span>

## <a name="syntax"></a><span data-ttu-id="aa2d6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aa2d6-105">Syntax</span></span>

```fsharp
// The definition of Result in FSharp.Core
[<StructuralEquality; StructuralComparison>]
[<CompiledName("FSharpResult`2")>]
[<Struct>]
type Result<'T,'TError> =
    | Ok of ResultValue:'T
    | Error of ErrorValue:'TError
```

## <a name="remarks"></a><span data-ttu-id="aa2d6-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="aa2d6-106">Remarks</span></span>

<span data-ttu-id="aa2d6-107">Vea el [`Result`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-resultmodule.html) módulo para los combinadores integrados para `Result` .</span><span class="sxs-lookup"><span data-stu-id="aa2d6-107">See the [`Result`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-resultmodule.html) module for the built-in combinators for the `Result`.</span></span> <span data-ttu-id="aa2d6-108">.</span><span class="sxs-lookup"><span data-stu-id="aa2d6-108">type.</span></span>

<span data-ttu-id="aa2d6-109">Tenga en cuenta que el tipo de resultado es una [Unión discriminada de struct](discriminated-unions.md#struct-discriminated-unions).</span><span class="sxs-lookup"><span data-stu-id="aa2d6-109">Note that the result type is a [struct discriminated union](discriminated-unions.md#struct-discriminated-unions).</span></span> <span data-ttu-id="aa2d6-110">La semántica de igualdad estructural se aplica aquí.</span><span class="sxs-lookup"><span data-stu-id="aa2d6-110">Structural equality semantics apply here.</span></span>

<span data-ttu-id="aa2d6-111">El `Result` tipo se usa normalmente en el control de errores de Monad, que a menudo se conoce como [programación orientada a ferrocarril](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/posts/recipe-part2.html) en la comunidad de F #.</span><span class="sxs-lookup"><span data-stu-id="aa2d6-111">The `Result` type is typically used in monadic error-handling, which is often referred to as [Railway-oriented Programming](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/posts/recipe-part2.html) within the F# community.</span></span>  <span data-ttu-id="aa2d6-112">En el siguiente ejemplo trivial se muestra este enfoque.</span><span class="sxs-lookup"><span data-stu-id="aa2d6-112">The following trivial example demonstrates this approach.</span></span>

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
    | Ok req -> printfn $"My request was valid! Name: {req.Name} Email {req.Email}"  
    | Error e -> printfn $"Error: {e}"
    // Prints: "My request was valid!  Name: Phillip Email: phillip@consoto.biz"

    let req2 = { Name = "Phillip"; Email = "phillip@bananas.com" }
    let res2 = validateRequest (Ok req2)
    match res2 with
    | Ok req -> printfn $"My request was valid! Name: {req.Name} Email {req.Email}"  
    | Error e -> printfn $"Error: {e}"
    // Prints: "Error: No email from bananas.com is allowed."

test()
```

<span data-ttu-id="aa2d6-113">Como puede ver, es muy fácil encadenar varias funciones de validación si las obliga a que devuelvan `Result` .</span><span class="sxs-lookup"><span data-stu-id="aa2d6-113">As you can see, it's quite easy to chain together various validation functions if you force them all to return a `Result`.</span></span>  <span data-ttu-id="aa2d6-114">Esto le permite dividir la funcionalidad como esta en pequeñas piezas que son comparables según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="aa2d6-114">This lets you break up functionality like this into small pieces which are as composable as you need them to be.</span></span>  <span data-ttu-id="aa2d6-115">También tiene el valor agregado de *exigir* el uso de la [coincidencia de patrones](pattern-matching.md) al final de una ronda de validación, que a su vez exige un mayor grado de corrección del programa.</span><span class="sxs-lookup"><span data-stu-id="aa2d6-115">This also has the added value of *enforcing* the use of [pattern matching](pattern-matching.md) at the end of a round of validation, which in turns enforces a higher degree of program correctness.</span></span>

## <a name="see-also"></a><span data-ttu-id="aa2d6-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="aa2d6-116">See also</span></span>

- [<span data-ttu-id="aa2d6-117">Uniones discriminadas</span><span class="sxs-lookup"><span data-stu-id="aa2d6-117">Discriminated Unions</span></span>](discriminated-unions.md)
- [<span data-ttu-id="aa2d6-118">Coincidencia de patrones</span><span class="sxs-lookup"><span data-stu-id="aa2d6-118">Pattern Matching</span></span>](pattern-matching.md)
