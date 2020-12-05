---
title: Expresiones de objeto
description: 'Obtenga información sobre cómo usar las expresiones de objeto de F # cuando desee evitar el código adicional y la sobrecarga necesaria para crear un nuevo tipo con nombre.'
ms.date: 02/08/2019
ms.openlocfilehash: 8a3e40b7833b551eefb95ec62b935acd1ba7b1f9
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "96740307"
---
# <a name="object-expressions"></a>Expresiones de objeto

Una *expresión de objeto* es una expresión que crea una nueva instancia de un tipo de objeto anónimo creado dinámicamente que se basa en un tipo base existente, una interfaz o un conjunto de interfaces.

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

En la sintaxis anterior, *TypeName* representa un tipo de clase o de interfaz existente. *Type-params* describe los parámetros de tipo genérico opcionales. Los *argumentos* solo se usan para los tipos de clase, que requieren parámetros de constructor. Las *definiciones de miembro* son invalidaciones de métodos de clase base o implementaciones de métodos abstractos de una clase base o una interfaz.

En el ejemplo siguiente se muestran varios tipos diferentes de expresiones de objeto.

```fsharp
// This object expression specifies a System.Object but overrides the
// ToString method.
let obj1 = { new System.Object() with member x.ToString() = "F#" }
printfn $"{obj1}"

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

// Define two interfaces
type IFirst =
  abstract F : unit -> unit
  abstract G : unit -> unit

type ISecond =
  inherit IFirst
  abstract H : unit -> unit
  abstract J : unit -> unit

// This object expression implements both interfaces.
let implementer() =
    { new ISecond with
        member this.H() = ()
        member this.J() = ()
      interface IFirst with
        member this.F() = ()
        member this.G() = () }
```

## <a name="using-object-expressions"></a>Usar expresiones de objeto

Las expresiones de objeto se usan cuando se desea evitar el código adicional y la sobrecarga necesaria para crear un nuevo tipo con nombre. Si utiliza expresiones de objeto para minimizar el número de tipos creados en un programa, puede reducir el número de líneas de código y evitar la proliferación innecesaria de tipos. En lugar de crear muchos tipos solo para controlar situaciones específicas, puede usar una expresión de objeto que personalice un tipo existente o proporcione una implementación adecuada de una interfaz para el caso concreto a mano.

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
