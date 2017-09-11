---
title: Funciones locales frente a expresiones lambda
description: "Obtenga información sobre por qué las funciones locales pueden ser una opción mejor que las expresiones lambda."
keywords: "C#, .NET, .NET Core, Características más recientes, Novedades, funciones locales, expresiones lambda"
author: BillWagner
ms.author: wiwagn
ms.date: 06/27/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 368d1752-3659-489a-97b4-f15d87e49ae3
ms.translationtype: HT
ms.sourcegitcommit: 9bb17207ba72bb22f5d6db55e9d1bd77e3013445
ms.openlocfilehash: 0730e7b7d6e3ef7b5c534d16baacde6a7dafacfc
ms.contentlocale: es-es
ms.lasthandoff: 08/25/2017

---
# <a name="local-functions-compared-to-lambda-expressions"></a><span data-ttu-id="ede98-104">Funciones locales frente a expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="ede98-104">Local functions compared to Lambda expressions</span></span>

<span data-ttu-id="ede98-105">A primera vista, las [funciones locales](programming-guide/classes-and-structs/local-functions.md) y las [expresiones lambda](lambda-expressions.md) son muy similares.</span><span class="sxs-lookup"><span data-stu-id="ede98-105">At first glance, [local functions](programming-guide/classes-and-structs/local-functions.md) and [lambda expressions](lambda-expressions.md) are very similar.</span></span>
<span data-ttu-id="ede98-106">Dependiendo de sus necesidades, las funciones locales pueden ser una solución mucho mejor y más sencilla.</span><span class="sxs-lookup"><span data-stu-id="ede98-106">Depending on your needs, local functions may be a much better and simpler solution.</span></span>

<span data-ttu-id="ede98-107">Vamos a examinar las diferencias entre las implementaciones de la función local y la expresión lambda del algoritmo factorial.</span><span class="sxs-lookup"><span data-stu-id="ede98-107">Let's examine the differences between the local function and lambda expression implementations of the factorial algorithm.</span></span> <span data-ttu-id="ede98-108">Primero la versión que usa una función local:</span><span class="sxs-lookup"><span data-stu-id="ede98-108">First the version using a local function:</span></span>

<span data-ttu-id="ede98-109">[!code-csharp[LocalFunctionFactorial](../../samples/snippets/csharp/new-in-7/MathUtilities.cs#37_LocalFunctionFactorial "Factorial recursivo con función local")]</span><span class="sxs-lookup"><span data-stu-id="ede98-109">[!code-csharp[LocalFunctionFactorial](../../samples/snippets/csharp/new-in-7/MathUtilities.cs#37_LocalFunctionFactorial "Recursive factorial using local function")]</span></span>

<span data-ttu-id="ede98-110">Compare esa implementación con una versión que use expresiones lambda:</span><span class="sxs-lookup"><span data-stu-id="ede98-110">Contrast that implementation with a version that uses lambda expressions:</span></span>

<span data-ttu-id="ede98-111">[!code-csharp[26_LambdaFactorial](../../samples/snippets/csharp/new-in-7/MathUtilities.cs#38_LambdaFactorial "Factorial recursivo con expresiones lambda")]</span><span class="sxs-lookup"><span data-stu-id="ede98-111">[!code-csharp[26_LambdaFactorial](../../samples/snippets/csharp/new-in-7/MathUtilities.cs#38_LambdaFactorial "Recursive factorial using lambda expressions")]</span></span>

<span data-ttu-id="ede98-112">Primero, las expresiones lambda se implementan mediante la creación de instancias de un delegado y la invocación de este.</span><span class="sxs-lookup"><span data-stu-id="ede98-112">First, lambda expressions are implemented by instantiating a delegate and invoking that delegate.</span></span> <span data-ttu-id="ede98-113">Las funciones locales se implementan como llamadas a métodos.</span><span class="sxs-lookup"><span data-stu-id="ede98-113">Local functions are implemented as method calls.</span></span>
<span data-ttu-id="ede98-114">La creación de instancias necesaria para las expresiones lambda significa asignaciones de memoria adicionales, lo que puede ser un factor de rendimiento en rutas de acceso de código crítico en el tiempo.</span><span class="sxs-lookup"><span data-stu-id="ede98-114">The instantiation necessary for lambda expressions means extra memory allocations, which may be a performance factor in time critical code paths.</span></span>
<span data-ttu-id="ede98-115">Las funciones locales no suponen esta sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="ede98-115">Local functions do not incur this overhead.</span></span> <span data-ttu-id="ede98-116">En el ejemplo anterior, la versión de las funciones locales tiene 2 asignaciones menos que la versión de la expresión lambda.</span><span class="sxs-lookup"><span data-stu-id="ede98-116">In the example above, the local functions version has 2 fewer allocations than the lambda expression version.</span></span>

<span data-ttu-id="ede98-117">Este método recursivo es lo suficientemente sencillo para que la función local se implemente como un método privado con el nombre generado por el compilador.</span><span class="sxs-lookup"><span data-stu-id="ede98-117">This recursive method is simple enough that the local function is implemented as a private method with a compiler generated name.</span></span> <span data-ttu-id="ede98-118">Su única diferencia de otros métodos privados es que semánticamente tiene su ámbito dentro de la función externa.</span><span class="sxs-lookup"><span data-stu-id="ede98-118">Its only difference from other private methods is that it is semantically scoped inside the outer function.</span></span>

<span data-ttu-id="ede98-119">En segundo lugar, es posible llamar a las funciones locales antes de que se definan.</span><span class="sxs-lookup"><span data-stu-id="ede98-119">Second, local functions can be called before they are defined.</span></span> <span data-ttu-id="ede98-120">Las expresiones lambda se deben declarar antes de definirse.</span><span class="sxs-lookup"><span data-stu-id="ede98-120">Lambda expressions must be declared before they are defined.</span></span> <span data-ttu-id="ede98-121">Esto significa que las funciones locales son más fáciles de usar en algoritmos recursivos, como se ha mostrado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="ede98-121">This means local functions are easier to use in recursive algorithms, as shown above.</span></span>

<span data-ttu-id="ede98-122">Observe que la versión con la expresión lambda debe declarar e inicializar la expresión lambda, `nthFactorial`, antes de definirla.</span><span class="sxs-lookup"><span data-stu-id="ede98-122">Notice that the version using the lambda expression must declare and initialize the lambda expression, `nthFactorial` before defining it.</span></span> <span data-ttu-id="ede98-123">De no hacerlo, se produce un error en tiempo de compilación por hacer referencia a `nthFactorial` antes de asignarlo.</span><span class="sxs-lookup"><span data-stu-id="ede98-123">Not doing so results in a compile time error for referencing `nthFactorial` before assigning it.</span></span>
<span data-ttu-id="ede98-124">Los algoritmos recursivos son más fáciles de crear con funciones locales.</span><span class="sxs-lookup"><span data-stu-id="ede98-124">Recursive algorithms are easier to create using local functions.</span></span>

<span data-ttu-id="ede98-125">En tercer lugar, en las expresiones lambda, el compilador siempre debe crear una clase anónima y una instancia de esa clase para almacenar cualquier variable capturada por la clausura.</span><span class="sxs-lookup"><span data-stu-id="ede98-125">Third, for lambda expressions, the compiler must always create an anonymous class and an instance of that class to store any variables captured by the closure.</span></span> <span data-ttu-id="ede98-126">Considere este ejemplo asincrónico:</span><span class="sxs-lookup"><span data-stu-id="ede98-126">Consider this async example:</span></span>

<span data-ttu-id="ede98-127">[!code-csharp[TaskLambdaExample](../../samples/snippets/csharp/new-in-7/AsyncWork.cs#36_TaskLambdaExample "Tarea que devuelve un método con una expresión lambda")]</span><span class="sxs-lookup"><span data-stu-id="ede98-127">[!code-csharp[TaskLambdaExample](../../samples/snippets/csharp/new-in-7/AsyncWork.cs#36_TaskLambdaExample "Task returning method with lambda expression")]</span></span>

<span data-ttu-id="ede98-128">La clausura de esta expresión lambda contiene las variables `address`, `index` y `name`.</span><span class="sxs-lookup"><span data-stu-id="ede98-128">The closure for this lambda expression contains the `address`, `index` and `name` variables.</span></span> <span data-ttu-id="ede98-129">En el caso de las funciones locales, el objeto que implementa el cierre puede ser un tipo `struct`.</span><span class="sxs-lookup"><span data-stu-id="ede98-129">In the case of local functions, the object that implements the closure may be a `struct` type.</span></span> <span data-ttu-id="ede98-130">Se guardaría en una asignación.</span><span class="sxs-lookup"><span data-stu-id="ede98-130">That would save on an allocation.</span></span>

> [!NOTE]
> <span data-ttu-id="ede98-131">La función local equivalente de este método también usa una clase para el cierre.</span><span class="sxs-lookup"><span data-stu-id="ede98-131">The local function equivalent of this method also uses a class for the closure.</span></span> <span data-ttu-id="ede98-132">Si el cierre de una función local se implementa como `class` o `struct` es un detalle de implementación.</span><span class="sxs-lookup"><span data-stu-id="ede98-132">Whether the closure for a local function is implemented as a `class` or a `struct` is an implementation detail.</span></span> <span data-ttu-id="ede98-133">Una función local puede usar `struct` mientras una expresión lambda siempre usará `class`.</span><span class="sxs-lookup"><span data-stu-id="ede98-133">A local function may use a `struct` whereas a lambda will always use a `class`.</span></span>

<span data-ttu-id="ede98-134">[!code-csharp[TaskLocalFunctionExample](../../samples/snippets/csharp/new-in-7/AsyncWork.cs#29_TaskExample "Método de devolución de tarea con función local")]</span><span class="sxs-lookup"><span data-stu-id="ede98-134">[!code-csharp[TaskLocalFunctionExample](../../samples/snippets/csharp/new-in-7/AsyncWork.cs#29_TaskExample "Task returning method with local function")]</span></span>

<span data-ttu-id="ede98-135">Una ventaja final que no se muestra en este ejemplo es que las funciones locales pueden implementarse como iteradores, con la sintaxis `yield return` para producir una secuencia de valores.</span><span class="sxs-lookup"><span data-stu-id="ede98-135">One final advantage not demonstrated in this sample is that local functions can be implemented as iterators, using the `yield return` syntax to produce a sequence of values.</span></span>

<span data-ttu-id="ede98-136">Aunque las funciones locales pueden parecer redundantes con respecto a las expresiones lambda, en realidad tienen finalidades y usos diferentes.</span><span class="sxs-lookup"><span data-stu-id="ede98-136">While local functions may seem redundant to lambda expressions, they actually serve different purposes and have different uses.</span></span>
<span data-ttu-id="ede98-137">Las funciones locales son más eficaces si se quiere escribir una función a la que solo se llame desde el contexto de otro método.</span><span class="sxs-lookup"><span data-stu-id="ede98-137">Local functions are more efficient for the case when you want to write a function that is called only from the context of another method.</span></span>

