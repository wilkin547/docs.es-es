---
title: "Excepciones: la expresión try...with (F#)"
description: "Obtenga información acerca de cómo usar la expresión 'try... with' de F # para el control de excepciones."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 36721076-95cd-4636-ae43-79dd512bee6c
ms.openlocfilehash: 163dfab49d4aaf23123800246fae2cad33e2257c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="exceptions-the-trywith-expression"></a><span data-ttu-id="e1e03-104">Excepciones: expresión try...with</span><span class="sxs-lookup"><span data-stu-id="e1e03-104">Exceptions: The try...with Expression</span></span>

<span data-ttu-id="e1e03-105">Este tema se describe la `try...with` expresión, la expresión que se usa para el control de excepciones en el lenguaje F #.</span><span class="sxs-lookup"><span data-stu-id="e1e03-105">This topic describes the `try...with` expression, the expression that is used for exception handling in the F# language.</span></span>


## <a name="syntax"></a><span data-ttu-id="e1e03-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e1e03-106">Syntax</span></span>

```fsharp
try
    expression1
with
| pattern1 -> expression2
| pattern2 -> expression3
...
```

## <a name="remarks"></a><span data-ttu-id="e1e03-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e1e03-107">Remarks</span></span>
<span data-ttu-id="e1e03-108">El `try...with` expresión se utiliza para controlar las excepciones en F #.</span><span class="sxs-lookup"><span data-stu-id="e1e03-108">The `try...with` expression is used to handle exceptions in F#.</span></span> <span data-ttu-id="e1e03-109">Es similar a la `try...catch` instrucción en C#.</span><span class="sxs-lookup"><span data-stu-id="e1e03-109">It is similar to the `try...catch` statement in C#.</span></span> <span data-ttu-id="e1e03-110">En la sintaxis anterior, el código en *expression1* podría generar una excepción.</span><span class="sxs-lookup"><span data-stu-id="e1e03-110">In the preceding syntax, the code in *expression1* might generate an exception.</span></span> <span data-ttu-id="e1e03-111">El `try...with` expresión devuelve un valor.</span><span class="sxs-lookup"><span data-stu-id="e1e03-111">The `try...with` expression returns a value.</span></span> <span data-ttu-id="e1e03-112">Si no se produce ninguna excepción, toda la expresión devuelve el valor de *expression1*.</span><span class="sxs-lookup"><span data-stu-id="e1e03-112">If no exception is thrown, the whole expression returns the value of *expression1*.</span></span> <span data-ttu-id="e1e03-113">Si se produce una excepción, cada uno de ellos *patrón* se compara a su vez con la excepción y para el primer patrón de búsqueda de coincidencias, la correspondiente *expresión*, que se conoce como el *delcontroladordeexcepciones*, para esa bifurcación se ejecuta y toda la expresión devuelve el valor de la expresión en ese controlador de excepciones.</span><span class="sxs-lookup"><span data-stu-id="e1e03-113">If an exception is thrown, each *pattern* is compared in turn with the exception, and for the first matching pattern, the corresponding *expression*, known as the *exception handler*, for that branch is executed, and the overall expression returns the value of the expression in that exception handler.</span></span> <span data-ttu-id="e1e03-114">Si ningún modelo coincide, la excepción se propaga la pila de llamadas hasta que encuentra un controlador coincidente.</span><span class="sxs-lookup"><span data-stu-id="e1e03-114">If no pattern matches, the exception propagates up the call stack until a matching handler is found.</span></span> <span data-ttu-id="e1e03-115">Los tipos de los valores devueltos por cada expresión de los controladores de excepción deben coincidir con el tipo devuelto de la expresión en el `try` bloque.</span><span class="sxs-lookup"><span data-stu-id="e1e03-115">The types of the values returned from each expression in the exception handlers must match the type returned from the expression in the `try` block.</span></span>

<span data-ttu-id="e1e03-116">Con frecuencia, el hecho de que ocurrió un error también significa que no hay ningún valor válido que se pueden devolver en las expresiones de cada controlador de excepciones.</span><span class="sxs-lookup"><span data-stu-id="e1e03-116">Frequently, the fact that an error occurred also means that there is no valid value that can be returned from the expressions in each exception handler.</span></span> <span data-ttu-id="e1e03-117">Una práctica habitual es que el tipo de la expresión sea un tipo de opción.</span><span class="sxs-lookup"><span data-stu-id="e1e03-117">A frequent pattern is to have the type of the expression be an option type.</span></span> <span data-ttu-id="e1e03-118">En el ejemplo de código siguiente se muestra este modelo.</span><span class="sxs-lookup"><span data-stu-id="e1e03-118">The following code example illustrates this pattern.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5601.fs)]

<span data-ttu-id="e1e03-119">Las excepciones pueden estar excepciones de. NET, o pueden ser excepciones de F #.</span><span class="sxs-lookup"><span data-stu-id="e1e03-119">Exceptions can be .NET exceptions, or they can be F# exceptions.</span></span> <span data-ttu-id="e1e03-120">Puede definir excepciones de F # mediante el `exception` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="e1e03-120">You can define F# exceptions by using the `exception` keyword.</span></span>

<span data-ttu-id="e1e03-121">Puede usar una variedad de modelos para filtrar según el tipo de excepción y otras condiciones; en la tabla siguiente se resumen las opciones.</span><span class="sxs-lookup"><span data-stu-id="e1e03-121">You can use a variety of patterns to filter on the exception type and other conditions; the options are summarized in the following table.</span></span>


|<span data-ttu-id="e1e03-122">Modelo</span><span class="sxs-lookup"><span data-stu-id="e1e03-122">Pattern</span></span>|<span data-ttu-id="e1e03-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="e1e03-123">Description</span></span>|
|-------|-----------|
|<span data-ttu-id="e1e03-124">:?</span><span class="sxs-lookup"><span data-stu-id="e1e03-124">:?</span></span> <span data-ttu-id="e1e03-125">*tipo de excepción*</span><span class="sxs-lookup"><span data-stu-id="e1e03-125">*exception-type*</span></span>|<span data-ttu-id="e1e03-126">Coincide con el tipo de excepción de .NET especificado.</span><span class="sxs-lookup"><span data-stu-id="e1e03-126">Matches the specified .NET exception type.</span></span>|
|<span data-ttu-id="e1e03-127">:?</span><span class="sxs-lookup"><span data-stu-id="e1e03-127">:?</span></span> <span data-ttu-id="e1e03-128">*tipo de excepción* como *identificador*</span><span class="sxs-lookup"><span data-stu-id="e1e03-128">*exception-type* as *identifier*</span></span>|<span data-ttu-id="e1e03-129">Coincide con el tipo de excepción de .NET especificado, pero da un valor con nombre de la excepción.</span><span class="sxs-lookup"><span data-stu-id="e1e03-129">Matches the specified .NET exception type, but gives the exception a named value.</span></span>|
|<span data-ttu-id="e1e03-130">*nombre de la excepción*(*argumentos*)</span><span class="sxs-lookup"><span data-stu-id="e1e03-130">*exception-name*(*arguments*)</span></span>|<span data-ttu-id="e1e03-131">Coincide con un tipo de excepción de F # y enlaza los argumentos.</span><span class="sxs-lookup"><span data-stu-id="e1e03-131">Matches an F# exception type and binds the arguments.</span></span>|
|<span data-ttu-id="e1e03-132">*identifier*</span><span class="sxs-lookup"><span data-stu-id="e1e03-132">*identifier*</span></span>|<span data-ttu-id="e1e03-133">Coincide con cualquier excepción y enlaza el nombre para el objeto de excepción.</span><span class="sxs-lookup"><span data-stu-id="e1e03-133">Matches any exception and binds the name to the exception object.</span></span> <span data-ttu-id="e1e03-134">¿Equivalente a **:? System.Exception como***identificador*</span><span class="sxs-lookup"><span data-stu-id="e1e03-134">Equivalent to **:? System.Exception as***identifier*</span></span>|
|<span data-ttu-id="e1e03-135">*identificador* cuando *condición*</span><span class="sxs-lookup"><span data-stu-id="e1e03-135">*identifier* when *condition*</span></span>|<span data-ttu-id="e1e03-136">Coincide con cualquier excepción si la condición es true.</span><span class="sxs-lookup"><span data-stu-id="e1e03-136">Matches any exception if the condition is true.</span></span>|

## <a name="examples"></a><span data-ttu-id="e1e03-137">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="e1e03-137">Examples</span></span>
<span data-ttu-id="e1e03-138">Ejemplos de código siguientes muestran el uso de los distintos patrones de controlador de excepción.</span><span class="sxs-lookup"><span data-stu-id="e1e03-138">The following code examples illustrate the use of the various exception handler patterns.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5602.fs)]
    
>[!NOTE] 
<span data-ttu-id="e1e03-139">El `try...with` construcción es una expresión independiente desde el `try...finally` expresión.</span><span class="sxs-lookup"><span data-stu-id="e1e03-139">The `try...with` construct is a separate expression from the `try...finally` expression.</span></span> <span data-ttu-id="e1e03-140">Por lo tanto, si el código requiere tanto un `with` bloque y un `finally` bloque, se deben anidar las dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="e1e03-140">Therefore, if your code requires both a `with` block and a `finally` block, you will have to nest the two expressions.</span></span>

>[!NOTE] 
<span data-ttu-id="e1e03-141">Puede usar `try...with` en flujos de trabajo asincrónicos y otras expresiones de cálculo, en el que caso una versión personalizada de la `try...with` se utiliza la expresión.</span><span class="sxs-lookup"><span data-stu-id="e1e03-141">You can use `try...with` in asynchronous workflows and other computation expressions, in which case a customized version of the `try...with` expression is used.</span></span> <span data-ttu-id="e1e03-142">Para obtener más información, consulte [flujos de trabajo asincrónicos](../asynchronous-workflows.md), y [expresiones de cálculo](../computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="e1e03-142">For more information, see [Asynchronous Workflows](../asynchronous-workflows.md), and [Computation Expressions](../computation-expressions.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="e1e03-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="e1e03-143">See Also</span></span>
[<span data-ttu-id="e1e03-144">Control de excepciones</span><span class="sxs-lookup"><span data-stu-id="e1e03-144">Exception Handling</span></span>](index.md)

[<span data-ttu-id="e1e03-145">Tipos de excepción</span><span class="sxs-lookup"><span data-stu-id="e1e03-145">Exception Types</span></span>](exception-types.md)

<span data-ttu-id="e1e03-146">[Exceptions: The `try...finally` Expression](the-try-finally-expression.md) (Excepciones: la expresión `try...finally`)</span><span class="sxs-lookup"><span data-stu-id="e1e03-146">[Exceptions: The `try...finally` Expression](the-try-finally-expression.md)</span></span>
