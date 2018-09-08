---
title: 'Resultados (F #)'
description: "Obtenga información sobre cómo usar el tipo 'Resultado' de F # para ayudarle a escribir código tolerante a errores."
ms.date: 04/24/2017
ms.openlocfilehash: a7ce2e1f6b8c6a32d99a2feaf9547c4b67b152b8
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44213045"
---
# <a name="results"></a>Resultados

A partir de F # 4.1, hay un `Result<'T,'TFailure>` tipo que se puede usar para escribir código tolerante a errores que se puede componer.

## <a name="syntax"></a>Sintaxis

```fsharp
// The definition of Result in FSharp.Core
[<StructuralEquality; StructuralComparison>]
[<CompiledName("FSharpResult`2")>]
[<Struct>]
type Result<'T,'TError> = 
    | Ok of ResultValue:'T 
    | Error of ErrorValue:'TError
```

## <a name="remarks"></a>Comentarios

Tenga en cuenta que el tipo de resultado es un [unión discriminada de struct](discriminated-unions.md#struct-discriminated-unions), que es otra característica presente en F # 4.1.  Aquí se aplica la semántica de igualdad estructural.

El `Result` tipo se utiliza normalmente en monádico control de errores, que a menudo se conoce como [programación orientada a ferroviarias](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/posts/recipe-part2.html) dentro de la Comunidad de F #.  El siguiente ejemplo trivial muestra este enfoque.

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

Como puede ver, es bastante fácil encadenar varias funciones de validación si se fuerza que todas ellas para devolver un `Result`.  Esto le permite dividir la funcionalidad similar al siguiente en pequeñas porciones que se admiten como composición según sea necesario.  Esto también tiene el valor agregado de *exigir* el uso de [coincidencia de patrones](pattern-matching.md) al final de una fase de validación, lo exige un mayor grado de corrección del programa.

## <a name="see-also"></a>Vea también

- [Uniones discriminadas](discriminated-unions.md)
- [Coincidencia de patrones](pattern-matching.md)
