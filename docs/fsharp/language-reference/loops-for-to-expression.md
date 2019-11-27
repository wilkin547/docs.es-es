---
title: 'Bucles: expresión for...to'
description: Vea cómo F# ... la expresión to se usa para iterar en un bucle en un intervalo de valores de una variable de bucle.
ms.date: 05/16/2016
ms.openlocfilehash: 882b6e48dd09efcb57f7ef2f419e68a6c43393a5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283900"
---
# <a name="loops-forto-expression"></a><span data-ttu-id="94ba3-103">Bucles: expresión for...to</span><span class="sxs-lookup"><span data-stu-id="94ba3-103">Loops: for...to Expression</span></span>

<span data-ttu-id="94ba3-104">La expresión `for...to` se usa para iterar en un bucle en un intervalo de valores de una variable de bucle.</span><span class="sxs-lookup"><span data-stu-id="94ba3-104">The `for...to` expression is used to iterate in a loop over a range of values of a loop variable.</span></span>

## <a name="syntax"></a><span data-ttu-id="94ba3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="94ba3-105">Syntax</span></span>

```fsharp
for identifier = start [ to | downto ] finish do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="94ba3-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="94ba3-106">Remarks</span></span>

<span data-ttu-id="94ba3-107">El tipo del identificador se deduce del tipo de las expresiones de *Inicio* y *finalización* .</span><span class="sxs-lookup"><span data-stu-id="94ba3-107">The type of the identifier is inferred from the type of the *start* and *finish* expressions.</span></span> <span data-ttu-id="94ba3-108">Los tipos de estas expresiones deben ser enteros de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="94ba3-108">Types for these expressions must be 32-bit integers.</span></span>

<span data-ttu-id="94ba3-109">A pesar de ser técnicamente una expresión, `for...to` es más similar a una instrucción tradicional en un lenguaje de programación imperativo.</span><span class="sxs-lookup"><span data-stu-id="94ba3-109">Although technically an expression, `for...to` is more like a traditional statement in an imperative programming language.</span></span> <span data-ttu-id="94ba3-110">El tipo de valor devuelto para la *expresión Body* debe ser `unit`.</span><span class="sxs-lookup"><span data-stu-id="94ba3-110">The return type for the *body-expression* must be `unit`.</span></span> <span data-ttu-id="94ba3-111">En los ejemplos siguientes se muestran varios usos de la expresión `for...to`.</span><span class="sxs-lookup"><span data-stu-id="94ba3-111">The following examples show various uses of the `for...to` expression.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5101.fs)]

<span data-ttu-id="94ba3-112">La salida del código anterior es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="94ba3-112">The output of the previous code is as follows.</span></span>

```console
1 2 3 4 5 6 7 8 9 10
10 9 8 7 6 5 4 3 2 1
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

## <a name="see-also"></a><span data-ttu-id="94ba3-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="94ba3-113">See also</span></span>

- [<span data-ttu-id="94ba3-114">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="94ba3-114">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="94ba3-115">Bucles: expresión `for...in`</span><span class="sxs-lookup"><span data-stu-id="94ba3-115">Loops: `for...in` Expression</span></span>](loops-for-in-expression.md)
- [<span data-ttu-id="94ba3-116">Bucles: expresión `while...do`</span><span class="sxs-lookup"><span data-stu-id="94ba3-116">Loops: `while...do` Expression</span></span>](loops-while-do-expression.md)
