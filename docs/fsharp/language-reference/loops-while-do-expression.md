---
title: "Bucles: expresión while...do (F#)"
description: "Vea cómo el while... hacer expresión se utiliza para realizar la ejecución reiterativa (bucle) mientras una condición de prueba especificada es true."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 0416ffca-7ed9-4aff-9493-e001fdba8c9b
ms.openlocfilehash: 5f10fda84a5e748856eb7b2c63ad46cc1fba44bb
ms.sourcegitcommit: 8ed4ebc15b5ef89d06a7507dc9d5e306e30accf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/14/2017
---
# <a name="loops-whiledo-expression"></a><span data-ttu-id="77930-104">Bucles: expresión while...do</span><span class="sxs-lookup"><span data-stu-id="77930-104">Loops: while...do Expression</span></span>

<span data-ttu-id="77930-105">El `while...do` expresión se utiliza para realizar la ejecución reiterativa (bucle) mientras una condición de prueba especificada es true.</span><span class="sxs-lookup"><span data-stu-id="77930-105">The `while...do` expression is used to perform iterative execution (looping) while a specified test condition is true.</span></span>


## <a name="syntax"></a><span data-ttu-id="77930-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="77930-106">Syntax</span></span>

```fsharp
while test-expression do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="77930-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="77930-107">Remarks</span></span>
<span data-ttu-id="77930-108">El *expresión de prueba* se evalúa; si es `true`, *cuerpo de la expresión* se ejecuta y se vuelve a evaluar la expresión de prueba.</span><span class="sxs-lookup"><span data-stu-id="77930-108">The *test-expression* is evaluated; if it is `true`, the *body-expression* is executed and the test expression is evaluated again.</span></span> <span data-ttu-id="77930-109">El *cuerpo-expression* debe tener tipo `unit`.</span><span class="sxs-lookup"><span data-stu-id="77930-109">The *body-expression* must have type `unit`.</span></span> <span data-ttu-id="77930-110">Si la expresión de prueba es `false`, los extremos de la iteración.</span><span class="sxs-lookup"><span data-stu-id="77930-110">If the test expression is `false`, the iteration ends.</span></span>

<span data-ttu-id="77930-111">En el ejemplo siguiente se muestra el uso de la `while...do` expresión.</span><span class="sxs-lookup"><span data-stu-id="77930-111">The following example illustrates the use of the `while...do` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5301.fs)]

<span data-ttu-id="77930-112">La salida del código anterior es una secuencia de números aleatorios entre 1 y 20, el último de los cuales es 10.</span><span class="sxs-lookup"><span data-stu-id="77930-112">The output of the previous code is a stream of random numbers between 1 and 20, the last of which is 10.</span></span>

```
13 19 8 18 16 2 10
Found a 10!
```

>[!NOTE] 
<span data-ttu-id="77930-113">Puede usar `while...do` en expresiones de secuencia y otras expresiones de cálculo, en cuyo caso una versión personalizada de la `while...do` se utiliza la expresión.</span><span class="sxs-lookup"><span data-stu-id="77930-113">You can use `while...do` in sequence expressions and other computation expressions, in which case a customized version of the `while...do` expression is used.</span></span> <span data-ttu-id="77930-114">Para obtener más información, consulte [secuencias](sequences.md), [flujos de trabajo asincrónicos](asynchronous-workflows.md), y [expresiones de cálculo](computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="77930-114">For more information, see [Sequences](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Computation Expressions](computation-expressions.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="77930-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="77930-115">See Also</span></span>
[<span data-ttu-id="77930-116">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="77930-116">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="77930-117">Bucles: expresión `for...in`</span><span class="sxs-lookup"><span data-stu-id="77930-117">Loops: `for...in` Expression</span></span>](loops-for-in-expression.md)

[<span data-ttu-id="77930-118">Bucles: expresión `for...to`</span><span class="sxs-lookup"><span data-stu-id="77930-118">Loops: `for...to` Expression</span></span>](loops-for-to-expression.md)
