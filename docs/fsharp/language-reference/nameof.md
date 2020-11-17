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
# <a name="nameof"></a><span data-ttu-id="42978-103">Nameof</span><span class="sxs-lookup"><span data-stu-id="42978-103">Nameof</span></span>

<span data-ttu-id="42978-104">La `nameof` expresión genera una constante de cadena que coincide con el nombre en el origen para prácticamente cualquier construcción de F # en el código fuente.</span><span class="sxs-lookup"><span data-stu-id="42978-104">The `nameof` expression produces a string constant that matches the name in source for nearly any F# construct in source.</span></span>

## <a name="syntax"></a><span data-ttu-id="42978-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="42978-105">Syntax</span></span>

```fsharp
nameof symbol
nameof<'TGeneric>
```

## <a name="remarks"></a><span data-ttu-id="42978-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="42978-106">Remarks</span></span>

<span data-ttu-id="42978-107">`nameof` funciona resolviendo el símbolo que se le ha pasado y genera el nombre de ese símbolo tal y como se declara en el código fuente.</span><span class="sxs-lookup"><span data-stu-id="42978-107">`nameof` works by resolving the symbol passed to it and produces the name of that symbol as it is declared in your source code.</span></span> <span data-ttu-id="42978-108">Esto resulta útil en varios escenarios, como el registro, y protege el registro de los cambios en el código fuente.</span><span class="sxs-lookup"><span data-stu-id="42978-108">This is useful in various scenarios, such as logging, and protects your logging against changes in source code.</span></span>

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

<span data-ttu-id="42978-109">La última línea producirá una excepción y se `"month"` mostrará en el mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="42978-109">The last line will throw an exception and `"month"` will be shown in the error message.</span></span>

<span data-ttu-id="42978-110">Puede tomar un nombre de casi todas las construcciones de F #:</span><span class="sxs-lookup"><span data-stu-id="42978-110">You can take a name of nearly every F# construct:</span></span>

```fsharp
module M =
    let f x = nameof x

printfn $"{(M.f 12)]}"
printfn $"{(nameof M)}"
printfn $"{(nameof M.f)}"
```

<span data-ttu-id="42978-111">`nameof` no es una función de primera clase y no se puede usar como tal.</span><span class="sxs-lookup"><span data-stu-id="42978-111">`nameof` is not a first-class function and cannot be used as such.</span></span> <span data-ttu-id="42978-112">Esto significa que no se puede aplicar parcialmente y los valores no se pueden canalizar a él a través de los operadores de canalización de F #.</span><span class="sxs-lookup"><span data-stu-id="42978-112">That means it cannot be partially applied and values cannot be piped into it via F# pipeline operators.</span></span>

## <a name="nameof-on-operators"></a><span data-ttu-id="42978-113">Nombre en operadores</span><span class="sxs-lookup"><span data-stu-id="42978-113">Nameof on operators</span></span>

<span data-ttu-id="42978-114">Los operadores de F # se pueden usar de dos maneras, como un texto de operador, o un símbolo que representa el formulario compilado.</span><span class="sxs-lookup"><span data-stu-id="42978-114">Operators in F# can be used in two ways, as an operator text itself, or a symbol representing the compiled form.</span></span> <span data-ttu-id="42978-115">`nameof` en un operador, se generará el nombre del operador tal y como se declara en el origen.</span><span class="sxs-lookup"><span data-stu-id="42978-115">`nameof` on an operator will produce the name of the operator as it is declared in source.</span></span> <span data-ttu-id="42978-116">Para obtener el nombre compilado, use el nombre compilado en el origen:</span><span class="sxs-lookup"><span data-stu-id="42978-116">To get the compiled name, use the compiled name in source:</span></span>

```fsharp
nameof(+) // "+"
nameof op_Addition // "op_Addition"
```

## <a name="nameof-on-generics"></a><span data-ttu-id="42978-117">Nombre en genéricos</span><span class="sxs-lookup"><span data-stu-id="42978-117">Nameof on generics</span></span>

<span data-ttu-id="42978-118">También puede tomar el nombre de un parámetro de tipo genérico, pero la sintaxis es diferente:</span><span class="sxs-lookup"><span data-stu-id="42978-118">You can also take a name of a generic type parameter, but the syntax is different:</span></span>

```fsharp
let f<'a> () = nameof<'a>
f() // "a"
```

<span data-ttu-id="42978-119">`nameof<'TGeneric>` tomará el nombre del símbolo tal y como se define en el origen, no el nombre del tipo que se sustituye en un sitio de llamada.</span><span class="sxs-lookup"><span data-stu-id="42978-119">`nameof<'TGeneric>` will take the name of the symbol as defined in source, not the name of the type substituted at a call site.</span></span>

<span data-ttu-id="42978-120">El motivo por el que la sintaxis es diferente es alinear con otros operadores intrínsecos de F # como `typeof<>` y `typedefof<>` .</span><span class="sxs-lookup"><span data-stu-id="42978-120">The reason why the syntax is different is to align with other F# intrinsic operators like `typeof<>` and `typedefof<>`.</span></span> <span data-ttu-id="42978-121">Esto hace que F # sea coherente con respecto a los operadores que actúan en tipos genéricos y en cualquier otro elemento de origen.</span><span class="sxs-lookup"><span data-stu-id="42978-121">This makes F# consistent with respect to operators that act on generic types and anything else in source.</span></span>

## <a name="nameof-in-pattern-matching"></a><span data-ttu-id="42978-122">Nombre en coincidencia de patrones</span><span class="sxs-lookup"><span data-stu-id="42978-122">Nameof in pattern matching</span></span>

<span data-ttu-id="42978-123">El [ `nameof` patrón](pattern-matching.md#nameof-pattern) le permite usar `nameof` en una expresión de coincidencia de patrones como la siguiente:</span><span class="sxs-lookup"><span data-stu-id="42978-123">The [`nameof` pattern](pattern-matching.md#nameof-pattern) lets you use `nameof` in a pattern match expression like so:</span></span>

```fsharp
let f (str: string) =
    match str with
    | nameof str -> "It's 'str'!"
    | _ -> "It is not 'str'!"

f "str" // matches
f "asdf" // does not match
```
