---
title: 'Expresiones condicionales: if... después... demás'
description: Obtenga información sobre cómo escribir expresiones condicionales en F# para ejecutar distintas ramas de código.
ms.date: 05/16/2016
ms.openlocfilehash: d9763f37cd9170c42e968282b54a3ce925e92591
ms.sourcegitcommit: a2d0e1f66367367065bc8dc0dde488ab536da73f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2019
ms.locfileid: "71083033"
---
# <a name="conditional-expressions-ifthenelse"></a><span data-ttu-id="5afdb-103">Expresiones condicionales:`if...then...else`</span><span class="sxs-lookup"><span data-stu-id="5afdb-103">Conditional Expressions: `if...then...else`</span></span>

<span data-ttu-id="5afdb-104">La `if...then...else` expresión ejecuta distintas bifurcaciones de código y también se evalúa como un valor diferente en función de la expresión booleana dada.</span><span class="sxs-lookup"><span data-stu-id="5afdb-104">The `if...then...else` expression runs different branches of code and also evaluates to a different value depending on the Boolean expression given.</span></span>

## <a name="syntax"></a><span data-ttu-id="5afdb-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5afdb-105">Syntax</span></span>

```fsharp
if boolean-expression then expression1 [ else expression2 ]
```

## <a name="remarks"></a><span data-ttu-id="5afdb-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5afdb-106">Remarks</span></span>

<span data-ttu-id="5afdb-107">En la sintaxis anterior, *expression1* se ejecuta cuando la expresión booleana se evalúa `true`como; de lo contrario, *expression2* se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="5afdb-107">In the previous syntax, *expression1* runs when the Boolean expression evaluates to `true`; otherwise, *expression2* runs.</span></span>

<span data-ttu-id="5afdb-108">A diferencia de otros lenguajes, `if...then...else` la construcción es una expresión, no una instrucción.</span><span class="sxs-lookup"><span data-stu-id="5afdb-108">Unlike in other languages, the `if...then...else` construct is an expression, not a statement.</span></span> <span data-ttu-id="5afdb-109">Esto significa que genera un valor, que es el valor de la última expresión de la bifurcación que se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="5afdb-109">That means that it produces a value, which is the value of the last expression in the branch that executes.</span></span> <span data-ttu-id="5afdb-110">Los tipos de los valores generados en cada bifurcación deben coincidir.</span><span class="sxs-lookup"><span data-stu-id="5afdb-110">The types of the values produced in each branch must match.</span></span> <span data-ttu-id="5afdb-111">Si no hay ninguna rama `else` explícita, su tipo es `unit`.</span><span class="sxs-lookup"><span data-stu-id="5afdb-111">If there is no explicit `else` branch, its type is `unit`.</span></span> <span data-ttu-id="5afdb-112">Por lo tanto, si el tipo `then` de la bifurcación es cualquier `unit`tipo que no sea, `else` debe haber una rama con el mismo tipo de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="5afdb-112">Therefore, if the type of the `then` branch is any type other than `unit`, there must be an `else` branch with the same return type.</span></span> <span data-ttu-id="5afdb-113">Al encadenar `if...then...else` expresiones juntas, puede usar la palabra `elif` clave en lugar `else if`de; son equivalentes.</span><span class="sxs-lookup"><span data-stu-id="5afdb-113">When chaining `if...then...else` expressions together, you can use the keyword `elif` instead of `else if`; they are equivalent.</span></span>

## <a name="example"></a><span data-ttu-id="5afdb-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5afdb-114">Example</span></span>

<span data-ttu-id="5afdb-115">En el ejemplo siguiente se muestra cómo usar la `if...then...else` expresión.</span><span class="sxs-lookup"><span data-stu-id="5afdb-115">The following example illustrates how to use the `if...then...else` expression.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4501.fs)]

```console
10 is less than 20
What is your name? John
How old are you? 9
You are only 9 years old and already learning F#? Wow!
```

## <a name="see-also"></a><span data-ttu-id="5afdb-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="5afdb-116">See also</span></span>

- [<span data-ttu-id="5afdb-117">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="5afdb-117">F# Language Reference</span></span>](index.md)
