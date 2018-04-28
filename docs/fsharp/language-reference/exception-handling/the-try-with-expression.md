---
title: 'Excepciones: la expresión try...with (F#)'
description: "Obtenga información acerca de cómo usar la expresión 'try... with' de F # para el control de excepciones."
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 06e40b79fc1958918dc0615ce9d1004e0a6e74a5
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="exceptions-the-trywith-expression"></a><span data-ttu-id="d951e-103">Excepciones: expresión try...with</span><span class="sxs-lookup"><span data-stu-id="d951e-103">Exceptions: The try...with Expression</span></span>

<span data-ttu-id="d951e-104">Este tema se describe la `try...with` expresión, la expresión que se usa para el control de excepciones en el lenguaje F #.</span><span class="sxs-lookup"><span data-stu-id="d951e-104">This topic describes the `try...with` expression, the expression that is used for exception handling in the F# language.</span></span>


## <a name="syntax"></a><span data-ttu-id="d951e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d951e-105">Syntax</span></span>

```fsharp
try
    expression1
with
| pattern1 -> expression2
| pattern2 -> expression3
...
```

## <a name="remarks"></a><span data-ttu-id="d951e-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d951e-106">Remarks</span></span>
<span data-ttu-id="d951e-107">El `try...with` expresión se utiliza para controlar las excepciones en F #.</span><span class="sxs-lookup"><span data-stu-id="d951e-107">The `try...with` expression is used to handle exceptions in F#.</span></span> <span data-ttu-id="d951e-108">Es similar a la `try...catch` instrucción en C#.</span><span class="sxs-lookup"><span data-stu-id="d951e-108">It is similar to the `try...catch` statement in C#.</span></span> <span data-ttu-id="d951e-109">En la sintaxis anterior, el código en *expression1* podría generar una excepción.</span><span class="sxs-lookup"><span data-stu-id="d951e-109">In the preceding syntax, the code in *expression1* might generate an exception.</span></span> <span data-ttu-id="d951e-110">El `try...with` expresión devuelve un valor.</span><span class="sxs-lookup"><span data-stu-id="d951e-110">The `try...with` expression returns a value.</span></span> <span data-ttu-id="d951e-111">Si no se produce ninguna excepción, toda la expresión devuelve el valor de *expression1*.</span><span class="sxs-lookup"><span data-stu-id="d951e-111">If no exception is thrown, the whole expression returns the value of *expression1*.</span></span> <span data-ttu-id="d951e-112">Si se produce una excepción, cada uno de ellos *patrón* se compara a su vez con la excepción y para el primer patrón de búsqueda de coincidencias, la correspondiente *expresión*, que se conoce como el *delcontroladordeexcepciones*, para esa bifurcación se ejecuta y toda la expresión devuelve el valor de la expresión en ese controlador de excepciones.</span><span class="sxs-lookup"><span data-stu-id="d951e-112">If an exception is thrown, each *pattern* is compared in turn with the exception, and for the first matching pattern, the corresponding *expression*, known as the *exception handler*, for that branch is executed, and the overall expression returns the value of the expression in that exception handler.</span></span> <span data-ttu-id="d951e-113">Si ningún modelo coincide, la excepción se propaga la pila de llamadas hasta que encuentra un controlador coincidente.</span><span class="sxs-lookup"><span data-stu-id="d951e-113">If no pattern matches, the exception propagates up the call stack until a matching handler is found.</span></span> <span data-ttu-id="d951e-114">Los tipos de los valores devueltos por cada expresión de los controladores de excepción deben coincidir con el tipo devuelto de la expresión en el `try` bloque.</span><span class="sxs-lookup"><span data-stu-id="d951e-114">The types of the values returned from each expression in the exception handlers must match the type returned from the expression in the `try` block.</span></span>

<span data-ttu-id="d951e-115">Con frecuencia, el hecho de que ocurrió un error también significa que no hay ningún valor válido que se pueden devolver en las expresiones de cada controlador de excepciones.</span><span class="sxs-lookup"><span data-stu-id="d951e-115">Frequently, the fact that an error occurred also means that there is no valid value that can be returned from the expressions in each exception handler.</span></span> <span data-ttu-id="d951e-116">Una práctica habitual es que el tipo de la expresión sea un tipo de opción.</span><span class="sxs-lookup"><span data-stu-id="d951e-116">A frequent pattern is to have the type of the expression be an option type.</span></span> <span data-ttu-id="d951e-117">En el ejemplo de código siguiente se muestra este modelo.</span><span class="sxs-lookup"><span data-stu-id="d951e-117">The following code example illustrates this pattern.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5601.fs)]

<span data-ttu-id="d951e-118">Las excepciones pueden estar excepciones de. NET, o pueden ser excepciones de F #.</span><span class="sxs-lookup"><span data-stu-id="d951e-118">Exceptions can be .NET exceptions, or they can be F# exceptions.</span></span> <span data-ttu-id="d951e-119">Puede definir excepciones de F # mediante el `exception` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="d951e-119">You can define F# exceptions by using the `exception` keyword.</span></span>

<span data-ttu-id="d951e-120">Puede usar una variedad de modelos para filtrar según el tipo de excepción y otras condiciones; en la tabla siguiente se resumen las opciones.</span><span class="sxs-lookup"><span data-stu-id="d951e-120">You can use a variety of patterns to filter on the exception type and other conditions; the options are summarized in the following table.</span></span>


|<span data-ttu-id="d951e-121">Modelo</span><span class="sxs-lookup"><span data-stu-id="d951e-121">Pattern</span></span>|<span data-ttu-id="d951e-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="d951e-122">Description</span></span>|
|-------|-----------|
|<span data-ttu-id="d951e-123">:?</span><span class="sxs-lookup"><span data-stu-id="d951e-123">:?</span></span> <span data-ttu-id="d951e-124">*tipo de excepción*</span><span class="sxs-lookup"><span data-stu-id="d951e-124">*exception-type*</span></span>|<span data-ttu-id="d951e-125">Coincide con el tipo de excepción de .NET especificado.</span><span class="sxs-lookup"><span data-stu-id="d951e-125">Matches the specified .NET exception type.</span></span>|
|<span data-ttu-id="d951e-126">:?</span><span class="sxs-lookup"><span data-stu-id="d951e-126">:?</span></span> <span data-ttu-id="d951e-127">*tipo de excepción* como *identificador*</span><span class="sxs-lookup"><span data-stu-id="d951e-127">*exception-type* as *identifier*</span></span>|<span data-ttu-id="d951e-128">Coincide con el tipo de excepción de .NET especificado, pero da un valor con nombre de la excepción.</span><span class="sxs-lookup"><span data-stu-id="d951e-128">Matches the specified .NET exception type, but gives the exception a named value.</span></span>|
|<span data-ttu-id="d951e-129">*nombre de la excepción*(*argumentos*)</span><span class="sxs-lookup"><span data-stu-id="d951e-129">*exception-name*(*arguments*)</span></span>|<span data-ttu-id="d951e-130">Coincide con un tipo de excepción de F # y enlaza los argumentos.</span><span class="sxs-lookup"><span data-stu-id="d951e-130">Matches an F# exception type and binds the arguments.</span></span>|
|<span data-ttu-id="d951e-131">*identifier*</span><span class="sxs-lookup"><span data-stu-id="d951e-131">*identifier*</span></span>|<span data-ttu-id="d951e-132">Coincide con cualquier excepción y enlaza el nombre para el objeto de excepción.</span><span class="sxs-lookup"><span data-stu-id="d951e-132">Matches any exception and binds the name to the exception object.</span></span> <span data-ttu-id="d951e-133">¿Equivalente a **:? System.Exception como *** identificador*</span><span class="sxs-lookup"><span data-stu-id="d951e-133">Equivalent to **:? System.Exception as***identifier*</span></span>|
|<span data-ttu-id="d951e-134">*identificador* cuando *condición*</span><span class="sxs-lookup"><span data-stu-id="d951e-134">*identifier* when *condition*</span></span>|<span data-ttu-id="d951e-135">Coincide con cualquier excepción si la condición es true.</span><span class="sxs-lookup"><span data-stu-id="d951e-135">Matches any exception if the condition is true.</span></span>|

## <a name="examples"></a><span data-ttu-id="d951e-136">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="d951e-136">Examples</span></span>
<span data-ttu-id="d951e-137">Ejemplos de código siguientes muestran el uso de los distintos patrones de controlador de excepción.</span><span class="sxs-lookup"><span data-stu-id="d951e-137">The following code examples illustrate the use of the various exception handler patterns.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5602.fs)]
    
>[!NOTE] 
<span data-ttu-id="d951e-138">El `try...with` construcción es una expresión independiente desde el `try...finally` expresión.</span><span class="sxs-lookup"><span data-stu-id="d951e-138">The `try...with` construct is a separate expression from the `try...finally` expression.</span></span> <span data-ttu-id="d951e-139">Por lo tanto, si el código requiere tanto un `with` bloque y un `finally` bloque, se deben anidar las dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="d951e-139">Therefore, if your code requires both a `with` block and a `finally` block, you will have to nest the two expressions.</span></span>

>[!NOTE] 
<span data-ttu-id="d951e-140">Puede usar `try...with` en flujos de trabajo asincrónicos y otras expresiones de cálculo, en el que caso una versión personalizada de la `try...with` se utiliza la expresión.</span><span class="sxs-lookup"><span data-stu-id="d951e-140">You can use `try...with` in asynchronous workflows and other computation expressions, in which case a customized version of the `try...with` expression is used.</span></span> <span data-ttu-id="d951e-141">Para obtener más información, consulte [flujos de trabajo asincrónicos](../asynchronous-workflows.md), y [expresiones de cálculo](../computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="d951e-141">For more information, see [Asynchronous Workflows](../asynchronous-workflows.md), and [Computation Expressions](../computation-expressions.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="d951e-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="d951e-142">See Also</span></span>
[<span data-ttu-id="d951e-143">Control de excepciones</span><span class="sxs-lookup"><span data-stu-id="d951e-143">Exception Handling</span></span>](index.md)

[<span data-ttu-id="d951e-144">Tipos de excepción</span><span class="sxs-lookup"><span data-stu-id="d951e-144">Exception Types</span></span>](exception-types.md)

<span data-ttu-id="d951e-145">[Exceptions: The `try...finally` Expression](the-try-finally-expression.md) (Excepciones: la expresión `try...finally`)</span><span class="sxs-lookup"><span data-stu-id="d951e-145">[Exceptions: The `try...finally` Expression](the-try-finally-expression.md)</span></span>
