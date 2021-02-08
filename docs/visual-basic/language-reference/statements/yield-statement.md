---
description: 'Más información acerca de: instrucción yield (Visual Basic)'
title: Instrucción Yield
ms.date: 07/20/2015
f1_keywords:
- vb.Yield
helpviewer_keywords:
- iterators, Yield statement [Visual Basic]
- iterators [Visual Basic]
- Yield statement [Visual Basic]
ms.assetid: f33126c5-d7c4-43e2-8e36-4ae3f0703d97
ms.openlocfilehash: cd07c271722a715beeddfddf660cec3e05127db8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787557"
---
# <a name="yield-statement-visual-basic"></a><span data-ttu-id="b4dde-103">Yield (Instrucción) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b4dde-103">Yield Statement (Visual Basic)</span></span>

<span data-ttu-id="b4dde-104">Envía el siguiente elemento de una colección a una `For Each...Next` instrucción.</span><span class="sxs-lookup"><span data-stu-id="b4dde-104">Sends the next element of a collection to a `For Each...Next` statement.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4dde-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b4dde-105">Syntax</span></span>  
  
```vb  
Yield expression  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4dde-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b4dde-106">Parameters</span></span>  
  
|<span data-ttu-id="b4dde-107">Término</span><span class="sxs-lookup"><span data-stu-id="b4dde-107">Term</span></span>|<span data-ttu-id="b4dde-108">Definición</span><span class="sxs-lookup"><span data-stu-id="b4dde-108">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="b4dde-109">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="b4dde-109">Required.</span></span> <span data-ttu-id="b4dde-110">Una expresión que se pueda convertir implícitamente al tipo de la función de iterador o `Get` descriptor de acceso que contiene la `Yield` instrucción.</span><span class="sxs-lookup"><span data-stu-id="b4dde-110">An expression that is implicitly convertible to the type of the iterator function or `Get` accessor that contains the `Yield` statement.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b4dde-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b4dde-111">Remarks</span></span>  

 <span data-ttu-id="b4dde-112">La `Yield` instrucción devuelve un elemento de una colección a la vez.</span><span class="sxs-lookup"><span data-stu-id="b4dde-112">The `Yield` statement returns one element of a collection at a time.</span></span> <span data-ttu-id="b4dde-113">La `Yield` instrucción se incluye en una función de iterador o `Get` descriptor de acceso, que realiza iteraciones personalizadas en una colección.</span><span class="sxs-lookup"><span data-stu-id="b4dde-113">The `Yield` statement is included in an iterator function or `Get` accessor, which perform custom iterations over a collection.</span></span>  
  
 <span data-ttu-id="b4dde-114">Utilice una función de iterador mediante un [... Instrucción Next](for-each-next-statement.md) o una consulta LINQ.</span><span class="sxs-lookup"><span data-stu-id="b4dde-114">You consume an iterator function by using a [For Each...Next Statement](for-each-next-statement.md) or a LINQ query.</span></span> <span data-ttu-id="b4dde-115">Cada iteración del `For Each` bucle llama a la función de iterador.</span><span class="sxs-lookup"><span data-stu-id="b4dde-115">Each iteration of the `For Each` loop calls the iterator function.</span></span> <span data-ttu-id="b4dde-116">Cuando `Yield` se alcanza una instrucción en la función de iterador, `expression` se devuelve y se conserva la ubicación actual en el código.</span><span class="sxs-lookup"><span data-stu-id="b4dde-116">When a `Yield` statement is reached in the iterator function, `expression` is returned, and the current location in code is retained.</span></span> <span data-ttu-id="b4dde-117">La ejecución se reinicia desde esa ubicación la próxima vez que se llama a la función del iterador.</span><span class="sxs-lookup"><span data-stu-id="b4dde-117">Execution is restarted from that location the next time that the iterator function is called.</span></span>  
  
 <span data-ttu-id="b4dde-118">Debe existir una conversión implícita del tipo de `expression` en la `Yield` instrucción al tipo de valor devuelto del iterador.</span><span class="sxs-lookup"><span data-stu-id="b4dde-118">An implicit conversion must exist from the type of `expression` in the `Yield` statement to the return type of the iterator.</span></span>  
  
 <span data-ttu-id="b4dde-119">Puede usar una `Exit Function` instrucción o `Return` para finalizar la iteración.</span><span class="sxs-lookup"><span data-stu-id="b4dde-119">You can use an `Exit Function` or `Return` statement to end the iteration.</span></span>  
  
 <span data-ttu-id="b4dde-120">"Yield" no es una palabra reservada y tiene un significado especial solo cuando se usa en una `Iterator` función o un `Get` descriptor de acceso.</span><span class="sxs-lookup"><span data-stu-id="b4dde-120">"Yield" is not a reserved word and has special meaning only when it is used in an `Iterator` function or `Get` accessor.</span></span>  
  
 <span data-ttu-id="b4dde-121">Para obtener más información sobre las funciones de iterador y los `Get` descriptores de acceso, vea [iteradores](../../programming-guide/concepts/iterators.md).</span><span class="sxs-lookup"><span data-stu-id="b4dde-121">For more information about iterator functions and `Get` accessors, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="iterator-functions-and-get-accessors"></a><span data-ttu-id="b4dde-122">Funciones de iterador y obtener descriptores de acceso</span><span class="sxs-lookup"><span data-stu-id="b4dde-122">Iterator Functions and Get Accessors</span></span>  

 <span data-ttu-id="b4dde-123">La declaración de una función de iterador o `Get` descriptor de acceso debe cumplir los siguientes requisitos:</span><span class="sxs-lookup"><span data-stu-id="b4dde-123">The declaration of an iterator function or `Get` accessor must meet the following requirements:</span></span>  
  
- <span data-ttu-id="b4dde-124">Debe incluir un modificador de [iterador](../modifiers/iterator.md) .</span><span class="sxs-lookup"><span data-stu-id="b4dde-124">It must include an [Iterator](../modifiers/iterator.md) modifier.</span></span>  
  
- <span data-ttu-id="b4dde-125">El tipo de valor devuelto debe ser <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator> o <xref:System.Collections.Generic.IEnumerator%601>.</span><span class="sxs-lookup"><span data-stu-id="b4dde-125">The return type must be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
- <span data-ttu-id="b4dde-126">No puede tener ningún `ByRef` parámetro.</span><span class="sxs-lookup"><span data-stu-id="b4dde-126">It cannot have any `ByRef` parameters.</span></span>  
  
 <span data-ttu-id="b4dde-127">Una función de iterador no puede aparecer en un evento, un constructor de instancia, un constructor estático o un destructor estático.</span><span class="sxs-lookup"><span data-stu-id="b4dde-127">An iterator function cannot occur in an event, instance constructor, static constructor, or static destructor.</span></span>  
  
 <span data-ttu-id="b4dde-128">Una función de iterador puede ser una función anónima.</span><span class="sxs-lookup"><span data-stu-id="b4dde-128">An iterator function can be an anonymous function.</span></span> <span data-ttu-id="b4dde-129">Para obtener más información, consulta [Iteradores](../../programming-guide/concepts/iterators.md).</span><span class="sxs-lookup"><span data-stu-id="b4dde-129">For more information, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="exception-handling"></a><span data-ttu-id="b4dde-130">Control de excepciones</span><span class="sxs-lookup"><span data-stu-id="b4dde-130">Exception Handling</span></span>  

 <span data-ttu-id="b4dde-131">Una `Yield` instrucción puede estar dentro `Try` de un bloque de instrucciones [try... Detectar... Finally](try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b4dde-131">A `Yield` statement can be inside a `Try` block of a [Try...Catch...Finally Statement](try-catch-finally-statement.md).</span></span> <span data-ttu-id="b4dde-132">Un `Try` bloque que tiene una `Yield` instrucción puede tener `Catch` bloques y puede tener un `Finally` bloque.</span><span class="sxs-lookup"><span data-stu-id="b4dde-132">A `Try` block that has a `Yield` statement can have `Catch` blocks, and can have a `Finally` block.</span></span>  
  
 <span data-ttu-id="b4dde-133">Una `Yield` instrucción no puede estar dentro de un `Catch` bloque o un `Finally` bloque.</span><span class="sxs-lookup"><span data-stu-id="b4dde-133">A `Yield` statement cannot be inside a `Catch` block or a `Finally` block.</span></span>  
  
 <span data-ttu-id="b4dde-134">Si el `For Each` cuerpo (fuera de la función de iterador) produce una excepción, `Catch` no se ejecuta un bloque de la función de iterador, pero `Finally` se ejecuta un bloque en la función de iterador.</span><span class="sxs-lookup"><span data-stu-id="b4dde-134">If the `For Each` body (outside of the iterator function) throws an exception, a `Catch` block in the iterator function is not executed, but a `Finally` block in the iterator function is executed.</span></span> <span data-ttu-id="b4dde-135">Un `Catch` bloque dentro de una función de iterador solo detecta las excepciones que se producen dentro de la función de iterador.</span><span class="sxs-lookup"><span data-stu-id="b4dde-135">A `Catch` block inside an iterator function catches only exceptions that occur inside the iterator function.</span></span>  
  
## <a name="technical-implementation"></a><span data-ttu-id="b4dde-136">Implementación técnica</span><span class="sxs-lookup"><span data-stu-id="b4dde-136">Technical Implementation</span></span>  

 <span data-ttu-id="b4dde-137">El código siguiente devuelve un `IEnumerable (Of String)` a partir de una función de iterador y, a continuación, recorre en iteración los elementos de `IEnumerable (Of String)` .</span><span class="sxs-lookup"><span data-stu-id="b4dde-137">The following code returns an `IEnumerable (Of String)` from an iterator function and then iterates through the elements of the `IEnumerable (Of String)`.</span></span>  
  
```vb  
Dim elements As IEnumerable(Of String) = MyIteratorFunction()  
    …  
For Each element As String In elements  
Next  
```  
  
 <span data-ttu-id="b4dde-138">La llamada a `MyIteratorFunction` no ejecuta el cuerpo de la función.</span><span class="sxs-lookup"><span data-stu-id="b4dde-138">The call to `MyIteratorFunction` doesn't execute the body of the function.</span></span> <span data-ttu-id="b4dde-139">En su lugar, la llamada devuelve un valor `IEnumerable(Of String)` en la variable `elements`.</span><span class="sxs-lookup"><span data-stu-id="b4dde-139">Instead the call returns an `IEnumerable(Of String)` into the `elements` variable.</span></span>  
  
 <span data-ttu-id="b4dde-140">En una iteración del bucle `For Each`, se llama al método <xref:System.Collections.IEnumerator.MoveNext%2A> para `elements`.</span><span class="sxs-lookup"><span data-stu-id="b4dde-140">On an iteration of the `For Each` loop, the <xref:System.Collections.IEnumerator.MoveNext%2A> method is called for `elements`.</span></span> <span data-ttu-id="b4dde-141">Esta llamada ejecuta el cuerpo de `MyIteratorFunction` hasta que se alcanza la siguiente instrucción `Yield`.</span><span class="sxs-lookup"><span data-stu-id="b4dde-141">This call executes the body of `MyIteratorFunction` until the next `Yield` statement is reached.</span></span> <span data-ttu-id="b4dde-142">La `Yield` instrucción devuelve una expresión que determina no solo el valor de la `element` variable para su consumo por parte del cuerpo del bucle, sino también la <xref:System.Collections.Generic.IEnumerator%601.Current%2A> propiedad de los elementos, que es `IEnumerable (Of String)` .</span><span class="sxs-lookup"><span data-stu-id="b4dde-142">The `Yield` statement returns an expression that determines not only the value of the `element` variable for consumption by the loop body but also the <xref:System.Collections.Generic.IEnumerator%601.Current%2A> property of elements, which is an `IEnumerable (Of String)`.</span></span>  
  
 <span data-ttu-id="b4dde-143">En cada iteración subsiguiente del bucle `For Each`, la ejecución del cuerpo del iterador continúa desde donde se dejó, deteniéndose de nuevo al alcanzar una instrucción `Yield`.</span><span class="sxs-lookup"><span data-stu-id="b4dde-143">On each subsequent iteration of the `For Each` loop, the execution of the iterator body continues from where it left off, again stopping when it reaches a `Yield` statement.</span></span> <span data-ttu-id="b4dde-144">El `For Each` bucle se completa cuando se alcanza el final de la función de iterador o una `Return` `Exit Function` instrucción o.</span><span class="sxs-lookup"><span data-stu-id="b4dde-144">The `For Each` loop completes when the end of the iterator function or a `Return` or `Exit Function` statement is reached.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4dde-145">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b4dde-145">Example</span></span>  

 <span data-ttu-id="b4dde-146">El ejemplo siguiente tiene una `Yield` instrucción que está dentro [de un... Siguiente](for-next-statement.md) bucle.</span><span class="sxs-lookup"><span data-stu-id="b4dde-146">The following example has a `Yield` statement that is inside a [For…Next](for-next-statement.md) loop.</span></span> <span data-ttu-id="b4dde-147">Cada iteración del cuerpo de la instrucción [for each](for-each-next-statement.md) en `Main` crea una llamada a la `Power` función de iterador.</span><span class="sxs-lookup"><span data-stu-id="b4dde-147">Each iteration of the [For Each](for-each-next-statement.md) statement body in `Main` creates a call to the `Power` iterator function.</span></span> <span data-ttu-id="b4dde-148">Cada llamada a la función de iterador prosigue con la siguiente ejecución de la instrucción `Yield`, que se produce durante la siguiente iteración del bucle `For…Next`.</span><span class="sxs-lookup"><span data-stu-id="b4dde-148">Each call to the iterator function proceeds to the next execution of the `Yield` statement, which occurs during the next iteration of the `For…Next` loop.</span></span>  
  
 <span data-ttu-id="b4dde-149">El tipo de valor devuelto del método iterador es <xref:System.Collections.Generic.IEnumerable%601> , un tipo de interfaz de iterador.</span><span class="sxs-lookup"><span data-stu-id="b4dde-149">The return type of the iterator method is <xref:System.Collections.Generic.IEnumerable%601>, an iterator interface type.</span></span> <span data-ttu-id="b4dde-150">Cuando se llama al método iterador, este devuelve un objeto enumerable que contiene las potencias de un número.</span><span class="sxs-lookup"><span data-stu-id="b4dde-150">When the iterator method is called, it returns an enumerable object that contains the powers of a number.</span></span>  
  
 [!code-vb[VbVbalrStatements#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#98)]  
  
## <a name="example"></a><span data-ttu-id="b4dde-151">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b4dde-151">Example</span></span>  

 <span data-ttu-id="b4dde-152">En el ejemplo siguiente se muestra un descriptor de acceso `Get` que es un iterador.</span><span class="sxs-lookup"><span data-stu-id="b4dde-152">The following example demonstrates a `Get` accessor that is an iterator.</span></span> <span data-ttu-id="b4dde-153">La declaración de propiedad incluye un `Iterator` modificador.</span><span class="sxs-lookup"><span data-stu-id="b4dde-153">The property declaration includes an `Iterator` modifier.</span></span>  
  
 [!code-vb[VbVbalrStatements#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#99)]  
  
 <span data-ttu-id="b4dde-154">Para obtener más ejemplos, vea [iteradores](../../programming-guide/concepts/iterators.md).</span><span class="sxs-lookup"><span data-stu-id="b4dde-154">For additional examples, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4dde-155">Vea también</span><span class="sxs-lookup"><span data-stu-id="b4dde-155">See also</span></span>

- [<span data-ttu-id="b4dde-156">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="b4dde-156">Statements</span></span>](index.md)
