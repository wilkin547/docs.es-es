---
title: 'Excepciones: Expresión try...with'
description: Aprenda a usar la F# instrucción ' try... with ' expresión para el control de excepciones.
ms.date: 05/16/2016
ms.openlocfilehash: e4d615086a93e26b76cca460e797659ca13792b5
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630249"
---
# <a name="exceptions-the-trywith-expression"></a><span data-ttu-id="15e66-103">Excepciones: Expresión try...with</span><span class="sxs-lookup"><span data-stu-id="15e66-103">Exceptions: The try...with Expression</span></span>

<span data-ttu-id="15e66-104">En este tema se `try...with` describe la expresión, la expresión que se utiliza para el control F# de excepciones en el lenguaje.</span><span class="sxs-lookup"><span data-stu-id="15e66-104">This topic describes the `try...with` expression, the expression that is used for exception handling in the F# language.</span></span>

## <a name="syntax"></a><span data-ttu-id="15e66-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="15e66-105">Syntax</span></span>

```fsharp
try
    expression1
with
| pattern1 -> expression2
| pattern2 -> expression3
...
```

## <a name="remarks"></a><span data-ttu-id="15e66-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="15e66-106">Remarks</span></span>

<span data-ttu-id="15e66-107">La `try...with` expresión se utiliza para controlar las excepciones F#en.</span><span class="sxs-lookup"><span data-stu-id="15e66-107">The `try...with` expression is used to handle exceptions in F#.</span></span> <span data-ttu-id="15e66-108">Es similar a la `try...catch` instrucción de. C#</span><span class="sxs-lookup"><span data-stu-id="15e66-108">It is similar to the `try...catch` statement in C#.</span></span> <span data-ttu-id="15e66-109">En la sintaxis anterior, el código de *expression1* podría generar una excepción.</span><span class="sxs-lookup"><span data-stu-id="15e66-109">In the preceding syntax, the code in *expression1* might generate an exception.</span></span> <span data-ttu-id="15e66-110">La `try...with` expresión devuelve un valor.</span><span class="sxs-lookup"><span data-stu-id="15e66-110">The `try...with` expression returns a value.</span></span> <span data-ttu-id="15e66-111">Si no se produce ninguna excepción, toda la expresión devuelve el valor de *expression1*.</span><span class="sxs-lookup"><span data-stu-id="15e66-111">If no exception is thrown, the whole expression returns the value of *expression1*.</span></span> <span data-ttu-id="15e66-112">Si se produce una excepción, cada *patrón* se compara a su vez con la excepción, y para el primer patrón coincidente, se ejecuta la *expresión*correspondiente, conocida como *controlador de excepciones*, para esa bifurcación y la expresión general Devuelve el valor de la expresión en ese controlador de excepciones.</span><span class="sxs-lookup"><span data-stu-id="15e66-112">If an exception is thrown, each *pattern* is compared in turn with the exception, and for the first matching pattern, the corresponding *expression*, known as the *exception handler*, for that branch is executed, and the overall expression returns the value of the expression in that exception handler.</span></span> <span data-ttu-id="15e66-113">Si ningún patrón coincide, la excepción propaga la pila de llamadas hasta que se encuentra un controlador coincidente.</span><span class="sxs-lookup"><span data-stu-id="15e66-113">If no pattern matches, the exception propagates up the call stack until a matching handler is found.</span></span> <span data-ttu-id="15e66-114">Los tipos de los valores devueltos por cada expresión en los controladores de excepciones deben coincidir con el tipo devuelto `try` de la expresión en el bloque.</span><span class="sxs-lookup"><span data-stu-id="15e66-114">The types of the values returned from each expression in the exception handlers must match the type returned from the expression in the `try` block.</span></span>

<span data-ttu-id="15e66-115">Con frecuencia, el hecho de que se produzca un error también significa que no hay ningún valor válido que se pueda devolver desde las expresiones de cada controlador de excepciones.</span><span class="sxs-lookup"><span data-stu-id="15e66-115">Frequently, the fact that an error occurred also means that there is no valid value that can be returned from the expressions in each exception handler.</span></span> <span data-ttu-id="15e66-116">Un patrón frecuente es que el tipo de la expresión sea un tipo de opción.</span><span class="sxs-lookup"><span data-stu-id="15e66-116">A frequent pattern is to have the type of the expression be an option type.</span></span> <span data-ttu-id="15e66-117">En el ejemplo de código siguiente se muestra este patrón.</span><span class="sxs-lookup"><span data-stu-id="15e66-117">The following code example illustrates this pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5601.fs)]

<span data-ttu-id="15e66-118">Las excepciones pueden ser excepciones de .NET o pueden ser F# excepciones.</span><span class="sxs-lookup"><span data-stu-id="15e66-118">Exceptions can be .NET exceptions, or they can be F# exceptions.</span></span> <span data-ttu-id="15e66-119">Puede definir F# excepciones mediante la `exception` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="15e66-119">You can define F# exceptions by using the `exception` keyword.</span></span>

<span data-ttu-id="15e66-120">Puede usar diversos patrones para filtrar según el tipo de excepción y otras condiciones; las opciones se resumen en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="15e66-120">You can use a variety of patterns to filter on the exception type and other conditions; the options are summarized in the following table.</span></span>

|<span data-ttu-id="15e66-121">Modelo</span><span class="sxs-lookup"><span data-stu-id="15e66-121">Pattern</span></span>|<span data-ttu-id="15e66-122">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="15e66-122">Description</span></span>|
|-------|-----------|
|<span data-ttu-id="15e66-123">:?</span><span class="sxs-lookup"><span data-stu-id="15e66-123">:?</span></span> <span data-ttu-id="15e66-124">*exception-type*</span><span class="sxs-lookup"><span data-stu-id="15e66-124">*exception-type*</span></span>|<span data-ttu-id="15e66-125">Coincide con el tipo de excepción de .NET especificado.</span><span class="sxs-lookup"><span data-stu-id="15e66-125">Matches the specified .NET exception type.</span></span>|
|<span data-ttu-id="15e66-126">:?</span><span class="sxs-lookup"><span data-stu-id="15e66-126">:?</span></span> <span data-ttu-id="15e66-127">*tipo de excepción* como *identificador*</span><span class="sxs-lookup"><span data-stu-id="15e66-127">*exception-type* as *identifier*</span></span>|<span data-ttu-id="15e66-128">Coincide con el tipo de excepción de .NET especificado, pero asigna a la excepción un valor con nombre.</span><span class="sxs-lookup"><span data-stu-id="15e66-128">Matches the specified .NET exception type, but gives the exception a named value.</span></span>|
|<span data-ttu-id="15e66-129">*nombre de excepción* (*argumentos*)</span><span class="sxs-lookup"><span data-stu-id="15e66-129">*exception-name*(*arguments*)</span></span>|<span data-ttu-id="15e66-130">Coincide con F# un tipo de excepción y enlaza los argumentos.</span><span class="sxs-lookup"><span data-stu-id="15e66-130">Matches an F# exception type and binds the arguments.</span></span>|
|<span data-ttu-id="15e66-131">*identifier*</span><span class="sxs-lookup"><span data-stu-id="15e66-131">*identifier*</span></span>|<span data-ttu-id="15e66-132">Coincide con cualquier excepción y enlaza el nombre al objeto de excepción.</span><span class="sxs-lookup"><span data-stu-id="15e66-132">Matches any exception and binds the name to the exception object.</span></span> <span data-ttu-id="15e66-133">Equivalente a **:? System. Exception como**_identificador_</span><span class="sxs-lookup"><span data-stu-id="15e66-133">Equivalent to **:? System.Exception as**_identifier_</span></span>|
|<span data-ttu-id="15e66-134">*identificador* cuando la *condición*</span><span class="sxs-lookup"><span data-stu-id="15e66-134">*identifier* when *condition*</span></span>|<span data-ttu-id="15e66-135">Coincide con cualquier excepción si la condición es true.</span><span class="sxs-lookup"><span data-stu-id="15e66-135">Matches any exception if the condition is true.</span></span>|

## <a name="examples"></a><span data-ttu-id="15e66-136">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="15e66-136">Examples</span></span>

<span data-ttu-id="15e66-137">En los siguientes ejemplos de código se muestra el uso de los distintos patrones de controlador de excepciones.</span><span class="sxs-lookup"><span data-stu-id="15e66-137">The following code examples illustrate the use of the various exception handler patterns.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5602.fs)]

> [!NOTE]
> <span data-ttu-id="15e66-138">La `try...with` construcción es una expresión independiente de la `try...finally` expresión.</span><span class="sxs-lookup"><span data-stu-id="15e66-138">The `try...with` construct is a separate expression from the `try...finally` expression.</span></span> <span data-ttu-id="15e66-139">Por lo tanto, si el código requiere `with` un bloque y `finally` un bloque, tendrá que anidar las dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="15e66-139">Therefore, if your code requires both a `with` block and a `finally` block, you will have to nest the two expressions.</span></span>

> [!NOTE]
> <span data-ttu-id="15e66-140">Puede usar `try...with` en flujos de trabajo asincrónicos y otras expresiones de cálculo, en cuyo caso se utiliza una versión personalizada `try...with` de la expresión.</span><span class="sxs-lookup"><span data-stu-id="15e66-140">You can use `try...with` in asynchronous workflows and other computation expressions, in which case a customized version of the `try...with` expression is used.</span></span> <span data-ttu-id="15e66-141">Para obtener más información, vea [flujos de trabajo asincrónicos](../asynchronous-workflows.md)y expresiones de [cálculo](../computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="15e66-141">For more information, see [Asynchronous Workflows](../asynchronous-workflows.md), and [Computation Expressions](../computation-expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="15e66-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="15e66-142">See also</span></span>

- [<span data-ttu-id="15e66-143">Control de excepciones</span><span class="sxs-lookup"><span data-stu-id="15e66-143">Exception Handling</span></span>](index.md)
- [<span data-ttu-id="15e66-144">Tipos de excepción</span><span class="sxs-lookup"><span data-stu-id="15e66-144">Exception Types</span></span>](exception-types.md)
- [<span data-ttu-id="15e66-145">Excepciones: La `try...finally` expresión</span><span class="sxs-lookup"><span data-stu-id="15e66-145">Exceptions: The `try...finally` Expression</span></span>](the-try-finally-expression.md)
