---
title: Distinct (Cláusula, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryDistinct
helpviewer_keywords:
- Distinct clause [Visual Basic]
- Distinct statement [Visual Basic]
- queries [Visual Basic], Distinct
ms.assetid: 86f42614-0d8f-4ffc-b888-ce8a37a8d36a
ms.openlocfilehash: fbca9fa8aa227d8d5b6488bef179f4bda08bb38c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58830063"
---
# <a name="distinct-clause-visual-basic"></a><span data-ttu-id="082ce-102">Distinct (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="082ce-102">Distinct Clause (Visual Basic)</span></span>
<span data-ttu-id="082ce-103">Restringe los valores de la variable de rango actual para eliminar valores duplicados en las cláusulas de consulta subsiguientes.</span><span class="sxs-lookup"><span data-stu-id="082ce-103">Restricts the values of the current range variable to eliminate duplicate values in subsequent query clauses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="082ce-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="082ce-104">Syntax</span></span>  
  
```  
Distinct  
```  
  
## <a name="remarks"></a><span data-ttu-id="082ce-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="082ce-105">Remarks</span></span>  
 <span data-ttu-id="082ce-106">Puede usar el `Distinct` cláusula para devolver una lista de elementos únicos.</span><span class="sxs-lookup"><span data-stu-id="082ce-106">You can use the `Distinct` clause to return a list of unique items.</span></span> <span data-ttu-id="082ce-107">El `Distinct` cláusula hace que la consulta pasar por alto los resultados de consulta duplicada.</span><span class="sxs-lookup"><span data-stu-id="082ce-107">The `Distinct` clause causes the query to ignore duplicate query results.</span></span> <span data-ttu-id="082ce-108">El `Distinct` cláusula se aplica a valores duplicados para todos los devueltos campos especificados por el `Select` cláusula.</span><span class="sxs-lookup"><span data-stu-id="082ce-108">The `Distinct` clause applies to duplicate values for all return fields specified by the `Select` clause.</span></span> <span data-ttu-id="082ce-109">Si no hay ningún `Select` cláusula se especifica, el `Distinct` cláusula se aplica a la variable de rango para la consulta identificada en el `From` cláusula.</span><span class="sxs-lookup"><span data-stu-id="082ce-109">If no `Select` clause is specified, the `Distinct` clause is applied to the range variable for the query identified in the `From` clause.</span></span> <span data-ttu-id="082ce-110">Si la variable de rango no es un tipo inmutable, la consulta omitirá únicamente un resultado de consulta si todos los miembros del tipo coinciden con un resultado de consulta existente.</span><span class="sxs-lookup"><span data-stu-id="082ce-110">If the range variable is not an immutable type, the query will only ignore a query result if all members of the type match an existing query result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="082ce-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="082ce-111">Example</span></span>  
 <span data-ttu-id="082ce-112">La expresión de consulta siguiente combina una lista de clientes y una lista de pedidos del cliente.</span><span class="sxs-lookup"><span data-stu-id="082ce-112">The following query expression joins a list of customers and a list of customer orders.</span></span> <span data-ttu-id="082ce-113">El `Distinct` cláusula se incluye para devolver una lista de nombres de cliente únicos y ordenar las fechas.</span><span class="sxs-lookup"><span data-stu-id="082ce-113">The `Distinct` clause is included to return a list of unique customer names and order dates.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#20)]  
  
## <a name="see-also"></a><span data-ttu-id="082ce-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="082ce-114">See also</span></span>

- [<span data-ttu-id="082ce-115">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="082ce-115">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="082ce-116">Consultas</span><span class="sxs-lookup"><span data-stu-id="082ce-116">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="082ce-117">From (cláusula)</span><span class="sxs-lookup"><span data-stu-id="082ce-117">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="082ce-118">Select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="082ce-118">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="082ce-119">Where (cláusula)</span><span class="sxs-lookup"><span data-stu-id="082ce-119">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
