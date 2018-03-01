---
title: "Funciones locales (Guía de programación de C#)"
ms.date: 06/14/2017
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- local functions [C#]
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2b4e95d48e451038f0f7004d0901f329b2c57fe5
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2017
---
# <a name="local-functions-c-programming-guide"></a><span data-ttu-id="c920c-102">Funciones locales (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="c920c-102">Local functions (C# Programming Guide)</span></span>

<span data-ttu-id="c920c-103">A partir de C# 7, C# admite *funciones locales*.</span><span class="sxs-lookup"><span data-stu-id="c920c-103">Starting with C# 7, C# supports *local functions*.</span></span> <span data-ttu-id="c920c-104">Las funciones locales son métodos privados de un tipo que están anidados en otro miembro.</span><span class="sxs-lookup"><span data-stu-id="c920c-104">Local functions are private methods of a type that are nested in another member.</span></span> <span data-ttu-id="c920c-105">Solo se pueden llamar desde su miembro contenedor.</span><span class="sxs-lookup"><span data-stu-id="c920c-105">They can only be called from their containing member.</span></span> <span data-ttu-id="c920c-106">Las funciones locales se pueden declarar en y llamar desde:</span><span class="sxs-lookup"><span data-stu-id="c920c-106">Local functions can be declared in and called from:</span></span>

- <span data-ttu-id="c920c-107">Métodos, especialmente los métodos de iterador y asincrónicos</span><span class="sxs-lookup"><span data-stu-id="c920c-107">Methods, especially iterator methods and async methods</span></span>
- <span data-ttu-id="c920c-108">Constructores</span><span class="sxs-lookup"><span data-stu-id="c920c-108">Constructors</span></span>
- <span data-ttu-id="c920c-109">Descriptores de acceso de propiedad</span><span class="sxs-lookup"><span data-stu-id="c920c-109">Property accessors</span></span>
- <span data-ttu-id="c920c-110">Descriptores de acceso de un evento</span><span class="sxs-lookup"><span data-stu-id="c920c-110">Event accessors</span></span>
- <span data-ttu-id="c920c-111">Métodos anónimos</span><span class="sxs-lookup"><span data-stu-id="c920c-111">Anonymous methods</span></span>
- <span data-ttu-id="c920c-112">Expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="c920c-112">Lambda expressions</span></span>
- <span data-ttu-id="c920c-113">Finalizadores</span><span class="sxs-lookup"><span data-stu-id="c920c-113">Finalizers</span></span>
- <span data-ttu-id="c920c-114">Otras funciones locales</span><span class="sxs-lookup"><span data-stu-id="c920c-114">Other local functions</span></span>

<span data-ttu-id="c920c-115">En cambio, las funciones locales no se pueden declarar dentro de un miembro con forma de expresión.</span><span class="sxs-lookup"><span data-stu-id="c920c-115">However, local functions can't be declared inside an expression-bodied member.</span></span>

> [!NOTE]
> <span data-ttu-id="c920c-116">En algunos casos, puede usar una expresión lambda para implementar funcionalidad compatible también con una función local.</span><span class="sxs-lookup"><span data-stu-id="c920c-116">In some cases, you can use a lambda expression to implement functionality also supported by a local function.</span></span> <span data-ttu-id="c920c-117">Para ver una comparación, consulte [Funciones locales frente a expresiones lambda](../../local-functions-vs-lambdas.md).</span><span class="sxs-lookup"><span data-stu-id="c920c-117">For a comparison, see [Local functions compared to Lambda expressions](../../local-functions-vs-lambdas.md).</span></span>

<span data-ttu-id="c920c-118">Las funciones locales aclaran la intención del código.</span><span class="sxs-lookup"><span data-stu-id="c920c-118">Local functions make the intent of your code clear.</span></span> <span data-ttu-id="c920c-119">Cualquiera que lea el código puede ver que solo el método que lo contiene puede llamar al método.</span><span class="sxs-lookup"><span data-stu-id="c920c-119">Anyone reading you code can see that the method is not callable except by the containing method.</span></span> <span data-ttu-id="c920c-120">Para los proyectos de equipo, también hacen que sea imposible que otro desarrollador llame erróneamente al método directamente desde cualquier otro punto de la clase o struct.</span><span class="sxs-lookup"><span data-stu-id="c920c-120">For team projects, they also make it impossible for another developer to mistakenly call the method directly from elsewhere in the class or stuct.</span></span>
 
## <a name="local-function-syntax"></a><span data-ttu-id="c920c-121">Sintaxis de función local</span><span class="sxs-lookup"><span data-stu-id="c920c-121">Local function syntax</span></span>

<span data-ttu-id="c920c-122">Una función local se define como un método anidado dentro de un miembro contenedor.</span><span class="sxs-lookup"><span data-stu-id="c920c-122">A local function is defined as a nested method inside a containing member.</span></span> <span data-ttu-id="c920c-123">Su definición tiene la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="c920c-123">Its definition has the following syntax:</span></span>

```txt
<modifiers: async | unsafe> <return-type> <method-name> <parameter-list>
```

<span data-ttu-id="c920c-124">Las funciones locales pueden usar los modificadores [async](../../language-reference/keywords/async.md) y [unsafe](../../language-reference/keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="c920c-124">Local functions can use the [async](../../language-reference/keywords/async.md) and [unsafe](../../language-reference/keywords/unsafe.md) modifiers.</span></span> 

<span data-ttu-id="c920c-125">Tenga en cuenta que todas las variables locales que se definen en el miembro contenedor, incluidos sus parámetros de método, son accesibles en la función local.</span><span class="sxs-lookup"><span data-stu-id="c920c-125">Note that all local variables that are defined in the containing member, including its method parameters, are accessible in the local function.</span></span> 

<span data-ttu-id="c920c-126">A diferencia de una definición de método, una definición de función local no puede incluir los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="c920c-126">Unlike a method definition, a local function definition cannot include the following elements:</span></span>

- <span data-ttu-id="c920c-127">El modificador de acceso de miembro.</span><span class="sxs-lookup"><span data-stu-id="c920c-127">The member access modifier.</span></span> <span data-ttu-id="c920c-128">Dado que todas las funciones locales son privadas, incluido un modificador de acceso, como la palabra clave `private`, se genera el error del compilador CS0106, "El modificador 'private' no es válido para este elemento".</span><span class="sxs-lookup"><span data-stu-id="c920c-128">Because all local functions are private, including an access modifier, such as the `private` keyword, generates compiler error CS0106, "The modifier 'private' is not valid for this item."</span></span>
 
- <span data-ttu-id="c920c-129">La palabra clave [static](../../language-reference/keywords/static.md).</span><span class="sxs-lookup"><span data-stu-id="c920c-129">The [static](../../language-reference/keywords/static.md) keyword.</span></span> <span data-ttu-id="c920c-130">Al incluir la palabra clave `static`, se genera el error del compilador CS0106, "El modificador 'static' no es válido para este elemento".</span><span class="sxs-lookup"><span data-stu-id="c920c-130">Including the `static` keyword generates compiler error CS0106, "The modifier 'static' is not valid for this item."</span></span>

<span data-ttu-id="c920c-131">Además, los atributos no se pueden aplicar a la función local o a sus parámetros y parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="c920c-131">In addition, attributes can't be applied to the local function or to its parameters and type parameters.</span></span> 
 
<span data-ttu-id="c920c-132">En el ejemplo siguiente, se define una función local denominada `AppendPathSeparator` que es privada a un método denominado `GetText`:</span><span class="sxs-lookup"><span data-stu-id="c920c-132">The following example defines a local function named `AppendPathSeparator` that is private to a method named `GetText`:</span></span>
   
[!code-csharp[LocalFunctionExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/local-functions1.cs)]  
   
## <a name="local-functions-and-exceptions"></a><span data-ttu-id="c920c-133">Excepciones y funciones locales</span><span class="sxs-lookup"><span data-stu-id="c920c-133">Local functions and exceptions</span></span>

<span data-ttu-id="c920c-134">Una de las características útiles de las funciones locales es que pueden permitir que las excepciones aparezcan inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="c920c-134">One of the useful features of local functions is that they can allow exceptions to surface immediately.</span></span> <span data-ttu-id="c920c-135">Para los iteradores de método, las excepciones aparecen solo cuando la secuencia devuelta se enumera y no cuando se recupera el iterador.</span><span class="sxs-lookup"><span data-stu-id="c920c-135">For method iterators, exceptions are surfaced only when the returned sequence is enumerated, and not when the iterator is retrieved.</span></span> <span data-ttu-id="c920c-136">Para los métodos asincrónicos, las excepciones producidas en un método asincrónico se observan cuando se espera la tarea devuelta.</span><span class="sxs-lookup"><span data-stu-id="c920c-136">For async methods, any exceptions thrown in an async method are observed when the returned task is awaited.</span></span> 

<span data-ttu-id="c920c-137">En el ejemplo siguiente, se define un método `OddSequence` que enumera los números impares entre un intervalo especificado.</span><span class="sxs-lookup"><span data-stu-id="c920c-137">The following example defines an `OddSequence` method that enumerates odd numbers between a specified range.</span></span> <span data-ttu-id="c920c-138">Dado que pasa un número mayor de 100 al método de enumerador `OddSequence`, el método produce una excepción <xref:System.ArgumentOutOfRangeException>.</span><span class="sxs-lookup"><span data-stu-id="c920c-138">Because it passes a number greater than 100 to the `OddSequence` enumerator method, the method throws an <xref:System.ArgumentOutOfRangeException>.</span></span> <span data-ttu-id="c920c-139">Como se muestra en el resultado del ejemplo, la excepción aparece solo cuando itera los números, y no al recuperar el enumerador.</span><span class="sxs-lookup"><span data-stu-id="c920c-139">As the output from the example shows, the exception surfaces only when you iterate the numbers, and not when you retrieve the enumerator.</span></span>

[!code-csharp[LocalFunctionIterator1](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-iterator1.cs)] 

<span data-ttu-id="c920c-140">En su lugar, puede producir una excepción al realizar la validación y antes de recuperar el iterador al devolver el iterador de una función local, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="c920c-140">Instead, you can throw an exception when performing validation and before retrieving the iterator by returning the iterator from a local function, as the following example shows.</span></span>

[!code-csharp[LocalFunctionIterator2](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-iterator2.cs)]

<span data-ttu-id="c920c-141">Las funciones locales se pueden usar de forma similar, para controlar las excepciones fuera de la operación asincrónica.</span><span class="sxs-lookup"><span data-stu-id="c920c-141">Local functions can be used in a similar way to handle exceptions outside of the asynchronous operation.</span></span> <span data-ttu-id="c920c-142">Normalmente, las excepciones producidas en el método asincrónico requieren que examine las excepciones internas de una excepción <xref:System.AggregateException>.</span><span class="sxs-lookup"><span data-stu-id="c920c-142">Ordinarily, exceptions thrown in async method require that you examine the inner exceptions of an <xref:System.AggregateException>.</span></span> <span data-ttu-id="c920c-143">Las funciones locales permiten que el código genere un error inmediato y permiten que la excepción se produzca y observe de forma sincrónica.</span><span class="sxs-lookup"><span data-stu-id="c920c-143">Local functions allow your code to fail fast and allow your exception to be both thrown and observed synchronously.</span></span>

<span data-ttu-id="c920c-144">En el ejemplo siguiente, se usa un método asincrónico denominado `GetMultipleAsync` para pausar durante un número especificado de segundos y se devuelve un valor que es un múltiplo aleatorio de ese número de segundos.</span><span class="sxs-lookup"><span data-stu-id="c920c-144">The following example uses an asynchronous method named `GetMultipleAsync` to pause for a specified number of seconds and return a value that is a random multiple of that number of seconds.</span></span> <span data-ttu-id="c920c-145">El retraso máximo es de 5 segundos; se produce una excepción <xref:System.ArgumentOutOfRangeException> si el valor es mayor que 5.</span><span class="sxs-lookup"><span data-stu-id="c920c-145">The maximum delay is 5 seconds; an <xref:System.ArgumentOutOfRangeException> results if the value is greater than 5.</span></span> <span data-ttu-id="c920c-146">Como se muestra en el ejemplo siguiente, la excepción que produce cuando se pasa un valor de 6 al método `GetMultipleAsync` se encapsula en una excepción <xref:System.AggregateException> después de que el método `GetMultipleAsync` empiece a ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="c920c-146">As the following example shows, the exception that is thrown when a value of 6 is passed to the `GetMultipleAsync` method is wrapped in an <xref:System.AggregateException> after the `GetMultipleAsync` method begins execution.</span></span>

[!code-csharp[LocalFunctionAsync`](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-async1.cs)] 

<span data-ttu-id="c920c-147">Igual que hemos hecho con el iterador de método, podemos refactorizar el código de este ejemplo para realizar la validación antes de llamar al método asincrónico.</span><span class="sxs-lookup"><span data-stu-id="c920c-147">As we did with the method iterator, we can refactor the code from this example to perform the validation before calling the asynchronous method.</span></span> <span data-ttu-id="c920c-148">Como se muestra en el resultado del ejemplo siguiente, la excepción <xref:System.ArgumentOutOfRangeException> no se encapsula en una excepción <x:System.AggregateException>.</span><span class="sxs-lookup"><span data-stu-id="c920c-148">As the output from the following example shows, the <xref:System.ArgumentOutOfRangeException> is not wrapped in a <x:System.AggregateException>.</span></span>

[!code-csharp[LocalFunctionAsync`](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-async2.cs)] 

## <a name="see-also"></a><span data-ttu-id="c920c-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="c920c-149">See also</span></span>
[<span data-ttu-id="c920c-150">Métodos</span><span class="sxs-lookup"><span data-stu-id="c920c-150">Methods</span></span>](methods.md)
