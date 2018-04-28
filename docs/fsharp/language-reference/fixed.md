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
# <a name="the-fixed-keyword"></a>La palabra clave Fixed

F # 4.1 presenta el `fixed` palabra clave, que le permite "fijar" una variable local en la pila para evitar que se recopilan o se mueve durante la recolección de elementos no utilizados.  Se usa para escenarios de programación de bajo nivel.

## <a name="syntax"></a>Sintaxis

```fsharp
use ptr = fixed expression
```

## <a name="remarks"></a>Comentarios

Este comando extiende la sintaxis de expresiones para permitir la extracción de un puntero y se enlaza a un nombre que ha impedido que se recopilan o se mueve durante la recolección de elementos no utilizados.  

Un puntero desde una expresión es fijo a través de la `fixed` palabra clave está enlazado a un identificador a través de la `use` (palabra clave).  La semántica de esto es similar a la administración de recursos a través de la `use` (palabra clave).  El puntero se fija mientras esté dentro del ámbito, y una vez que está fuera del ámbito, ya no es fijo.  `fixed` no se puede usar fuera del contexto de un `use` enlace.  Debe enlazar el puntero a un nombre con `use`.

El uso de `fixed` debe producirse dentro de una expresión en una función o un método.  No puede utilizarse en un ámbito de nivel de script o el nivel de módulo.

Al igual que todo el código de puntero, esto es una característica no segura y emitirá una advertencia cuando se utiliza.

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

[NativePtr (módulo)](https://msdn.microsoft.com/visualfsharpdocs/conceptual/nativeinterop.nativeptr-module-%5Bfsharp%5D)
