---
title: "Bucles: expresión for...to (F#)"
description: "Vea cómo la estructura de F # for.. en expresión se usa para iterar en un bucle en un intervalo de valores de una variable de bucle."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: e14c38d9-b1ef-4b7f-be9a-fb6ef6708e02
ms.openlocfilehash: 1a1d71d30b5e87e4691a78acd5032de9419399db
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="loops-forto-expression"></a><span data-ttu-id="16c57-104">Bucles: expresión for...to</span><span class="sxs-lookup"><span data-stu-id="16c57-104">Loops: for...to Expression</span></span>

<span data-ttu-id="16c57-105">El `for...to` expresión se usa para iterar en un bucle en un intervalo de valores de una variable de bucle.</span><span class="sxs-lookup"><span data-stu-id="16c57-105">The `for...to` expression is used to iterate in a loop over a range of values of a loop variable.</span></span>


## <a name="syntax"></a><span data-ttu-id="16c57-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="16c57-106">Syntax</span></span>

```fsharp
for identifier = start [ to | downto ] finish do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="16c57-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="16c57-107">Remarks</span></span>
<span data-ttu-id="16c57-108">El tipo del identificador se deduce del tipo de la *iniciar* y *finalizar* expresiones.</span><span class="sxs-lookup"><span data-stu-id="16c57-108">The type of the identifier is inferred from the type of the *start* and *finish* expressions.</span></span> <span data-ttu-id="16c57-109">Tipos de estas expresiones deben ser enteros de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="16c57-109">Types for these expressions must be 32-bit integers.</span></span>

<span data-ttu-id="16c57-110">Aunque técnicamente es una expresión, `for...to` más parecido a una instrucción en un lenguaje de programación imperativo tradicional.</span><span class="sxs-lookup"><span data-stu-id="16c57-110">Although technically an expression, `for...to` is more like a traditional statement in an imperative programming language.</span></span> <span data-ttu-id="16c57-111">El tipo de valor devuelto para la *cuerpo-expression* debe ser `unit`.</span><span class="sxs-lookup"><span data-stu-id="16c57-111">The return type for the *body-expression* must be `unit`.</span></span> <span data-ttu-id="16c57-112">Los ejemplos siguientes muestran varios usos de la `for...to` expresión.</span><span class="sxs-lookup"><span data-stu-id="16c57-112">The following examples show various uses of the `for...to` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5101.fs)]

<span data-ttu-id="16c57-113">La salida del código anterior es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="16c57-113">The output of the previous code is as follows.</span></span>

```
1 2 3 4 5 6 7 8 9 10
10 9 8 7 6 5 4 3 2 1
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

## <a name="see-also"></a><span data-ttu-id="16c57-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="16c57-114">See Also</span></span>
[<span data-ttu-id="16c57-115">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="16c57-115">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="16c57-116">Bucles: expresión `for...in`</span><span class="sxs-lookup"><span data-stu-id="16c57-116">Loops: `for...in` Expression</span></span>](loops-for-in-expression.md)

[<span data-ttu-id="16c57-117">Bucles: expresión `while...do`</span><span class="sxs-lookup"><span data-stu-id="16c57-117">Loops: `while...do` Expression</span></span>](loops-while-do-expression.md)
