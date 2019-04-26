---
title: Iterador (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Iterator
helpviewer_keywords:
- Iterator keyword [Visual Basic]
ms.assetid: 69cb0b04-ac87-49d0-bcfe-810c0d60daff
ms.openlocfilehash: 499949d1f4c20e1f465355bd076ba39f1496779b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61920723"
---
# <a name="iterator-visual-basic"></a><span data-ttu-id="5255a-102">Iterador (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5255a-102">Iterator (Visual Basic)</span></span>
<span data-ttu-id="5255a-103">Especifica que una función o `Get` descriptor de acceso es un iterador.</span><span class="sxs-lookup"><span data-stu-id="5255a-103">Specifies that a function or `Get` accessor is an iterator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5255a-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5255a-104">Remarks</span></span>  
 <span data-ttu-id="5255a-105">Un *iterador* realiza una iteración personalizada en una colección.</span><span class="sxs-lookup"><span data-stu-id="5255a-105">An *iterator* performs a custom iteration over a collection.</span></span> <span data-ttu-id="5255a-106">Un iterador usa la [Yield](../../../visual-basic/language-reference/statements/yield-statement.md) instrucción para devolver cada elemento de la colección a la vez.</span><span class="sxs-lookup"><span data-stu-id="5255a-106">An iterator uses the [Yield](../../../visual-basic/language-reference/statements/yield-statement.md) statement to return each element in the collection one at a time.</span></span> <span data-ttu-id="5255a-107">Cuando un `Yield` se alcanza la instrucción, se conserva la ubicación actual en el código.</span><span class="sxs-lookup"><span data-stu-id="5255a-107">When a `Yield` statement is reached, the current location in code is retained.</span></span> <span data-ttu-id="5255a-108">La ejecución se reinicia desde esa ubicación la próxima vez que se llama a la función del iterador.</span><span class="sxs-lookup"><span data-stu-id="5255a-108">Execution is restarted from that location the next time that the iterator function is called.</span></span>  
  
 <span data-ttu-id="5255a-109">Un iterador se puede implementar como una función o como un `Get` descriptor de acceso de una definición de propiedad.</span><span class="sxs-lookup"><span data-stu-id="5255a-109">An iterator can be implemented as a function or as a `Get` accessor of a property definition.</span></span> <span data-ttu-id="5255a-110">El `Iterator` modificador aparece en la declaración de la función de iterador o `Get` descriptor de acceso.</span><span class="sxs-lookup"><span data-stu-id="5255a-110">The `Iterator` modifier appears in the declaration of the iterator function or `Get` accessor.</span></span>  
  
 <span data-ttu-id="5255a-111">Llamar a un iterador desde código de cliente mediante un [For Each... Instrucción Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="5255a-111">You call an iterator from client code by using a [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span></span>  
  
 <span data-ttu-id="5255a-112">El tipo de valor devuelto de una función de iterador o `Get` descriptor de acceso puede ser <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, o <xref:System.Collections.Generic.IEnumerator%601>.</span><span class="sxs-lookup"><span data-stu-id="5255a-112">The return type of an iterator function or `Get` accessor can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
 <span data-ttu-id="5255a-113">Un iterador no puede tener ninguno `ByRef` parámetros.</span><span class="sxs-lookup"><span data-stu-id="5255a-113">An iterator cannot have any `ByRef` parameters.</span></span>  
  
 <span data-ttu-id="5255a-114">Un iterador no puede aparecer en un evento, un constructor de instancia, un constructor estático o un destructor estático.</span><span class="sxs-lookup"><span data-stu-id="5255a-114">An iterator cannot occur in an event, instance constructor, static constructor, or static destructor.</span></span>  
  
 <span data-ttu-id="5255a-115">Un iterador puede ser una función anónima.</span><span class="sxs-lookup"><span data-stu-id="5255a-115">An iterator can be an anonymous function.</span></span> <span data-ttu-id="5255a-116">Para obtener más información, consulta [Iteradores](../../programming-guide/concepts/iterators.md).</span><span class="sxs-lookup"><span data-stu-id="5255a-116">For more information, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="usage"></a><span data-ttu-id="5255a-117">Uso</span><span class="sxs-lookup"><span data-stu-id="5255a-117">Usage</span></span>  
 <span data-ttu-id="5255a-118">El modificador `Iterator` se puede utilizar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="5255a-118">The `Iterator` modifier can be used in these contexts:</span></span>  
  
-   [<span data-ttu-id="5255a-119">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="5255a-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [<span data-ttu-id="5255a-120">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="5255a-120">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="example"></a><span data-ttu-id="5255a-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5255a-121">Example</span></span>  
 <span data-ttu-id="5255a-122">El ejemplo siguiente muestra una función de iterador.</span><span class="sxs-lookup"><span data-stu-id="5255a-122">The following example demonstrates an iterator function.</span></span> <span data-ttu-id="5255a-123">La función de iterador tiene una `Yield` instrucción que está dentro de un [para... Siguiente](../../../visual-basic/language-reference/statements/for-next-statement.md) bucle.</span><span class="sxs-lookup"><span data-stu-id="5255a-123">The iterator function has a `Yield` statement that is inside a [For…Next](../../../visual-basic/language-reference/statements/for-next-statement.md) loop.</span></span> <span data-ttu-id="5255a-124">Cada iteración de la [para cada](../../../visual-basic/language-reference/statements/for-each-next-statement.md) cuerpo de instrucción en `Main` crea una llamada a la `Power` función de iterador.</span><span class="sxs-lookup"><span data-stu-id="5255a-124">Each iteration of the [For Each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) statement body in `Main` creates a call to the `Power` iterator function.</span></span> <span data-ttu-id="5255a-125">Cada llamada a la función de iterador prosigue con la siguiente ejecución de la instrucción `Yield`, que se produce durante la siguiente iteración del bucle `For…Next`.</span><span class="sxs-lookup"><span data-stu-id="5255a-125">Each call to the iterator function proceeds to the next execution of the `Yield` statement, which occurs during the next iteration of the `For…Next` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#98)]  
  
## <a name="example"></a><span data-ttu-id="5255a-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5255a-126">Example</span></span>  
 <span data-ttu-id="5255a-127">En el ejemplo siguiente se muestra un descriptor de acceso `Get` que es un iterador.</span><span class="sxs-lookup"><span data-stu-id="5255a-127">The following example demonstrates a `Get` accessor that is an iterator.</span></span> <span data-ttu-id="5255a-128">El `Iterator` modificador está en la declaración de propiedad.</span><span class="sxs-lookup"><span data-stu-id="5255a-128">The `Iterator` modifier is in the property declaration.</span></span>  
  
 [!code-vb[VbVbalrStatements#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#99)]  
  
 <span data-ttu-id="5255a-129">Para obtener ejemplos adicionales, consulte [iteradores](../../programming-guide/concepts/iterators.md).</span><span class="sxs-lookup"><span data-stu-id="5255a-129">For additional examples, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5255a-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="5255a-130">See also</span></span>

- <xref:System.Runtime.CompilerServices.IteratorStateMachineAttribute>
- [<span data-ttu-id="5255a-131">Iteradores</span><span class="sxs-lookup"><span data-stu-id="5255a-131">Iterators</span></span>](../../programming-guide/concepts/iterators.md)
- [<span data-ttu-id="5255a-132">Yield (instrucción)</span><span class="sxs-lookup"><span data-stu-id="5255a-132">Yield Statement</span></span>](../../../visual-basic/language-reference/statements/yield-statement.md)
