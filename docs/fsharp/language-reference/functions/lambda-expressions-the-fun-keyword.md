---
title: 'Expresiones lambda: La palabra clave fun'
description: Aprenda a usar el F# palabra clave "diversión" para definir una expresión lambda, que es una función anónima.
ms.date: 05/16/2016
ms.openlocfilehash: c59d32bd4226384213453f1a9d362209e68a6fb5
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645387"
---
# <a name="lambda-expressions-the-fun-keyword-f"></a><span data-ttu-id="72fb1-103">Expresiones lambda: La palabra clave fun (F#)</span><span class="sxs-lookup"><span data-stu-id="72fb1-103">Lambda Expressions: The fun Keyword (F#)</span></span>

<span data-ttu-id="72fb1-104">El `fun` palabra clave se usa para definir una expresión lambda, es decir, una función anónima.</span><span class="sxs-lookup"><span data-stu-id="72fb1-104">The `fun` keyword is used to define a lambda expression, that is, an anonymous function.</span></span>

## <a name="syntax"></a><span data-ttu-id="72fb1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="72fb1-105">Syntax</span></span>

```fsharp
fun parameter-list -> expression
```

## <a name="remarks"></a><span data-ttu-id="72fb1-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="72fb1-106">Remarks</span></span>

<span data-ttu-id="72fb1-107">El *lista de parámetros* normalmente consta de los nombres y, opcionalmente, tipos de parámetros.</span><span class="sxs-lookup"><span data-stu-id="72fb1-107">The *parameter-list* typically consists of names and, optionally, types of parameters.</span></span> <span data-ttu-id="72fb1-108">Por lo general, el *lista de parámetros* puede estar formada por cualquier F# patrones.</span><span class="sxs-lookup"><span data-stu-id="72fb1-108">More generally, the *parameter-list* can be composed of any F# patterns.</span></span> <span data-ttu-id="72fb1-109">Para obtener una lista completa de patrones posibles, consulte [coincidencia de patrones](../pattern-matching.md).</span><span class="sxs-lookup"><span data-stu-id="72fb1-109">For a full list of possible patterns, see [Pattern Matching](../pattern-matching.md).</span></span> <span data-ttu-id="72fb1-110">Listas de parámetros válidos incluyen los ejemplos siguientes.</span><span class="sxs-lookup"><span data-stu-id="72fb1-110">Lists of valid parameters include the following examples.</span></span>

```fsharp
// Lambda expressions with parameter lists.
fun a b c -> ...
fun (a: int) b c -> ...
fun (a : int) (b : string) (c:float) -> ...

// A lambda expression with a tuple pattern.
fun (a, b) -> …

// A lambda expression with a list pattern.
fun head :: tail -> …
```

<span data-ttu-id="72fb1-111">El *expresión* es el cuerpo de la función, la última expresión que genera un valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="72fb1-111">The *expression* is the body of the function, the last expression of which generates a return value.</span></span> <span data-ttu-id="72fb1-112">Ejemplos de expresiones lambda válidas incluyen lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="72fb1-112">Examples of valid lambda expressions include the following:</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet301.fs)]

## <a name="using-lambda-expressions"></a><span data-ttu-id="72fb1-113">Uso de expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="72fb1-113">Using Lambda Expressions</span></span>

<span data-ttu-id="72fb1-114">Las expresiones lambda son especialmente útiles cuando desea realizar operaciones en una lista o en otra colección y desea evitar el trabajo adicional de definir una función.</span><span class="sxs-lookup"><span data-stu-id="72fb1-114">Lambda expressions are especially useful when you want to perform operations on a list or other collection and want to avoid the extra work of defining a function.</span></span> <span data-ttu-id="72fb1-115">Muchos F# las funciones de biblioteca toman los valores de función como argumentos, y puede ser especialmente útil usar una expresión lambda en esos casos.</span><span class="sxs-lookup"><span data-stu-id="72fb1-115">Many F# library functions take function values as arguments, and it can be especially convenient to use a lambda expression in those cases.</span></span> <span data-ttu-id="72fb1-116">El código siguiente aplica una expresión lambda a elementos de una lista.</span><span class="sxs-lookup"><span data-stu-id="72fb1-116">The following code applies a lambda expression to elements of a list.</span></span> <span data-ttu-id="72fb1-117">En este caso, la función anónima suma 1 a cada elemento de una lista.</span><span class="sxs-lookup"><span data-stu-id="72fb1-117">In this case, the anonymous function adds 1 to every element of a list.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet302.fs)]

## <a name="see-also"></a><span data-ttu-id="72fb1-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="72fb1-118">See also</span></span>

- [<span data-ttu-id="72fb1-119">Funciones</span><span class="sxs-lookup"><span data-stu-id="72fb1-119">Functions</span></span>](index.md)
