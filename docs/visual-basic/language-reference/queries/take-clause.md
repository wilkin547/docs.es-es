---
title: Take (Cláusula)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTake
helpviewer_keywords:
- Take statement [Visual Basic]
- queries [Visual Basic], Take
- Take clause [Visual Basic]
ms.assetid: 77bf87b2-1476-4456-957f-fee922fbad8c
ms.openlocfilehash: 3082954ef84560ccb70f7a47cd3532f622829392
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349643"
---
# <a name="take-clause-visual-basic"></a><span data-ttu-id="182ce-102">Take (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="182ce-102">Take Clause (Visual Basic)</span></span>
<span data-ttu-id="182ce-103">Devuelve un número especificado de elementos contiguos desde el principio de una colección.</span><span class="sxs-lookup"><span data-stu-id="182ce-103">Returns a specified number of contiguous elements from the start of a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="182ce-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="182ce-104">Syntax</span></span>  
  
```vb  
Take count  
```  
  
## <a name="parts"></a><span data-ttu-id="182ce-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="182ce-105">Parts</span></span>  
 `count`  
 <span data-ttu-id="182ce-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="182ce-106">Required.</span></span> <span data-ttu-id="182ce-107">Un valor o una expresión que se evalúa como el número de elementos de la secuencia que se va a devolver.</span><span class="sxs-lookup"><span data-stu-id="182ce-107">A value or an expression that evaluates to the number of elements of the sequence to return.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="182ce-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="182ce-108">Remarks</span></span>  
 <span data-ttu-id="182ce-109">La cláusula `Take` hace que una consulta incluya un número especificado de elementos contiguos desde el principio de una lista de resultados.</span><span class="sxs-lookup"><span data-stu-id="182ce-109">The `Take` clause causes a query to include a specified number of contiguous elements from the start of a results list.</span></span> <span data-ttu-id="182ce-110">El número de elementos que se van a incluir se especifica mediante el parámetro `count`.</span><span class="sxs-lookup"><span data-stu-id="182ce-110">The number of elements to include is specified by the `count` parameter.</span></span>  
  
 <span data-ttu-id="182ce-111">Puede usar la cláusula `Take` con la cláusula `Skip` para devolver un intervalo de datos de cualquier segmento de una consulta.</span><span class="sxs-lookup"><span data-stu-id="182ce-111">You can use the `Take` clause with the `Skip` clause to return a range of data from any segment of a query.</span></span> <span data-ttu-id="182ce-112">Para ello, pase el índice del primer elemento del intervalo a la cláusula `Skip` y el tamaño del intervalo a la cláusula `Take`.</span><span class="sxs-lookup"><span data-stu-id="182ce-112">To do this, pass the index of the first element of the range to the `Skip` clause and the size of the range to the `Take` clause.</span></span> <span data-ttu-id="182ce-113">En este caso, la cláusula `Take` debe especificarse después de la cláusula `Skip`.</span><span class="sxs-lookup"><span data-stu-id="182ce-113">In this case, the `Take` clause must be specified after the `Skip` clause.</span></span>  
  
 <span data-ttu-id="182ce-114">Al utilizar la cláusula `Take` en una consulta, puede que también tenga que asegurarse de que los resultados se devuelven en un orden que permita a la cláusula `Take` incluir los resultados deseados.</span><span class="sxs-lookup"><span data-stu-id="182ce-114">When you use the `Take` clause in a query, you may also need to ensure that the results are returned in an order that will enable the `Take` clause to include the intended results.</span></span> <span data-ttu-id="182ce-115">Para obtener más información sobre cómo ordenar los resultados de una consulta, vea [cláusula order by](../../../visual-basic/language-reference/queries/order-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="182ce-115">For more information about ordering query results, see [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
 <span data-ttu-id="182ce-116">Puede usar la cláusula `TakeWhile` para especificar que solo se devuelvan determinados elementos, en función de una condición proporcionada.</span><span class="sxs-lookup"><span data-stu-id="182ce-116">You can use the `TakeWhile` clause to specify that only certain elements be returned, depending on a supplied condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="182ce-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="182ce-117">Example</span></span>  
 <span data-ttu-id="182ce-118">En el ejemplo de código siguiente se usa la cláusula `Take` junto con la cláusula `Skip` para devolver datos de una consulta en páginas.</span><span class="sxs-lookup"><span data-stu-id="182ce-118">The following code example uses the `Take` clause together with the `Skip` clause to return data from a query in pages.</span></span> <span data-ttu-id="182ce-119">La función GetCustomers usa la cláusula `Skip` para omitir los clientes de la lista hasta el valor del índice de inicio proporcionado, y usa la cláusula `Take` para devolver una página de clientes a partir de ese valor de índice.</span><span class="sxs-lookup"><span data-stu-id="182ce-119">The GetCustomers function uses the `Skip` clause to bypass the customers in the list until the supplied starting index value, and uses the `Take` clause to return a page of customers starting from that index value.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="182ce-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="182ce-120">See also</span></span>

- [<span data-ttu-id="182ce-121">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="182ce-121">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="182ce-122">Consultas</span><span class="sxs-lookup"><span data-stu-id="182ce-122">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="182ce-123">Select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="182ce-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="182ce-124">From (cláusula)</span><span class="sxs-lookup"><span data-stu-id="182ce-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="182ce-125">Order By (cláusula)</span><span class="sxs-lookup"><span data-stu-id="182ce-125">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [<span data-ttu-id="182ce-126">Take While (cláusula)</span><span class="sxs-lookup"><span data-stu-id="182ce-126">Take While Clause</span></span>](../../../visual-basic/language-reference/queries/take-while-clause.md)
- [<span data-ttu-id="182ce-127">Skip (cláusula)</span><span class="sxs-lookup"><span data-stu-id="182ce-127">Skip Clause</span></span>](../../../visual-basic/language-reference/queries/skip-clause.md)
