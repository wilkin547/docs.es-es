---
title: Expresiones de objeto
description: Aprenda a usar F# expresiones de objeto cuando desea evitar el código adicional y la sobrecarga necesaria para crear un nuevo tipo con nombre.
ms.date: 02/08/2019
ms.openlocfilehash: c00b2e329a97b86ec2c8c84c143d2aa199875442
ms.sourcegitcommit: d2ccb199ae6bc5787b4762e9ea6d3f6fe88677af
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2019
ms.locfileid: "56091674"
---
# <a name="object-expressions"></a>Expresiones de objeto

Un *objeto expresión* es una expresión que crea una nueva instancia de un tipo de objeto anónimo creado dinámicamente que se basa en un tipo base existente, una interfaz o un conjunto de interfaces.

## <a name="syntax"></a>Sintaxis

```fsharp
// When typename is a class:
{ new typename [type-params]arguments with
    member-definitions
    [ additional-interface-definitions ]
}
// When typename is not a class:
{ new typename [generic-type-args] with
    member-definitions
    [ additional-interface-definitions ]
}
```

## <a name="remarks"></a>Comentarios

En la sintaxis anterior, el *typename* representa un tipo de clase existente o un tipo de interfaz. *parámetros de tipo* se describen los parámetros de tipo genérico opcionales. El *argumentos* se usan únicamente para los tipos de clase, que requieren los parámetros del constructor. El *definiciones de miembros* son reemplazos de métodos de clase base o implementaciones de los métodos abstractos de una clase base o una interfaz.

El ejemplo siguiente muestra los distintos tipos de expresiones de objeto.

```fsharp
// This object expression specifies a System.Object but overrides the
// ToString method.
let obj1 = { new System.Object() with member x.ToString() = "F#" }
printfn "%A" obj1

// This object expression implements the IFormattable interface.
let delimiter(delim1: string, delim2: string, value: string) =
    { new System.IFormattable with
        member x.ToString(format: string, provider: System.IFormatProvider) =
            if format = "D" then
                delim1 + value + delim2
            else
                value }

let obj2 = delimiter("{","}", "Bananas!");

printfn "%A" (System.String.Format("{0:D}", obj2))

// This object expression implements multiple interfaces.
type IFirst =
  abstract F : unit -> unit
  abstract G : unit -> unit

type ISecond =
  inherit IFirst
  abstract H : unit -> unit
  abstract J : unit -> unit

// This object expression implements an interface chain.
let implementer() =
    { new ISecond with
        member this.H() = ()
        member this.J() = ()
      interface IFirst with
        member this.F() = ()
        member this.G() = () }
```

## <a name="using-object-expressions"></a>Uso de expresiones de objeto

Usar expresiones de objeto cuando desea evitar el código adicional y la sobrecarga que se necesita para crear un nuevo tipo con nombre. Si se usan expresiones de objeto para minimizar el número de tipos creados en un programa, puede reducir el número de líneas de código y evitar la proliferación innecesaria de tipos. En lugar de crear muchos tipos simplemente para controlar situaciones específicas, puede usar una expresión de objeto que se personaliza un tipo existente o proporcione una implementación apropiada de una interfaz para el caso en cuestión.

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
