---
title: Iterador (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Iterator
helpviewer_keywords: Iterator keyword [Visual Basic]
ms.assetid: 69cb0b04-ac87-49d0-bcfe-810c0d60daff
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 503d586c0515b4cb53f8ec5656e5fe765cc094a7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="iterator-visual-basic"></a><span data-ttu-id="bfde3-102">Iterador (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bfde3-102">Iterator (Visual Basic)</span></span>
<span data-ttu-id="bfde3-103">Especifica que una función o `Get` descriptor de acceso es un iterador.</span><span class="sxs-lookup"><span data-stu-id="bfde3-103">Specifies that a function or `Get` accessor is an iterator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bfde3-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bfde3-104">Remarks</span></span>  
 <span data-ttu-id="bfde3-105">Un *iterador* realiza una iteración personalizada en una colección.</span><span class="sxs-lookup"><span data-stu-id="bfde3-105">An *iterator* performs a custom iteration over a collection.</span></span> <span data-ttu-id="bfde3-106">Un iterador utiliza la [producen](../../../visual-basic/language-reference/statements/yield-statement.md) instrucción para devolver cada elemento en la colección a la vez.</span><span class="sxs-lookup"><span data-stu-id="bfde3-106">An iterator uses the [Yield](../../../visual-basic/language-reference/statements/yield-statement.md) statement to return each element in the collection one at a time.</span></span> <span data-ttu-id="bfde3-107">Cuando un `Yield` se alcanza la instrucción, se conserva la ubicación actual en el código.</span><span class="sxs-lookup"><span data-stu-id="bfde3-107">When a `Yield` statement is reached, the current location in code is retained.</span></span> <span data-ttu-id="bfde3-108">La ejecución se reinicia desde esa ubicación la próxima vez que se llama a la función del iterador.</span><span class="sxs-lookup"><span data-stu-id="bfde3-108">Execution is restarted from that location the next time that the iterator function is called.</span></span>  
  
 <span data-ttu-id="bfde3-109">Un iterador se puede implementar como una función o como un `Get` descriptor de acceso de una definición de propiedad.</span><span class="sxs-lookup"><span data-stu-id="bfde3-109">An iterator can be implemented as a function or as a `Get` accessor of a property definition.</span></span> <span data-ttu-id="bfde3-110">El `Iterator` modificador aparece en la declaración de la función de iterador o `Get` descriptor de acceso.</span><span class="sxs-lookup"><span data-stu-id="bfde3-110">The `Iterator` modifier appears in the declaration of the iterator function or `Get` accessor.</span></span>  
  
 <span data-ttu-id="bfde3-111">Llamar a un iterador de código de cliente mediante un [For Each... Next (instrucción)](../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="bfde3-111">You call an iterator from client code by using a [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span></span>  
  
 <span data-ttu-id="bfde3-112">El tipo de valor devuelto de una función de iterador o `Get` descriptor de acceso puede ser <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, o <xref:System.Collections.Generic.IEnumerator%601>.</span><span class="sxs-lookup"><span data-stu-id="bfde3-112">The return type of an iterator function or `Get` accessor can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
 <span data-ttu-id="bfde3-113">Un iterador no puede tener ningún `ByRef` parámetros.</span><span class="sxs-lookup"><span data-stu-id="bfde3-113">An iterator cannot have any `ByRef` parameters.</span></span>  
  
 <span data-ttu-id="bfde3-114">Un iterador no puede aparecer en un evento, un constructor de instancia, un constructor estático o un destructor estático.</span><span class="sxs-lookup"><span data-stu-id="bfde3-114">An iterator cannot occur in an event, instance constructor, static constructor, or static destructor.</span></span>  
  
 <span data-ttu-id="bfde3-115">Un iterador puede ser una función anónima.</span><span class="sxs-lookup"><span data-stu-id="bfde3-115">An iterator can be an anonymous function.</span></span> <span data-ttu-id="bfde3-116">Para más información, vea [Iteradores](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span><span class="sxs-lookup"><span data-stu-id="bfde3-116">For more information, see [Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span></span>  
  
 <span data-ttu-id="bfde3-117">Para obtener más información sobre los iteradores, vea [Iteradores](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span><span class="sxs-lookup"><span data-stu-id="bfde3-117">For more information about iterators, see [Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span></span>  
  
## <a name="usage"></a><span data-ttu-id="bfde3-118">Uso</span><span class="sxs-lookup"><span data-stu-id="bfde3-118">Usage</span></span>  
 <span data-ttu-id="bfde3-119">El modificador `Iterator` se puede utilizar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="bfde3-119">The `Iterator` modifier can be used in these contexts:</span></span>  
  
-   [<span data-ttu-id="bfde3-120">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="bfde3-120">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [<span data-ttu-id="bfde3-121">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="bfde3-121">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="example"></a><span data-ttu-id="bfde3-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bfde3-122">Example</span></span>  
 <span data-ttu-id="bfde3-123">En el ejemplo siguiente se muestra una función de iterador.</span><span class="sxs-lookup"><span data-stu-id="bfde3-123">The following example demonstrates an iterator function.</span></span> <span data-ttu-id="bfde3-124">La función de iterador tiene una `Yield` que esté dentro de un [para... Siguiente](../../../visual-basic/language-reference/statements/for-next-statement.md) bucle.</span><span class="sxs-lookup"><span data-stu-id="bfde3-124">The iterator function has a `Yield` statement that is inside a [For…Next](../../../visual-basic/language-reference/statements/for-next-statement.md) loop.</span></span> <span data-ttu-id="bfde3-125">Cada iteración de la [For Each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) cuerpo de instrucción en `Main` crea una llamada a la `Power` función del iterador.</span><span class="sxs-lookup"><span data-stu-id="bfde3-125">Each iteration of the [For Each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) statement body in `Main` creates a call to the `Power` iterator function.</span></span> <span data-ttu-id="bfde3-126">Cada llamada a la función de iterador prosigue con la siguiente ejecución de la instrucción `Yield`, que se produce durante la siguiente iteración del bucle `For…Next`.</span><span class="sxs-lookup"><span data-stu-id="bfde3-126">Each call to the iterator function proceeds to the next execution of the `Yield` statement, which occurs during the next iteration of the `For…Next` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#98](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/iterator_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="bfde3-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bfde3-127">Example</span></span>  
 <span data-ttu-id="bfde3-128">En el ejemplo siguiente se muestra un descriptor de acceso `Get` que es un iterador.</span><span class="sxs-lookup"><span data-stu-id="bfde3-128">The following example demonstrates a `Get` accessor that is an iterator.</span></span> <span data-ttu-id="bfde3-129">El `Iterator` modificador está en la declaración de propiedad.</span><span class="sxs-lookup"><span data-stu-id="bfde3-129">The `Iterator` modifier is in the property declaration.</span></span>  
  
 [!code-vb[VbVbalrStatements#99](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/iterator_2.vb)]  
  
 <span data-ttu-id="bfde3-130">Para obtener ejemplos adicionales, vea [iteradores](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span><span class="sxs-lookup"><span data-stu-id="bfde3-130">For additional examples, see [Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfde3-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="bfde3-131">See Also</span></span>  
 <xref:System.Runtime.CompilerServices.IteratorStateMachineAttribute>  
 [<span data-ttu-id="bfde3-132">Iteradores</span><span class="sxs-lookup"><span data-stu-id="bfde3-132">Iterators</span></span>](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)  
 [<span data-ttu-id="bfde3-133">Yield (instrucción)</span><span class="sxs-lookup"><span data-stu-id="bfde3-133">Yield Statement</span></span>](../../../visual-basic/language-reference/statements/yield-statement.md)
