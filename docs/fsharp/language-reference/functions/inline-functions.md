---
title: Funciones inline (F#)
description: 'Obtenga información acerca de cómo usar F # en línea las funciones que se integran directamente en el código de llamada.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: cb0addd1456af1ab97e249b9c5ece4d9f0818fa3
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="inline-functions"></a><span data-ttu-id="fb317-103">Funciones insertadas</span><span class="sxs-lookup"><span data-stu-id="fb317-103">Inline Functions</span></span>

<span data-ttu-id="fb317-104">*Funciones inline* son funciones que se integran directamente en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="fb317-104">*Inline functions* are functions that are integrated directly into the calling code.</span></span>


## <a name="using-inline-functions"></a><span data-ttu-id="fb317-105">Uso de funciones Inline</span><span class="sxs-lookup"><span data-stu-id="fb317-105">Using Inline Functions</span></span>
<span data-ttu-id="fb317-106">Cuando se usan parámetros de tipo estático, las funciones con parámetros de tipo deben ser funciones inline.</span><span class="sxs-lookup"><span data-stu-id="fb317-106">When you use static type parameters, any functions that are parameterized by type parameters must be inline.</span></span> <span data-ttu-id="fb317-107">Esto garantiza que el compilador puede resolver estos parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="fb317-107">This guarantees that the compiler can resolve these type parameters.</span></span> <span data-ttu-id="fb317-108">Cuando se usan parámetros de tipo genérico normal, no hay ninguna restricción así.</span><span class="sxs-lookup"><span data-stu-id="fb317-108">When you use ordinary generic type parameters, there is no such restriction.</span></span>

<span data-ttu-id="fb317-109">Además de habilitar el uso de restricciones de miembro, funciones insertadas pueden resultar útil para optimizar el código.</span><span class="sxs-lookup"><span data-stu-id="fb317-109">Other than enabling the use of member constraints, inline functions can be helpful in optimizing code.</span></span> <span data-ttu-id="fb317-110">Sin embargo, el uso excesivo de funciones insertadas puede provocar que el código sea menos resistente a los cambios en las optimizaciones del compilador y la implementación de funciones de la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="fb317-110">However, overuse of inline functions can cause your code to be less resistant to changes in compiler optimizations and the implementation of library functions.</span></span> <span data-ttu-id="fb317-111">Por esta razón, debe evitar el uso de funciones inline para la optimización, a menos que se han intentado todas las otras técnicas de optimización.</span><span class="sxs-lookup"><span data-stu-id="fb317-111">For this reason, you should avoid using inline functions for optimization unless you have tried all other optimization techniques.</span></span> <span data-ttu-id="fb317-112">Realizar una función o método en línea a veces puede mejorar el rendimiento, pero no es siempre el caso.</span><span class="sxs-lookup"><span data-stu-id="fb317-112">Making a function or method inline can sometimes improve performance, but that is not always the case.</span></span> <span data-ttu-id="fb317-113">Por lo tanto, también debe usar las medidas de rendimiento para comprobar que realizar cualquier función especificada insertada en realidad tienen un efecto positivo.</span><span class="sxs-lookup"><span data-stu-id="fb317-113">Therefore, you should also use performance measurements to verify that making any given function inline does in fact have a positive effect.</span></span>

<span data-ttu-id="fb317-114">El `inline` modificador se puede aplicar a las funciones en el nivel superior, en el nivel de módulo o en el nivel de método en una clase.</span><span class="sxs-lookup"><span data-stu-id="fb317-114">The `inline` modifier can be applied to functions at the top level, at the module level, or at the method level in a class.</span></span>

<span data-ttu-id="fb317-115">En el ejemplo de código siguiente se muestra una función inline en el nivel superior, un método de instancia insertado y un método estático insertado.</span><span class="sxs-lookup"><span data-stu-id="fb317-115">The following code example illustrates an inline function at the top level, an inline instance method, and an inline static method.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet201.fs)]
    
## <a name="inline-functions-and-type-inference"></a><span data-ttu-id="fb317-116">Funciones inline e inferencia de tipo</span><span class="sxs-lookup"><span data-stu-id="fb317-116">Inline Functions and Type Inference</span></span>
<span data-ttu-id="fb317-117">La presencia de `inline` afecta a la inferencia de tipo.</span><span class="sxs-lookup"><span data-stu-id="fb317-117">The presence of `inline` affects type inference.</span></span> <span data-ttu-id="fb317-118">Esto es porque las funciones insertadas pueden resueltos estáticamente parámetros de tipo, mientras que no sean inline (funciones) no pueden.</span><span class="sxs-lookup"><span data-stu-id="fb317-118">This is because inline functions can have statically resolved type parameters, whereas non-inline functions cannot.</span></span> <span data-ttu-id="fb317-119">En el ejemplo de código siguiente se muestra un caso donde `inline` es útil porque se usa una función que tiene un parámetro de tipo resueltos estáticamente, la `float` operador de conversión.</span><span class="sxs-lookup"><span data-stu-id="fb317-119">The following code example shows a case where `inline` is helpful because you are using a function that has a statically resolved type parameter, the `float` conversion operator.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet202.fs)]

<span data-ttu-id="fb317-120">Sin el `inline` fuerza la inferencia de tipo modificador, la función para que acepte un tipo específico, en este caso `int`.</span><span class="sxs-lookup"><span data-stu-id="fb317-120">Without the `inline` modifier, type inference forces the function to take a specific type, in this case `int`.</span></span> <span data-ttu-id="fb317-121">Pero con la `inline` modificador, la función también se deduce que tiene un parámetro de tipo resueltos estáticamente.</span><span class="sxs-lookup"><span data-stu-id="fb317-121">But with the `inline` modifier, the function is also inferred to have a statically resolved type parameter.</span></span> <span data-ttu-id="fb317-122">Con el `inline` modificador, el tipo se deduce que la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="fb317-122">With the `inline` modifier, the type is inferred to be the following:</span></span>

```fsharp
^a -> unit when ^a : (static member op_Explicit : ^a -> float)
```

<span data-ttu-id="fb317-123">Esto significa que la función acepta cualquier tipo que admita una conversión a **float**.</span><span class="sxs-lookup"><span data-stu-id="fb317-123">This means that the function accepts any type that supports a conversion to **float**.</span></span>


## <a name="see-also"></a><span data-ttu-id="fb317-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb317-124">See Also</span></span>
[<span data-ttu-id="fb317-125">Funciones</span><span class="sxs-lookup"><span data-stu-id="fb317-125">Functions</span></span>](index.md)

[<span data-ttu-id="fb317-126">Restricciones</span><span class="sxs-lookup"><span data-stu-id="fb317-126">Constraints</span></span>](../generics/constraints.md)

[<span data-ttu-id="fb317-127">Parámetros de tipo resueltos estáticamente</span><span class="sxs-lookup"><span data-stu-id="fb317-127">Statically Resolved Type Parameters</span></span>](../generics/statically-resolved-type-parameters.md)
