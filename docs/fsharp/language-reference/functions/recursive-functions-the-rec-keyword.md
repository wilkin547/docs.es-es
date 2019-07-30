---
title: 'Funciones recursivas: La palabra clave REC'
description: Obtenga información sobre F# cómo se usa la palabra clave ' Rec ' con la palabra clave ' Let ' para definir una función recursiva.
ms.date: 05/16/2016
ms.openlocfilehash: 7edaa7206b2109c7b1a405624b9b2330968f9c52
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630657"
---
# <a name="recursive-functions-the-rec-keyword"></a><span data-ttu-id="17eff-103">Funciones recursivas: La palabra clave REC</span><span class="sxs-lookup"><span data-stu-id="17eff-103">Recursive Functions: The rec Keyword</span></span>

<span data-ttu-id="17eff-104">La `rec` palabra clave se usa junto con `let` la palabra clave para definir una función recursiva.</span><span class="sxs-lookup"><span data-stu-id="17eff-104">The `rec` keyword is used together with the `let` keyword to define a recursive function.</span></span>

## <a name="syntax"></a><span data-ttu-id="17eff-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="17eff-105">Syntax</span></span>

```fsharp
// Recursive function:
let rec function-nameparameter-list =
function-body

// Mutually recursive functions:
let rec function1-nameparameter-list =
function1-body
and function2-nameparameter-list =
function2-body
...
```

## <a name="remarks"></a><span data-ttu-id="17eff-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="17eff-106">Remarks</span></span>

<span data-ttu-id="17eff-107">Las funciones recursivas, las funciones que se llaman a sí mismas, F# se identifican explícitamente en el lenguaje.</span><span class="sxs-lookup"><span data-stu-id="17eff-107">Recursive functions, functions that call themselves, are identified explicitly in the F# language.</span></span> <span data-ttu-id="17eff-108">Esto hace que el identificador que se está definiendo esté disponible en el ámbito de la función.</span><span class="sxs-lookup"><span data-stu-id="17eff-108">This makes the identifer that is being defined available in the scope of the function.</span></span>

<span data-ttu-id="17eff-109">En el código siguiente se muestra una función recursiva que calcula el número<sup>de Fibonacci</sup> n.</span><span class="sxs-lookup"><span data-stu-id="17eff-109">The following code illustrates a recursive function that computes the *n*<sup>th</sup> Fibonacci number.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet4001.fs)]

> [!NOTE]
> <span data-ttu-id="17eff-110">En la práctica, el código como el anterior es una pérdida de memoria y tiempo de procesador porque implica el recálculo de valores calculados previamente.</span><span class="sxs-lookup"><span data-stu-id="17eff-110">In practice, code like that above is wasteful of memory and processor time because it involves the recomputation of previously computed values.</span></span>

<span data-ttu-id="17eff-111">Los métodos son implícitamente recursivos dentro del tipo; no es necesario agregar la `rec` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="17eff-111">Methods are implicitly recursive within the type; there is no need to add the `rec` keyword.</span></span> <span data-ttu-id="17eff-112">Los enlaces Let dentro de las clases no son implícitamente recursivos.</span><span class="sxs-lookup"><span data-stu-id="17eff-112">Let bindings within classes are not implicitly recursive.</span></span>

## <a name="mutually-recursive-functions"></a><span data-ttu-id="17eff-113">Funciones mutuamente recursivas</span><span class="sxs-lookup"><span data-stu-id="17eff-113">Mutually Recursive Functions</span></span>

<span data-ttu-id="17eff-114">A veces,las funciones son mutuamente recursivas, lo que significa que las llamadas forman un círculo, donde una función llama a otra que, a su vez, llama a la primera, con cualquier número de llamadas entre.</span><span class="sxs-lookup"><span data-stu-id="17eff-114">Sometimes functions are *mutually recursive*, meaning that calls form a circle, where one function calls another which in turn calls the first, with any number of calls in between.</span></span> <span data-ttu-id="17eff-115">Debe definir estas funciones juntas en un `let` enlace, utilizando la `and` palabra clave para vincularlas.</span><span class="sxs-lookup"><span data-stu-id="17eff-115">You must define such functions together in the one `let` binding, using the `and` keyword to link them together.</span></span>

<span data-ttu-id="17eff-116">En el ejemplo siguiente se muestran dos funciones mutuamente recursivas.</span><span class="sxs-lookup"><span data-stu-id="17eff-116">The following example shows two mutually recursive functions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet4002.fs)]

## <a name="see-also"></a><span data-ttu-id="17eff-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="17eff-117">See also</span></span>

- [<span data-ttu-id="17eff-118">Funciones</span><span class="sxs-lookup"><span data-stu-id="17eff-118">Functions</span></span>](index.md)
