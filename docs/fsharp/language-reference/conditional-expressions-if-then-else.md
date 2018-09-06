---
title: 'Expresiones condicionales: if... then...else (F#)'
description: 'Obtenga información sobre cómo escribir expresiones condicionales en F # para ejecutar distintas bifurcaciones de código.'
ms.date: 05/16/2016
ms.openlocfilehash: 10e4224bef772f00520cf5a0fff2f2920147c2fc
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2018
ms.locfileid: "43745201"
---
# <a name="conditional-expressions-ifthenelse"></a><span data-ttu-id="f8341-103">Expresiones condicionales: `if...then...else`</span><span class="sxs-lookup"><span data-stu-id="f8341-103">Conditional Expressions: `if...then...else`</span></span>

<span data-ttu-id="f8341-104">El `if...then...else` expresión ejecuta diferentes ramas de código y también se evalúa como un valor distinto según la expresión booleana especificada.</span><span class="sxs-lookup"><span data-stu-id="f8341-104">The `if...then...else` expression runs different branches of code and also evaluates to a different value depending on the Boolean expression given.</span></span>

## <a name="syntax"></a><span data-ttu-id="f8341-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f8341-105">Syntax</span></span>

```fsharp
if boolean-expression then expression1 [ else expression2 ]
```

## <a name="remarks"></a><span data-ttu-id="f8341-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f8341-106">Remarks</span></span>

<span data-ttu-id="f8341-107">En la sintaxis anterior, *expression1* se ejecuta cuando la expresión booleana se evalúa como `true`; en caso contrario, *expression2* se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="f8341-107">In the previous syntax, *expression1* runs when the Boolean expression evaluates to `true`; otherwise, *expression2* runs.</span></span>

<span data-ttu-id="f8341-108">A diferencia de otros lenguajes, la `if...then...else` construcción es una expresión, no una instrucción.</span><span class="sxs-lookup"><span data-stu-id="f8341-108">Unlike in other languages, the `if...then...else` construct is an expression, not a statement.</span></span> <span data-ttu-id="f8341-109">Esto significa que genera un valor, que es el valor de la última expresión en la rama que se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="f8341-109">That means that it produces a value, which is the value of the last expression in the branch that executes.</span></span> <span data-ttu-id="f8341-110">Deben coincidir con los tipos de los valores generados en cada rama.</span><span class="sxs-lookup"><span data-stu-id="f8341-110">The types of the values produced in each branch must match.</span></span> <span data-ttu-id="f8341-111">Si hay explícita no `else` rama, su tipo es `unit`.</span><span class="sxs-lookup"><span data-stu-id="f8341-111">If there is no explicit `else` branch, its type is `unit`.</span></span> <span data-ttu-id="f8341-112">Por lo tanto, si el tipo de la `then` rama es cualquier tipo distinto `unit`, debe haber un `else` rama con el mismo tipo de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="f8341-112">Therefore, if the type of the `then` branch is any type other than `unit`, there must be an `else` branch with the same return type.</span></span> <span data-ttu-id="f8341-113">Cuando se encadenan `if...then...else` juntas, puede usar la palabra clave expresiones `elif` en lugar de `else if`; son equivalentes.</span><span class="sxs-lookup"><span data-stu-id="f8341-113">When chaining `if...then...else` expressions together, you can use the keyword `elif` instead of `else if`; they are equivalent.</span></span>

## <a name="example"></a><span data-ttu-id="f8341-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f8341-114">Example</span></span>

<span data-ttu-id="f8341-115">El ejemplo siguiente muestra cómo usar el `if...then...else` expresión.</span><span class="sxs-lookup"><span data-stu-id="f8341-115">The following example illustrates how to use the `if...then...else` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4501.fs)]

```
10 is less than 20
What is your name? John
How old are you? 9
You are only 9 years old and already learning F#? Wow!
```

## <a name="see-also"></a><span data-ttu-id="f8341-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8341-116">See also</span></span>

- [<span data-ttu-id="f8341-117">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="f8341-117">F# Language Reference</span></span>](index.md)
