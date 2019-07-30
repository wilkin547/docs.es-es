---
title: Inferencia de tipos
description: Obtenga información sobre F# cómo el compilador deduce los tipos de valores, variables, parámetros y valores devueltos.
ms.date: 05/16/2016
ms.openlocfilehash: 4b18c1a67a8b7ddadb4fb334ea4736e9fd29feb0
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630187"
---
# <a name="type-inference"></a><span data-ttu-id="98232-103">Inferencia de tipos</span><span class="sxs-lookup"><span data-stu-id="98232-103">Type Inference</span></span>

<span data-ttu-id="98232-104">En este tema se describe F# cómo el compilador deduce los tipos de valores, variables, parámetros y valores devueltos.</span><span class="sxs-lookup"><span data-stu-id="98232-104">This topic describes how the F# compiler infers the types of values, variables, parameters and return values.</span></span>

## <a name="type-inference-in-general"></a><span data-ttu-id="98232-105">Inferencia de tipos en general</span><span class="sxs-lookup"><span data-stu-id="98232-105">Type Inference in General</span></span>

<span data-ttu-id="98232-106">La idea de la inferencia de tipos es que no es necesario especificar los tipos de F# construcciones excepto cuando el compilador no puede deducir el tipo de forma concluyente.</span><span class="sxs-lookup"><span data-stu-id="98232-106">The idea of type inference is that you do not have to specify the types of F# constructs except when the compiler cannot conclusively deduce the type.</span></span> <span data-ttu-id="98232-107">Omitir la información de tipo explícita no F# significa que se trata de un lenguaje con establecimiento dinámico de F# tipos o que los valores de están débilmente tipados.</span><span class="sxs-lookup"><span data-stu-id="98232-107">Omitting explicit type information does not mean that F# is a dynamically typed language or that values in F# are weakly typed.</span></span> <span data-ttu-id="98232-108">F#es un lenguaje de tipo estático, lo que significa que el compilador deduce un tipo exacto para cada construcción durante la compilación.</span><span class="sxs-lookup"><span data-stu-id="98232-108">F# is a statically typed language, which means that the compiler deduces an exact type for each construct during compilation.</span></span> <span data-ttu-id="98232-109">Si no hay información suficiente para que el compilador deduzca los tipos de cada construcción, debe proporcionar información de tipo adicional, normalmente agregando anotaciones de tipo explícito en algún lugar del código.</span><span class="sxs-lookup"><span data-stu-id="98232-109">If there is not enough information for the compiler to deduce the types of each construct, you must supply additional type information, typically by adding explicit type annotations somewhere in the code.</span></span>

## <a name="inference-of-parameter-and-return-types"></a><span data-ttu-id="98232-110">Inferencia de tipos de parámetro y de valor devuelto</span><span class="sxs-lookup"><span data-stu-id="98232-110">Inference of Parameter and Return Types</span></span>

<span data-ttu-id="98232-111">En una lista de parámetros, no es necesario especificar el tipo de cada parámetro.</span><span class="sxs-lookup"><span data-stu-id="98232-111">In a parameter list, you do not have to specify the type of each parameter.</span></span> <span data-ttu-id="98232-112">Y, sin F# embargo, es un lenguaje de tipos estáticos y, por tanto, cada valor y expresión tiene un tipo definito en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="98232-112">And yet, F# is a statically typed language, and therefore every value and expression has a definite type at compile time.</span></span> <span data-ttu-id="98232-113">En el caso de los tipos que no se especifican de forma explícita, el compilador deduce el tipo basándose en el contexto.</span><span class="sxs-lookup"><span data-stu-id="98232-113">For those types that you do not specify explicitly, the compiler infers the type based on the context.</span></span> <span data-ttu-id="98232-114">Si el tipo no se especifica de otra forma, se deduce que es genérico.</span><span class="sxs-lookup"><span data-stu-id="98232-114">If the type is not otherwise specified, it is inferred to be generic.</span></span> <span data-ttu-id="98232-115">Si el código usa un valor de manera incoherente, de tal forma que no hay ningún tipo inferido único que cumpla todos los usos de un valor, el compilador informa de un error.</span><span class="sxs-lookup"><span data-stu-id="98232-115">If the code uses a value inconsistently, in such a way that there is no single inferred type that satisfies all the uses of a value, the compiler reports an error.</span></span>

<span data-ttu-id="98232-116">El tipo de valor devuelto de una función viene determinado por el tipo de la última expresión de la función.</span><span class="sxs-lookup"><span data-stu-id="98232-116">The return type of a function is determined by the type of the last expression in the function.</span></span>

<span data-ttu-id="98232-117">Por ejemplo, en el código siguiente, se infiere `a` que `b` `int` los tipos de parámetro y y el tipo de valor devuelto son `100` porque el literal `int`es de tipo.</span><span class="sxs-lookup"><span data-stu-id="98232-117">For example, in the following code, the parameter types `a` and `b` and the return type are all inferred to be `int` because the literal `100` is of type `int`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet301.fs)]

<span data-ttu-id="98232-118">Puede influir en la inferencia de tipos cambiando los literales.</span><span class="sxs-lookup"><span data-stu-id="98232-118">You can influence type inference by changing the literals.</span></span> <span data-ttu-id="98232-119">`100` Si realiza la `uint32` adición del sufijo `u`, los tipos de `a` `b`, y el valor devuelto se deducen a. `uint32`</span><span class="sxs-lookup"><span data-stu-id="98232-119">If you make the `100` a `uint32` by appending the suffix `u`, the types of `a`, `b`, and the return value are inferred to be `uint32`.</span></span>

<span data-ttu-id="98232-120">También puede influir en la inferencia de tipos mediante el uso de otras construcciones que impliquen restricciones en el tipo, como funciones y métodos que funcionan solo con un tipo determinado.</span><span class="sxs-lookup"><span data-stu-id="98232-120">You can also influence type inference by using other constructs that imply restrictions on the type, such as functions and methods that work with only a particular type.</span></span>

<span data-ttu-id="98232-121">Además, puede aplicar anotaciones de tipo explícitos a parámetros de función o de método o a variables en expresiones, tal como se muestra en los ejemplos siguientes.</span><span class="sxs-lookup"><span data-stu-id="98232-121">Also, you can apply explicit type annotations to function or method parameters or to variables in expressions, as shown in the following examples.</span></span> <span data-ttu-id="98232-122">Se producirán errores si se producen conflictos entre las distintas restricciones.</span><span class="sxs-lookup"><span data-stu-id="98232-122">Errors result if conflicts occur between different constraints.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet302.fs)]

<span data-ttu-id="98232-123">También puede especificar explícitamente el valor devuelto de una función proporcionando una anotación de tipo después de todos los parámetros.</span><span class="sxs-lookup"><span data-stu-id="98232-123">You can also explicitly specify the return value of a function by providing a type annotation after all the parameters.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet303.fs)]

<span data-ttu-id="98232-124">Un caso común en el que una anotación de tipo es útil en un parámetro es cuando el parámetro es un tipo de objeto y se desea usar un miembro.</span><span class="sxs-lookup"><span data-stu-id="98232-124">A common case where a type annotation is useful on a parameter is when the parameter is an object type and you want to use a member.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet304.fs)]

## <a name="automatic-generalization"></a><span data-ttu-id="98232-125">Generalización automática</span><span class="sxs-lookup"><span data-stu-id="98232-125">Automatic Generalization</span></span>

<span data-ttu-id="98232-126">Si el código de la función no depende del tipo de un parámetro, el compilador considera que el parámetro es genérico.</span><span class="sxs-lookup"><span data-stu-id="98232-126">If the function code is not dependent on the type of a parameter, the compiler considers the parameter to be generic.</span></span> <span data-ttu-id="98232-127">Esto se denomina *generalización automática*y puede ser una ayuda eficaz para escribir código genérico sin aumentar la complejidad.</span><span class="sxs-lookup"><span data-stu-id="98232-127">This is called *automatic generalization*, and it can be a powerful aid to writing generic code without increasing complexity.</span></span>

<span data-ttu-id="98232-128">Por ejemplo, la función siguiente combina dos parámetros de cualquier tipo en una tupla.</span><span class="sxs-lookup"><span data-stu-id="98232-128">For example, the following function combines two parameters of any type into a tuple.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet305.fs)]

<span data-ttu-id="98232-129">Se deduce que el tipo es</span><span class="sxs-lookup"><span data-stu-id="98232-129">The type is inferred to be</span></span>

```fsharp
'a -> 'b -> 'a * 'b
```

## <a name="additional-information"></a><span data-ttu-id="98232-130">Información adicional</span><span class="sxs-lookup"><span data-stu-id="98232-130">Additional Information</span></span>

<span data-ttu-id="98232-131">La inferencia de tipos se describe con más detalle F# en la especificación del lenguaje.</span><span class="sxs-lookup"><span data-stu-id="98232-131">Type inference is described in more detail in the F# Language Specification.</span></span>

## <a name="see-also"></a><span data-ttu-id="98232-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="98232-132">See also</span></span>

- [<span data-ttu-id="98232-133">Generalización automática</span><span class="sxs-lookup"><span data-stu-id="98232-133">Automatic Generalization</span></span>](./generics/automatic-generalization.md)
