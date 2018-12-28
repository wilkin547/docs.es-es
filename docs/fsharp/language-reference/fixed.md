---
title: La palabra clave fixed
description: Aprenda cómo puede 'pin', una variable local en la pila para evitar que la colección con el F# 'fixed' palabra clave.
ms.date: 04/24/2017
ms.openlocfilehash: 7fdf66560f3e2ab7584b00c7e4584d7f6c161858
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2018
ms.locfileid: "53614368"
---
# <a name="the-fixed-keyword"></a><span data-ttu-id="68c4a-103">La palabra clave fixed</span><span class="sxs-lookup"><span data-stu-id="68c4a-103">The fixed keyword</span></span>

<span data-ttu-id="68c4a-104">F#4.1 presenta el `fixed` palabra clave, lo que permite que una variable local en la pila para evitar que se recopilan o movido durante la recolección de elementos no utilizados "anclar".</span><span class="sxs-lookup"><span data-stu-id="68c4a-104">F# 4.1 introduces the `fixed` keyword, which allows you to "pin" a local onto the stack to prevent it from being collected or moved during garbage-collection.</span></span>  <span data-ttu-id="68c4a-105">Se usa para escenarios de programación de bajo nivel.</span><span class="sxs-lookup"><span data-stu-id="68c4a-105">It is used for low-level programming scenarios.</span></span>

## <a name="syntax"></a><span data-ttu-id="68c4a-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="68c4a-106">Syntax</span></span>

```fsharp
use ptr = fixed expression
```

## <a name="remarks"></a><span data-ttu-id="68c4a-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="68c4a-107">Remarks</span></span>

<span data-ttu-id="68c4a-108">Esto amplía la sintaxis de expresiones para permitir que un puntero de extracción y se enlaza a un nombre que ha impedido que se recopilan o movido durante la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="68c4a-108">This extends the syntax of expressions to allow extracting a pointer and binding it to a name which is prevented from being collected or moved during garbage-collection.</span></span>  

<span data-ttu-id="68c4a-109">Un puntero de una expresión que se ha corregido a través de la `fixed` palabra clave está enlazado a un identificador a través de la `use` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="68c4a-109">A pointer from an expression is fixed via the `fixed` keyword is bound to an identifier via the `use` keyword.</span></span>  <span data-ttu-id="68c4a-110">La semántica de esto es similar a la administración de recursos a través de la `use` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="68c4a-110">The semantics of this are similar to resource management via the `use` keyword.</span></span>  <span data-ttu-id="68c4a-111">El puntero se fija mientras esté dentro del ámbito, y una vez que esté fuera del ámbito, ya no es fijo.</span><span class="sxs-lookup"><span data-stu-id="68c4a-111">The pointer is fixed while it is in scope, and once it is out of scope, it is no longer fixed.</span></span>  <span data-ttu-id="68c4a-112">`fixed` no se puede usar fuera del contexto de un `use` enlace.</span><span class="sxs-lookup"><span data-stu-id="68c4a-112">`fixed` cannot be used outside the context of a `use` binding.</span></span>  <span data-ttu-id="68c4a-113">Debe enlazar el puntero a un nombre con `use`.</span><span class="sxs-lookup"><span data-stu-id="68c4a-113">You must bind the pointer to a name with `use`.</span></span>

<span data-ttu-id="68c4a-114">El uso de `fixed` debe producirse dentro de una expresión en una función o un método.</span><span class="sxs-lookup"><span data-stu-id="68c4a-114">Use of `fixed` must occur within an expression in a function or a method.</span></span>  <span data-ttu-id="68c4a-115">No se puede usar en un ámbito de nivel de módulo o script.</span><span class="sxs-lookup"><span data-stu-id="68c4a-115">It cannot be used at a script-level or module-level scope.</span></span>

<span data-ttu-id="68c4a-116">Como todo el código de puntero, esto es una característica no segura y emitirá una advertencia cuando se usa.</span><span class="sxs-lookup"><span data-stu-id="68c4a-116">Like all pointer code, this is an unsafe feature and will emit a warning when used.</span></span>

## <a name="example"></a><span data-ttu-id="68c4a-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="68c4a-117">Example</span></span>

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
printfn "pnt before - X: %d Y: %d" pnt.X pnt.Y // prints 1 and 2

// Note that the use of 'fixed' is inside a function.
// You cannot fix a pointer at a script-level or module-level scope.
let doPointerWork() =
    use ptr = fixed &pnt.Y

    // Square the Y value
    squareWithPointer ptr
    printfn "pnt after - X: %d Y: %d" pnt.X pnt.Y // prints 1 and 4

doPointerWork()
```

## <a name="see-also"></a><span data-ttu-id="68c4a-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="68c4a-118">See also</span></span>

- [<span data-ttu-id="68c4a-119">NativePtr (módulo)</span><span class="sxs-lookup"><span data-stu-id="68c4a-119">NativePtr Module</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/nativeinterop.nativeptr-module-%5Bfsharp%5D)
