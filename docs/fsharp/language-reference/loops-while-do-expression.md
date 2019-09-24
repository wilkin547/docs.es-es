---
title: 'Bucles: expresión while...do'
description: Vea cómo... la expresión do se usa para realizar la ejecución iterativa (bucle) mientras se cumple una condición de prueba especificada.
ms.date: 05/16/2016
ms.openlocfilehash: 73526279358db101f8d07721a200920f1e87f119
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216638"
---
# <a name="loops-whiledo-expression"></a><span data-ttu-id="313f0-103">Bucles: expresión while...do</span><span class="sxs-lookup"><span data-stu-id="313f0-103">Loops: while...do Expression</span></span>

<span data-ttu-id="313f0-104">La `while...do` expresión se usa para realizar la ejecución iterativa (en bucle) mientras se cumple una condición de prueba especificada.</span><span class="sxs-lookup"><span data-stu-id="313f0-104">The `while...do` expression is used to perform iterative execution (looping) while a specified test condition is true.</span></span>

## <a name="syntax"></a><span data-ttu-id="313f0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="313f0-105">Syntax</span></span>

```fsharp
while test-expression do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="313f0-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="313f0-106">Remarks</span></span>

<span data-ttu-id="313f0-107">Se evalúa *Test-Expression* ; Si es `true`así, se ejecuta la *expresión Body* y se vuelve a evaluar la expresión de prueba.</span><span class="sxs-lookup"><span data-stu-id="313f0-107">The *test-expression* is evaluated; if it is `true`, the *body-expression* is executed and the test expression is evaluated again.</span></span> <span data-ttu-id="313f0-108">El *cuerpo-expresión* debe tener el `unit`tipo.</span><span class="sxs-lookup"><span data-stu-id="313f0-108">The *body-expression* must have type `unit`.</span></span> <span data-ttu-id="313f0-109">Si la expresión de prueba `false`es, finaliza la iteración.</span><span class="sxs-lookup"><span data-stu-id="313f0-109">If the test expression is `false`, the iteration ends.</span></span>

<span data-ttu-id="313f0-110">En el ejemplo siguiente se muestra el uso de `while...do` la expresión.</span><span class="sxs-lookup"><span data-stu-id="313f0-110">The following example illustrates the use of the `while...do` expression.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5301.fs)]

<span data-ttu-id="313f0-111">La salida del código anterior es un flujo de números aleatorios entre 1 y 20, el último de los cuales es 10.</span><span class="sxs-lookup"><span data-stu-id="313f0-111">The output of the previous code is a stream of random numbers between 1 and 20, the last of which is 10.</span></span>

```console
13 19 8 18 16 2 10
Found a 10!
```

> [!NOTE]
> <span data-ttu-id="313f0-112">Puede usar `while...do` en expresiones de secuencia y otras expresiones de cálculo, en cuyo caso se utiliza una versión personalizada `while...do` de la expresión.</span><span class="sxs-lookup"><span data-stu-id="313f0-112">You can use `while...do` in sequence expressions and other computation expressions, in which case a customized version of the `while...do` expression is used.</span></span> <span data-ttu-id="313f0-113">Para obtener más información, vea [secuencias](sequences.md), [flujos de trabajo asincrónicos](asynchronous-workflows.md)y [expresiones de cálculo](computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="313f0-113">For more information, see [Sequences](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Computation Expressions](computation-expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="313f0-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="313f0-114">See also</span></span>

- [<span data-ttu-id="313f0-115">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="313f0-115">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="313f0-116">Bucles `for...in`Expresiones</span><span class="sxs-lookup"><span data-stu-id="313f0-116">Loops: `for...in` Expression</span></span>](loops-for-in-expression.md)
- [<span data-ttu-id="313f0-117">Bucles `for...to`Expresiones</span><span class="sxs-lookup"><span data-stu-id="313f0-117">Loops: `for...to` Expression</span></span>](loops-for-to-expression.md)
