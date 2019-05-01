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
ms.openlocfilehash: cb109eaf43fee19b77ac690492b85919c9d78301
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62054398"
---
# <a name="take-clause-visual-basic"></a><span data-ttu-id="61cb6-102">Take (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="61cb6-102">Take Clause (Visual Basic)</span></span>
<span data-ttu-id="61cb6-103">Devuelve un número especificado de elementos contiguos desde el principio de una colección.</span><span class="sxs-lookup"><span data-stu-id="61cb6-103">Returns a specified number of contiguous elements from the start of a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61cb6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="61cb6-104">Syntax</span></span>  
  
```  
Take count  
```  
  
## <a name="parts"></a><span data-ttu-id="61cb6-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="61cb6-105">Parts</span></span>  
 `count`  
 <span data-ttu-id="61cb6-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="61cb6-106">Required.</span></span> <span data-ttu-id="61cb6-107">Un valor o una expresión que se evalúa como el número de elementos de la secuencia que se va a devolver.</span><span class="sxs-lookup"><span data-stu-id="61cb6-107">A value or an expression that evaluates to the number of elements of the sequence to return.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="61cb6-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="61cb6-108">Remarks</span></span>  
 <span data-ttu-id="61cb6-109">El `Take` cláusula hace una consulta incluir un número especificado de elementos contiguos desde el principio de una lista de resultados.</span><span class="sxs-lookup"><span data-stu-id="61cb6-109">The `Take` clause causes a query to include a specified number of contiguous elements from the start of a results list.</span></span> <span data-ttu-id="61cb6-110">Especificado por el número de elementos que desee incluir el `count` parámetro.</span><span class="sxs-lookup"><span data-stu-id="61cb6-110">The number of elements to include is specified by the `count` parameter.</span></span>  
  
 <span data-ttu-id="61cb6-111">Puede usar el `Take` cláusula con el `Skip` cláusula para devolver un intervalo de datos de cualquier segmento de una consulta.</span><span class="sxs-lookup"><span data-stu-id="61cb6-111">You can use the `Take` clause with the `Skip` clause to return a range of data from any segment of a query.</span></span> <span data-ttu-id="61cb6-112">Para ello, pase el índice del primer elemento del intervalo para el `Skip` cláusula y el tamaño del intervalo para el `Take` cláusula.</span><span class="sxs-lookup"><span data-stu-id="61cb6-112">To do this, pass the index of the first element of the range to the `Skip` clause and the size of the range to the `Take` clause.</span></span> <span data-ttu-id="61cb6-113">En este caso, el `Take` cláusula debe especificarse después el `Skip` cláusula.</span><span class="sxs-lookup"><span data-stu-id="61cb6-113">In this case, the `Take` clause must be specified after the `Skip` clause.</span></span>  
  
 <span data-ttu-id="61cb6-114">Cuando se usa el `Take` cláusula en una consulta, es posible que también deberá asegurarse de que los resultados se devuelven en un orden que le permitirán la `Take` cláusula para incluir los resultados deseados.</span><span class="sxs-lookup"><span data-stu-id="61cb6-114">When you use the `Take` clause in a query, you may also need to ensure that the results are returned in an order that will enable the `Take` clause to include the intended results.</span></span> <span data-ttu-id="61cb6-115">Para obtener más información sobre cómo ordenar los resultados de la consulta, vea [cláusula Order By](../../../visual-basic/language-reference/queries/order-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="61cb6-115">For more information about ordering query results, see [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
 <span data-ttu-id="61cb6-116">Puede usar el `TakeWhile` cláusula para especificar que se devuelvan sólo ciertos elementos, según la condición proporcionada.</span><span class="sxs-lookup"><span data-stu-id="61cb6-116">You can use the `TakeWhile` clause to specify that only certain elements be returned, depending on a supplied condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="61cb6-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="61cb6-117">Example</span></span>  
 <span data-ttu-id="61cb6-118">El siguiente ejemplo de código utiliza el `Take` cláusula junto con el `Skip` cláusula para devolver datos de una consulta en las páginas.</span><span class="sxs-lookup"><span data-stu-id="61cb6-118">The following code example uses the `Take` clause together with the `Skip` clause to return data from a query in pages.</span></span> <span data-ttu-id="61cb6-119">El GetCustomers función usa el `Skip` cláusula para omitir los clientes en la lista hasta que la proporcionada a partir de índice valor y se usa el `Take` cláusula para devolver una página de clientes a partir de ese valor de índice.</span><span class="sxs-lookup"><span data-stu-id="61cb6-119">The GetCustomers function uses the `Skip` clause to bypass the customers in the list until the supplied starting index value, and uses the `Take` clause to return a page of customers starting from that index value.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="61cb6-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="61cb6-120">See also</span></span>

- [<span data-ttu-id="61cb6-121">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="61cb6-121">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="61cb6-122">Consultas</span><span class="sxs-lookup"><span data-stu-id="61cb6-122">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="61cb6-123">Select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="61cb6-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="61cb6-124">From (cláusula)</span><span class="sxs-lookup"><span data-stu-id="61cb6-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="61cb6-125">Order By (cláusula)</span><span class="sxs-lookup"><span data-stu-id="61cb6-125">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [<span data-ttu-id="61cb6-126">Take While (cláusula)</span><span class="sxs-lookup"><span data-stu-id="61cb6-126">Take While Clause</span></span>](../../../visual-basic/language-reference/queries/take-while-clause.md)
- [<span data-ttu-id="61cb6-127">Skip (cláusula)</span><span class="sxs-lookup"><span data-stu-id="61cb6-127">Skip Clause</span></span>](../../../visual-basic/language-reference/queries/skip-clause.md)
