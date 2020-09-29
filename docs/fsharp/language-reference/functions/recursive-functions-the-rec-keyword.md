---
title: 'Funciones recursivas: palabra clave rec'
description: "Obtenga información sobre cómo se usa la palabra clave ' Rec ' de F # con la palabra clave ' Let ' para definir una función recursiva."
ms.date: 08/12/2020
ms.openlocfilehash: 1ab00ff9400129e531fd7320861b3d9625cad08c
ms.sourcegitcommit: b4a46f6d7ebf44c0035627d00924164bcae2db30
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2020
ms.locfileid: "91438074"
---
# <a name="recursive-functions-the-rec-keyword"></a><span data-ttu-id="ebd4b-103">Funciones recursivas: palabra clave rec</span><span class="sxs-lookup"><span data-stu-id="ebd4b-103">Recursive Functions: The rec Keyword</span></span>

<span data-ttu-id="ebd4b-104">La `rec` palabra clave se usa junto con la `let` palabra clave para definir una función recursiva.</span><span class="sxs-lookup"><span data-stu-id="ebd4b-104">The `rec` keyword is used together with the `let` keyword to define a recursive function.</span></span>

## <a name="syntax"></a><span data-ttu-id="ebd4b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ebd4b-105">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="ebd4b-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ebd4b-106">Remarks</span></span>

<span data-ttu-id="ebd4b-107">Las funciones recursivas, que se llaman a sí mismas, se identifican explícitamente en el lenguaje F # con la `rec` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="ebd4b-107">Recursive functions - functions that call themselves - are identified explicitly in the F# language with the `rec` keyword.</span></span> <span data-ttu-id="ebd4b-108">La `rec` palabra clave hace que el nombre del `let` enlace esté disponible en su cuerpo.</span><span class="sxs-lookup"><span data-stu-id="ebd4b-108">The `rec` keyword makes the name of the `let` binding available in its body.</span></span>

<span data-ttu-id="ebd4b-109">En el ejemplo siguiente se muestra una función recursiva que *calcula el número*<sup>de Fibonacci</sup> con la definición matemática.</span><span class="sxs-lookup"><span data-stu-id="ebd4b-109">The following example shows a recursive function that computes the *n*<sup>th</sup> Fibonacci number using the mathematical definition.</span></span>

```fsharp
let rec fib n =
    match n with
    | 0 | 1 -> 1
    | n -> fib (n-1) + fib (n-2)
```

> [!NOTE]
> <span data-ttu-id="ebd4b-110">En la práctica, el código como el ejemplo anterior no es el ideal porque unecessarily vuelve a calcular los valores que ya se han calculado.</span><span class="sxs-lookup"><span data-stu-id="ebd4b-110">In practice, code like the previous sample is not ideal because it unecessarily recomputes values that have already been computed.</span></span> <span data-ttu-id="ebd4b-111">Esto se debe a que no es recursivo, lo que se explica más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="ebd4b-111">This is because it is not tail recursive, which is explained further in this article.</span></span>

<span data-ttu-id="ebd4b-112">Los métodos son implícitamente recursivos dentro del tipo en el que se definen, lo que significa que no es necesario agregar la `rec` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="ebd4b-112">Methods are implicitly recursive within the type they are defined in, meaning there is no need to add the `rec` keyword.</span></span> <span data-ttu-id="ebd4b-113">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ebd4b-113">For example:</span></span>

```fsharp
type MyClass() =
    member this.Fib(n) =
        match n with
        | 0 | 1 -> 1
        | n -> this.Fib(n-1) + this.Fib(n-2)
```

<span data-ttu-id="ebd4b-114">Sin embargo, los enlaces Let dentro de las clases no son implícitamente recursivos.</span><span class="sxs-lookup"><span data-stu-id="ebd4b-114">Let bindings within classes are not implicitly recursive, though.</span></span> <span data-ttu-id="ebd4b-115">Todas `let` las funciones enlazadas a requieren la `rec` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="ebd4b-115">All `let`-bound functions require the `rec` keyword.</span></span>

## <a name="tail-recursion"></a><span data-ttu-id="ebd4b-116">Recursividad de cola</span><span class="sxs-lookup"><span data-stu-id="ebd4b-116">Tail recursion</span></span>

<span data-ttu-id="ebd4b-117">En el caso de algunas funciones recursivas, es necesario refactorizar una definición más "pura" a una que sea [recursiva](https://cs.stackexchange.com/questions/6230/what-is-tail-recursion).</span><span class="sxs-lookup"><span data-stu-id="ebd4b-117">For some recursive functions, it is necessary to refactor a more "pure" definition to one that is [tail recursive](https://cs.stackexchange.com/questions/6230/what-is-tail-recursion).</span></span> <span data-ttu-id="ebd4b-118">Esto evita los cálculos innecesarios.</span><span class="sxs-lookup"><span data-stu-id="ebd4b-118">This prevents unnecessary recomputations.</span></span> <span data-ttu-id="ebd4b-119">Por ejemplo, el generador de números de Fibonacci anterior se puede volver a escribir de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="ebd4b-119">For example, the previous fibonacci number generator can be rewritten like this:</span></span>

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

<span data-ttu-id="ebd4b-120">Se trata de una implementación más complicada.</span><span class="sxs-lookup"><span data-stu-id="ebd4b-120">This is a more complicated implementation.</span></span> <span data-ttu-id="ebd4b-121">La generación de un número de Fibonacci es un buen ejemplo de un algoritmo "naive" que es matemáticamente puro pero ineficaz en la práctica.</span><span class="sxs-lookup"><span data-stu-id="ebd4b-121">Generating a fibonacci number is a great example of a "naive" algorithm that's mathematically pure but inefficient in practice.</span></span> <span data-ttu-id="ebd4b-122">Varios aspectos hacen que sea eficaz en F # mientras sigue estando definido de forma recursiva:</span><span class="sxs-lookup"><span data-stu-id="ebd4b-122">Several aspects make it efficient in F# while still remaining recursively defined:</span></span>

* <span data-ttu-id="ebd4b-123">Una función interna recursiva denominada `loop` , que es un patrón de idiomático F #.</span><span class="sxs-lookup"><span data-stu-id="ebd4b-123">A recursive inner function named `loop`, which is an idiomatic F# pattern.</span></span>
* <span data-ttu-id="ebd4b-124">Dos parámetros de acumulador, que pasan los valores acumulados a las llamadas recursivas.</span><span class="sxs-lookup"><span data-stu-id="ebd4b-124">Two accumulator parameters, which pass accumulate values to recursive calls.</span></span>
* <span data-ttu-id="ebd4b-125">Una comprobación del valor de `n` para devolver un acumulado específico.</span><span class="sxs-lookup"><span data-stu-id="ebd4b-125">A check on the value of `n` to return a specific accumulate.</span></span>

<span data-ttu-id="ebd4b-126">Si este ejemplo se escribió de forma iterativa con un bucle, el código tendría un aspecto similar al de dos valores diferentes acumulados hasta que se cumpliera una condición determinada.</span><span class="sxs-lookup"><span data-stu-id="ebd4b-126">If this example were written iteratively with a loop, the code would look similar with two different values accumulating numbers until a particular condition was met.</span></span>

<span data-ttu-id="ebd4b-127">La razón por la que se trata de la finalización del error es que la llamada recursiva no tiene que guardar ningún valor en la pila de llamadas.</span><span class="sxs-lookup"><span data-stu-id="ebd4b-127">The reason why this is tail-recursive is because the recursive call does not need to save any values on the call stack.</span></span> <span data-ttu-id="ebd4b-128">Todos los valores intermedios que se calculan se acumulan a través de entradas de la función interna.</span><span class="sxs-lookup"><span data-stu-id="ebd4b-128">All intermediate values being calculated are accumulated via inputs to the inner function.</span></span> <span data-ttu-id="ebd4b-129">Esto también permite que el compilador de F # optimice el código para que sea tan rápido como si hubiera escrito algo parecido a un `while` bucle.</span><span class="sxs-lookup"><span data-stu-id="ebd4b-129">This also allows the F# compiler to optimize the code to be just as fast as if you had written something like a `while` loop.</span></span>

<span data-ttu-id="ebd4b-130">Es habitual escribir código de F # que procese de forma recursiva algo con una función interna y externa, como se muestra en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="ebd4b-130">It's common to write F# code that recursively processes something with an inner and outer function, as the previous example shows.</span></span> <span data-ttu-id="ebd4b-131">La función interna utiliza la recursividad de cola, mientras que la función externa tiene una interfaz mejor para los llamadores.</span><span class="sxs-lookup"><span data-stu-id="ebd4b-131">The inner function uses tail recursion, while the outer function has a better interface for callers.</span></span>

## <a name="mutually-recursive-functions"></a><span data-ttu-id="ebd4b-132">Funciones mutuamente recursivas</span><span class="sxs-lookup"><span data-stu-id="ebd4b-132">Mutually Recursive Functions</span></span>

<span data-ttu-id="ebd4b-133">A veces, las funciones son *mutuamente recursivas*, lo que significa que las llamadas forman un círculo, donde una función llama a otra que, a su vez, llama a la primera, con cualquier número de llamadas entre.</span><span class="sxs-lookup"><span data-stu-id="ebd4b-133">Sometimes functions are *mutually recursive*, meaning that calls form a circle, where one function calls another which in turn calls the first, with any number of calls in between.</span></span> <span data-ttu-id="ebd4b-134">Debe definir estas funciones juntas en un `let` enlace, utilizando la `and` palabra clave para vincularlas.</span><span class="sxs-lookup"><span data-stu-id="ebd4b-134">You must define such functions together in the one `let` binding, using the `and` keyword to link them together.</span></span>

<span data-ttu-id="ebd4b-135">En el ejemplo siguiente se muestran dos funciones mutuamente recursivas.</span><span class="sxs-lookup"><span data-stu-id="ebd4b-135">The following example shows two mutually recursive functions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet4002.fs)]

## <a name="recursive-values"></a><span data-ttu-id="ebd4b-136">Valores recursivos</span><span class="sxs-lookup"><span data-stu-id="ebd4b-136">Recursive values</span></span>

<span data-ttu-id="ebd4b-137">También puede definir un `let` valor enlazado a que sea recursivo.</span><span class="sxs-lookup"><span data-stu-id="ebd4b-137">You can also define a `let`-bound value to be recursive.</span></span> <span data-ttu-id="ebd4b-138">Esto se hace a veces para el registro.</span><span class="sxs-lookup"><span data-stu-id="ebd4b-138">This is sometimes done for logging.</span></span> <span data-ttu-id="ebd4b-139">Con F # 5 y la `nameof` función, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ebd4b-139">With F# 5 and the `nameof` function, you can do this:</span></span>

```fsharp
let rec nameDoubles = nameof nameDoubles + nameof nameDoubles
```

## <a name="see-also"></a><span data-ttu-id="ebd4b-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="ebd4b-140">See also</span></span>

- [<span data-ttu-id="ebd4b-141">Funciones</span><span class="sxs-lookup"><span data-stu-id="ebd4b-141">Functions</span></span>](index.md)
