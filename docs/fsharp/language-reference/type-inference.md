---
title: Inferencia de tipos (F#)
description: 'Obtenga información acerca de cómo el compilador de F # infiere los tipos de valores, variables, parámetros y valores devueltos.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: b5f7861c0a638baebfe72c9b4cf7dca119339ae3
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="type-inference"></a><span data-ttu-id="d07fa-103">Inferencia de tipos</span><span class="sxs-lookup"><span data-stu-id="d07fa-103">Type Inference</span></span>

<span data-ttu-id="d07fa-104">Este tema describe cómo el compilador de F # infiere los tipos de valores, variables, parámetros y valores devueltos.</span><span class="sxs-lookup"><span data-stu-id="d07fa-104">This topic describes how the F# compiler infers the types of values, variables, parameters and return values.</span></span>

## <a name="type-inference-in-general"></a><span data-ttu-id="d07fa-105">Inferencia de tipos en General</span><span class="sxs-lookup"><span data-stu-id="d07fa-105">Type Inference in General</span></span>
<span data-ttu-id="d07fa-106">La idea de inferencia de tipos es que no es necesario especificar los tipos de construcciones de F # excepto cuando el compilador no puede deducir de forma concluyente el tipo.</span><span class="sxs-lookup"><span data-stu-id="d07fa-106">The idea of type inference is that you do not have to specify the types of F# constructs except when the compiler cannot conclusively deduce the type.</span></span> <span data-ttu-id="d07fa-107">Omisión de información de tipos explícita no significa que F # es un lenguaje con tipos dinámicos o que los valores de F # estén débilmente tipados.</span><span class="sxs-lookup"><span data-stu-id="d07fa-107">Omitting explicit type information does not mean that F# is a dynamically typed language or that values in F# are weakly typed.</span></span> <span data-ttu-id="d07fa-108">F # es un lenguaje de tipos estáticos, lo que significa que el compilador deduce un tipo exacto para cada construcción durante la compilación.</span><span class="sxs-lookup"><span data-stu-id="d07fa-108">F# is a statically typed language, which means that the compiler deduces an exact type for each construct during compilation.</span></span> <span data-ttu-id="d07fa-109">Si no hay suficiente información para que el compilador deduzca los tipos de cada construcción, debe proporcionar información adicional sobre tipos, normalmente mediante la adición de anotaciones de tipo explícitas en alguna parte en el código.</span><span class="sxs-lookup"><span data-stu-id="d07fa-109">If there is not enough information for the compiler to deduce the types of each construct, you must supply additional type information, typically by adding explicit type annotations somewhere in the code.</span></span>


## <a name="inference-of-parameter-and-return-types"></a><span data-ttu-id="d07fa-110">Inferencia de parámetro y tipos de valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d07fa-110">Inference of Parameter and Return Types</span></span>
<span data-ttu-id="d07fa-111">En una lista de parámetros, no es necesario especificar el tipo de cada parámetro.</span><span class="sxs-lookup"><span data-stu-id="d07fa-111">In a parameter list, you do not have to specify the type of each parameter.</span></span> <span data-ttu-id="d07fa-112">Sin embargo, F # es un lenguaje con tipos estáticos y, por tanto, cada valor y expresión tiene un tipo definido en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="d07fa-112">And yet, F# is a statically typed language, and therefore every value and expression has a definite type at compile time.</span></span> <span data-ttu-id="d07fa-113">Para los tipos que no se especifique explícitamente, el compilador deduce el tipo en función del contexto.</span><span class="sxs-lookup"><span data-stu-id="d07fa-113">For those types that you do not specify explicitly, the compiler infers the type based on the context.</span></span> <span data-ttu-id="d07fa-114">Si el tipo no es lo contrario especificado, se deduce para ser genérico.</span><span class="sxs-lookup"><span data-stu-id="d07fa-114">If the type is not otherwise specified, it is inferred to be generic.</span></span> <span data-ttu-id="d07fa-115">Si el código utiliza un valor de forma incoherente, de tal forma que hay no único tipo deducido que satisfaga todos los usos de un valor, que el compilador informa de un error.</span><span class="sxs-lookup"><span data-stu-id="d07fa-115">If the code uses a value inconsistently, in such a way that there is no single inferred type that satisfies all the uses of a value, the compiler reports an error.</span></span>

<span data-ttu-id="d07fa-116">El tipo de valor devuelto de una función está determinado por el tipo de la última expresión de la función.</span><span class="sxs-lookup"><span data-stu-id="d07fa-116">The return type of a function is determined by the type of the last expression in the function.</span></span>

<span data-ttu-id="d07fa-117">Por ejemplo, en el código siguiente, los tipos de parámetro `a` y `b` y el tipo de valor devuelto se deducen como `int` porque el literal `100` es de tipo `int`.</span><span class="sxs-lookup"><span data-stu-id="d07fa-117">For example, in the following code, the parameter types `a` and `b` and the return type are all inferred to be `int` because the literal `100` is of type `int`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet301.fs)]

<span data-ttu-id="d07fa-118">Puede influir en la inferencia de tipo cambiando los literales.</span><span class="sxs-lookup"><span data-stu-id="d07fa-118">You can influence type inference by changing the literals.</span></span> <span data-ttu-id="d07fa-119">Si realiza la `100` una `uint32` anexando el sufijo `u`, los tipos de `a`, `b`, y el valor devuelto se deducen como `uint32`.</span><span class="sxs-lookup"><span data-stu-id="d07fa-119">If you make the `100` a `uint32` by appending the suffix `u`, the types of `a`, `b`, and the return value are inferred to be `uint32`.</span></span>

<span data-ttu-id="d07fa-120">También puede influir en inferencia de tipos utilizando otras construcciones que impliquen restricciones sobre el tipo, como las funciones y métodos que funcionan con solo un tipo determinado.</span><span class="sxs-lookup"><span data-stu-id="d07fa-120">You can also influence type inference by using other constructs that imply restrictions on the type, such as functions and methods that work with only a particular type.</span></span>

<span data-ttu-id="d07fa-121">Además, puede aplicar anotaciones de tipo explícitas a los parámetros de función o un método o a las variables en las expresiones, como se muestra en los ejemplos siguientes.</span><span class="sxs-lookup"><span data-stu-id="d07fa-121">Also, you can apply explicit type annotations to function or method parameters or to variables in expressions, as shown in the following examples.</span></span> <span data-ttu-id="d07fa-122">Producir un error si se producen conflictos entre diferentes restricciones.</span><span class="sxs-lookup"><span data-stu-id="d07fa-122">Errors result if conflicts occur between different constraints.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet302.fs)]

<span data-ttu-id="d07fa-123">Puede especificar explícitamente el valor devuelto de una función proporcionando una anotación de tipo después de que todos los parámetros.</span><span class="sxs-lookup"><span data-stu-id="d07fa-123">You can also explicitly specify the return value of a function by providing a type annotation after all the parameters.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet303.fs)]

<span data-ttu-id="d07fa-124">Un caso común donde es útil en un parámetro de una anotación de tipo es cuando el parámetro es un tipo de objeto y desea usar a un miembro.</span><span class="sxs-lookup"><span data-stu-id="d07fa-124">A common case where a type annotation is useful on a parameter is when the parameter is an object type and you want to use a member.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet304.fs)]
    
## <a name="automatic-generalization"></a><span data-ttu-id="d07fa-125">Generalización automática</span><span class="sxs-lookup"><span data-stu-id="d07fa-125">Automatic Generalization</span></span>
<span data-ttu-id="d07fa-126">Si el código de función no es depende del tipo de un parámetro, el compilador considera que el parámetro para ser genérico.</span><span class="sxs-lookup"><span data-stu-id="d07fa-126">If the function code is not dependent on the type of a parameter, the compiler considers the parameter to be generic.</span></span> <span data-ttu-id="d07fa-127">Esto se denomina *generalización automática*, y puede ser una ayuda eficaz para escribir código genérico sin aumentar la complejidad.</span><span class="sxs-lookup"><span data-stu-id="d07fa-127">This is called *automatic generalization*, and it can be a powerful aid to writing generic code without increasing complexity.</span></span>

<span data-ttu-id="d07fa-128">Por ejemplo, la función siguiente combina dos parámetros de cualquier tipo en una tupla.</span><span class="sxs-lookup"><span data-stu-id="d07fa-128">For example, the following function combines two parameters of any type into a tuple.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet305.fs)]

<span data-ttu-id="d07fa-129">El tipo se deduce como</span><span class="sxs-lookup"><span data-stu-id="d07fa-129">The type is inferred to be</span></span>

```fsharp
'a -> 'b -> 'a * 'b
```

## <a name="additional-information"></a><span data-ttu-id="d07fa-130">Información adicional</span><span class="sxs-lookup"><span data-stu-id="d07fa-130">Additional Information</span></span>
<span data-ttu-id="d07fa-131">Inferencia de tipo se describe con más detalle en la especificación del lenguaje F #.</span><span class="sxs-lookup"><span data-stu-id="d07fa-131">Type inference is described in more detail in the F# Language Specification.</span></span>


## <a name="see-also"></a><span data-ttu-id="d07fa-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="d07fa-132">See Also</span></span>
[<span data-ttu-id="d07fa-133">Generalización automática</span><span class="sxs-lookup"><span data-stu-id="d07fa-133">Automatic Generalization</span></span>](generics/automatic-generalization.md)
