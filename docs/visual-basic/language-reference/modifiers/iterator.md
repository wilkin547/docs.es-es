---
description: 'Más información acerca de: iterator (Visual Basic)'
title: Iterator
ms.date: 07/20/2015
f1_keywords:
- vb.Iterator
helpviewer_keywords:
- Iterator keyword [Visual Basic]
ms.assetid: 69cb0b04-ac87-49d0-bcfe-810c0d60daff
ms.openlocfilehash: 7a3329ba23a3f2487343b332f3bb9c4b19c36496
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99730530"
---
# <a name="iterator-visual-basic"></a><span data-ttu-id="091cb-103">Iterador (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="091cb-103">Iterator (Visual Basic)</span></span>

<span data-ttu-id="091cb-104">Especifica que una función o un `Get` descriptor de acceso es un iterador.</span><span class="sxs-lookup"><span data-stu-id="091cb-104">Specifies that a function or `Get` accessor is an iterator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="091cb-105">Observaciones</span><span class="sxs-lookup"><span data-stu-id="091cb-105">Remarks</span></span>  

 <span data-ttu-id="091cb-106">Un *iterador* realiza una iteración personalizada en una colección.</span><span class="sxs-lookup"><span data-stu-id="091cb-106">An *iterator* performs a custom iteration over a collection.</span></span> <span data-ttu-id="091cb-107">Un iterador usa la instrucción [yield](../statements/yield-statement.md) para devolver cada elemento de la colección de uno en uno.</span><span class="sxs-lookup"><span data-stu-id="091cb-107">An iterator uses the [Yield](../statements/yield-statement.md) statement to return each element in the collection one at a time.</span></span> <span data-ttu-id="091cb-108">Cuando `Yield` se alcanza una instrucción, se conserva la ubicación actual en el código.</span><span class="sxs-lookup"><span data-stu-id="091cb-108">When a `Yield` statement is reached, the current location in code is retained.</span></span> <span data-ttu-id="091cb-109">La ejecución se reinicia desde esa ubicación la próxima vez que se llama a la función del iterador.</span><span class="sxs-lookup"><span data-stu-id="091cb-109">Execution is restarted from that location the next time that the iterator function is called.</span></span>  
  
 <span data-ttu-id="091cb-110">Un iterador se puede implementar como una función o como un `Get` descriptor de acceso de una definición de propiedad.</span><span class="sxs-lookup"><span data-stu-id="091cb-110">An iterator can be implemented as a function or as a `Get` accessor of a property definition.</span></span> <span data-ttu-id="091cb-111">El `Iterator` modificador aparece en la declaración de la función de iterador o el `Get` descriptor de acceso.</span><span class="sxs-lookup"><span data-stu-id="091cb-111">The `Iterator` modifier appears in the declaration of the iterator function or `Get` accessor.</span></span>  
  
 <span data-ttu-id="091cb-112">Se llama a un iterador desde el código de cliente mediante un método [for each... Instrucción siguiente](../statements/for-each-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="091cb-112">You call an iterator from client code by using a [For Each...Next Statement](../statements/for-each-next-statement.md).</span></span>  
  
 <span data-ttu-id="091cb-113">El tipo de valor devuelto de una función de iterador o `Get` descriptor de acceso puede ser <xref:System.Collections.IEnumerable> , <xref:System.Collections.Generic.IEnumerable%601> , <xref:System.Collections.IEnumerator> o <xref:System.Collections.Generic.IEnumerator%601> .</span><span class="sxs-lookup"><span data-stu-id="091cb-113">The return type of an iterator function or `Get` accessor can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
 <span data-ttu-id="091cb-114">Un iterador no puede tener ningún `ByRef` parámetro.</span><span class="sxs-lookup"><span data-stu-id="091cb-114">An iterator cannot have any `ByRef` parameters.</span></span>  
  
 <span data-ttu-id="091cb-115">Un iterador no puede aparecer en un evento, un constructor de instancia, un constructor estático o un destructor estático.</span><span class="sxs-lookup"><span data-stu-id="091cb-115">An iterator cannot occur in an event, instance constructor, static constructor, or static destructor.</span></span>  
  
 <span data-ttu-id="091cb-116">Un iterador puede ser una función anónima.</span><span class="sxs-lookup"><span data-stu-id="091cb-116">An iterator can be an anonymous function.</span></span> <span data-ttu-id="091cb-117">Para obtener más información, consulta [Iteradores](../../programming-guide/concepts/iterators.md).</span><span class="sxs-lookup"><span data-stu-id="091cb-117">For more information, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="usage"></a><span data-ttu-id="091cb-118">Uso</span><span class="sxs-lookup"><span data-stu-id="091cb-118">Usage</span></span>  

 <span data-ttu-id="091cb-119">El modificador `Iterator` se puede utilizar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="091cb-119">The `Iterator` modifier can be used in these contexts:</span></span>  
  
- [<span data-ttu-id="091cb-120">Instrucción Function</span><span class="sxs-lookup"><span data-stu-id="091cb-120">Function Statement</span></span>](../statements/function-statement.md)  
  
- [<span data-ttu-id="091cb-121">Property Statement</span><span class="sxs-lookup"><span data-stu-id="091cb-121">Property Statement</span></span>](../statements/property-statement.md)  
  
## <a name="example"></a><span data-ttu-id="091cb-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="091cb-122">Example</span></span>  

 <span data-ttu-id="091cb-123">En el ejemplo siguiente se muestra una función de iterador.</span><span class="sxs-lookup"><span data-stu-id="091cb-123">The following example demonstrates an iterator function.</span></span> <span data-ttu-id="091cb-124">La función de iterador tiene una `Yield` instrucción que está dentro de un [... Siguiente](../statements/for-next-statement.md) bucle.</span><span class="sxs-lookup"><span data-stu-id="091cb-124">The iterator function has a `Yield` statement that is inside a [For…Next](../statements/for-next-statement.md) loop.</span></span> <span data-ttu-id="091cb-125">Cada iteración del cuerpo de la instrucción [for each](../statements/for-each-next-statement.md) en `Main` crea una llamada a la `Power` función de iterador.</span><span class="sxs-lookup"><span data-stu-id="091cb-125">Each iteration of the [For Each](../statements/for-each-next-statement.md) statement body in `Main` creates a call to the `Power` iterator function.</span></span> <span data-ttu-id="091cb-126">Cada llamada a la función de iterador prosigue con la siguiente ejecución de la instrucción `Yield`, que se produce durante la siguiente iteración del bucle `For…Next`.</span><span class="sxs-lookup"><span data-stu-id="091cb-126">Each call to the iterator function proceeds to the next execution of the `Yield` statement, which occurs during the next iteration of the `For…Next` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#98)]  
  
## <a name="example"></a><span data-ttu-id="091cb-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="091cb-127">Example</span></span>  

 <span data-ttu-id="091cb-128">En el ejemplo siguiente se muestra un descriptor de acceso `Get` que es un iterador.</span><span class="sxs-lookup"><span data-stu-id="091cb-128">The following example demonstrates a `Get` accessor that is an iterator.</span></span> <span data-ttu-id="091cb-129">El `Iterator` modificador está en la declaración de propiedad.</span><span class="sxs-lookup"><span data-stu-id="091cb-129">The `Iterator` modifier is in the property declaration.</span></span>  
  
 [!code-vb[VbVbalrStatements#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#99)]  
  
 <span data-ttu-id="091cb-130">Para obtener más ejemplos, vea [iteradores](../../programming-guide/concepts/iterators.md).</span><span class="sxs-lookup"><span data-stu-id="091cb-130">For additional examples, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="091cb-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="091cb-131">See also</span></span>

- <xref:System.Runtime.CompilerServices.IteratorStateMachineAttribute>
- [<span data-ttu-id="091cb-132">Iteradores</span><span class="sxs-lookup"><span data-stu-id="091cb-132">Iterators</span></span>](../../programming-guide/concepts/iterators.md)
- [<span data-ttu-id="091cb-133">Instrucción Yield</span><span class="sxs-lookup"><span data-stu-id="091cb-133">Yield Statement</span></span>](../statements/yield-statement.md)
