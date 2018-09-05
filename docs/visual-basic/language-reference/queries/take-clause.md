---
title: Take (Cláusula, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTake
helpviewer_keywords:
- Take statement [Visual Basic]
- queries [Visual Basic], Take
- Take clause [Visual Basic]
ms.assetid: 77bf87b2-1476-4456-957f-fee922fbad8c
ms.openlocfilehash: bfaccf470d93a6a72451e7ad8b41e8dbb1171c71
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43673527"
---
# <a name="take-clause-visual-basic"></a><span data-ttu-id="e6458-102">Take (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e6458-102">Take Clause (Visual Basic)</span></span>
<span data-ttu-id="e6458-103">Devuelve un número especificado de elementos contiguos desde el principio de una colección.</span><span class="sxs-lookup"><span data-stu-id="e6458-103">Returns a specified number of contiguous elements from the start of a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6458-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e6458-104">Syntax</span></span>  
  
```  
Take count  
```  
  
## <a name="parts"></a><span data-ttu-id="e6458-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="e6458-105">Parts</span></span>  
 `count`  
 <span data-ttu-id="e6458-106">Requerido.</span><span class="sxs-lookup"><span data-stu-id="e6458-106">Required.</span></span> <span data-ttu-id="e6458-107">Un valor o una expresión que se evalúa como el número de elementos de la secuencia que se va a devolver.</span><span class="sxs-lookup"><span data-stu-id="e6458-107">A value or an expression that evaluates to the number of elements of the sequence to return.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e6458-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e6458-108">Remarks</span></span>  
 <span data-ttu-id="e6458-109">El `Take` cláusula hace una consulta incluir un número especificado de elementos contiguos desde el principio de una lista de resultados.</span><span class="sxs-lookup"><span data-stu-id="e6458-109">The `Take` clause causes a query to include a specified number of contiguous elements from the start of a results list.</span></span> <span data-ttu-id="e6458-110">Especificado por el número de elementos que desee incluir el `count` parámetro.</span><span class="sxs-lookup"><span data-stu-id="e6458-110">The number of elements to include is specified by the `count` parameter.</span></span>  
  
 <span data-ttu-id="e6458-111">Puede usar el `Take` cláusula con el `Skip` cláusula para devolver un intervalo de datos de cualquier segmento de una consulta.</span><span class="sxs-lookup"><span data-stu-id="e6458-111">You can use the `Take` clause with the `Skip` clause to return a range of data from any segment of a query.</span></span> <span data-ttu-id="e6458-112">Para ello, pase el índice del primer elemento del intervalo para el `Skip` cláusula y el tamaño del intervalo para el `Take` cláusula.</span><span class="sxs-lookup"><span data-stu-id="e6458-112">To do this, pass the index of the first element of the range to the `Skip` clause and the size of the range to the `Take` clause.</span></span> <span data-ttu-id="e6458-113">En este caso, el `Take` cláusula debe especificarse después el `Skip` cláusula.</span><span class="sxs-lookup"><span data-stu-id="e6458-113">In this case, the `Take` clause must be specified after the `Skip` clause.</span></span>  
  
 <span data-ttu-id="e6458-114">Cuando se usa el `Take` cláusula en una consulta, es posible que también deberá asegurarse de que los resultados se devuelven en un orden que le permitirán la `Take` cláusula para incluir los resultados deseados.</span><span class="sxs-lookup"><span data-stu-id="e6458-114">When you use the `Take` clause in a query, you may also need to ensure that the results are returned in an order that will enable the `Take` clause to include the intended results.</span></span> <span data-ttu-id="e6458-115">Para obtener más información sobre cómo ordenar los resultados de la consulta, vea [cláusula Order By](../../../visual-basic/language-reference/queries/order-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="e6458-115">For more information about ordering query results, see [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
 <span data-ttu-id="e6458-116">Puede usar el `TakeWhile` cláusula para especificar que se devuelvan sólo ciertos elementos, según la condición proporcionada.</span><span class="sxs-lookup"><span data-stu-id="e6458-116">You can use the `TakeWhile` clause to specify that only certain elements be returned, depending on a supplied condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6458-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e6458-117">Example</span></span>  
 <span data-ttu-id="e6458-118">El siguiente ejemplo de código utiliza el `Take` cláusula junto con el `Skip` cláusula para devolver datos de una consulta en las páginas.</span><span class="sxs-lookup"><span data-stu-id="e6458-118">The following code example uses the `Take` clause together with the `Skip` clause to return data from a query in pages.</span></span> <span data-ttu-id="e6458-119">El GetCustomers función usa el `Skip` cláusula para omitir los clientes en la lista hasta que la proporcionada a partir de índice valor y se usa el `Take` cláusula para devolver una página de clientes a partir de ese valor de índice.</span><span class="sxs-lookup"><span data-stu-id="e6458-119">The GetCustomers function uses the `Skip` clause to bypass the customers in the list until the supplied starting index value, and uses the `Take` clause to return a page of customers starting from that index value.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#1](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/take-clause_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="e6458-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="e6458-120">See Also</span></span>  
 [<span data-ttu-id="e6458-121">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e6458-121">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="e6458-122">Consultas</span><span class="sxs-lookup"><span data-stu-id="e6458-122">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)  
 [<span data-ttu-id="e6458-123">Select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="e6458-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="e6458-124">From (cláusula)</span><span class="sxs-lookup"><span data-stu-id="e6458-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="e6458-125">Order By (cláusula)</span><span class="sxs-lookup"><span data-stu-id="e6458-125">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 [<span data-ttu-id="e6458-126">Take While (cláusula)</span><span class="sxs-lookup"><span data-stu-id="e6458-126">Take While Clause</span></span>](../../../visual-basic/language-reference/queries/take-while-clause.md)  
 [<span data-ttu-id="e6458-127">Skip (cláusula)</span><span class="sxs-lookup"><span data-stu-id="e6458-127">Skip Clause</span></span>](../../../visual-basic/language-reference/queries/skip-clause.md)
