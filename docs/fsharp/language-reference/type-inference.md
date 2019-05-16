---
title: Inferencia de tipos
description: Obtenga información sobre cómo el F# compilador infiere los tipos de valores, variables, parámetros y valores devueltos.
ms.date: 05/16/2016
ms.openlocfilehash: ab1a4aa8df4312287df749d5d6d0ea2858091152
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641663"
---
# <a name="type-inference"></a><span data-ttu-id="5346f-103">Inferencia de tipos</span><span class="sxs-lookup"><span data-stu-id="5346f-103">Type Inference</span></span>

<span data-ttu-id="5346f-104">Este tema se describe cómo el F# compilador infiere los tipos de valores, variables, parámetros y valores devueltos.</span><span class="sxs-lookup"><span data-stu-id="5346f-104">This topic describes how the F# compiler infers the types of values, variables, parameters and return values.</span></span>

## <a name="type-inference-in-general"></a><span data-ttu-id="5346f-105">Inferencia de tipos en General</span><span class="sxs-lookup"><span data-stu-id="5346f-105">Type Inference in General</span></span>

<span data-ttu-id="5346f-106">La idea de inferencia de tipos es que no es necesario especificar los tipos de F# construcciones excepto cuando el compilador de forma concluyente no puede deducir el tipo.</span><span class="sxs-lookup"><span data-stu-id="5346f-106">The idea of type inference is that you do not have to specify the types of F# constructs except when the compiler cannot conclusively deduce the type.</span></span> <span data-ttu-id="5346f-107">Omitir información de tipo explícita no significa que F# es un lenguaje dinámico o que los valores de F# son débilmente tipado.</span><span class="sxs-lookup"><span data-stu-id="5346f-107">Omitting explicit type information does not mean that F# is a dynamically typed language or that values in F# are weakly typed.</span></span> <span data-ttu-id="5346f-108">F#es un lenguaje de tipo estático, lo que significa que el compilador deduce un tipo exacto para cada construcción durante la compilación.</span><span class="sxs-lookup"><span data-stu-id="5346f-108">F# is a statically typed language, which means that the compiler deduces an exact type for each construct during compilation.</span></span> <span data-ttu-id="5346f-109">Si no hay información suficiente para que el compilador deduzca los tipos de cada construcción, debe proporcionar información adicional de tipo, normalmente mediante la adición de anotaciones de tipo explícitas en algún lugar en el código.</span><span class="sxs-lookup"><span data-stu-id="5346f-109">If there is not enough information for the compiler to deduce the types of each construct, you must supply additional type information, typically by adding explicit type annotations somewhere in the code.</span></span>

## <a name="inference-of-parameter-and-return-types"></a><span data-ttu-id="5346f-110">Inferencia de parámetro y tipos de valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5346f-110">Inference of Parameter and Return Types</span></span>

<span data-ttu-id="5346f-111">En una lista de parámetros, no es necesario especificar el tipo de cada parámetro.</span><span class="sxs-lookup"><span data-stu-id="5346f-111">In a parameter list, you do not have to specify the type of each parameter.</span></span> <span data-ttu-id="5346f-112">Y aún, F# es un lenguaje de tipo estático y, por lo tanto, cada valor y expresión tiene un tipo definido en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="5346f-112">And yet, F# is a statically typed language, and therefore every value and expression has a definite type at compile time.</span></span> <span data-ttu-id="5346f-113">Para esos tipos que no se especifique explícitamente, el compilador deduce el tipo según el contexto.</span><span class="sxs-lookup"><span data-stu-id="5346f-113">For those types that you do not specify explicitly, the compiler infers the type based on the context.</span></span> <span data-ttu-id="5346f-114">Si el tipo no es lo contrario especificado, se deduce para ser genérico.</span><span class="sxs-lookup"><span data-stu-id="5346f-114">If the type is not otherwise specified, it is inferred to be generic.</span></span> <span data-ttu-id="5346f-115">Si el código usa un valor de forma incoherente, de tal manera que no es único no puede inferir tipo que cumpla todos los usos de un valor, que el compilador notifica un error.</span><span class="sxs-lookup"><span data-stu-id="5346f-115">If the code uses a value inconsistently, in such a way that there is no single inferred type that satisfies all the uses of a value, the compiler reports an error.</span></span>

<span data-ttu-id="5346f-116">El tipo de valor devuelto de una función viene determinada por el tipo de la última expresión en la función.</span><span class="sxs-lookup"><span data-stu-id="5346f-116">The return type of a function is determined by the type of the last expression in the function.</span></span>

<span data-ttu-id="5346f-117">Por ejemplo, en el código siguiente, los tipos de parámetro `a` y `b` y el tipo de valor devuelto se infiere para ser `int` porque el literal `100` es de tipo `int`.</span><span class="sxs-lookup"><span data-stu-id="5346f-117">For example, in the following code, the parameter types `a` and `b` and the return type are all inferred to be `int` because the literal `100` is of type `int`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet301.fs)]

<span data-ttu-id="5346f-118">Puede influir en la inferencia de tipo cambiando los literales.</span><span class="sxs-lookup"><span data-stu-id="5346f-118">You can influence type inference by changing the literals.</span></span> <span data-ttu-id="5346f-119">Si realiza la `100` un `uint32` anexando el sufijo `u`, los tipos de `a`, `b`, y el valor devuelto se infiere para ser `uint32`.</span><span class="sxs-lookup"><span data-stu-id="5346f-119">If you make the `100` a `uint32` by appending the suffix `u`, the types of `a`, `b`, and the return value are inferred to be `uint32`.</span></span>

<span data-ttu-id="5346f-120">También puede influir en inferencia de tipos mediante el uso de otras construcciones que implican restricciones sobre el tipo, como las funciones y métodos que funcionan con solo un tipo determinado.</span><span class="sxs-lookup"><span data-stu-id="5346f-120">You can also influence type inference by using other constructs that imply restrictions on the type, such as functions and methods that work with only a particular type.</span></span>

<span data-ttu-id="5346f-121">Además, puede aplicar anotaciones de tipo explícitas a parámetros de función o un método o a variables en expresiones, como se muestra en los ejemplos siguientes.</span><span class="sxs-lookup"><span data-stu-id="5346f-121">Also, you can apply explicit type annotations to function or method parameters or to variables in expressions, as shown in the following examples.</span></span> <span data-ttu-id="5346f-122">Producir un error si se producen conflictos entre las distintas restricciones.</span><span class="sxs-lookup"><span data-stu-id="5346f-122">Errors result if conflicts occur between different constraints.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet302.fs)]

<span data-ttu-id="5346f-123">Puede especificar explícitamente el valor devuelto de una función proporcionando una anotación de tipo después de todo los parámetros.</span><span class="sxs-lookup"><span data-stu-id="5346f-123">You can also explicitly specify the return value of a function by providing a type annotation after all the parameters.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet303.fs)]

<span data-ttu-id="5346f-124">Un caso común donde es útil en un parámetro de una anotación de tipo es cuando el parámetro es un tipo de objeto y desea usar a un miembro.</span><span class="sxs-lookup"><span data-stu-id="5346f-124">A common case where a type annotation is useful on a parameter is when the parameter is an object type and you want to use a member.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet304.fs)]

## <a name="automatic-generalization"></a><span data-ttu-id="5346f-125">Generalización automática</span><span class="sxs-lookup"><span data-stu-id="5346f-125">Automatic Generalization</span></span>

<span data-ttu-id="5346f-126">Si el código de función no es depende del tipo de un parámetro, el compilador considera que el parámetro es genérico.</span><span class="sxs-lookup"><span data-stu-id="5346f-126">If the function code is not dependent on the type of a parameter, the compiler considers the parameter to be generic.</span></span> <span data-ttu-id="5346f-127">Esto se denomina *generalización automática*, y puede ser una ayuda eficaz para escribir código genérico sin aumentar la complejidad.</span><span class="sxs-lookup"><span data-stu-id="5346f-127">This is called *automatic generalization*, and it can be a powerful aid to writing generic code without increasing complexity.</span></span>

<span data-ttu-id="5346f-128">Por ejemplo, la función siguiente combina dos parámetros de cualquier tipo en una tupla.</span><span class="sxs-lookup"><span data-stu-id="5346f-128">For example, the following function combines two parameters of any type into a tuple.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet305.fs)]

<span data-ttu-id="5346f-129">El tipo se infiere para ser</span><span class="sxs-lookup"><span data-stu-id="5346f-129">The type is inferred to be</span></span>

```fsharp
'a -> 'b -> 'a * 'b
```

## <a name="additional-information"></a><span data-ttu-id="5346f-130">Información adicional</span><span class="sxs-lookup"><span data-stu-id="5346f-130">Additional Information</span></span>

<span data-ttu-id="5346f-131">Inferencia de tipos se describe con más detalle en la F# especificación del lenguaje.</span><span class="sxs-lookup"><span data-stu-id="5346f-131">Type inference is described in more detail in the F# Language Specification.</span></span>

## <a name="see-also"></a><span data-ttu-id="5346f-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="5346f-132">See also</span></span>

- [<span data-ttu-id="5346f-133">Generalización automática</span><span class="sxs-lookup"><span data-stu-id="5346f-133">Automatic Generalization</span></span>](generics/automatic-generalization.md)
