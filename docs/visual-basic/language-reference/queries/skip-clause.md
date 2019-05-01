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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945254"
---
# <a name="skip-clause-visual-basic"></a><span data-ttu-id="99187-102">Skip (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="99187-102">Skip Clause (Visual Basic)</span></span>
<span data-ttu-id="99187-103">Omite un número especificado de elementos de una colección y, a continuación, devuelve los elementos restantes.</span><span class="sxs-lookup"><span data-stu-id="99187-103">Bypasses a specified number of elements in a collection and then returns the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99187-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="99187-104">Syntax</span></span>  
  
```  
Skip count  
```  
  
## <a name="parts"></a><span data-ttu-id="99187-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="99187-105">Parts</span></span>  
 `count`  
 <span data-ttu-id="99187-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="99187-106">Required.</span></span> <span data-ttu-id="99187-107">Un valor o una expresión que se evalúa como el número de elementos de la secuencia que se va a omitir.</span><span class="sxs-lookup"><span data-stu-id="99187-107">A value or an expression that evaluates to the number of elements of the sequence to skip.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99187-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="99187-108">Remarks</span></span>  
 <span data-ttu-id="99187-109">El `Skip` cláusula hace una consulta para omitir los elementos al principio de una lista de resultados y devolver los elementos restantes.</span><span class="sxs-lookup"><span data-stu-id="99187-109">The `Skip` clause causes a query to bypass elements at the beginning of a results list and return the remaining elements.</span></span> <span data-ttu-id="99187-110">Identifica el número de elementos para omitir la `count` parámetro.</span><span class="sxs-lookup"><span data-stu-id="99187-110">The number of elements to skip is identified by the `count` parameter.</span></span>  
  
 <span data-ttu-id="99187-111">Puede usar el `Skip` cláusula con el `Take` cláusula para devolver un intervalo de datos de cualquier segmento de una consulta.</span><span class="sxs-lookup"><span data-stu-id="99187-111">You can use the `Skip` clause with the `Take` clause to return a range of data from any segment of a query.</span></span> <span data-ttu-id="99187-112">Para ello, pase el índice del primer elemento del intervalo para el `Skip` cláusula y el tamaño del intervalo para el `Take` cláusula.</span><span class="sxs-lookup"><span data-stu-id="99187-112">To do this, pass the index of the first element of the range to the `Skip` clause and the size of the range to the `Take` clause.</span></span>  
  
 <span data-ttu-id="99187-113">Cuando se usa el `Skip` cláusula en una consulta, es posible que también deberá asegurarse de que los resultados se devuelven en un orden que le permitirán la `Skip` cláusula para omitir los resultados deseados.</span><span class="sxs-lookup"><span data-stu-id="99187-113">When you use the `Skip` clause in a query, you may also need to ensure that the results are returned in an order that will enable the `Skip` clause to bypass the intended results.</span></span> <span data-ttu-id="99187-114">Para obtener más información sobre cómo ordenar los resultados de la consulta, vea [cláusula Order By](../../../visual-basic/language-reference/queries/order-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="99187-114">For more information about ordering query results, see [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
 <span data-ttu-id="99187-115">Puede usar el `SkipWhile` cláusula para especificar que sólo determinados elementos se omiten, dependiendo de la condición proporcionada.</span><span class="sxs-lookup"><span data-stu-id="99187-115">You can use the `SkipWhile` clause to specify that only certain elements are ignored, depending on a supplied condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="99187-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="99187-116">Example</span></span>  
 <span data-ttu-id="99187-117">El siguiente ejemplo de código utiliza el `Skip` cláusula junto con el `Take` cláusula para devolver datos de una consulta en las páginas.</span><span class="sxs-lookup"><span data-stu-id="99187-117">The following code example uses the `Skip` clause together with the `Take` clause to return data from a query in pages.</span></span> <span data-ttu-id="99187-118">El `GetCustomers` función usa el `Skip` cláusula para omitir los clientes en la lista hasta que la proporcionada a partir de índice valor y se usa el `Take` cláusula para devolver una página de clientes a partir de ese valor de índice.</span><span class="sxs-lookup"><span data-stu-id="99187-118">The `GetCustomers` function uses the `Skip` clause to bypass the customers in the list until the supplied starting index value, and uses the `Take` clause to return a page of customers starting from that index value.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="99187-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="99187-119">See also</span></span>

- [<span data-ttu-id="99187-120">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="99187-120">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="99187-121">Consultas</span><span class="sxs-lookup"><span data-stu-id="99187-121">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="99187-122">Select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="99187-122">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="99187-123">From (cláusula)</span><span class="sxs-lookup"><span data-stu-id="99187-123">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="99187-124">Order By (cláusula)</span><span class="sxs-lookup"><span data-stu-id="99187-124">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [<span data-ttu-id="99187-125">Skip While (cláusula)</span><span class="sxs-lookup"><span data-stu-id="99187-125">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [<span data-ttu-id="99187-126">Take (cláusula)</span><span class="sxs-lookup"><span data-stu-id="99187-126">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)
