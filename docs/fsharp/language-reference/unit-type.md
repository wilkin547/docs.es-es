---
title: Unit (Tipo)
description: Obtenga información sobre F# cómo el tipo ' Unit ' se usa a menudo para contener el lugar en el que la sintaxis del lenguaje requiere un valor cuando no se necesita ningún valor o se desea.
ms.date: 05/16/2016
ms.openlocfilehash: 4e586702324565b8dcd4f6c7e11a0e1754f89c58
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630175"
---
# <a name="unit-type"></a><span data-ttu-id="195cf-103">Unit (Tipo)</span><span class="sxs-lookup"><span data-stu-id="195cf-103">Unit Type</span></span>

<span data-ttu-id="195cf-104">El `unit` tipo es un tipo que indica la ausencia de un valor específico; el `unit` tipo solo tiene un valor, que actúa como marcador de posición cuando no existe ningún otro valor o es necesario.</span><span class="sxs-lookup"><span data-stu-id="195cf-104">The `unit` type is a type that indicates the absence of a specific value; the `unit` type has only a single value, which acts as a placeholder when no other value exists or is needed.</span></span>

## <a name="syntax"></a><span data-ttu-id="195cf-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="195cf-105">Syntax</span></span>

```fsharp
// The value of the unit type.
()
```

## <a name="remarks"></a><span data-ttu-id="195cf-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="195cf-106">Remarks</span></span>

<span data-ttu-id="195cf-107">Cada F# expresión debe evaluarse como un valor.</span><span class="sxs-lookup"><span data-stu-id="195cf-107">Every F# expression must evaluate to a value.</span></span> <span data-ttu-id="195cf-108">En el caso de las expresiones que no generan un valor de interés, se utiliza el `unit` valor de tipo.</span><span class="sxs-lookup"><span data-stu-id="195cf-108">For expressions that do not generate a value that is of interest, the value of type `unit` is used.</span></span> <span data-ttu-id="195cf-109">El `unit` tipo es similar al `void` tipo en lenguajes como C# y C++.</span><span class="sxs-lookup"><span data-stu-id="195cf-109">The `unit` type resembles the `void` type in languages such as C# and C++.</span></span>

<span data-ttu-id="195cf-110">El `unit` tipo tiene un valor único y ese valor se indica mediante el token `()`.</span><span class="sxs-lookup"><span data-stu-id="195cf-110">The `unit` type has a single value, and that value is indicated by the token `()`.</span></span>

<span data-ttu-id="195cf-111">El valor del `unit` tipo se usa a menudo en F# la programación para contener el lugar en el que la sintaxis del lenguaje requiere un valor, pero cuando no se necesita ningún valor o no se desea.</span><span class="sxs-lookup"><span data-stu-id="195cf-111">The value of the `unit` type is often used in F# programming to hold the place where a value is required by the language syntax, but when no value is needed or desired.</span></span> <span data-ttu-id="195cf-112">Un ejemplo podría ser el valor devuelto de `printf` una función.</span><span class="sxs-lookup"><span data-stu-id="195cf-112">An example might be the return value of a `printf` function.</span></span> <span data-ttu-id="195cf-113">Dado que las acciones importantes de `printf` la operación se producen en la función, la función no tiene que devolver un valor real.</span><span class="sxs-lookup"><span data-stu-id="195cf-113">Because the important actions of the `printf` operation occur in the function, the function does not have to return an actual value.</span></span> <span data-ttu-id="195cf-114">Por lo tanto, el valor devuelto `unit`es de tipo.</span><span class="sxs-lookup"><span data-stu-id="195cf-114">Therefore, the return value is of type `unit`.</span></span>

<span data-ttu-id="195cf-115">Algunas construcciones esperan un `unit` valor.</span><span class="sxs-lookup"><span data-stu-id="195cf-115">Some constructs expect a `unit` value.</span></span> <span data-ttu-id="195cf-116">Por ejemplo, se `do` espera que un enlace o cualquier código en el nivel superior de un módulo se evalúe como `unit` un valor.</span><span class="sxs-lookup"><span data-stu-id="195cf-116">For example, a `do` binding or any code at the top level of a module is expected to evaluate to a `unit` value.</span></span> <span data-ttu-id="195cf-117">El compilador emite una advertencia `do` cuando un enlace o código en el nivel superior de un módulo produce un resultado distinto `unit` del valor que no se utiliza, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="195cf-117">The compiler reports a warning when a `do` binding or code at the top level of a module produces a result other than the `unit` value that is not used, as shown in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet901.fs)]

<span data-ttu-id="195cf-118">Esta advertencia es una característica de la programación funcional; no aparece en otros lenguajes de programación de .NET.</span><span class="sxs-lookup"><span data-stu-id="195cf-118">This warning is a characteristic of functional programming; it does not appear in other .NET programming languages.</span></span> <span data-ttu-id="195cf-119">En un programa puramente funcional, en el que las funciones no tienen ningún efecto secundario, el valor devuelto final es el único resultado de una llamada de función.</span><span class="sxs-lookup"><span data-stu-id="195cf-119">In a purely functional program, in which functions do not have any side effects, the final return value is the only result of a function call.</span></span> <span data-ttu-id="195cf-120">Por lo tanto, cuando se omite el resultado, es posible que se produzca un error de programación.</span><span class="sxs-lookup"><span data-stu-id="195cf-120">Therefore, when the result is ignored, it is a possible programming error.</span></span> <span data-ttu-id="195cf-121">Aunque F# no es un lenguaje de programación puramente funcional, se recomienda seguir el estilo de programación funcional siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="195cf-121">Although F# is not a purely functional programming language, it is a good practice to follow functional programming style whenever possible.</span></span>

## <a name="see-also"></a><span data-ttu-id="195cf-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="195cf-122">See also</span></span>

- [<span data-ttu-id="195cf-123">Rectangle</span><span class="sxs-lookup"><span data-stu-id="195cf-123">Primitive</span></span>](primitive-types.md)
- [<span data-ttu-id="195cf-124">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="195cf-124">F# Language Reference</span></span>](index.md)
