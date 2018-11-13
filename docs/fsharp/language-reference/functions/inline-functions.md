---
title: Funciones inline (F#)
description: Obtenga información sobre cómo usar F# en línea las funciones que se integran directamente en el código de llamada.
ms.date: 05/16/2016
ms.openlocfilehash: 47fca0fe34630792aeb0908b0cee02a927e2567d
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2018
ms.locfileid: "45745950"
---
# <a name="inline-functions"></a><span data-ttu-id="f3f85-103">Funciones insertadas</span><span class="sxs-lookup"><span data-stu-id="f3f85-103">Inline Functions</span></span>

<span data-ttu-id="f3f85-104">*Las funciones insertadas* son funciones que se integran directamente en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="f3f85-104">*Inline functions* are functions that are integrated directly into the calling code.</span></span>

## <a name="using-inline-functions"></a><span data-ttu-id="f3f85-105">Uso de funciones Inline</span><span class="sxs-lookup"><span data-stu-id="f3f85-105">Using Inline Functions</span></span>

<span data-ttu-id="f3f85-106">Al usar parámetros de tipo estático, todas las funciones que están parametrizadas según los parámetros de tipo deben ser en línea.</span><span class="sxs-lookup"><span data-stu-id="f3f85-106">When you use static type parameters, any functions that are parameterized by type parameters must be inline.</span></span> <span data-ttu-id="f3f85-107">Esto garantiza que el compilador puede resolver estos parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="f3f85-107">This guarantees that the compiler can resolve these type parameters.</span></span> <span data-ttu-id="f3f85-108">Cuando se usan parámetros de tipo genérico normal, no hay ninguna restricción.</span><span class="sxs-lookup"><span data-stu-id="f3f85-108">When you use ordinary generic type parameters, there is no such restriction.</span></span>

<span data-ttu-id="f3f85-109">Además de habilitar el uso de restricciones de miembro, funciones insertadas pueden ser útil para optimizar el código.</span><span class="sxs-lookup"><span data-stu-id="f3f85-109">Other than enabling the use of member constraints, inline functions can be helpful in optimizing code.</span></span> <span data-ttu-id="f3f85-110">Sin embargo, uso excesivo de las funciones insertadas puede provocar que el código sea menos resistente a los cambios en las optimizaciones del compilador y la implementación de funciones de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="f3f85-110">However, overuse of inline functions can cause your code to be less resistant to changes in compiler optimizations and the implementation of library functions.</span></span> <span data-ttu-id="f3f85-111">Por este motivo, debe evitar el uso de funciones insertadas para la optimización, a menos que haya intentado todas las otras técnicas de optimización.</span><span class="sxs-lookup"><span data-stu-id="f3f85-111">For this reason, you should avoid using inline functions for optimization unless you have tried all other optimization techniques.</span></span> <span data-ttu-id="f3f85-112">Realizar una función o método en línea a veces puede mejorar el rendimiento, pero no es siempre el caso.</span><span class="sxs-lookup"><span data-stu-id="f3f85-112">Making a function or method inline can sometimes improve performance, but that is not always the case.</span></span> <span data-ttu-id="f3f85-113">Por lo tanto, también debe usar las medidas de rendimiento para comprobar que la que hace el código de una función realmente tiene un efecto positivo.</span><span class="sxs-lookup"><span data-stu-id="f3f85-113">Therefore, you should also use performance measurements to verify that making any given function inline does in fact have a positive effect.</span></span>

<span data-ttu-id="f3f85-114">El `inline` modificador se puede aplicar a las funciones en el nivel superior, en el nivel de módulo o en el nivel de método en una clase.</span><span class="sxs-lookup"><span data-stu-id="f3f85-114">The `inline` modifier can be applied to functions at the top level, at the module level, or at the method level in a class.</span></span>

<span data-ttu-id="f3f85-115">El ejemplo de código siguiente muestra una función inline en el nivel superior, un método de instancia en línea y un método estático en línea.</span><span class="sxs-lookup"><span data-stu-id="f3f85-115">The following code example illustrates an inline function at the top level, an inline instance method, and an inline static method.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet201.fs)]

## <a name="inline-functions-and-type-inference"></a><span data-ttu-id="f3f85-116">Las funciones insertadas e inferencia de tipo</span><span class="sxs-lookup"><span data-stu-id="f3f85-116">Inline Functions and Type Inference</span></span>

<span data-ttu-id="f3f85-117">La presencia de `inline` afecta a la inferencia de tipo.</span><span class="sxs-lookup"><span data-stu-id="f3f85-117">The presence of `inline` affects type inference.</span></span> <span data-ttu-id="f3f85-118">Esto es porque las funciones insertadas pueden resueltos estáticamente los parámetros de tipo, mientras que las funciones no insertadas no.</span><span class="sxs-lookup"><span data-stu-id="f3f85-118">This is because inline functions can have statically resolved type parameters, whereas non-inline functions cannot.</span></span> <span data-ttu-id="f3f85-119">El ejemplo de código siguiente muestra un caso donde `inline` es útil porque, utilizas una función que tiene un parámetro de tipo resueltos estáticamente el `float` operador de conversión.</span><span class="sxs-lookup"><span data-stu-id="f3f85-119">The following code example shows a case where `inline` is helpful because you are using a function that has a statically resolved type parameter, the `float` conversion operator.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet202.fs)]

<span data-ttu-id="f3f85-120">Sin el `inline` fuerza la inferencia de tipo modificador, la función que tome un tipo específico, en este caso `int`.</span><span class="sxs-lookup"><span data-stu-id="f3f85-120">Without the `inline` modifier, type inference forces the function to take a specific type, in this case `int`.</span></span> <span data-ttu-id="f3f85-121">Pero con la `inline` modificador, la función también se infiere para tener un parámetro de tipo resueltos estáticamente.</span><span class="sxs-lookup"><span data-stu-id="f3f85-121">But with the `inline` modifier, the function is also inferred to have a statically resolved type parameter.</span></span> <span data-ttu-id="f3f85-122">Con el `inline` modificador, el tipo se infiere para ser lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f3f85-122">With the `inline` modifier, the type is inferred to be the following:</span></span>

```fsharp
^a -> unit when ^a : (static member op_Explicit : ^a -> float)
```

<span data-ttu-id="f3f85-123">Esto significa que la función acepta cualquier tipo que admita una conversión a **float**.</span><span class="sxs-lookup"><span data-stu-id="f3f85-123">This means that the function accepts any type that supports a conversion to **float**.</span></span>

## <a name="see-also"></a><span data-ttu-id="f3f85-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="f3f85-124">See also</span></span>

- [<span data-ttu-id="f3f85-125">Funciones</span><span class="sxs-lookup"><span data-stu-id="f3f85-125">Functions</span></span>](index.md)
- [<span data-ttu-id="f3f85-126">Restricciones</span><span class="sxs-lookup"><span data-stu-id="f3f85-126">Constraints</span></span>](../generics/constraints.md)
- [<span data-ttu-id="f3f85-127">Parámetros de tipo resueltos estáticamente</span><span class="sxs-lookup"><span data-stu-id="f3f85-127">Statically Resolved Type Parameters</span></span>](../generics/statically-resolved-type-parameters.md)
