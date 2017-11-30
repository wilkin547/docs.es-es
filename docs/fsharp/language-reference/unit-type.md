---
title: Tipo unit (F#)
description: "Obtenga información acerca de cómo el tipo de 'unidad' F # a menudo se usa para contener el lugar donde se requiere un valor mediante la sintaxis del lenguaje cuando se es necesario o deseable ningún valor."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: eabbb6d7-80f3-4fa5-80b4-0f48982466a7
ms.openlocfilehash: 60ac08c0e3f8380a8f9dec7a083ede93c68bb0e8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="unit-type"></a><span data-ttu-id="a4874-104">Unit (Tipo)</span><span class="sxs-lookup"><span data-stu-id="a4874-104">Unit Type</span></span>

<span data-ttu-id="a4874-105">El `unit` es un tipo que indica la ausencia de un valor específico; el `unit` tipo tiene un único valor, que actúa como un marcador de posición cuando ningún otro valor existe o es necesario.</span><span class="sxs-lookup"><span data-stu-id="a4874-105">The `unit` type is a type that indicates the absence of a specific value; the `unit` type has only a single value, which acts as a placeholder when no other value exists or is needed.</span></span>


## <a name="syntax"></a><span data-ttu-id="a4874-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a4874-106">Syntax</span></span>

```fsharp
// The value of the unit type.
()
```

## <a name="remarks"></a><span data-ttu-id="a4874-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a4874-107">Remarks</span></span>
<span data-ttu-id="a4874-108">Cada expresión de F # debe evaluarse como un valor.</span><span class="sxs-lookup"><span data-stu-id="a4874-108">Every F# expression must evaluate to a value.</span></span> <span data-ttu-id="a4874-109">Para las expresiones que no generan un valor que es de interés, el valor de tipo `unit` se utiliza.</span><span class="sxs-lookup"><span data-stu-id="a4874-109">For expressions that do not generate a value that is of interest, the value of type `unit` is used.</span></span> <span data-ttu-id="a4874-110">El `unit` tipo es similar a la `void` tipo en lenguajes como C# y C++.</span><span class="sxs-lookup"><span data-stu-id="a4874-110">The `unit` type resembles the `void` type in languages such as C# and C++.</span></span>

<span data-ttu-id="a4874-111">El `unit` tipo tiene un solo valor y ese valor se indica mediante el token `()`.</span><span class="sxs-lookup"><span data-stu-id="a4874-111">The `unit` type has a single value, and that value is indicated by the token `()`.</span></span>

<span data-ttu-id="a4874-112">El valor de la `unit` tipo suele utilizarse en programación para mantener la posición donde se requiere un valor mediante la sintaxis del lenguaje, pero cuando se es necesario o deseable ningún valor de F #.</span><span class="sxs-lookup"><span data-stu-id="a4874-112">The value of the `unit` type is often used in F# programming to hold the place where a value is required by the language syntax, but when no value is needed or desired.</span></span> <span data-ttu-id="a4874-113">Un ejemplo podría ser el valor devuelto de un `printf` función.</span><span class="sxs-lookup"><span data-stu-id="a4874-113">An example might be the return value of a `printf` function.</span></span> <span data-ttu-id="a4874-114">Dado que las acciones importantes de la `printf` operación se realiza en la función, la función no tiene que devolver un valor real.</span><span class="sxs-lookup"><span data-stu-id="a4874-114">Because the important actions of the `printf` operation occur in the function, the function does not have to return an actual value.</span></span> <span data-ttu-id="a4874-115">Por lo tanto, el valor devuelto es de tipo `unit`.</span><span class="sxs-lookup"><span data-stu-id="a4874-115">Therefore, the return value is of type `unit`.</span></span>

<span data-ttu-id="a4874-116">Algunas construcciones esperan un `unit` valor.</span><span class="sxs-lookup"><span data-stu-id="a4874-116">Some constructs expect a `unit` value.</span></span> <span data-ttu-id="a4874-117">Por ejemplo, un `do` enlace o en cualquier código en el nivel superior de un módulo se espera que se evalúen como un `unit` valor.</span><span class="sxs-lookup"><span data-stu-id="a4874-117">For example, a `do` binding or any code at the top level of a module is expected to evaluate to a `unit` value.</span></span> <span data-ttu-id="a4874-118">El compilador emite una advertencia cuando un `do` enlace o el código en el nivel superior de un módulo genera un resultado distinto de la `unit` valor que no se utiliza, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="a4874-118">The compiler reports a warning when a `do` binding or code at the top level of a module produces a result other than the `unit` value that is not used, as shown in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet901.fs)]

<span data-ttu-id="a4874-119">Esta advertencia es una característica de programación funcional; no aparecen en otros lenguajes de programación. NET.</span><span class="sxs-lookup"><span data-stu-id="a4874-119">This warning is a characteristic of functional programming; it does not appear in other .NET programming languages.</span></span> <span data-ttu-id="a4874-120">En un programa puramente funcional, en el que las funciones no tienen efectos secundarios, el valor devuelto final es el único resultado de una llamada de función.</span><span class="sxs-lookup"><span data-stu-id="a4874-120">In a purely functional program, in which functions do not have any side effects, the final return value is the only result of a function call.</span></span> <span data-ttu-id="a4874-121">Por lo tanto, cuando se omite el resultado, es un posible error de programación.</span><span class="sxs-lookup"><span data-stu-id="a4874-121">Therefore, when the result is ignored, it is a possible programming error.</span></span> <span data-ttu-id="a4874-122">Aunque F # no es un lenguaje de programación puramente funcional, es recomendable seguir el estilo de programación funcional siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="a4874-122">Although F# is not a purely functional programming language, it is a good practice to follow functional programming style whenever possible.</span></span>

## <a name="see-also"></a><span data-ttu-id="a4874-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="a4874-123">See Also</span></span>
[<span data-ttu-id="a4874-124">Primitivos</span><span class="sxs-lookup"><span data-stu-id="a4874-124">Primitive</span></span>](primitive-types.md)

[<span data-ttu-id="a4874-125">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="a4874-125">F# Language Reference</span></span>](index.md)
