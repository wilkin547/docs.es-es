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
ms.openlocfilehash: 3531a112eb53657d5e9102d5e5f3be988360b76e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="conditional-expressions-ifthenelse"></a><span data-ttu-id="c113f-104">Expresiones condicionales:`if...then...else`</span><span class="sxs-lookup"><span data-stu-id="c113f-104">Conditional Expressions: `if...then...else`</span></span>

<span data-ttu-id="c113f-105">El `if...then...else` expresión ejecuta diferentes bifurcaciones de código y también se evalúa como un valor diferente dependiendo de la expresión booleana especificada.</span><span class="sxs-lookup"><span data-stu-id="c113f-105">The `if...then...else` expression runs different branches of code and also evaluates to a different value depending on the Boolean expression given.</span></span>


## <a name="syntax"></a><span data-ttu-id="c113f-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c113f-106">Syntax</span></span>

```fsharp
if boolean-expression then expression1 [ else expression2 ]
```

## <a name="remarks"></a><span data-ttu-id="c113f-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c113f-107">Remarks</span></span>
<span data-ttu-id="c113f-108">En la sintaxis anterior, *expression1* se ejecuta cuando la expresión booleana se evalúa como `true`; en caso contrario, *expression2* se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="c113f-108">In the previous syntax, *expression1* runs when the Boolean expression evaluates to `true`; otherwise, *expression2* runs.</span></span>

<span data-ttu-id="c113f-109">A diferencia de otros lenguajes, la `if...then...else` construcción es una expresión, no una instrucción.</span><span class="sxs-lookup"><span data-stu-id="c113f-109">Unlike in other languages, the `if...then...else` construct is an expression, not a statement.</span></span> <span data-ttu-id="c113f-110">Esto significa que genera un valor, que es el valor de la última expresión de la bifurcación que se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="c113f-110">That means that it produces a value, which is the value of the last expression in the branch that executes.</span></span> <span data-ttu-id="c113f-111">Los tipos de los valores generados en cada bifurcación deben coincidir.</span><span class="sxs-lookup"><span data-stu-id="c113f-111">The types of the values produced in each branch must match.</span></span> <span data-ttu-id="c113f-112">Si no hay ningún `else` rama, su tipo es `unit`.</span><span class="sxs-lookup"><span data-stu-id="c113f-112">If there is no explicit `else` branch, its type is `unit`.</span></span> <span data-ttu-id="c113f-113">Por lo tanto, si el tipo de la `then` bifurcación es cualquier tipo distinto de `unit`, debe haber un `else` rama con el mismo tipo de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="c113f-113">Therefore, if the type of the `then` branch is any type other than `unit`, there must be an `else` branch with the same return type.</span></span> <span data-ttu-id="c113f-114">Cuando se encadenan `if...then...else` expresiones, puede usar la palabra clave `elif` en lugar de `else if`; son equivalentes.</span><span class="sxs-lookup"><span data-stu-id="c113f-114">When chaining `if...then...else` expressions together, you can use the keyword `elif` instead of `else if`; they are equivalent.</span></span>

## <a name="example"></a><span data-ttu-id="c113f-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c113f-115">Example</span></span>
<span data-ttu-id="c113f-116">En el ejemplo siguiente se muestra cómo utilizar el `if...then...else` expresión.</span><span class="sxs-lookup"><span data-stu-id="c113f-116">The following example illustrates how to use the `if...then...else` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4501.fs)]

```
John
910 is less than 20
You are only 9 years old and already learning F#? Wow!
```

## <a name="see-also"></a><span data-ttu-id="c113f-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="c113f-117">See Also</span></span>
[<span data-ttu-id="c113f-118">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="c113f-118">F# Language Reference</span></span>](index.md)

