---
title: Palabra clave Fixed
description: 'Obtenga información sobre cómo puede "anclar" un local en la pila para evitar la recopilación con la palabra clave "Fixed" de F #.'
ms.date: 08/15/2020
ms.openlocfilehash: b4b0d1ae101d5f7b65bff80fa070c9fd54de8d66
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "96740359"
---
# <a name="the-fixed-keyword"></a><span data-ttu-id="37c87-103">Palabra clave Fixed</span><span class="sxs-lookup"><span data-stu-id="37c87-103">The fixed keyword</span></span>

<span data-ttu-id="37c87-104">La `fixed` palabra clave permite "anclar" un local en la pila para impedir que se recopile o se mueva durante la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="37c87-104">The `fixed` keyword allows you to "pin" a local onto the stack to prevent it from being collected or moved during garbage-collection.</span></span>  <span data-ttu-id="37c87-105">Se utiliza para escenarios de programación de bajo nivel.</span><span class="sxs-lookup"><span data-stu-id="37c87-105">It is used for low-level programming scenarios.</span></span>

## <a name="syntax"></a><span data-ttu-id="37c87-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="37c87-106">Syntax</span></span>

```fsharp
use ptr = fixed expression
```

## <a name="remarks"></a><span data-ttu-id="37c87-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="37c87-107">Remarks</span></span>

<span data-ttu-id="37c87-108">Esto extiende la sintaxis de las expresiones para permitir la extracción de un puntero y su enlace a un nombre que se impide que se recopile o se mueva durante la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="37c87-108">This extends the syntax of expressions to allow extracting a pointer and binding it to a name which is prevented from being collected or moved during garbage-collection.</span></span>  

<span data-ttu-id="37c87-109">Un puntero de una expresión se fija a través de la `fixed` palabra clave se enlaza a un identificador a través de la `use` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="37c87-109">A pointer from an expression is fixed via the `fixed` keyword is bound to an identifier via the `use` keyword.</span></span>  <span data-ttu-id="37c87-110">La semántica de esto es similar a la de la administración de recursos a través de la `use` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="37c87-110">The semantics of this are similar to resource management via the `use` keyword.</span></span>  <span data-ttu-id="37c87-111">El puntero es fijo mientras está en el ámbito y, una vez que está fuera del ámbito, ya no se corrige.</span><span class="sxs-lookup"><span data-stu-id="37c87-111">The pointer is fixed while it is in scope, and once it is out of scope, it is no longer fixed.</span></span>  <span data-ttu-id="37c87-112">`fixed` no se puede usar fuera del contexto de un `use` enlace.</span><span class="sxs-lookup"><span data-stu-id="37c87-112">`fixed` cannot be used outside the context of a `use` binding.</span></span>  <span data-ttu-id="37c87-113">Debe enlazar el puntero a un nombre con `use` .</span><span class="sxs-lookup"><span data-stu-id="37c87-113">You must bind the pointer to a name with `use`.</span></span>

<span data-ttu-id="37c87-114">El uso de `fixed` debe producirse dentro de una expresión en una función o un método.</span><span class="sxs-lookup"><span data-stu-id="37c87-114">Use of `fixed` must occur within an expression in a function or a method.</span></span>  <span data-ttu-id="37c87-115">No se puede usar en un ámbito de nivel de script o de módulo.</span><span class="sxs-lookup"><span data-stu-id="37c87-115">It cannot be used at a script-level or module-level scope.</span></span>

<span data-ttu-id="37c87-116">Como todo el código de puntero, se trata de una característica no segura y emitirá una advertencia cuando se use.</span><span class="sxs-lookup"><span data-stu-id="37c87-116">Like all pointer code, this is an unsafe feature and will emit a warning when used.</span></span>

## <a name="example"></a><span data-ttu-id="37c87-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="37c87-117">Example</span></span>

```fsharp
open Microsoft.FSharp.NativeInterop

type Point = { mutable X: int; mutable Y: int}

let squareWithPointer (p: nativeptr<int>) =
    // Dereference the pointer at the 0th address.
    let mutable value = NativePtr.get p 0

    // Perform some work
    value <- value * value

    // Set the value in the pointer at the 0th address.
    NativePtr.set p 0 value

let pnt = { X = 1; Y = 2 }
printfn $"pnt before - X: %d{pnt.X} Y: %d{pnt.Y}" // prints 1 and 2

// Note that the use of 'fixed' is inside a function.
// You cannot fix a pointer at a script-level or module-level scope.
let doPointerWork() =
    use ptr = fixed &pnt.Y

    // Square the Y value
    squareWithPointer ptr
    printfn $"pnt after - X: %d{pnt.X} Y: %d{pnt.Y}" // prints 1 and 4

doPointerWork()
```

## <a name="see-also"></a><span data-ttu-id="37c87-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="37c87-118">See also</span></span>

- [<span data-ttu-id="37c87-119">NativePtr (módulo)</span><span class="sxs-lookup"><span data-stu-id="37c87-119">NativePtr Module</span></span>](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-nativeinterop-nativeptrmodule.html)
