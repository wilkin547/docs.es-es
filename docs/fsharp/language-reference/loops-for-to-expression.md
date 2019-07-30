---
title: 'Bucles: expresión for...to'
description: Vea cómo F# ... la expresión to se usa para iterar en un bucle en un intervalo de valores de una variable de bucle.
ms.date: 05/16/2016
ms.openlocfilehash: 910c04aa4ea6b2c637dcad147347c1c317b5e0c0
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68626627"
---
# <a name="loops-forto-expression"></a><span data-ttu-id="0fdb9-103">Bucles: expresión for...to</span><span class="sxs-lookup"><span data-stu-id="0fdb9-103">Loops: for...to Expression</span></span>

<span data-ttu-id="0fdb9-104">La `for...to` expresión se usa para iterar en un bucle en un intervalo de valores de una variable de bucle.</span><span class="sxs-lookup"><span data-stu-id="0fdb9-104">The `for...to` expression is used to iterate in a loop over a range of values of a loop variable.</span></span>

## <a name="syntax"></a><span data-ttu-id="0fdb9-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0fdb9-105">Syntax</span></span>

```fsharp
for identifier = start [ to | downto ] finish do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="0fdb9-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0fdb9-106">Remarks</span></span>

<span data-ttu-id="0fdb9-107">El tipo del identificador se deduce del tipo de las expresiones de *Inicio* y *finalización* .</span><span class="sxs-lookup"><span data-stu-id="0fdb9-107">The type of the identifier is inferred from the type of the *start* and *finish* expressions.</span></span> <span data-ttu-id="0fdb9-108">Los tipos de estas expresiones deben ser enteros de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="0fdb9-108">Types for these expressions must be 32-bit integers.</span></span>

<span data-ttu-id="0fdb9-109">A pesar de ser técnicamente `for...to` una expresión, es más similar a una instrucción tradicional en un lenguaje de programación imperativo.</span><span class="sxs-lookup"><span data-stu-id="0fdb9-109">Although technically an expression, `for...to` is more like a traditional statement in an imperative programming language.</span></span> <span data-ttu-id="0fdb9-110">El tipo de valor devuelto para la *expresión de cuerpo* debe ser `unit`.</span><span class="sxs-lookup"><span data-stu-id="0fdb9-110">The return type for the *body-expression* must be `unit`.</span></span> <span data-ttu-id="0fdb9-111">En los ejemplos siguientes se muestran varios usos `for...to` de la expresión.</span><span class="sxs-lookup"><span data-stu-id="0fdb9-111">The following examples show various uses of the `for...to` expression.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5101.fs)]

<span data-ttu-id="0fdb9-112">La salida del código anterior es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="0fdb9-112">The output of the previous code is as follows.</span></span>

```
1 2 3 4 5 6 7 8 9 10
10 9 8 7 6 5 4 3 2 1
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

## <a name="see-also"></a><span data-ttu-id="0fdb9-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="0fdb9-113">See also</span></span>

- [<span data-ttu-id="0fdb9-114">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="0fdb9-114">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="0fdb9-115">Bucles `for...in`Expresiones</span><span class="sxs-lookup"><span data-stu-id="0fdb9-115">Loops: `for...in` Expression</span></span>](loops-for-in-expression.md)
- [<span data-ttu-id="0fdb9-116">Bucles `while...do`Expresiones</span><span class="sxs-lookup"><span data-stu-id="0fdb9-116">Loops: `while...do` Expression</span></span>](loops-while-do-expression.md)
