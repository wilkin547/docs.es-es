---
title: Expresiones de objeto
description: Aprenda a usar F# expresiones de objeto cuando desea evitar el código adicional y la sobrecarga necesaria para crear un nuevo tipo con nombre.
ms.date: 02/08/2019
ms.openlocfilehash: 63f2c1d7128721b7b8c744e4cf02d73c2a8b4a07
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59157857"
---
# <a name="object-expressions"></a><span data-ttu-id="90fde-103">Expresiones de objeto</span><span class="sxs-lookup"><span data-stu-id="90fde-103">Object Expressions</span></span>

<span data-ttu-id="90fde-104">Un *objeto expresión* es una expresión que crea una nueva instancia de un tipo de objeto anónimo creado dinámicamente que se basa en un tipo base existente, una interfaz o un conjunto de interfaces.</span><span class="sxs-lookup"><span data-stu-id="90fde-104">An *object expression* is an expression that creates a new instance of a dynamically created, anonymous object type that is based on an existing base type, interface, or set of interfaces.</span></span>

## <a name="syntax"></a><span data-ttu-id="90fde-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="90fde-105">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="90fde-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="90fde-106">Remarks</span></span>

<span data-ttu-id="90fde-107">En la sintaxis anterior, el *typename* representa un tipo de clase existente o un tipo de interfaz.</span><span class="sxs-lookup"><span data-stu-id="90fde-107">In the previous syntax, the *typename* represents an existing class type or interface type.</span></span> <span data-ttu-id="90fde-108">*parámetros de tipo* se describen los parámetros de tipo genérico opcionales.</span><span class="sxs-lookup"><span data-stu-id="90fde-108">*type-params* describes the optional generic type parameters.</span></span> <span data-ttu-id="90fde-109">El *argumentos* se usan únicamente para los tipos de clase, que requieren los parámetros del constructor.</span><span class="sxs-lookup"><span data-stu-id="90fde-109">The *arguments* are used only for class types, which require constructor parameters.</span></span> <span data-ttu-id="90fde-110">El *definiciones de miembros* son reemplazos de métodos de clase base o implementaciones de los métodos abstractos de una clase base o una interfaz.</span><span class="sxs-lookup"><span data-stu-id="90fde-110">The *member-definitions* are overrides of base class methods, or implementations of abstract methods from either a base class or an interface.</span></span>

<span data-ttu-id="90fde-111">El ejemplo siguiente muestra los distintos tipos de expresiones de objeto.</span><span class="sxs-lookup"><span data-stu-id="90fde-111">The following example illustrates several different types of object expressions.</span></span>

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

## <a name="using-object-expressions"></a><span data-ttu-id="90fde-112">Uso de expresiones de objeto</span><span class="sxs-lookup"><span data-stu-id="90fde-112">Using Object Expressions</span></span>

<span data-ttu-id="90fde-113">Usar expresiones de objeto cuando desea evitar el código adicional y la sobrecarga que se necesita para crear un nuevo tipo con nombre.</span><span class="sxs-lookup"><span data-stu-id="90fde-113">You use object expressions when you want to avoid the extra code and overhead that is required to create a new, named type.</span></span> <span data-ttu-id="90fde-114">Si se usan expresiones de objeto para minimizar el número de tipos creados en un programa, puede reducir el número de líneas de código y evitar la proliferación innecesaria de tipos.</span><span class="sxs-lookup"><span data-stu-id="90fde-114">If you use object expressions to minimize the number of types created in a program, you can reduce the number of lines of code and prevent the unnecessary proliferation of types.</span></span> <span data-ttu-id="90fde-115">En lugar de crear muchos tipos simplemente para controlar situaciones específicas, puede usar una expresión de objeto que se personaliza un tipo existente o proporcione una implementación apropiada de una interfaz para el caso en cuestión.</span><span class="sxs-lookup"><span data-stu-id="90fde-115">Instead of creating many types just to handle specific situations, you can use an object expression that customizes an existing type or provides an appropriate implementation of an interface for the specific case at hand.</span></span>

## <a name="see-also"></a><span data-ttu-id="90fde-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="90fde-116">See also</span></span>

- [<span data-ttu-id="90fde-117">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="90fde-117">F# Language Reference</span></span>](index.md)
