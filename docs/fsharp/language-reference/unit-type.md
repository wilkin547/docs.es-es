---
title: Unit (Tipo)
description: Obtenga información sobre F# cómo el tipo ' Unit ' se usa a menudo para contener el lugar en el que la sintaxis del lenguaje requiere un valor cuando no se necesita ningún valor o se desea.
ms.date: 05/16/2016
ms.openlocfilehash: a5960fb05af50486a78345d10a5ad913e65729e3
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424033"
---
# <a name="unit-type"></a><span data-ttu-id="3eba4-103">Unit (Tipo)</span><span class="sxs-lookup"><span data-stu-id="3eba4-103">Unit Type</span></span>

<span data-ttu-id="3eba4-104">El tipo de `unit` es un tipo que indica la ausencia de un valor concreto; el tipo de `unit` solo tiene un valor único, que actúa como marcador de posición cuando no existe ningún otro valor o es necesario.</span><span class="sxs-lookup"><span data-stu-id="3eba4-104">The `unit` type is a type that indicates the absence of a specific value; the `unit` type has only a single value, which acts as a placeholder when no other value exists or is needed.</span></span>

## <a name="syntax"></a><span data-ttu-id="3eba4-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3eba4-105">Syntax</span></span>

```fsharp
// The value of the unit type.
()
```

## <a name="remarks"></a><span data-ttu-id="3eba4-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3eba4-106">Remarks</span></span>

<span data-ttu-id="3eba4-107">Cada F# expresión debe evaluarse como un valor.</span><span class="sxs-lookup"><span data-stu-id="3eba4-107">Every F# expression must evaluate to a value.</span></span> <span data-ttu-id="3eba4-108">En el caso de las expresiones que no generan un valor de interés, se utiliza el valor de tipo `unit`.</span><span class="sxs-lookup"><span data-stu-id="3eba4-108">For expressions that do not generate a value that is of interest, the value of type `unit` is used.</span></span> <span data-ttu-id="3eba4-109">El tipo de `unit` se parece al tipo de `void` en C# lenguajes C++como y.</span><span class="sxs-lookup"><span data-stu-id="3eba4-109">The `unit` type resembles the `void` type in languages such as C# and C++.</span></span>

<span data-ttu-id="3eba4-110">El tipo de `unit` tiene un valor único y ese valor se indica mediante el token `()`.</span><span class="sxs-lookup"><span data-stu-id="3eba4-110">The `unit` type has a single value, and that value is indicated by the token `()`.</span></span>

<span data-ttu-id="3eba4-111">El valor del tipo de `unit` se usa a menudo F# en la programación para contener el lugar donde se requiere un valor en la sintaxis del lenguaje, pero cuando no se necesita ningún valor o no se desea.</span><span class="sxs-lookup"><span data-stu-id="3eba4-111">The value of the `unit` type is often used in F# programming to hold the place where a value is required by the language syntax, but when no value is needed or desired.</span></span> <span data-ttu-id="3eba4-112">Un ejemplo podría ser el valor devuelto de una función `printf`.</span><span class="sxs-lookup"><span data-stu-id="3eba4-112">An example might be the return value of a `printf` function.</span></span> <span data-ttu-id="3eba4-113">Dado que las acciones importantes de la operación de `printf` se producen en la función, la función no tiene que devolver un valor real.</span><span class="sxs-lookup"><span data-stu-id="3eba4-113">Because the important actions of the `printf` operation occur in the function, the function does not have to return an actual value.</span></span> <span data-ttu-id="3eba4-114">Por lo tanto, el valor devuelto es de tipo `unit`.</span><span class="sxs-lookup"><span data-stu-id="3eba4-114">Therefore, the return value is of type `unit`.</span></span>

<span data-ttu-id="3eba4-115">Algunas construcciones esperan un valor `unit`.</span><span class="sxs-lookup"><span data-stu-id="3eba4-115">Some constructs expect a `unit` value.</span></span> <span data-ttu-id="3eba4-116">Por ejemplo, se espera que un enlace de `do` o cualquier código en el nivel superior de un módulo se evalúe como un valor de `unit`.</span><span class="sxs-lookup"><span data-stu-id="3eba4-116">For example, a `do` binding or any code at the top level of a module is expected to evaluate to a `unit` value.</span></span> <span data-ttu-id="3eba4-117">El compilador emite una advertencia cuando una `do` enlace o código en el nivel superior de un módulo produce un resultado distinto del valor de `unit` que no se utiliza, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="3eba4-117">The compiler reports a warning when a `do` binding or code at the top level of a module produces a result other than the `unit` value that is not used, as shown in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet901.fs)]

<span data-ttu-id="3eba4-118">Esta advertencia es una característica de la programación funcional; no aparece en otros lenguajes de programación de .NET.</span><span class="sxs-lookup"><span data-stu-id="3eba4-118">This warning is a characteristic of functional programming; it does not appear in other .NET programming languages.</span></span> <span data-ttu-id="3eba4-119">En un programa puramente funcional, en el que las funciones no tienen ningún efecto secundario, el valor devuelto final es el único resultado de una llamada de función.</span><span class="sxs-lookup"><span data-stu-id="3eba4-119">In a purely functional program, in which functions do not have any side effects, the final return value is the only result of a function call.</span></span> <span data-ttu-id="3eba4-120">Por lo tanto, cuando se omite el resultado, es posible que se produzca un error de programación.</span><span class="sxs-lookup"><span data-stu-id="3eba4-120">Therefore, when the result is ignored, it is a possible programming error.</span></span> <span data-ttu-id="3eba4-121">Aunque F# no es un lenguaje de programación puramente funcional, se recomienda seguir el estilo de programación funcional siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="3eba4-121">Although F# is not a purely functional programming language, it is a good practice to follow functional programming style whenever possible.</span></span>

## <a name="see-also"></a><span data-ttu-id="3eba4-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="3eba4-122">See also</span></span>

- [<span data-ttu-id="3eba4-123">Rectangle</span><span class="sxs-lookup"><span data-stu-id="3eba4-123">Primitive</span></span>](basic-types.md)
- [<span data-ttu-id="3eba4-124">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="3eba4-124">F# Language Reference</span></span>](index.md)
