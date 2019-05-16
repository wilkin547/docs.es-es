---
title: 'Bucles: expresión while...do'
description: Vea cómo el while... hacer expresión se utiliza para realizar la ejecución iterativa (bucle) mientras una condición de prueba especificada es true.
ms.date: 05/16/2016
ms.openlocfilehash: 5823ace27348ff4d4397a726bf2254f8fa0ee09b
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641832"
---
# <a name="loops-whiledo-expression"></a><span data-ttu-id="1b3d4-103">Bucles: expresión while...do</span><span class="sxs-lookup"><span data-stu-id="1b3d4-103">Loops: while...do Expression</span></span>

<span data-ttu-id="1b3d4-104">El `while...do` expresión se utiliza para realizar la ejecución iterativa (bucle) mientras una condición de prueba especificada es true.</span><span class="sxs-lookup"><span data-stu-id="1b3d4-104">The `while...do` expression is used to perform iterative execution (looping) while a specified test condition is true.</span></span>

## <a name="syntax"></a><span data-ttu-id="1b3d4-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1b3d4-105">Syntax</span></span>

```fsharp
while test-expression do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="1b3d4-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1b3d4-106">Remarks</span></span>

<span data-ttu-id="1b3d4-107">El *expresión de prueba* se evalúa; si es `true`, *cuerpo de expresión* se ejecuta y se vuelve a evaluar la expresión de prueba.</span><span class="sxs-lookup"><span data-stu-id="1b3d4-107">The *test-expression* is evaluated; if it is `true`, the *body-expression* is executed and the test expression is evaluated again.</span></span> <span data-ttu-id="1b3d4-108">El *cuerpo de expresión* debe tener tipo `unit`.</span><span class="sxs-lookup"><span data-stu-id="1b3d4-108">The *body-expression* must have type `unit`.</span></span> <span data-ttu-id="1b3d4-109">Si la expresión de prueba es `false`, los extremos de la iteración.</span><span class="sxs-lookup"><span data-stu-id="1b3d4-109">If the test expression is `false`, the iteration ends.</span></span>

<span data-ttu-id="1b3d4-110">El ejemplo siguiente muestra el uso de la `while...do` expresión.</span><span class="sxs-lookup"><span data-stu-id="1b3d4-110">The following example illustrates the use of the `while...do` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5301.fs)]

<span data-ttu-id="1b3d4-111">La salida del código anterior es una secuencia de números aleatorios entre 1 y 20, el último de los cuales es 10.</span><span class="sxs-lookup"><span data-stu-id="1b3d4-111">The output of the previous code is a stream of random numbers between 1 and 20, the last of which is 10.</span></span>

```
13 19 8 18 16 2 10
Found a 10!
```

> [!NOTE]
> <span data-ttu-id="1b3d4-112">Puede usar `while...do` en las expresiones de secuencia y otras expresiones de cálculo, en cuyo caso una versión personalizada de la `while...do` se usa la expresión.</span><span class="sxs-lookup"><span data-stu-id="1b3d4-112">You can use `while...do` in sequence expressions and other computation expressions, in which case a customized version of the `while...do` expression is used.</span></span> <span data-ttu-id="1b3d4-113">Para obtener más información, consulte [secuencias](sequences.md), [flujos de trabajo asincrónicos](asynchronous-workflows.md), y [expresiones de cálculo](computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="1b3d4-113">For more information, see [Sequences](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Computation Expressions](computation-expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1b3d4-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="1b3d4-114">See also</span></span>

- [<span data-ttu-id="1b3d4-115">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="1b3d4-115">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="1b3d4-116">Bucles: `for...in` Expresión</span><span class="sxs-lookup"><span data-stu-id="1b3d4-116">Loops: `for...in` Expression</span></span>](loops-for-in-expression.md)
- [<span data-ttu-id="1b3d4-117">Bucles: `for...to` Expresión</span><span class="sxs-lookup"><span data-stu-id="1b3d4-117">Loops: `for...to` Expression</span></span>](loops-for-to-expression.md)
