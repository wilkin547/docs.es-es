---
title: 'La palabra clave fija (F #)'
description: "Obtenga información acerca de cómo puede 'pin' local en la pila para evitar que la colección con F # 'fixed' palabra clave."
author: cartermp
ms.author: phcart
ms.date: 04/24/2017
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 8c1d486ec754335dfbaeec439b1eb949494e4241
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="the-fixed-keyword"></a><span data-ttu-id="8173e-103">La palabra clave Fixed</span><span class="sxs-lookup"><span data-stu-id="8173e-103">The Fixed Keyword</span></span>

<span data-ttu-id="8173e-104">F # 4.1 presenta el `fixed` palabra clave, que le permite "fijar" una variable local en la pila para evitar que se recopilan o se mueve durante la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="8173e-104">F# 4.1 introduces the `fixed` keyword, which allows you to "pin" a local onto the stack to prevent it from being collected or moved during garbage-collection.</span></span>  <span data-ttu-id="8173e-105">Se usa para escenarios de programación de bajo nivel.</span><span class="sxs-lookup"><span data-stu-id="8173e-105">It is used for low-level programming scenarios.</span></span>

## <a name="syntax"></a><span data-ttu-id="8173e-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8173e-106">Syntax</span></span>

```fsharp
use ptr = fixed expression
```

## <a name="remarks"></a><span data-ttu-id="8173e-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8173e-107">Remarks</span></span>

<span data-ttu-id="8173e-108">Este comando extiende la sintaxis de expresiones para permitir la extracción de un puntero y se enlaza a un nombre que ha impedido que se recopilan o se mueve durante la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="8173e-108">This extends the syntax of expressions to allow extracting a pointer and binding it to a name which is prevented from being collected or moved during garbage-collection.</span></span>  

<span data-ttu-id="8173e-109">Un puntero desde una expresión es fijo a través de la `fixed` palabra clave está enlazado a un identificador a través de la `use` (palabra clave).</span><span class="sxs-lookup"><span data-stu-id="8173e-109">A pointer from an expression is fixed via the `fixed` keyword is bound to an identifier via the `use` keyword.</span></span>  <span data-ttu-id="8173e-110">La semántica de esto es similar a la administración de recursos a través de la `use` (palabra clave).</span><span class="sxs-lookup"><span data-stu-id="8173e-110">The semantics of this are similar to resource management via the `use` keyword.</span></span>  <span data-ttu-id="8173e-111">El puntero se fija mientras esté dentro del ámbito, y una vez que está fuera del ámbito, ya no es fijo.</span><span class="sxs-lookup"><span data-stu-id="8173e-111">The pointer is fixed while it is in scope, and once it is out of scope, it is no longer fixed.</span></span>  <span data-ttu-id="8173e-112">`fixed` no se puede usar fuera del contexto de un `use` enlace.</span><span class="sxs-lookup"><span data-stu-id="8173e-112">`fixed` cannot be used outside the context of a `use` binding.</span></span>  <span data-ttu-id="8173e-113">Debe enlazar el puntero a un nombre con `use`.</span><span class="sxs-lookup"><span data-stu-id="8173e-113">You must bind the pointer to a name with `use`.</span></span>

<span data-ttu-id="8173e-114">El uso de `fixed` debe producirse dentro de una expresión en una función o un método.</span><span class="sxs-lookup"><span data-stu-id="8173e-114">Use of `fixed` must occur within an expression in a function or a method.</span></span>  <span data-ttu-id="8173e-115">No puede utilizarse en un ámbito de nivel de script o el nivel de módulo.</span><span class="sxs-lookup"><span data-stu-id="8173e-115">It cannot be used at a script-level or module-level scope.</span></span>

<span data-ttu-id="8173e-116">Al igual que todo el código de puntero, esto es una característica no segura y emitirá una advertencia cuando se utiliza.</span><span class="sxs-lookup"><span data-stu-id="8173e-116">Like all pointer code, this is an unsafe feature and will emit a warning when used.</span></span>

## <a name="example"></a><span data-ttu-id="8173e-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8173e-117">Example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="8173e-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="8173e-118">See Also</span></span>

[<span data-ttu-id="8173e-119">NativePtr (módulo)</span><span class="sxs-lookup"><span data-stu-id="8173e-119">NativePtr Module</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/nativeinterop.nativeptr-module-%5Bfsharp%5D)
