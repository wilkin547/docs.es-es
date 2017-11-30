---
title: 'La palabra clave fija (F #)'
description: "Obtenga información acerca de cómo puede 'pin' local en la pila para evitar que la colección con F # 'fixed' palabra clave."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 04/24/2017
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 5795ce1f-11bf-4798-9f1f-6e44ffa1477e
ms.openlocfilehash: ac6be2bb9df8da1b6d0a29c2e27f777eade07cb9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="the-fixed-keyword"></a><span data-ttu-id="c76cf-104">La palabra clave Fixed</span><span class="sxs-lookup"><span data-stu-id="c76cf-104">The Fixed Keyword</span></span>

<span data-ttu-id="c76cf-105">F # 4.1 presenta el `fixed` palabra clave, que le permite "fijar" una variable local en la pila para evitar que se recopilan o se mueve durante la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="c76cf-105">F# 4.1 introduces the `fixed` keyword, which allows you to "pin" a local onto the stack to prevent it from being collected or moved during garbage-collection.</span></span>  <span data-ttu-id="c76cf-106">Se usa para escenarios de programación de bajo nivel.</span><span class="sxs-lookup"><span data-stu-id="c76cf-106">It is used for low-level programming scenarios.</span></span>

## <a name="syntax"></a><span data-ttu-id="c76cf-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c76cf-107">Syntax</span></span>

```fsharp
use ptr = fixed expression
```

## <a name="remarks"></a><span data-ttu-id="c76cf-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c76cf-108">Remarks</span></span>

<span data-ttu-id="c76cf-109">Este comando extiende la sintaxis de expresiones para permitir la extracción de un puntero y se enlaza a un nombre que ha impedido que se recopilan o se mueve durante la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="c76cf-109">This extends the syntax of expressions to allow extracting a pointer and binding it to a name which is prevented from being collected or moved during garbage-collection.</span></span>  

<span data-ttu-id="c76cf-110">Un puntero desde una expresión es fijo a través de la `fixed` palabra clave está enlazado a un identificador a través de la `use` (palabra clave).</span><span class="sxs-lookup"><span data-stu-id="c76cf-110">A pointer from an expression is fixed via the `fixed` keyword is bound to an identifier via the `use` keyword.</span></span>  <span data-ttu-id="c76cf-111">La semántica de esto es similar a la administración de recursos a través de la `use` (palabra clave).</span><span class="sxs-lookup"><span data-stu-id="c76cf-111">The semantics of this are similar to resource management via the `use` keyword.</span></span>  <span data-ttu-id="c76cf-112">El puntero se fija mientras esté dentro del ámbito, y una vez que está fuera del ámbito, ya no es fijo.</span><span class="sxs-lookup"><span data-stu-id="c76cf-112">The pointer is fixed while it is in scope, and once it is out of scope, it is no longer fixed.</span></span>  <span data-ttu-id="c76cf-113">`fixed`no se puede usar fuera del contexto de un `use` enlace.</span><span class="sxs-lookup"><span data-stu-id="c76cf-113">`fixed` cannot be used outside the context of a `use` binding.</span></span>  <span data-ttu-id="c76cf-114">Debe enlazar el puntero a un nombre con `use`.</span><span class="sxs-lookup"><span data-stu-id="c76cf-114">You must bind the pointer to a name with `use`.</span></span>

<span data-ttu-id="c76cf-115">El uso de `fixed` debe producirse dentro de una expresión en una función o un método.</span><span class="sxs-lookup"><span data-stu-id="c76cf-115">Use of `fixed` must occur within an expression in a function or a method.</span></span>  <span data-ttu-id="c76cf-116">No puede utilizarse en un ámbito de nivel de script o el nivel de módulo.</span><span class="sxs-lookup"><span data-stu-id="c76cf-116">It cannot be used at a script-level or module-level scope.</span></span>

<span data-ttu-id="c76cf-117">Al igual que todo el código de puntero, esto es una característica no segura y emitirá una advertencia cuando se utiliza.</span><span class="sxs-lookup"><span data-stu-id="c76cf-117">Like all pointer code, this is an unsafe feature and will emit a warning when used.</span></span>

## <a name="example"></a><span data-ttu-id="c76cf-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c76cf-118">Example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="c76cf-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="c76cf-119">See Also</span></span>

[<span data-ttu-id="c76cf-120">NativePtr (módulo)</span><span class="sxs-lookup"><span data-stu-id="c76cf-120">NativePtr Module</span></span>](https://msdn.microsoft.com/en-us/visualfsharpdocs/conceptual/nativeinterop.nativeptr-module-%5Bfsharp%5D)
