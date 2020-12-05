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
# <a name="object-expressions"></a><span data-ttu-id="5d356-103">Expresiones de objeto</span><span class="sxs-lookup"><span data-stu-id="5d356-103">Object Expressions</span></span>

<span data-ttu-id="5d356-104">Una *expresión de objeto* es una expresión que crea una nueva instancia de un tipo de objeto anónimo creado dinámicamente que se basa en un tipo base existente, una interfaz o un conjunto de interfaces.</span><span class="sxs-lookup"><span data-stu-id="5d356-104">An *object expression* is an expression that creates a new instance of a dynamically created, anonymous object type that is based on an existing base type, interface, or set of interfaces.</span></span>

## <a name="syntax"></a><span data-ttu-id="5d356-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5d356-105">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="5d356-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5d356-106">Remarks</span></span>

<span data-ttu-id="5d356-107">En la sintaxis anterior, *TypeName* representa un tipo de clase o de interfaz existente.</span><span class="sxs-lookup"><span data-stu-id="5d356-107">In the previous syntax, the *typename* represents an existing class type or interface type.</span></span> <span data-ttu-id="5d356-108">*Type-params* describe los parámetros de tipo genérico opcionales.</span><span class="sxs-lookup"><span data-stu-id="5d356-108">*type-params* describes the optional generic type parameters.</span></span> <span data-ttu-id="5d356-109">Los *argumentos* solo se usan para los tipos de clase, que requieren parámetros de constructor.</span><span class="sxs-lookup"><span data-stu-id="5d356-109">The *arguments* are used only for class types, which require constructor parameters.</span></span> <span data-ttu-id="5d356-110">Las *definiciones de miembro* son invalidaciones de métodos de clase base o implementaciones de métodos abstractos de una clase base o una interfaz.</span><span class="sxs-lookup"><span data-stu-id="5d356-110">The *member-definitions* are overrides of base class methods, or implementations of abstract methods from either a base class or an interface.</span></span>

<span data-ttu-id="5d356-111">En el ejemplo siguiente se muestran varios tipos diferentes de expresiones de objeto.</span><span class="sxs-lookup"><span data-stu-id="5d356-111">The following example illustrates several different types of object expressions.</span></span>

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

## <a name="using-object-expressions"></a><span data-ttu-id="5d356-112">Usar expresiones de objeto</span><span class="sxs-lookup"><span data-stu-id="5d356-112">Using Object Expressions</span></span>

<span data-ttu-id="5d356-113">Las expresiones de objeto se usan cuando se desea evitar el código adicional y la sobrecarga necesaria para crear un nuevo tipo con nombre.</span><span class="sxs-lookup"><span data-stu-id="5d356-113">You use object expressions when you want to avoid the extra code and overhead that is required to create a new, named type.</span></span> <span data-ttu-id="5d356-114">Si utiliza expresiones de objeto para minimizar el número de tipos creados en un programa, puede reducir el número de líneas de código y evitar la proliferación innecesaria de tipos.</span><span class="sxs-lookup"><span data-stu-id="5d356-114">If you use object expressions to minimize the number of types created in a program, you can reduce the number of lines of code and prevent the unnecessary proliferation of types.</span></span> <span data-ttu-id="5d356-115">En lugar de crear muchos tipos solo para controlar situaciones específicas, puede usar una expresión de objeto que personalice un tipo existente o proporcione una implementación adecuada de una interfaz para el caso concreto a mano.</span><span class="sxs-lookup"><span data-stu-id="5d356-115">Instead of creating many types just to handle specific situations, you can use an object expression that customizes an existing type or provides an appropriate implementation of an interface for the specific case at hand.</span></span>

## <a name="see-also"></a><span data-ttu-id="5d356-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="5d356-116">See also</span></span>

- [<span data-ttu-id="5d356-117">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="5d356-117">F# Language Reference</span></span>](index.md)
