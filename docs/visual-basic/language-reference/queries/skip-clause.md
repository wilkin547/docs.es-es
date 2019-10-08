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
ms.openlocfilehash: e52de186e1475bfabd02821a0cd2384d8350eed3
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004766"
---
# <a name="skip-clause-visual-basic"></a><span data-ttu-id="06287-102">Skip (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="06287-102">Skip Clause (Visual Basic)</span></span>
<span data-ttu-id="06287-103">Omite un número especificado de elementos de una colección y, a continuación, devuelve los elementos restantes.</span><span class="sxs-lookup"><span data-stu-id="06287-103">Bypasses a specified number of elements in a collection and then returns the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06287-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="06287-104">Syntax</span></span>  
  
```vb  
Skip count  
```  
  
## <a name="parts"></a><span data-ttu-id="06287-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="06287-105">Parts</span></span>  
 `count`  
 <span data-ttu-id="06287-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="06287-106">Required.</span></span> <span data-ttu-id="06287-107">Un valor o una expresión que se evalúa como el número de elementos de la secuencia que se va a omitir.</span><span class="sxs-lookup"><span data-stu-id="06287-107">A value or an expression that evaluates to the number of elements of the sequence to skip.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="06287-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="06287-108">Remarks</span></span>  
 <span data-ttu-id="06287-109">La cláusula `Skip` hace que una consulta omita los elementos al principio de una lista de resultados y devuelva los elementos restantes.</span><span class="sxs-lookup"><span data-stu-id="06287-109">The `Skip` clause causes a query to bypass elements at the beginning of a results list and return the remaining elements.</span></span> <span data-ttu-id="06287-110">El número de elementos que se van a omitir se identifica mediante el parámetro `count`.</span><span class="sxs-lookup"><span data-stu-id="06287-110">The number of elements to skip is identified by the `count` parameter.</span></span>  
  
 <span data-ttu-id="06287-111">Puede usar la cláusula `Skip` con la cláusula `Take` para devolver un intervalo de datos de cualquier segmento de una consulta.</span><span class="sxs-lookup"><span data-stu-id="06287-111">You can use the `Skip` clause with the `Take` clause to return a range of data from any segment of a query.</span></span> <span data-ttu-id="06287-112">Para ello, pase el índice del primer elemento del intervalo a la cláusula `Skip` y el tamaño del intervalo a la cláusula `Take`.</span><span class="sxs-lookup"><span data-stu-id="06287-112">To do this, pass the index of the first element of the range to the `Skip` clause and the size of the range to the `Take` clause.</span></span>  
  
 <span data-ttu-id="06287-113">Cuando se usa la cláusula `Skip` en una consulta, también es necesario asegurarse de que los resultados se devuelven en un orden que permita que la cláusula `Skip` omita los resultados deseados.</span><span class="sxs-lookup"><span data-stu-id="06287-113">When you use the `Skip` clause in a query, you may also need to ensure that the results are returned in an order that will enable the `Skip` clause to bypass the intended results.</span></span> <span data-ttu-id="06287-114">Para obtener más información sobre cómo ordenar los resultados de una consulta, vea [cláusula order by](../../../visual-basic/language-reference/queries/order-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="06287-114">For more information about ordering query results, see [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
 <span data-ttu-id="06287-115">Puede usar la cláusula `SkipWhile` para especificar que solo se omitan determinados elementos, en función de una condición proporcionada.</span><span class="sxs-lookup"><span data-stu-id="06287-115">You can use the `SkipWhile` clause to specify that only certain elements are ignored, depending on a supplied condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="06287-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="06287-116">Example</span></span>  
 <span data-ttu-id="06287-117">En el ejemplo de código siguiente se usa la cláusula `Skip` junto con la cláusula `Take` para devolver datos de una consulta en páginas.</span><span class="sxs-lookup"><span data-stu-id="06287-117">The following code example uses the `Skip` clause together with the `Take` clause to return data from a query in pages.</span></span> <span data-ttu-id="06287-118">La función `GetCustomers` usa la cláusula `Skip` para omitir los clientes de la lista hasta el valor del índice de inicio proporcionado y usa la cláusula `Take` para devolver una página de clientes a partir de ese valor de índice.</span><span class="sxs-lookup"><span data-stu-id="06287-118">The `GetCustomers` function uses the `Skip` clause to bypass the customers in the list until the supplied starting index value, and uses the `Take` clause to return a page of customers starting from that index value.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="06287-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="06287-119">See also</span></span>

- [<span data-ttu-id="06287-120">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="06287-120">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="06287-121">Consultas</span><span class="sxs-lookup"><span data-stu-id="06287-121">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="06287-122">Select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="06287-122">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="06287-123">From (cláusula)</span><span class="sxs-lookup"><span data-stu-id="06287-123">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="06287-124">Order By (cláusula)</span><span class="sxs-lookup"><span data-stu-id="06287-124">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [<span data-ttu-id="06287-125">Skip While (cláusula)</span><span class="sxs-lookup"><span data-stu-id="06287-125">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [<span data-ttu-id="06287-126">Take (cláusula)</span><span class="sxs-lookup"><span data-stu-id="06287-126">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)
