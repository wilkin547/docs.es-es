---
title: 'Bucles: expresión for...to (F#)'
description: Vea cómo la estructura de F# for … para la expresión se utiliza para iterar en un bucle a través de un intervalo de valores de una variable de bucle.
ms.date: 05/16/2016
ms.openlocfilehash: 8160fd30c4f3afe8bb6b58f468802ef1c0ef32ee
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2018
ms.locfileid: "43800474"
---
# <a name="loops-forto-expression"></a><span data-ttu-id="9716b-103">Bucles: expresión for...to</span><span class="sxs-lookup"><span data-stu-id="9716b-103">Loops: for...to Expression</span></span>

<span data-ttu-id="9716b-104">El `for...to` expresión se utiliza para iterar en un bucle a través de un intervalo de valores de una variable de bucle.</span><span class="sxs-lookup"><span data-stu-id="9716b-104">The `for...to` expression is used to iterate in a loop over a range of values of a loop variable.</span></span>

## <a name="syntax"></a><span data-ttu-id="9716b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9716b-105">Syntax</span></span>

```fsharp
for identifier = start [ to | downto ] finish do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="9716b-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9716b-106">Remarks</span></span>

<span data-ttu-id="9716b-107">El tipo del identificador se deduce del tipo de la *iniciar* y *finalizar* expresiones.</span><span class="sxs-lookup"><span data-stu-id="9716b-107">The type of the identifier is inferred from the type of the *start* and *finish* expressions.</span></span> <span data-ttu-id="9716b-108">Tipos de estas expresiones deben ser enteros de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="9716b-108">Types for these expressions must be 32-bit integers.</span></span>

<span data-ttu-id="9716b-109">Aunque técnicamente es una expresión, `for...to` es más parecido a una instrucción en un lenguaje de programación imperativo tradicional.</span><span class="sxs-lookup"><span data-stu-id="9716b-109">Although technically an expression, `for...to` is more like a traditional statement in an imperative programming language.</span></span> <span data-ttu-id="9716b-110">El tipo de valor devuelto para la *cuerpo de expresión* debe ser `unit`.</span><span class="sxs-lookup"><span data-stu-id="9716b-110">The return type for the *body-expression* must be `unit`.</span></span> <span data-ttu-id="9716b-111">Los ejemplos siguientes muestran varios usos de la `for...to` expresión.</span><span class="sxs-lookup"><span data-stu-id="9716b-111">The following examples show various uses of the `for...to` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5101.fs)]

<span data-ttu-id="9716b-112">La salida del código anterior es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="9716b-112">The output of the previous code is as follows.</span></span>

```
1 2 3 4 5 6 7 8 9 10
10 9 8 7 6 5 4 3 2 1
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

## <a name="see-also"></a><span data-ttu-id="9716b-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="9716b-113">See also</span></span>

- [<span data-ttu-id="9716b-114">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="9716b-114">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="9716b-115">Bucles: expresión `for...in`</span><span class="sxs-lookup"><span data-stu-id="9716b-115">Loops: `for...in` Expression</span></span>](loops-for-in-expression.md)
- [<span data-ttu-id="9716b-116">Bucles: expresión `while...do`</span><span class="sxs-lookup"><span data-stu-id="9716b-116">Loops: `while...do` Expression</span></span>](loops-while-do-expression.md)
