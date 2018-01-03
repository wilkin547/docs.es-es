---
title: "Yield (Instrucción) (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Yield
helpviewer_keywords:
- iterators, Yield statement [Visual Basic]
- iterators [Visual Basic]
- Yield statement [Visual Basic]
ms.assetid: f33126c5-d7c4-43e2-8e36-4ae3f0703d97
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0bc2f5c2dca1fbd6039f10ddd6204673f60a679d
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2017
---
# <a name="yield-statement-visual-basic"></a><span data-ttu-id="6ad16-102">Yield (Instrucción) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6ad16-102">Yield Statement (Visual Basic)</span></span>
<span data-ttu-id="6ad16-103">Envía el siguiente elemento de una colección para un `For Each...Next` instrucción.</span><span class="sxs-lookup"><span data-stu-id="6ad16-103">Sends the next element of a collection to a `For Each...Next` statement.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ad16-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6ad16-104">Syntax</span></span>  
  
```  
Yield expression  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6ad16-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6ad16-105">Parameters</span></span>  
  
|<span data-ttu-id="6ad16-106">Término</span><span class="sxs-lookup"><span data-stu-id="6ad16-106">Term</span></span>|<span data-ttu-id="6ad16-107">Definición</span><span class="sxs-lookup"><span data-stu-id="6ad16-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="6ad16-108">Requerido.</span><span class="sxs-lookup"><span data-stu-id="6ad16-108">Required.</span></span> <span data-ttu-id="6ad16-109">Una expresión que sea implícitamente convertible al tipo de la función del iterador o `Get` descriptor de acceso que contiene el `Yield` instrucción.</span><span class="sxs-lookup"><span data-stu-id="6ad16-109">An expression that is implicitly convertible to the type of the iterator function or `Get` accessor that contains the `Yield` statement.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6ad16-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6ad16-110">Remarks</span></span>  
 <span data-ttu-id="6ad16-111">El `Yield` instrucción devuelve un elemento de una colección a la vez.</span><span class="sxs-lookup"><span data-stu-id="6ad16-111">The `Yield` statement returns one element of a collection at a time.</span></span> <span data-ttu-id="6ad16-112">El `Yield` instrucción se incluye en una función de iterador o `Get` descriptor de acceso, que realizan iteraciones personalizadas en una colección.</span><span class="sxs-lookup"><span data-stu-id="6ad16-112">The `Yield` statement is included in an iterator function or `Get` accessor, which perform custom iterations over a collection.</span></span>  
  
 <span data-ttu-id="6ad16-113">Utilizar una función de iterador mediante un [For Each... Next (instrucción)](../../../visual-basic/language-reference/statements/for-each-next-statement.md) o una consulta LINQ.</span><span class="sxs-lookup"><span data-stu-id="6ad16-113">You consume an iterator function by using a [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md) or a LINQ query.</span></span> <span data-ttu-id="6ad16-114">Cada iteración de la `For Each` bucle llama a la función de iterador.</span><span class="sxs-lookup"><span data-stu-id="6ad16-114">Each iteration of the `For Each` loop calls the iterator function.</span></span> <span data-ttu-id="6ad16-115">Cuando un `Yield` se alcanza la instrucción en la función de iterador, `expression` se devuelve, y se conserva la ubicación actual en el código.</span><span class="sxs-lookup"><span data-stu-id="6ad16-115">When a `Yield` statement is reached in the iterator function, `expression` is returned, and the current location in code is retained.</span></span> <span data-ttu-id="6ad16-116">La ejecución se reinicia desde esa ubicación la próxima vez que se llama a la función del iterador.</span><span class="sxs-lookup"><span data-stu-id="6ad16-116">Execution is restarted from that location the next time that the iterator function is called.</span></span>  
  
 <span data-ttu-id="6ad16-117">Debe existir una conversión implícita del tipo de `expression` en el `Yield` instrucción para el tipo de valor devuelto del iterador.</span><span class="sxs-lookup"><span data-stu-id="6ad16-117">An implicit conversion must exist from the type of `expression` in the `Yield` statement to the return type of the iterator.</span></span>  
  
 <span data-ttu-id="6ad16-118">Puede usar un `Exit Function` o `Return` instrucción para finalizar la iteración.</span><span class="sxs-lookup"><span data-stu-id="6ad16-118">You can use an `Exit Function` or `Return` statement to end the iteration.</span></span>  
  
 <span data-ttu-id="6ad16-119">"Producción" no es una palabra reservada y tiene un significado especial solo cuando se usa en un `Iterator` función o `Get` descriptor de acceso.</span><span class="sxs-lookup"><span data-stu-id="6ad16-119">"Yield" is not a reserved word and has special meaning only when it is used in an `Iterator` function or `Get` accessor.</span></span>  
  
 <span data-ttu-id="6ad16-120">Para obtener más información acerca de las funciones de iterador y `Get` descriptores de acceso, consulte [iteradores](../../programming-guide/concepts/iterators.md).</span><span class="sxs-lookup"><span data-stu-id="6ad16-120">For more information about iterator functions and `Get` accessors, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="iterator-functions-and-get-accessors"></a><span data-ttu-id="6ad16-121">Funciones de iterador y descriptores de acceso Get</span><span class="sxs-lookup"><span data-stu-id="6ad16-121">Iterator Functions and Get Accessors</span></span>  
 <span data-ttu-id="6ad16-122">La declaración de una función de iterador o `Get` descriptor de acceso debe cumplir los siguientes requisitos:</span><span class="sxs-lookup"><span data-stu-id="6ad16-122">The declaration of an iterator function or `Get` accessor must meet the following requirements:</span></span>  
  
-   <span data-ttu-id="6ad16-123">Debe incluir un [iterador](../../../visual-basic/language-reference/modifiers/iterator.md) modificador.</span><span class="sxs-lookup"><span data-stu-id="6ad16-123">It must include an [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md) modifier.</span></span>  
  
-   <span data-ttu-id="6ad16-124">El tipo de valor devuelto debe ser <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator> o <xref:System.Collections.Generic.IEnumerator%601>.</span><span class="sxs-lookup"><span data-stu-id="6ad16-124">The return type must be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
-   <span data-ttu-id="6ad16-125">No puede tener ningún `ByRef` parámetros.</span><span class="sxs-lookup"><span data-stu-id="6ad16-125">It cannot have any `ByRef` parameters.</span></span>  
  
 <span data-ttu-id="6ad16-126">Una función de iterador no se puede producir en un evento, un constructor de instancia, un constructor estático o un destructor estático.</span><span class="sxs-lookup"><span data-stu-id="6ad16-126">An iterator function cannot occur in an event, instance constructor, static constructor, or static destructor.</span></span>  
  
 <span data-ttu-id="6ad16-127">Una función de iterador puede ser una función anónima.</span><span class="sxs-lookup"><span data-stu-id="6ad16-127">An iterator function can be an anonymous function.</span></span> <span data-ttu-id="6ad16-128">Para obtener más información, consulta [Iteradores](../../programming-guide/concepts/iterators.md).</span><span class="sxs-lookup"><span data-stu-id="6ad16-128">For more information, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="exception-handling"></a><span data-ttu-id="6ad16-129">Control de excepciones</span><span class="sxs-lookup"><span data-stu-id="6ad16-129">Exception Handling</span></span>  
 <span data-ttu-id="6ad16-130">A `Yield` instrucción puede estar dentro de un `Try` bloquear de un [intente... Catch... Finally (instrucción)](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="6ad16-130">A `Yield` statement can be inside a `Try` block of a [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span> <span data-ttu-id="6ad16-131">A `Try` bloque con un `Yield` instrucción puede tener `Catch` bloquea y puede tener un `Finally` bloque.</span><span class="sxs-lookup"><span data-stu-id="6ad16-131">A `Try` block that has a `Yield` statement can have `Catch` blocks, and can have a `Finally` block.</span></span>  
  
 <span data-ttu-id="6ad16-132">A `Yield` instrucción no puede estar dentro de un `Catch` bloque o una `Finally` bloque.</span><span class="sxs-lookup"><span data-stu-id="6ad16-132">A `Yield` statement cannot be inside a `Catch` block or a `Finally` block.</span></span>  
  
 <span data-ttu-id="6ad16-133">Si el `For Each` cuerpo (fuera de la función del iterador) produce una excepción, un `Catch` no se ejecuta el bloque de la función del iterador, pero un `Finally` se ejecuta el bloque de la función del iterador.</span><span class="sxs-lookup"><span data-stu-id="6ad16-133">If the `For Each` body (outside of the iterator function) throws an exception, a `Catch` block in the iterator function is not executed, but a `Finally` block in the iterator function is executed.</span></span> <span data-ttu-id="6ad16-134">Un `Catch` bloque dentro de una función de iterador captura solo las excepciones que se producen dentro de la función de iterador.</span><span class="sxs-lookup"><span data-stu-id="6ad16-134">A `Catch` block inside an iterator function catches only exceptions that occur inside the iterator function.</span></span>  
  
## <a name="technical-implementation"></a><span data-ttu-id="6ad16-135">Implementación técnica</span><span class="sxs-lookup"><span data-stu-id="6ad16-135">Technical Implementation</span></span>  
 <span data-ttu-id="6ad16-136">El código siguiente devuelve una `IEnumerable (Of String)` desde una función de iterador y, a continuación, recorre en iteración los elementos de la `IEnumerable (Of String)`.</span><span class="sxs-lookup"><span data-stu-id="6ad16-136">The following code returns an `IEnumerable (Of String)` from an iterator function and then iterates through the elements of the `IEnumerable (Of String)`.</span></span>  
  
```vb  
Dim elements As IEnumerable(Of String) = MyIteratorFunction()  
    …  
For Each element As String In elements  
Next  
```  
  
 <span data-ttu-id="6ad16-137">La llamada a `MyIteratorFunction` no ejecuta el cuerpo de la función.</span><span class="sxs-lookup"><span data-stu-id="6ad16-137">The call to `MyIteratorFunction` doesn't execute the body of the function.</span></span> <span data-ttu-id="6ad16-138">En su lugar, la llamada devuelve un valor `IEnumerable(Of String)` en la variable `elements`.</span><span class="sxs-lookup"><span data-stu-id="6ad16-138">Instead the call returns an `IEnumerable(Of String)` into the `elements` variable.</span></span>  
  
 <span data-ttu-id="6ad16-139">En una iteración del bucle `For Each`, se llama al método <xref:System.Collections.IEnumerator.MoveNext%2A> para `elements`.</span><span class="sxs-lookup"><span data-stu-id="6ad16-139">On an iteration of the `For Each` loop, the <xref:System.Collections.IEnumerator.MoveNext%2A> method is called for `elements`.</span></span> <span data-ttu-id="6ad16-140">Esta llamada ejecuta el cuerpo de `MyIteratorFunction` hasta que se alcanza la siguiente instrucción `Yield`.</span><span class="sxs-lookup"><span data-stu-id="6ad16-140">This call executes the body of `MyIteratorFunction` until the next `Yield` statement is reached.</span></span> <span data-ttu-id="6ad16-141">El `Yield` instrucción devuelve una expresión que determina no solo el valor de la `element` variable para su uso por el cuerpo del bucle, sino también la <xref:System.Collections.Generic.IEnumerator%601.Current%2A> propiedad de elementos, que es un `IEnumerable (Of String)`.</span><span class="sxs-lookup"><span data-stu-id="6ad16-141">The `Yield` statement returns an expression that determines not only the value of the `element` variable for consumption by the loop body but also the <xref:System.Collections.Generic.IEnumerator%601.Current%2A> property of elements, which is an `IEnumerable (Of String)`.</span></span>  
  
 <span data-ttu-id="6ad16-142">En cada iteración subsiguiente del bucle `For Each`, la ejecución del cuerpo del iterador continúa desde donde se dejó, deteniéndose de nuevo al alcanzar una instrucción `Yield`.</span><span class="sxs-lookup"><span data-stu-id="6ad16-142">On each subsequent iteration of the `For Each` loop, the execution of the iterator body continues from where it left off, again stopping when it reaches a `Yield` statement.</span></span> <span data-ttu-id="6ad16-143">El `For Each` bucle completa cuando el final de la función de iterador o `Return` o `Exit Function` se alcanza la instrucción.</span><span class="sxs-lookup"><span data-stu-id="6ad16-143">The `For Each` loop completes when the end of the iterator function or a `Return` or `Exit Function` statement is reached.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6ad16-144">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6ad16-144">Example</span></span>  
 <span data-ttu-id="6ad16-145">El siguiente ejemplo tiene un `Yield` que esté dentro de un [para... Siguiente](../../../visual-basic/language-reference/statements/for-next-statement.md) bucle.</span><span class="sxs-lookup"><span data-stu-id="6ad16-145">The following example has a `Yield` statement that is inside a [For…Next](../../../visual-basic/language-reference/statements/for-next-statement.md) loop.</span></span> <span data-ttu-id="6ad16-146">Cada iteración de la [For Each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) cuerpo de instrucción en `Main` crea una llamada a la `Power` función del iterador.</span><span class="sxs-lookup"><span data-stu-id="6ad16-146">Each iteration of the [For Each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) statement body in `Main` creates a call to the `Power` iterator function.</span></span> <span data-ttu-id="6ad16-147">Cada llamada a la función de iterador prosigue con la siguiente ejecución de la instrucción `Yield`, que se produce durante la siguiente iteración del bucle `For…Next`.</span><span class="sxs-lookup"><span data-stu-id="6ad16-147">Each call to the iterator function proceeds to the next execution of the `Yield` statement, which occurs during the next iteration of the `For…Next` loop.</span></span>  
  
 <span data-ttu-id="6ad16-148">El tipo de valor devuelto del método iterador es <xref:System.Collections.Generic.IEnumerable%601>, un tipo de interfaz de iterador.</span><span class="sxs-lookup"><span data-stu-id="6ad16-148">The return type of the iterator method is <xref:System.Collections.Generic.IEnumerable%601>, an iterator interface type.</span></span> <span data-ttu-id="6ad16-149">Cuando se llama al método iterador, este devuelve un objeto enumerable que contiene las potencias de un número.</span><span class="sxs-lookup"><span data-stu-id="6ad16-149">When the iterator method is called, it returns an enumerable object that contains the powers of a number.</span></span>  
  
 [!code-vb[VbVbalrStatements#98](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/yield-statement_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="6ad16-150">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6ad16-150">Example</span></span>  
 <span data-ttu-id="6ad16-151">En el ejemplo siguiente se muestra un descriptor de acceso `Get` que es un iterador.</span><span class="sxs-lookup"><span data-stu-id="6ad16-151">The following example demonstrates a `Get` accessor that is an iterator.</span></span> <span data-ttu-id="6ad16-152">La declaración de propiedad incluye un `Iterator` modificador.</span><span class="sxs-lookup"><span data-stu-id="6ad16-152">The property declaration includes an `Iterator` modifier.</span></span>  
  
 [!code-vb[VbVbalrStatements#99](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/yield-statement_2.vb)]  
  
 <span data-ttu-id="6ad16-153">Para obtener ejemplos adicionales, vea [iteradores](../../programming-guide/concepts/iterators.md).</span><span class="sxs-lookup"><span data-stu-id="6ad16-153">For additional examples, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ad16-154">Vea también</span><span class="sxs-lookup"><span data-stu-id="6ad16-154">See Also</span></span>  
 [<span data-ttu-id="6ad16-155">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="6ad16-155">Statements</span></span>](../../../visual-basic/language-reference/statements/index.md)
