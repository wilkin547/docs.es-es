---
title: Expresiones de objeto (F#)
description: "Aprenda cómo usar expresiones de objeto de F # cuando desee evitar el código adicional y la sobrecarga necesaria para crear un nuevo tipo con nombre."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: c6dcf4c9-e7fd-4eee-9e4e-1176f4c27f57
ms.openlocfilehash: 28660d430473de02a8a55e37a26609827b364012
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="object-expressions"></a><span data-ttu-id="6a6de-104">Expresiones de objeto</span><span class="sxs-lookup"><span data-stu-id="6a6de-104">Object Expressions</span></span>

<span data-ttu-id="6a6de-105">Un *objeto expresión* es una expresión que crea una nueva instancia de un tipo de objeto anónimo creado dinámicamente que se basa en un tipo base existente, una interfaz o un conjunto de interfaces.</span><span class="sxs-lookup"><span data-stu-id="6a6de-105">An *object expression* is an expression that creates a new instance of a dynamically created, anonymous object type that is based on an existing base type, interface, or set of interfaces.</span></span>


## <a name="syntax"></a><span data-ttu-id="6a6de-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6a6de-106">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="6a6de-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6a6de-107">Remarks</span></span>
<span data-ttu-id="6a6de-108">En la sintaxis anterior, el *typename* representa un tipo de clase existente o un tipo de interfaz.</span><span class="sxs-lookup"><span data-stu-id="6a6de-108">In the previous syntax, the *typename* represents an existing class type or interface type.</span></span> <span data-ttu-id="6a6de-109">*parámetros de tipo* se describen los parámetros de tipo genérico opcionales.</span><span class="sxs-lookup"><span data-stu-id="6a6de-109">*type-params* describes the optional generic type parameters.</span></span> <span data-ttu-id="6a6de-110">El *argumentos* se usan únicamente para los tipos de clase, que requieren parámetros de constructor.</span><span class="sxs-lookup"><span data-stu-id="6a6de-110">The *arguments* are used only for class types, which require constructor parameters.</span></span> <span data-ttu-id="6a6de-111">El *definiciones de miembros* son reemplazos de métodos de clase base o implementaciones de métodos abstractos de una clase base o una interfaz.</span><span class="sxs-lookup"><span data-stu-id="6a6de-111">The *member-definitions* are overrides of base class methods, or implementations of abstract methods from either a base class or an interface.</span></span>

<span data-ttu-id="6a6de-112">En el ejemplo siguiente se muestra distintos tipos de expresiones de objeto.</span><span class="sxs-lookup"><span data-stu-id="6a6de-112">The following example illustrates several different types of object expressions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4301.fs)]

## <a name="using-object-expressions"></a><span data-ttu-id="6a6de-113">Uso de expresiones de objeto</span><span class="sxs-lookup"><span data-stu-id="6a6de-113">Using Object Expressions</span></span>
<span data-ttu-id="6a6de-114">Usar expresiones de objeto cuando desee evitar el código adicional y la sobrecarga necesaria para crear un nuevo tipo con nombre.</span><span class="sxs-lookup"><span data-stu-id="6a6de-114">You use object expressions when you want to avoid the extra code and overhead that is required to create a new, named type.</span></span> <span data-ttu-id="6a6de-115">Si se usan expresiones de objeto para minimizar el número de tipos creados en un programa, puede reducir el número de líneas de código y evitar la proliferación innecesaria de tipos.</span><span class="sxs-lookup"><span data-stu-id="6a6de-115">If you use object expressions to minimize the number of types created in a program, you can reduce the number of lines of code and prevent the unnecessary proliferation of types.</span></span> <span data-ttu-id="6a6de-116">En lugar de crear muchos tipos simplemente para hacer frente a situaciones concretas, puede usar una expresión de objeto que se personaliza un tipo existente o proporcione una implementación adecuada de una interfaz para el caso concreto en cuestión.</span><span class="sxs-lookup"><span data-stu-id="6a6de-116">Instead of creating many types just to handle specific situations, you can use an object expression that customizes an existing type or provides an appropriate implementation of an interface for the specific case at hand.</span></span>


## <a name="see-also"></a><span data-ttu-id="6a6de-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="6a6de-117">See Also</span></span>
[<span data-ttu-id="6a6de-118">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="6a6de-118">F# Language Reference</span></span>](index.md)
