---
title: 'Funciones recursivas: palabra clave rec'
description: "Obtenga información sobre cómo se usa la palabra clave ' Rec ' de F # con la palabra clave ' Let ' para definir una función recursiva."
ms.date: 05/16/2016
ms.openlocfilehash: c9a3b7dc27f4ed86948a08b7783d7e8e8b60e57f
ms.sourcegitcommit: 32f0d6f4c01ddc6ca78767c3a30e3305f8cd032c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2020
ms.locfileid: "87426981"
---
# <a name="recursive-functions-the-rec-keyword"></a><span data-ttu-id="aefd0-103">Funciones recursivas: palabra clave rec</span><span class="sxs-lookup"><span data-stu-id="aefd0-103">Recursive Functions: The rec Keyword</span></span>

<span data-ttu-id="aefd0-104">La `rec` palabra clave se usa junto con la `let` palabra clave para definir una función recursiva.</span><span class="sxs-lookup"><span data-stu-id="aefd0-104">The `rec` keyword is used together with the `let` keyword to define a recursive function.</span></span>

## <a name="syntax"></a><span data-ttu-id="aefd0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aefd0-105">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="aefd0-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="aefd0-106">Remarks</span></span>

<span data-ttu-id="aefd0-107">Las funciones recursivas, las funciones que se llaman a sí mismas, se identifican explícitamente en el lenguaje F #.</span><span class="sxs-lookup"><span data-stu-id="aefd0-107">Recursive functions, functions that call themselves, are identified explicitly in the F# language.</span></span> <span data-ttu-id="aefd0-108">Esto hace que el identificador que se está definiendo esté disponible en el ámbito de la función.</span><span class="sxs-lookup"><span data-stu-id="aefd0-108">This makes the identifer that is being defined available in the scope of the function.</span></span>

<span data-ttu-id="aefd0-109">En el código siguiente se muestra una función recursiva que *calcula el número*<sup>de Fibonacci</sup> con la definición matemática.</span><span class="sxs-lookup"><span data-stu-id="aefd0-109">The following code illustrates a recursive function that computes the *n*<sup>th</sup> Fibonacci number using the mathematical definition.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet4001.fs)]

> [!NOTE]
> <span data-ttu-id="aefd0-110">En la práctica, el código como el ejemplo anterior no es el ideal porque unecessarily vuelve a calcular los valores que ya se han calculado.</span><span class="sxs-lookup"><span data-stu-id="aefd0-110">In practice, code like the previous sample is not ideal because it unecessarily recomputes values that have already been computed.</span></span> <span data-ttu-id="aefd0-111">Esto se debe a que no es recursivo, lo que se explica más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="aefd0-111">This is because it is not tail recursive, which is explained further in this article.</span></span>

<span data-ttu-id="aefd0-112">Los métodos son implícitamente recursivos dentro del tipo; no es necesario agregar la `rec` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="aefd0-112">Methods are implicitly recursive within the type; there is no need to add the `rec` keyword.</span></span> <span data-ttu-id="aefd0-113">Los enlaces Let dentro de las clases no son implícitamente recursivos.</span><span class="sxs-lookup"><span data-stu-id="aefd0-113">Let bindings within classes are not implicitly recursive.</span></span>

## <a name="tail-recursion"></a><span data-ttu-id="aefd0-114">Recursividad de cola</span><span class="sxs-lookup"><span data-stu-id="aefd0-114">Tail recursion</span></span>

<span data-ttu-id="aefd0-115">En el caso de algunas funciones recursivas, es necesario refactorizar una definición más "pura" a una que sea [recursiva](https://cs.stackexchange.com/questions/6230/what-is-tail-recursion).</span><span class="sxs-lookup"><span data-stu-id="aefd0-115">For some recursive functions, it is necessary to refactor a more "pure" definition to one that is [tail recursive](https://cs.stackexchange.com/questions/6230/what-is-tail-recursion).</span></span> <span data-ttu-id="aefd0-116">Esto evita los recálculos de innecesarios.</span><span class="sxs-lookup"><span data-stu-id="aefd0-116">This prevents unecessary recomputations.</span></span> <span data-ttu-id="aefd0-117">Por ejemplo, el generador de números de Fibonacci anterior se puede volver a escribir de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="aefd0-117">For example, the previous fibonacci number generator can be rewritten like this:</span></span>

```fsharp
let fib n =
    let rec loop acc1 acc2 n =
        match n with
        | 0 -> acc1
        | 1 -> acc2
        | _ ->
            loop acc2 (acc1 + acc2) (n - 1)
    loop 0 1 n
```

<span data-ttu-id="aefd0-118">Se trata de una implementación más complicada.</span><span class="sxs-lookup"><span data-stu-id="aefd0-118">This is a more complicated implementation.</span></span> <span data-ttu-id="aefd0-119">La generación de un número de Fibonacci es un buen ejemplo de un algoritmo "naive" que es matemáticamente puro pero ineficaz en la práctica.</span><span class="sxs-lookup"><span data-stu-id="aefd0-119">Generating a fibonacci number is a great example of a "naive" algorithm that's mathematically pure but inefficient in practice.</span></span> <span data-ttu-id="aefd0-120">Varios aspectos hacen que sea eficaz en F # mientras sigue estando definido de forma recursiva:</span><span class="sxs-lookup"><span data-stu-id="aefd0-120">Several aspects make it efficient in F# while still remaining recursively defined:</span></span>

* <span data-ttu-id="aefd0-121">Una función interna recursiva denominada `loop` , que es un patrón de idiomático F #.</span><span class="sxs-lookup"><span data-stu-id="aefd0-121">A recursive inner function named `loop`, which is an idiomatic F# pattern.</span></span>
* <span data-ttu-id="aefd0-122">Dos parámetros de acumulador, que pasan los valores acumulados a las llamadas recursivas.</span><span class="sxs-lookup"><span data-stu-id="aefd0-122">Two accumulator parameters, which pass accumulate values to recursive calls.</span></span>
* <span data-ttu-id="aefd0-123">Una comprobación del valor de `n` para devolver un acumulado específico.</span><span class="sxs-lookup"><span data-stu-id="aefd0-123">A check on the value of `n` to return a specific accumulate.</span></span>

<span data-ttu-id="aefd0-124">Si este ejemplo se escribió de forma iterativa con un bucle, el código tendría un aspecto similar al de dos valores diferentes acumulados hasta que se cumpliera una condición determinada.</span><span class="sxs-lookup"><span data-stu-id="aefd0-124">If this example were written iteratively with a loop, the code would look similar with two different values accumulating numbers until a particular condition was met.</span></span>

<span data-ttu-id="aefd0-125">La razón por la que se trata de la finalización del error es que la llamada recursiva no tiene que guardar ningún valor en la pila de llamadas.</span><span class="sxs-lookup"><span data-stu-id="aefd0-125">The reason why this is tail-recursive is because the recursive call does not need to save any values on the call stack.</span></span> <span data-ttu-id="aefd0-126">Todos los valores intermedios que se calculan se acumulan a través de entradas de la función interna.</span><span class="sxs-lookup"><span data-stu-id="aefd0-126">All intermediate values being calculated are accumulated via inputs to the inner function.</span></span> <span data-ttu-id="aefd0-127">Esto también permite que el compilador de F # optimice el código para que sea tan rápido como si hubiera escrito algo parecido a un `while` bucle.</span><span class="sxs-lookup"><span data-stu-id="aefd0-127">This also allows the F# compiler to optimize the code to be just as fast as if you had written something like a `while` loop.</span></span>

<span data-ttu-id="aefd0-128">Es habitual escribir código de F # que procese de forma recursiva algo con una función interna y externa, como se muestra en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="aefd0-128">It's common to write F# code that recursively processes something with an inner and outer function, as the previous example shows.</span></span> <span data-ttu-id="aefd0-129">La función interna utiliza la recursividad de cola, mientras que la función externa tiene una interfaz mejor para los llamadores.</span><span class="sxs-lookup"><span data-stu-id="aefd0-129">The inner function uses tail recursion, while the outer function has a better interface for callers.</span></span>

## <a name="mutually-recursive-functions"></a><span data-ttu-id="aefd0-130">Funciones mutuamente recursivas</span><span class="sxs-lookup"><span data-stu-id="aefd0-130">Mutually Recursive Functions</span></span>

<span data-ttu-id="aefd0-131">A veces, las funciones son *mutuamente recursivas*, lo que significa que las llamadas forman un círculo, donde una función llama a otra que, a su vez, llama a la primera, con cualquier número de llamadas entre.</span><span class="sxs-lookup"><span data-stu-id="aefd0-131">Sometimes functions are *mutually recursive*, meaning that calls form a circle, where one function calls another which in turn calls the first, with any number of calls in between.</span></span> <span data-ttu-id="aefd0-132">Debe definir estas funciones juntas en un `let` enlace, utilizando la `and` palabra clave para vincularlas.</span><span class="sxs-lookup"><span data-stu-id="aefd0-132">You must define such functions together in the one `let` binding, using the `and` keyword to link them together.</span></span>

<span data-ttu-id="aefd0-133">En el ejemplo siguiente se muestran dos funciones mutuamente recursivas.</span><span class="sxs-lookup"><span data-stu-id="aefd0-133">The following example shows two mutually recursive functions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet4002.fs)]

## <a name="see-also"></a><span data-ttu-id="aefd0-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="aefd0-134">See also</span></span>

- [<span data-ttu-id="aefd0-135">Funciones</span><span class="sxs-lookup"><span data-stu-id="aefd0-135">Functions</span></span>](index.md)
