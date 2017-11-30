---
title: Funciones inline (F#)
description: "Obtenga información acerca de cómo usar F # en línea las funciones que se integran directamente en el código de llamada."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 3fa31178-08f8-463d-9d41-d29220a90027
ms.openlocfilehash: 0489d411e2754eaab6a10ff0feb4405491b3b511
ms.sourcegitcommit: 425524461530f020f9747492b42f8cd72b011ae7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2017
---
# <a name="inline-functions"></a><span data-ttu-id="d5888-104">Funciones insertadas</span><span class="sxs-lookup"><span data-stu-id="d5888-104">Inline Functions</span></span>

<span data-ttu-id="d5888-105">*Funciones inline* son funciones que se integran directamente en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="d5888-105">*Inline functions* are functions that are integrated directly into the calling code.</span></span>


## <a name="using-inline-functions"></a><span data-ttu-id="d5888-106">Uso de funciones Inline</span><span class="sxs-lookup"><span data-stu-id="d5888-106">Using Inline Functions</span></span>
<span data-ttu-id="d5888-107">Cuando se usan parámetros de tipo estático, las funciones con parámetros de tipo deben ser funciones inline.</span><span class="sxs-lookup"><span data-stu-id="d5888-107">When you use static type parameters, any functions that are parameterized by type parameters must be inline.</span></span> <span data-ttu-id="d5888-108">Esto garantiza que el compilador puede resolver estos parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="d5888-108">This guarantees that the compiler can resolve these type parameters.</span></span> <span data-ttu-id="d5888-109">Cuando se usan parámetros de tipo genérico normal, no hay ninguna restricción así.</span><span class="sxs-lookup"><span data-stu-id="d5888-109">When you use ordinary generic type parameters, there is no such restriction.</span></span>

<span data-ttu-id="d5888-110">Además de habilitar el uso de restricciones de miembro, funciones insertadas pueden resultar útil para optimizar el código.</span><span class="sxs-lookup"><span data-stu-id="d5888-110">Other than enabling the use of member constraints, inline functions can be helpful in optimizing code.</span></span> <span data-ttu-id="d5888-111">Sin embargo, el uso excesivo de funciones insertadas puede provocar que el código sea menos resistente a los cambios en las optimizaciones del compilador y la implementación de funciones de la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="d5888-111">However, overuse of inline functions can cause your code to be less resistant to changes in compiler optimizations and the implementation of library functions.</span></span> <span data-ttu-id="d5888-112">Por esta razón, debe evitar el uso de funciones inline para la optimización, a menos que se han intentado todas las otras técnicas de optimización.</span><span class="sxs-lookup"><span data-stu-id="d5888-112">For this reason, you should avoid using inline functions for optimization unless you have tried all other optimization techniques.</span></span> <span data-ttu-id="d5888-113">Realizar una función o método en línea a veces puede mejorar el rendimiento, pero no es siempre el caso.</span><span class="sxs-lookup"><span data-stu-id="d5888-113">Making a function or method inline can sometimes improve performance, but that is not always the case.</span></span> <span data-ttu-id="d5888-114">Por lo tanto, también debe usar las medidas de rendimiento para comprobar que realizar cualquier función especificada insertada en realidad tienen un efecto positivo.</span><span class="sxs-lookup"><span data-stu-id="d5888-114">Therefore, you should also use performance measurements to verify that making any given function inline does in fact have a positive effect.</span></span>

<span data-ttu-id="d5888-115">El `inline` modificador se puede aplicar a las funciones en el nivel superior, en el nivel de módulo o en el nivel de método en una clase.</span><span class="sxs-lookup"><span data-stu-id="d5888-115">The `inline` modifier can be applied to functions at the top level, at the module level, or at the method level in a class.</span></span>

<span data-ttu-id="d5888-116">En el ejemplo de código siguiente se muestra una función inline en el nivel superior, un método de instancia insertado y un método estático insertado.</span><span class="sxs-lookup"><span data-stu-id="d5888-116">The following code example illustrates an inline function at the top level, an inline instance method, and an inline static method.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet201.fs)]
    
## <a name="inline-functions-and-type-inference"></a><span data-ttu-id="d5888-117">Funciones inline e inferencia de tipo</span><span class="sxs-lookup"><span data-stu-id="d5888-117">Inline Functions and Type Inference</span></span>
<span data-ttu-id="d5888-118">La presencia de `inline` afecta a la inferencia de tipo.</span><span class="sxs-lookup"><span data-stu-id="d5888-118">The presence of `inline` affects type inference.</span></span> <span data-ttu-id="d5888-119">Esto es porque las funciones insertadas pueden resueltos estáticamente parámetros de tipo, mientras que no sean inline (funciones) no pueden.</span><span class="sxs-lookup"><span data-stu-id="d5888-119">This is because inline functions can have statically resolved type parameters, whereas non-inline functions cannot.</span></span> <span data-ttu-id="d5888-120">En el ejemplo de código siguiente se muestra un caso donde `inline` es útil porque se usa una función que tiene un parámetro de tipo resueltos estáticamente, la `float` operador de conversión.</span><span class="sxs-lookup"><span data-stu-id="d5888-120">The following code example shows a case where `inline` is helpful because you are using a function that has a statically resolved type parameter, the `float` conversion operator.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet202.fs)]

<span data-ttu-id="d5888-121">Sin el `inline` fuerza la inferencia de tipo modificador, la función para que acepte un tipo específico, en este caso `int`.</span><span class="sxs-lookup"><span data-stu-id="d5888-121">Without the `inline` modifier, type inference forces the function to take a specific type, in this case `int`.</span></span> <span data-ttu-id="d5888-122">Pero con la `inline` modificador, la función también se deduce que tiene un parámetro de tipo resueltos estáticamente.</span><span class="sxs-lookup"><span data-stu-id="d5888-122">But with the `inline` modifier, the function is also inferred to have a statically resolved type parameter.</span></span> <span data-ttu-id="d5888-123">Con el `inline` modificador, el tipo se deduce que la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="d5888-123">With the `inline` modifier, the type is inferred to be the following:</span></span>

```fsharp
^a -> unit when ^a : (static member op_Explicit : ^a -> float)
```

<span data-ttu-id="d5888-124">Esto significa que la función acepta cualquier tipo que admita una conversión a **float**.</span><span class="sxs-lookup"><span data-stu-id="d5888-124">This means that the function accepts any type that supports a conversion to **float**.</span></span>


## <a name="see-also"></a><span data-ttu-id="d5888-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="d5888-125">See Also</span></span>
[<span data-ttu-id="d5888-126">Funciones</span><span class="sxs-lookup"><span data-stu-id="d5888-126">Functions</span></span>](index.md)

[<span data-ttu-id="d5888-127">Restricciones</span><span class="sxs-lookup"><span data-stu-id="d5888-127">Constraints</span></span>](../generics/constraints.md)

[<span data-ttu-id="d5888-128">Parámetros de tipo resueltos estáticamente</span><span class="sxs-lookup"><span data-stu-id="d5888-128">Statically Resolved Type Parameters</span></span>](../generics/statically-resolved-type-parameters.md)
