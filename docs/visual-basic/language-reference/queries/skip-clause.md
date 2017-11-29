---
title: "Skip (Cláusula, Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.QuerySkip
helpviewer_keywords:
- queries [Visual Basic], Skip
- Skip statement [Visual Basic]
- Skip clause [Visual Basic]
ms.assetid: f00eb172-3907-4c43-9745-d8546ab86234
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 508f3c094df4c834305bcb4a78223c1cee82b1c8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="skip-clause-visual-basic"></a><span data-ttu-id="43c3a-102">Skip (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="43c3a-102">Skip Clause (Visual Basic)</span></span>
<span data-ttu-id="43c3a-103">Omite un número especificado de elementos de una colección y, a continuación, devuelve los elementos restantes.</span><span class="sxs-lookup"><span data-stu-id="43c3a-103">Bypasses a specified number of elements in a collection and then returns the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43c3a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="43c3a-104">Syntax</span></span>  
  
```  
Skip count  
```  
  
## <a name="parts"></a><span data-ttu-id="43c3a-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="43c3a-105">Parts</span></span>  
 `count`  
 <span data-ttu-id="43c3a-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="43c3a-106">Required.</span></span> <span data-ttu-id="43c3a-107">Un valor o una expresión que se evalúa como el número de elementos de la secuencia que se va a omitir.</span><span class="sxs-lookup"><span data-stu-id="43c3a-107">A value or an expression that evaluates to the number of elements of the sequence to skip.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43c3a-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="43c3a-108">Remarks</span></span>  
 <span data-ttu-id="43c3a-109">El `Skip` cláusula hace que una consulta omita los elementos al principio de una lista de resultados y devolver los elementos restantes.</span><span class="sxs-lookup"><span data-stu-id="43c3a-109">The `Skip` clause causes a query to bypass elements at the beginning of a results list and return the remaining elements.</span></span> <span data-ttu-id="43c3a-110">El número de elementos que se van a omitir se identifica mediante el `count` parámetro.</span><span class="sxs-lookup"><span data-stu-id="43c3a-110">The number of elements to skip is identified by the `count` parameter.</span></span>  
  
 <span data-ttu-id="43c3a-111">Puede usar el `Skip` cláusula con el `Take` cláusula para devolver un intervalo de datos de cualquier segmento de una consulta.</span><span class="sxs-lookup"><span data-stu-id="43c3a-111">You can use the `Skip` clause with the `Take` clause to return a range of data from any segment of a query.</span></span> <span data-ttu-id="43c3a-112">Para ello, pase el índice del primer elemento del intervalo para el `Skip` cláusula y el tamaño del intervalo para el `Take` cláusula.</span><span class="sxs-lookup"><span data-stu-id="43c3a-112">To do this, pass the index of the first element of the range to the `Skip` clause and the size of the range to the `Take` clause.</span></span>  
  
 <span data-ttu-id="43c3a-113">Cuando se usa el `Skip` cláusula en una consulta, también debe asegurarse de que los resultados se devuelven en un orden que permita la `Skip` cláusula para omitir los resultados previstos.</span><span class="sxs-lookup"><span data-stu-id="43c3a-113">When you use the `Skip` clause in a query, you may also need to ensure that the results are returned in an order that will enable the `Skip` clause to bypass the intended results.</span></span> <span data-ttu-id="43c3a-114">Para obtener más información sobre cómo ordenar los resultados de la consulta, vea [cláusula Order By](../../../visual-basic/language-reference/queries/order-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="43c3a-114">For more information about ordering query results, see [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
 <span data-ttu-id="43c3a-115">Puede usar el `SkipWhile` cláusula para especificar que sólo ciertos elementos se omiten, dependiendo de la condición proporcionada.</span><span class="sxs-lookup"><span data-stu-id="43c3a-115">You can use the `SkipWhile` clause to specify that only certain elements are ignored, depending on a supplied condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="43c3a-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="43c3a-116">Example</span></span>  
 <span data-ttu-id="43c3a-117">El siguiente ejemplo de código utiliza el `Skip` cláusula junto con el `Take` cláusula se devuelven datos de una consulta en páginas.</span><span class="sxs-lookup"><span data-stu-id="43c3a-117">The following code example uses the `Skip` clause together with the `Take` clause to return data from a query in pages.</span></span> <span data-ttu-id="43c3a-118">El `GetCustomers` función utiliza la `Skip` cláusula para omitir los clientes en la lista hasta que la proporcionada a partir de índice valor y se utiliza el `Take` cláusula para devolver una página de los clientes a partir de ese valor de índice.</span><span class="sxs-lookup"><span data-stu-id="43c3a-118">The `GetCustomers` function uses the `Skip` clause to bypass the customers in the list until the supplied starting index value, and uses the `Take` clause to return a page of customers starting from that index value.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#1](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/skip-clause_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="43c3a-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="43c3a-119">See Also</span></span>  
 [<span data-ttu-id="43c3a-120">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="43c3a-120">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="43c3a-121">Consultas</span><span class="sxs-lookup"><span data-stu-id="43c3a-121">Queries</span></span>](../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="43c3a-122">Select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="43c3a-122">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="43c3a-123">From (cláusula)</span><span class="sxs-lookup"><span data-stu-id="43c3a-123">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="43c3a-124">Order By (cláusula)</span><span class="sxs-lookup"><span data-stu-id="43c3a-124">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 [<span data-ttu-id="43c3a-125">Skip While (cláusula)</span><span class="sxs-lookup"><span data-stu-id="43c3a-125">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)  
 [<span data-ttu-id="43c3a-126">Take (cláusula)</span><span class="sxs-lookup"><span data-stu-id="43c3a-126">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)
