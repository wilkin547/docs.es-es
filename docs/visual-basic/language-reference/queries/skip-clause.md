---
title: Skip (Cláusula, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySkip
helpviewer_keywords:
- queries [Visual Basic], Skip
- Skip statement [Visual Basic]
- Skip clause [Visual Basic]
ms.assetid: f00eb172-3907-4c43-9745-d8546ab86234
ms.openlocfilehash: db2d79596895505ddaa7778e831082a94c7ad44e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58821106"
---
# <a name="skip-clause-visual-basic"></a><span data-ttu-id="b68d8-102">Skip (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b68d8-102">Skip Clause (Visual Basic)</span></span>
<span data-ttu-id="b68d8-103">Omite un número especificado de elementos de una colección y, a continuación, devuelve los elementos restantes.</span><span class="sxs-lookup"><span data-stu-id="b68d8-103">Bypasses a specified number of elements in a collection and then returns the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b68d8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b68d8-104">Syntax</span></span>  
  
```  
Skip count  
```  
  
## <a name="parts"></a><span data-ttu-id="b68d8-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="b68d8-105">Parts</span></span>  
 `count`  
 <span data-ttu-id="b68d8-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="b68d8-106">Required.</span></span> <span data-ttu-id="b68d8-107">Un valor o una expresión que se evalúa como el número de elementos de la secuencia que se va a omitir.</span><span class="sxs-lookup"><span data-stu-id="b68d8-107">A value or an expression that evaluates to the number of elements of the sequence to skip.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b68d8-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b68d8-108">Remarks</span></span>  
 <span data-ttu-id="b68d8-109">El `Skip` cláusula hace una consulta para omitir los elementos al principio de una lista de resultados y devolver los elementos restantes.</span><span class="sxs-lookup"><span data-stu-id="b68d8-109">The `Skip` clause causes a query to bypass elements at the beginning of a results list and return the remaining elements.</span></span> <span data-ttu-id="b68d8-110">Identifica el número de elementos para omitir la `count` parámetro.</span><span class="sxs-lookup"><span data-stu-id="b68d8-110">The number of elements to skip is identified by the `count` parameter.</span></span>  
  
 <span data-ttu-id="b68d8-111">Puede usar el `Skip` cláusula con el `Take` cláusula para devolver un intervalo de datos de cualquier segmento de una consulta.</span><span class="sxs-lookup"><span data-stu-id="b68d8-111">You can use the `Skip` clause with the `Take` clause to return a range of data from any segment of a query.</span></span> <span data-ttu-id="b68d8-112">Para ello, pase el índice del primer elemento del intervalo para el `Skip` cláusula y el tamaño del intervalo para el `Take` cláusula.</span><span class="sxs-lookup"><span data-stu-id="b68d8-112">To do this, pass the index of the first element of the range to the `Skip` clause and the size of the range to the `Take` clause.</span></span>  
  
 <span data-ttu-id="b68d8-113">Cuando se usa el `Skip` cláusula en una consulta, es posible que también deberá asegurarse de que los resultados se devuelven en un orden que le permitirán la `Skip` cláusula para omitir los resultados deseados.</span><span class="sxs-lookup"><span data-stu-id="b68d8-113">When you use the `Skip` clause in a query, you may also need to ensure that the results are returned in an order that will enable the `Skip` clause to bypass the intended results.</span></span> <span data-ttu-id="b68d8-114">Para obtener más información sobre cómo ordenar los resultados de la consulta, vea [cláusula Order By](../../../visual-basic/language-reference/queries/order-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="b68d8-114">For more information about ordering query results, see [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
 <span data-ttu-id="b68d8-115">Puede usar el `SkipWhile` cláusula para especificar que sólo determinados elementos se omiten, dependiendo de la condición proporcionada.</span><span class="sxs-lookup"><span data-stu-id="b68d8-115">You can use the `SkipWhile` clause to specify that only certain elements are ignored, depending on a supplied condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b68d8-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b68d8-116">Example</span></span>  
 <span data-ttu-id="b68d8-117">El siguiente ejemplo de código utiliza el `Skip` cláusula junto con el `Take` cláusula para devolver datos de una consulta en las páginas.</span><span class="sxs-lookup"><span data-stu-id="b68d8-117">The following code example uses the `Skip` clause together with the `Take` clause to return data from a query in pages.</span></span> <span data-ttu-id="b68d8-118">El `GetCustomers` función usa el `Skip` cláusula para omitir los clientes en la lista hasta que la proporcionada a partir de índice valor y se usa el `Take` cláusula para devolver una página de clientes a partir de ese valor de índice.</span><span class="sxs-lookup"><span data-stu-id="b68d8-118">The `GetCustomers` function uses the `Skip` clause to bypass the customers in the list until the supplied starting index value, and uses the `Take` clause to return a page of customers starting from that index value.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="b68d8-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="b68d8-119">See also</span></span>

- [<span data-ttu-id="b68d8-120">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b68d8-120">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="b68d8-121">Consultas</span><span class="sxs-lookup"><span data-stu-id="b68d8-121">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="b68d8-122">Select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="b68d8-122">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="b68d8-123">From (cláusula)</span><span class="sxs-lookup"><span data-stu-id="b68d8-123">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="b68d8-124">Order By (cláusula)</span><span class="sxs-lookup"><span data-stu-id="b68d8-124">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [<span data-ttu-id="b68d8-125">Skip While (cláusula)</span><span class="sxs-lookup"><span data-stu-id="b68d8-125">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [<span data-ttu-id="b68d8-126">Take (cláusula)</span><span class="sxs-lookup"><span data-stu-id="b68d8-126">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)
