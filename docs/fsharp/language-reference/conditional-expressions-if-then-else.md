---
title: 'Expresiones condicionales: if... then...else (F#)'
description: "Obtenga información acerca de cómo escribir expresiones condicionales en F # para ejecutar distintas bifurcaciones de código."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 16e1871c-4d4d-4691-9ab2-bd2c6f65589a
ms.openlocfilehash: 5823e46cd13053fcd31f94f2d79d1f7470ca5118
ms.sourcegitcommit: d3cfda0943364aaf6ccd574f55f584576c8a4fee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2018
---
# <a name="conditional-expressions-ifthenelse"></a><span data-ttu-id="6103d-104">Expresiones condicionales: `if...then...else`</span><span class="sxs-lookup"><span data-stu-id="6103d-104">Conditional Expressions: `if...then...else`</span></span>

<span data-ttu-id="6103d-105">El `if...then...else` expresión ejecuta diferentes bifurcaciones de código y también se evalúa como un valor diferente dependiendo de la expresión booleana especificada.</span><span class="sxs-lookup"><span data-stu-id="6103d-105">The `if...then...else` expression runs different branches of code and also evaluates to a different value depending on the Boolean expression given.</span></span>


## <a name="syntax"></a><span data-ttu-id="6103d-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6103d-106">Syntax</span></span>

```fsharp
if boolean-expression then expression1 [ else expression2 ]
```

## <a name="remarks"></a><span data-ttu-id="6103d-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6103d-107">Remarks</span></span>
<span data-ttu-id="6103d-108">En la sintaxis anterior, *expression1* se ejecuta cuando la expresión booleana se evalúa como `true`; en caso contrario, *expression2* se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="6103d-108">In the previous syntax, *expression1* runs when the Boolean expression evaluates to `true`; otherwise, *expression2* runs.</span></span>

<span data-ttu-id="6103d-109">A diferencia de otros lenguajes, la `if...then...else` construcción es una expresión, no una instrucción.</span><span class="sxs-lookup"><span data-stu-id="6103d-109">Unlike in other languages, the `if...then...else` construct is an expression, not a statement.</span></span> <span data-ttu-id="6103d-110">Esto significa que genera un valor, que es el valor de la última expresión de la bifurcación que se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="6103d-110">That means that it produces a value, which is the value of the last expression in the branch that executes.</span></span> <span data-ttu-id="6103d-111">Los tipos de los valores generados en cada bifurcación deben coincidir.</span><span class="sxs-lookup"><span data-stu-id="6103d-111">The types of the values produced in each branch must match.</span></span> <span data-ttu-id="6103d-112">Si no hay ningún `else` rama, su tipo es `unit`.</span><span class="sxs-lookup"><span data-stu-id="6103d-112">If there is no explicit `else` branch, its type is `unit`.</span></span> <span data-ttu-id="6103d-113">Por lo tanto, si el tipo de la `then` bifurcación es cualquier tipo distinto de `unit`, debe haber un `else` rama con el mismo tipo de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="6103d-113">Therefore, if the type of the `then` branch is any type other than `unit`, there must be an `else` branch with the same return type.</span></span> <span data-ttu-id="6103d-114">Cuando se encadenan `if...then...else` expresiones, puede usar la palabra clave `elif` en lugar de `else if`; son equivalentes.</span><span class="sxs-lookup"><span data-stu-id="6103d-114">When chaining `if...then...else` expressions together, you can use the keyword `elif` instead of `else if`; they are equivalent.</span></span>

## <a name="example"></a><span data-ttu-id="6103d-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6103d-115">Example</span></span>
<span data-ttu-id="6103d-116">En el ejemplo siguiente se muestra cómo utilizar el `if...then...else` expresión.</span><span class="sxs-lookup"><span data-stu-id="6103d-116">The following example illustrates how to use the `if...then...else` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4501.fs)]

```
10 is less than 20
What is your name? John
How old are you? 9
You are only 9 years old and already learning F#? Wow!
```

## <a name="see-also"></a><span data-ttu-id="6103d-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="6103d-117">See Also</span></span>
[<span data-ttu-id="6103d-118">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="6103d-118">F# Language Reference</span></span>](index.md)

