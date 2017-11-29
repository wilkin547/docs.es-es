---
title: 'Funciones recursivas: palabra clave rec (F#)'
description: "Obtenga información acerca de cómo se utiliza la palabra clave 'rec' de F # con la palabra clave 'let' para definir una función recursiva."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 1a95639f-9bfe-4f1d-a5e2-246d1d37776e
ms.openlocfilehash: b837d2c0f8e2b1d28980620103097ccc8345c098
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="recursive-functions-the-rec-keyword"></a><span data-ttu-id="e85db-104">Funciones recursivas: palabra clave rec</span><span class="sxs-lookup"><span data-stu-id="e85db-104">Recursive Functions: The rec Keyword</span></span>

<span data-ttu-id="e85db-105">El `rec` palabra clave se utiliza junto con el `let` palabra clave para definir una función recursiva.</span><span class="sxs-lookup"><span data-stu-id="e85db-105">The `rec` keyword is used together with the `let` keyword to define a recursive function.</span></span>


## <a name="syntax"></a><span data-ttu-id="e85db-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e85db-106">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="e85db-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e85db-107">Remarks</span></span>
<span data-ttu-id="e85db-108">Funciones recursivas, las funciones que llaman a sí mismos, se identifican explícitamente en el lenguaje F #.</span><span class="sxs-lookup"><span data-stu-id="e85db-108">Recursive functions, functions that call themselves, are identified explicitly in the F# language.</span></span> <span data-ttu-id="e85db-109">Esto hace que el identificador que se está definiendo estén disponibles en el ámbito de la función.</span><span class="sxs-lookup"><span data-stu-id="e85db-109">This makes the identifer that is being defined available in the scope of the function.</span></span>

<span data-ttu-id="e85db-110">El código siguiente muestra una función recursiva que calcula el  *n* número de Fibonacci.</span><span class="sxs-lookup"><span data-stu-id="e85db-110">The following code illustrates a recursive function that computes the *n*th Fibonacci number.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet4001.fs)]

>[!NOTE]
<span data-ttu-id="e85db-111">En la práctica, código similar anterior es desperdicia memoria y tiempo de procesador, ya que implica el cálculo de valores previamente calculados.</span><span class="sxs-lookup"><span data-stu-id="e85db-111">In practice, code like that above is wasteful of memory and processor time because it involves the recomputation of previously computed values.</span></span>


<span data-ttu-id="e85db-112">Los métodos son implícitamente recursivos dentro del tipo; no es necesario agregar el `rec` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="e85db-112">Methods are implicitly recursive within the type; there is no need to add the `rec` keyword.</span></span> <span data-ttu-id="e85db-113">Enlaces let en clases no son implícitamente recursivos.</span><span class="sxs-lookup"><span data-stu-id="e85db-113">Let bindings within classes are not implicitly recursive.</span></span>


## <a name="mutually-recursive-functions"></a><span data-ttu-id="e85db-114">Funciones mutuamente recursivas</span><span class="sxs-lookup"><span data-stu-id="e85db-114">Mutually Recursive Functions</span></span>
<span data-ttu-id="e85db-115">A veces, las funciones son *mutuamente recursivas*, lo que significa que las llamadas forman un círculo, donde una función llama a otro que a su vez llama a la primera, con cualquier número de llamadas en medio.</span><span class="sxs-lookup"><span data-stu-id="e85db-115">Sometimes functions are *mutually recursive*, meaning that calls form a circle, where one function calls another which in turn calls the first, with any number of calls in between.</span></span> <span data-ttu-id="e85db-116">Debe definir estas funciones juntas en el `let` enlace, usando la `and` palabra clave que se va a vincular todos estos elementos.</span><span class="sxs-lookup"><span data-stu-id="e85db-116">You must define such functions together in the one `let` binding, using the `and` keyword to link them together.</span></span>

<span data-ttu-id="e85db-117">En el ejemplo siguiente se muestra dos mutuamente las funciones recursivas.</span><span class="sxs-lookup"><span data-stu-id="e85db-117">The following example shows two mutually recursive functions.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet4002.fs)]

## <a name="see-also"></a><span data-ttu-id="e85db-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="e85db-118">See Also</span></span>
[<span data-ttu-id="e85db-119">Funciones</span><span class="sxs-lookup"><span data-stu-id="e85db-119">Functions</span></span>](index.md)
