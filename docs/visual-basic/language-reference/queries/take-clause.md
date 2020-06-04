---
title: Cláusula Take
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTake
helpviewer_keywords:
- Take statement [Visual Basic]
- queries [Visual Basic], Take
- Take clause [Visual Basic]
ms.assetid: 77bf87b2-1476-4456-957f-fee922fbad8c
ms.openlocfilehash: 25dd06905525a96bc1504f033eb4f19af6d454a2
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84359637"
---
# <a name="take-clause-visual-basic"></a><span data-ttu-id="f597e-102">Take (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f597e-102">Take Clause (Visual Basic)</span></span>
<span data-ttu-id="f597e-103">Devuelve un número especificado de elementos contiguos desde el principio de una colección.</span><span class="sxs-lookup"><span data-stu-id="f597e-103">Returns a specified number of contiguous elements from the start of a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f597e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f597e-104">Syntax</span></span>  
  
```vb  
Take count  
```  
  
## <a name="parts"></a><span data-ttu-id="f597e-105">Partes</span><span class="sxs-lookup"><span data-stu-id="f597e-105">Parts</span></span>  
 `count`  
 <span data-ttu-id="f597e-106">Necesario.</span><span class="sxs-lookup"><span data-stu-id="f597e-106">Required.</span></span> <span data-ttu-id="f597e-107">Un valor o una expresión que se evalúa como el número de elementos de la secuencia que se va a devolver.</span><span class="sxs-lookup"><span data-stu-id="f597e-107">A value or an expression that evaluates to the number of elements of the sequence to return.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f597e-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f597e-108">Remarks</span></span>  
 <span data-ttu-id="f597e-109">La `Take` cláusula hace que una consulta incluya un número especificado de elementos contiguos desde el principio de una lista de resultados.</span><span class="sxs-lookup"><span data-stu-id="f597e-109">The `Take` clause causes a query to include a specified number of contiguous elements from the start of a results list.</span></span> <span data-ttu-id="f597e-110">El parámetro especifica el número de elementos que se van a incluir `count` .</span><span class="sxs-lookup"><span data-stu-id="f597e-110">The number of elements to include is specified by the `count` parameter.</span></span>  
  
 <span data-ttu-id="f597e-111">Puede usar la `Take` cláusula con la `Skip` cláusula para devolver un intervalo de datos de cualquier segmento de una consulta.</span><span class="sxs-lookup"><span data-stu-id="f597e-111">You can use the `Take` clause with the `Skip` clause to return a range of data from any segment of a query.</span></span> <span data-ttu-id="f597e-112">Para ello, pase el índice del primer elemento del intervalo a la `Skip` cláusula y el tamaño del intervalo a la `Take` cláusula.</span><span class="sxs-lookup"><span data-stu-id="f597e-112">To do this, pass the index of the first element of the range to the `Skip` clause and the size of the range to the `Take` clause.</span></span> <span data-ttu-id="f597e-113">En este caso, la `Take` cláusula debe especificarse después de la `Skip` cláusula.</span><span class="sxs-lookup"><span data-stu-id="f597e-113">In this case, the `Take` clause must be specified after the `Skip` clause.</span></span>  
  
 <span data-ttu-id="f597e-114">Al utilizar la `Take` cláusula en una consulta, puede que también tenga que asegurarse de que los resultados se devuelven en un orden que permita `Take` a la cláusula incluir los resultados deseados.</span><span class="sxs-lookup"><span data-stu-id="f597e-114">When you use the `Take` clause in a query, you may also need to ensure that the results are returned in an order that will enable the `Take` clause to include the intended results.</span></span> <span data-ttu-id="f597e-115">Para obtener más información sobre cómo ordenar los resultados de una consulta, vea [cláusula order by](order-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="f597e-115">For more information about ordering query results, see [Order By Clause](order-by-clause.md).</span></span>  
  
 <span data-ttu-id="f597e-116">Puede usar la `TakeWhile` cláusula para especificar que solo se devuelvan determinados elementos, en función de una condición proporcionada.</span><span class="sxs-lookup"><span data-stu-id="f597e-116">You can use the `TakeWhile` clause to specify that only certain elements be returned, depending on a supplied condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f597e-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f597e-117">Example</span></span>  
 <span data-ttu-id="f597e-118">En el ejemplo de código siguiente `Take` se usa la cláusula junto con la `Skip` cláusula para devolver datos de una consulta en páginas.</span><span class="sxs-lookup"><span data-stu-id="f597e-118">The following code example uses the `Take` clause together with the `Skip` clause to return data from a query in pages.</span></span> <span data-ttu-id="f597e-119">La función GetCustomers usa la `Skip` cláusula para omitir los clientes de la lista hasta el valor del índice de inicio proporcionado y usa la `Take` cláusula para devolver una página de clientes a partir de ese valor de índice.</span><span class="sxs-lookup"><span data-stu-id="f597e-119">The GetCustomers function uses the `Skip` clause to bypass the customers in the list until the supplied starting index value, and uses the `Take` clause to return a page of customers starting from that index value.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="f597e-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f597e-120">See also</span></span>

- [<span data-ttu-id="f597e-121">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f597e-121">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="f597e-122">Consultas</span><span class="sxs-lookup"><span data-stu-id="f597e-122">Queries</span></span>](index.md)
- [<span data-ttu-id="f597e-123">Select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="f597e-123">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="f597e-124">Cláusula FROM</span><span class="sxs-lookup"><span data-stu-id="f597e-124">From Clause</span></span>](from-clause.md)
- [<span data-ttu-id="f597e-125">Cláusula Order By</span><span class="sxs-lookup"><span data-stu-id="f597e-125">Order By Clause</span></span>](order-by-clause.md)
- [<span data-ttu-id="f597e-126">Cláusula Take While</span><span class="sxs-lookup"><span data-stu-id="f597e-126">Take While Clause</span></span>](take-while-clause.md)
- [<span data-ttu-id="f597e-127">Cláusula Skip</span><span class="sxs-lookup"><span data-stu-id="f597e-127">Skip Clause</span></span>](skip-clause.md)
