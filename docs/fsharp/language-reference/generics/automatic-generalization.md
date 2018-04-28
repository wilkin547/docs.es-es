---
title: Generalización automática (F#)
description: 'Obtenga información acerca de cómo F # generaliza automáticamente los argumentos y los tipos de funciones para que funcionen con varios tipos cuando sea posible.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 9b599fd9fe1220b41987bc14a420ed5740aa05f5
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="automatic-generalization"></a><span data-ttu-id="d17e7-103">Generalización automática</span><span class="sxs-lookup"><span data-stu-id="d17e7-103">Automatic Generalization</span></span>

<span data-ttu-id="d17e7-104">F # utiliza la inferencia para evaluar los tipos de funciones y expresiones.</span><span class="sxs-lookup"><span data-stu-id="d17e7-104">F# uses type inference to evaluate the types of functions and expressions.</span></span> <span data-ttu-id="d17e7-105">Este tema describe cómo F # generaliza automáticamente los argumentos y los tipos de funciones para que funcionen con varios tipos cuando sea posible.</span><span class="sxs-lookup"><span data-stu-id="d17e7-105">This topic describes how F# automatically generalizes the arguments and types of functions so that they work with multiple types when this is possible.</span></span>


## <a name="automatic-generalization"></a><span data-ttu-id="d17e7-106">Generalización automática</span><span class="sxs-lookup"><span data-stu-id="d17e7-106">Automatic Generalization</span></span>
<span data-ttu-id="d17e7-107">El compilador de F #, mientras se realiza la inferencia de tipo en una función, determina si un parámetro determinado puede ser genérico.</span><span class="sxs-lookup"><span data-stu-id="d17e7-107">The F# compiler, when it performs type inference on a function, determines whether a given parameter can be generic.</span></span> <span data-ttu-id="d17e7-108">El compilador examina cada parámetro y determina si la función tiene una dependencia en el tipo específico de ese parámetro.</span><span class="sxs-lookup"><span data-stu-id="d17e7-108">The compiler examines each parameter and determines whether the function has a dependency on the specific type of that parameter.</span></span> <span data-ttu-id="d17e7-109">Si no es así, el tipo se deduce para ser genérico.</span><span class="sxs-lookup"><span data-stu-id="d17e7-109">If it does not, the type is inferred to be generic.</span></span>

<span data-ttu-id="d17e7-110">En el ejemplo de código siguiente se muestra una función que el compilador deduce para ser genérico.</span><span class="sxs-lookup"><span data-stu-id="d17e7-110">The following code example illustrates a function that the compiler infers to be generic.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet101.fs)]

<span data-ttu-id="d17e7-111">El tipo se deduce como `'a -> 'a -> 'a`.</span><span class="sxs-lookup"><span data-stu-id="d17e7-111">The type is inferred to be `'a -> 'a -> 'a`.</span></span>

<span data-ttu-id="d17e7-112">El tipo indica que se trata de una función que toma dos argumentos del mismo tipo desconocido y devuelve un valor de ese mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="d17e7-112">The type indicates that this is a function that takes two arguments of the same unknown type and returns a value of that same type.</span></span> <span data-ttu-id="d17e7-113">Uno de los motivos que la función anterior puede ser genérica es que el mayor-que (operador) (`>`) es genérico.</span><span class="sxs-lookup"><span data-stu-id="d17e7-113">One of the reasons that the previous function can be generic is that the greater-than operator (`>`) is itself generic.</span></span> <span data-ttu-id="d17e7-114">La mayor-de operador tiene la firma `'a -> 'a -> bool`.</span><span class="sxs-lookup"><span data-stu-id="d17e7-114">The greater-than operator has the signature `'a -> 'a -> bool`.</span></span> <span data-ttu-id="d17e7-115">No todos los operadores son genéricos, y si el código de una función usa un tipo de parámetro junto con un operador o función no genérica, no se puede generalizar ese tipo de parámetro.</span><span class="sxs-lookup"><span data-stu-id="d17e7-115">Not all operators are generic, and if the code in a function uses a parameter type together with a non-generic function or operator, that parameter type cannot be generalized.</span></span>

<span data-ttu-id="d17e7-116">Dado que `max` es genérico, se puede utilizar con tipos como `int`, `float`, y así sucesivamente, tal como se muestra en los ejemplos siguientes.</span><span class="sxs-lookup"><span data-stu-id="d17e7-116">Because `max` is generic, it can be used with types such as `int`, `float`, and so on, as shown in the following examples.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet102.fs)]

<span data-ttu-id="d17e7-117">Sin embargo, los dos argumentos deben ser del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="d17e7-117">However, the two arguments must be of the same type.</span></span> <span data-ttu-id="d17e7-118">La firma es `'a -> 'a -> 'a`, no `'a -> 'b -> 'a`.</span><span class="sxs-lookup"><span data-stu-id="d17e7-118">The signature is `'a -> 'a -> 'a`, not `'a -> 'b -> 'a`.</span></span> <span data-ttu-id="d17e7-119">Por lo tanto, el código siguiente genera un error porque los tipos no coinciden.</span><span class="sxs-lookup"><span data-stu-id="d17e7-119">Therefore, the following code produces an error because the types do not match.</span></span>

```fsharp
// Error: type mismatch.
let biggestIntFloat = max 2.0 3
```

<span data-ttu-id="d17e7-120">El `max` función también funciona con cualquier tipo que admita la mayor-que el operador.</span><span class="sxs-lookup"><span data-stu-id="d17e7-120">The `max` function also works with any type that supports the greater-than operator.</span></span> <span data-ttu-id="d17e7-121">Por lo tanto, se puede también usarla en una cadena, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="d17e7-121">Therefore, you could also use it on a string, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet104.fs)]
    
## <a name="value-restriction"></a><span data-ttu-id="d17e7-122">Restricción de valor</span><span class="sxs-lookup"><span data-stu-id="d17e7-122">Value Restriction</span></span>
<span data-ttu-id="d17e7-123">El compilador realiza la generalización automática sólo en las definiciones de función completa que tienen argumentos explícitos y en valores inmutables simples.</span><span class="sxs-lookup"><span data-stu-id="d17e7-123">The compiler performs automatic generalization only on complete function definitions that have explicit arguments, and on simple immutable values.</span></span>

<span data-ttu-id="d17e7-124">Esto significa que el compilador emite un error si intenta compilar el código que no es lo suficientemente restringirse para que sea un tipo específico, pero también no es generalizable.</span><span class="sxs-lookup"><span data-stu-id="d17e7-124">This means that the compiler issues an error if you try to compile code that is not sufficiently constrained to be a specific type, but is also not generalizable.</span></span> <span data-ttu-id="d17e7-125">El mensaje de error para este problema se refiere a esta restricción de la generalización automática para los valores como el *valor restricción*.</span><span class="sxs-lookup"><span data-stu-id="d17e7-125">The error message for this problem refers to this restriction on automatic generalization for values as the *value restriction*.</span></span>

<span data-ttu-id="d17e7-126">Normalmente, se produce el error de restricción de valor cuando se desea una construcción sea genérica pero el compilador tiene información suficiente para generalizarla, o cuando se omite involuntariamente suficiente información de tipo en una construcción no genérica.</span><span class="sxs-lookup"><span data-stu-id="d17e7-126">Typically, the value restriction error occurs either when you want a construct to be generic but the compiler has insufficient information to generalize it, or when you unintentionally omit sufficient type information in a nongeneric construct.</span></span> <span data-ttu-id="d17e7-127">La solución para el error de restricción de valor es proporcionar información más explícita para limitar detalla el problema de inferencia de tipo en una de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="d17e7-127">The solution to the value restriction error is to provide more explicit information to more fully constrain the type inference problem, in one of the following ways:</span></span>


- <span data-ttu-id="d17e7-128">Restringir un tipo para que no sea genérico agregando una anotación de tipo explícita a un valor o parámetro.</span><span class="sxs-lookup"><span data-stu-id="d17e7-128">Constrain a type to be nongeneric by adding an explicit type annotation to a value or parameter.</span></span>

- <span data-ttu-id="d17e7-129">Si el problema está usando una construcción no generalizable para definir una función genérica, como una composición de funciones o argumentos de funciones currificadas no se han aplicado, intente volver a escribir la función como una definición de función ordinaria.</span><span class="sxs-lookup"><span data-stu-id="d17e7-129">If the problem is using a nongeneralizable construct to define a generic function, such as a function composition or incompletely applied curried function arguments, try to rewrite the function as an ordinary function definition.</span></span>

- <span data-ttu-id="d17e7-130">Si el problema es una expresión que es demasiado compleja para generalizarla, conviértala en una función mediante la adición de un parámetro adicional no utilizado.</span><span class="sxs-lookup"><span data-stu-id="d17e7-130">If the problem is an expression that is too complex to be generalized, make it into a function by adding an extra, unused parameter.</span></span>

- <span data-ttu-id="d17e7-131">Agregar parámetros de tipo genérico explícitos.</span><span class="sxs-lookup"><span data-stu-id="d17e7-131">Add explicit generic type parameters.</span></span> <span data-ttu-id="d17e7-132">Esta opción se usa con poca frecuencia.</span><span class="sxs-lookup"><span data-stu-id="d17e7-132">This option is rarely used.</span></span>

- <span data-ttu-id="d17e7-133">Los ejemplos de código siguiente muestran cada uno de estos escenarios.</span><span class="sxs-lookup"><span data-stu-id="d17e7-133">The following code examples illustrate each of these scenarios.</span></span>

<span data-ttu-id="d17e7-134">Caso 1: Expresión demasiado compleja.</span><span class="sxs-lookup"><span data-stu-id="d17e7-134">Case 1: Too complex an expression.</span></span> <span data-ttu-id="d17e7-135">En este ejemplo, la lista `counter` está diseñada para ser `int option ref`, pero no está definido como un valor inmutable simple.</span><span class="sxs-lookup"><span data-stu-id="d17e7-135">In this example, the list `counter` is intended to be `int option ref`, but it is not defined as a simple immutable value.</span></span>

```fsharp
let counter = ref None
// Adding a type annotation fixes the problem:
let counter : int option ref = ref None
```

<span data-ttu-id="d17e7-136">Caso 2: Uso de una construcción no generalizable para definir una función genérica.</span><span class="sxs-lookup"><span data-stu-id="d17e7-136">Case 2: Using a nongeneralizable construct to define a generic function.</span></span> <span data-ttu-id="d17e7-137">En este ejemplo, la construcción es no generalizable porque implica la aplicación parcial de argumentos de función.</span><span class="sxs-lookup"><span data-stu-id="d17e7-137">In this example, the construct is nongeneralizable because it involves partial application of function arguments.</span></span>

```fsharp
let maxhash = max << hash
// The following is acceptable because the argument for maxhash is explicit:
let maxhash obj = (max << hash) obj
```

<span data-ttu-id="d17e7-138">Caso 3: Agregar un parámetro adicional no utilizado.</span><span class="sxs-lookup"><span data-stu-id="d17e7-138">Case 3: Adding an extra, unused parameter.</span></span> <span data-ttu-id="d17e7-139">Dado que esta expresión no es lo suficientemente sencilla para la generalización, el compilador emite el error de restricción de valor.</span><span class="sxs-lookup"><span data-stu-id="d17e7-139">Because this expression is not simple enough for generalization, the compiler issues the value restriction error.</span></span>

```fsharp
let emptyList10 = Array.create 10 []
// Adding an extra (unused) parameter makes it a function, which is generalizable.
let emptyList10 () = Array.create 10 []
```

<span data-ttu-id="d17e7-140">Caso 4: Agregar los parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="d17e7-140">Case 4: Adding type parameters.</span></span>

```fsharp
let arrayOf10Lists = Array.create 10 []
// Adding a type parameter and type annotation lets you write a generic value.
let arrayOf10Lists<'T> = Array.create 10 ([]:'T list)
```

<span data-ttu-id="d17e7-141">En el último caso, el valor se convierte en una función de tipo, que puede utilizarse para crear valores de muchos tipos diferentes, por ejemplo como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="d17e7-141">In the last case, the value becomes a type function, which may be used to create values of many different types, for example as follows:</span></span>

```fsharp
let intLists = arrayOf10Lists<int>
let floatLists = arrayOf10Lists<float>
```

## <a name="see-also"></a><span data-ttu-id="d17e7-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="d17e7-142">See Also</span></span>
[<span data-ttu-id="d17e7-143">Inferencia de tipos</span><span class="sxs-lookup"><span data-stu-id="d17e7-143">Type Inference</span></span>](../type-inference.md)

[<span data-ttu-id="d17e7-144">Genéricos</span><span class="sxs-lookup"><span data-stu-id="d17e7-144">Generics</span></span>](index.md)

[<span data-ttu-id="d17e7-145">Parámetros de tipo resueltos estáticamente</span><span class="sxs-lookup"><span data-stu-id="d17e7-145">Statically Resolved Type Parameters</span></span>](statically-resolved-type-parameters.md)

[<span data-ttu-id="d17e7-146">Restricciones</span><span class="sxs-lookup"><span data-stu-id="d17e7-146">Constraints</span></span>](constraints.md)

