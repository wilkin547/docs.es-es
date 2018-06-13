---
title: Expresiones de objeto (F#)
description: 'Aprenda cómo usar expresiones de objeto de F # cuando desee evitar el código adicional y la sobrecarga necesaria para crear un nuevo tipo con nombre.'
ms.date: 05/16/2016
ms.openlocfilehash: fed78e2be52838eedf55759b195696f1210a8a20
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564396"
---
# <a name="object-expressions"></a><span data-ttu-id="c3819-103">Expresiones de objeto</span><span class="sxs-lookup"><span data-stu-id="c3819-103">Object Expressions</span></span>

<span data-ttu-id="c3819-104">Un *objeto expresión* es una expresión que crea una nueva instancia de un tipo de objeto anónimo creado dinámicamente que se basa en un tipo base existente, una interfaz o un conjunto de interfaces.</span><span class="sxs-lookup"><span data-stu-id="c3819-104">An *object expression* is an expression that creates a new instance of a dynamically created, anonymous object type that is based on an existing base type, interface, or set of interfaces.</span></span>


## <a name="syntax"></a><span data-ttu-id="c3819-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c3819-105">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="c3819-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c3819-106">Remarks</span></span>
<span data-ttu-id="c3819-107">En la sintaxis anterior, el *typename* representa un tipo de clase existente o un tipo de interfaz.</span><span class="sxs-lookup"><span data-stu-id="c3819-107">In the previous syntax, the *typename* represents an existing class type or interface type.</span></span> <span data-ttu-id="c3819-108">*parámetros de tipo* se describen los parámetros de tipo genérico opcionales.</span><span class="sxs-lookup"><span data-stu-id="c3819-108">*type-params* describes the optional generic type parameters.</span></span> <span data-ttu-id="c3819-109">El *argumentos* se usan únicamente para los tipos de clase, que requieren parámetros de constructor.</span><span class="sxs-lookup"><span data-stu-id="c3819-109">The *arguments* are used only for class types, which require constructor parameters.</span></span> <span data-ttu-id="c3819-110">El *definiciones de miembros* son reemplazos de métodos de clase base o implementaciones de métodos abstractos de una clase base o una interfaz.</span><span class="sxs-lookup"><span data-stu-id="c3819-110">The *member-definitions* are overrides of base class methods, or implementations of abstract methods from either a base class or an interface.</span></span>

<span data-ttu-id="c3819-111">En el ejemplo siguiente se muestra distintos tipos de expresiones de objeto.</span><span class="sxs-lookup"><span data-stu-id="c3819-111">The following example illustrates several different types of object expressions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4301.fs)]

## <a name="using-object-expressions"></a><span data-ttu-id="c3819-112">Uso de expresiones de objeto</span><span class="sxs-lookup"><span data-stu-id="c3819-112">Using Object Expressions</span></span>
<span data-ttu-id="c3819-113">Usar expresiones de objeto cuando desee evitar el código adicional y la sobrecarga necesaria para crear un nuevo tipo con nombre.</span><span class="sxs-lookup"><span data-stu-id="c3819-113">You use object expressions when you want to avoid the extra code and overhead that is required to create a new, named type.</span></span> <span data-ttu-id="c3819-114">Si se usan expresiones de objeto para minimizar el número de tipos creados en un programa, puede reducir el número de líneas de código y evitar la proliferación innecesaria de tipos.</span><span class="sxs-lookup"><span data-stu-id="c3819-114">If you use object expressions to minimize the number of types created in a program, you can reduce the number of lines of code and prevent the unnecessary proliferation of types.</span></span> <span data-ttu-id="c3819-115">En lugar de crear muchos tipos simplemente para hacer frente a situaciones concretas, puede usar una expresión de objeto que se personaliza un tipo existente o proporcione una implementación adecuada de una interfaz para el caso concreto en cuestión.</span><span class="sxs-lookup"><span data-stu-id="c3819-115">Instead of creating many types just to handle specific situations, you can use an object expression that customizes an existing type or provides an appropriate implementation of an interface for the specific case at hand.</span></span>


## <a name="see-also"></a><span data-ttu-id="c3819-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="c3819-116">See Also</span></span>
[<span data-ttu-id="c3819-117">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="c3819-117">F# Language Reference</span></span>](index.md)
