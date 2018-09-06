---
title: 'La palabra clave Fixed (F #)'
description: "Obtenga información sobre cómo puede 'pin' local en la pila para evitar que la colección con F # 'fixed' palabra clave."
ms.date: 04/24/2017
ms.openlocfilehash: 1bf1b2ad67d2dd7f854e569cfca7c06e8aec7f4c
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2018
ms.locfileid: "43779254"
---
# <a name="the-fixed-keyword"></a>La palabra clave Fixed

F # 4.1 presenta el `fixed` palabra clave, lo que permite que una variable local en la pila para evitar que se recopilan o movido durante la recolección de elementos no utilizados "anclar".  Se usa para escenarios de programación de bajo nivel.

## <a name="syntax"></a>Sintaxis

```fsharp
use ptr = fixed expression
```

## <a name="remarks"></a>Comentarios

Esto amplía la sintaxis de expresiones para permitir que un puntero de extracción y se enlaza a un nombre que ha impedido que se recopilan o movido durante la recolección de elementos no utilizados.  

Un puntero de una expresión que se ha corregido a través de la `fixed` palabra clave está enlazado a un identificador a través de la `use` palabra clave.  La semántica de esto es similar a la administración de recursos a través de la `use` palabra clave.  El puntero se fija mientras esté dentro del ámbito, y una vez que esté fuera del ámbito, ya no es fijo.  `fixed` no se puede usar fuera del contexto de un `use` enlace.  Debe enlazar el puntero a un nombre con `use`.

El uso de `fixed` debe producirse dentro de una expresión en una función o un método.  No se puede usar en un ámbito de nivel de módulo o script.

Como todo el código de puntero, esto es una característica no segura y emitirá una advertencia cuando se usa.

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

## <a name="see-also"></a>Vea también

- [NativePtr (módulo)](https://msdn.microsoft.com/visualfsharpdocs/conceptual/nativeinterop.nativeptr-module-%5Bfsharp%5D)
