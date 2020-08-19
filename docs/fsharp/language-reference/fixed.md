---
title: Palabra clave Fixed
description: 'Obtenga información sobre cómo puede "anclar" un local en la pila para evitar la recopilación con la palabra clave "Fixed" de F #.'
ms.date: 08/15/2020
ms.openlocfilehash: 786ffd706c243fc83f8fb3afc2201d2a34536372
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/18/2020
ms.locfileid: "88559185"
---
# <a name="the-fixed-keyword"></a>Palabra clave Fixed

La `fixed` palabra clave permite "anclar" un local en la pila para impedir que se recopile o se mueva durante la recolección de elementos no utilizados.  Se utiliza para escenarios de programación de bajo nivel.

## <a name="syntax"></a>Sintaxis

```fsharp
use ptr = fixed expression
```

## <a name="remarks"></a>Observaciones

Esto extiende la sintaxis de las expresiones para permitir la extracción de un puntero y su enlace a un nombre que se impide que se recopile o se mueva durante la recolección de elementos no utilizados.  

Un puntero de una expresión se fija a través de la `fixed` palabra clave se enlaza a un identificador a través de la `use` palabra clave.  La semántica de esto es similar a la de la administración de recursos a través de la `use` palabra clave.  El puntero es fijo mientras está en el ámbito y, una vez que está fuera del ámbito, ya no se corrige.  `fixed` no se puede usar fuera del contexto de un `use` enlace.  Debe enlazar el puntero a un nombre con `use` .

El uso de `fixed` debe producirse dentro de una expresión en una función o un método.  No se puede usar en un ámbito de nivel de script o de módulo.

Como todo el código de puntero, se trata de una característica no segura y emitirá una advertencia cuando se use.

## <a name="example"></a>Ejemplo

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

## <a name="see-also"></a>Consulte también

- [NativePtr (módulo)](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-nativeinterop-nativeptrmodule.html)
