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
ms.openlocfilehash: 00a2e52bd6669869bb2e25bc2857f1598da5763f
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56971252"
---
# <a name="distinct-clause-visual-basic"></a><span data-ttu-id="0238f-102">Distinct (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0238f-102">Distinct Clause (Visual Basic)</span></span>
<span data-ttu-id="0238f-103">Restringe los valores de la variable de rango actual para eliminar valores duplicados en las cláusulas de consulta subsiguientes.</span><span class="sxs-lookup"><span data-stu-id="0238f-103">Restricts the values of the current range variable to eliminate duplicate values in subsequent query clauses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0238f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0238f-104">Syntax</span></span>  
  
```  
Distinct  
```  
  
## <a name="remarks"></a><span data-ttu-id="0238f-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0238f-105">Remarks</span></span>  
 <span data-ttu-id="0238f-106">Puede usar el `Distinct` cláusula para devolver una lista de elementos únicos.</span><span class="sxs-lookup"><span data-stu-id="0238f-106">You can use the `Distinct` clause to return a list of unique items.</span></span> <span data-ttu-id="0238f-107">El `Distinct` cláusula hace que la consulta pasar por alto los resultados de consulta duplicada.</span><span class="sxs-lookup"><span data-stu-id="0238f-107">The `Distinct` clause causes the query to ignore duplicate query results.</span></span> <span data-ttu-id="0238f-108">El `Distinct` cláusula se aplica a valores duplicados para todos los devueltos campos especificados por el `Select` cláusula.</span><span class="sxs-lookup"><span data-stu-id="0238f-108">The `Distinct` clause applies to duplicate values for all return fields specified by the `Select` clause.</span></span> <span data-ttu-id="0238f-109">Si no hay ningún `Select` cláusula se especifica, el `Distinct` cláusula se aplica a la variable de rango para la consulta identificada en el `From` cláusula.</span><span class="sxs-lookup"><span data-stu-id="0238f-109">If no `Select` clause is specified, the `Distinct` clause is applied to the range variable for the query identified in the `From` clause.</span></span> <span data-ttu-id="0238f-110">Si la variable de rango no es un tipo inmutable, la consulta omitirá únicamente un resultado de consulta si todos los miembros del tipo coinciden con un resultado de consulta existente.</span><span class="sxs-lookup"><span data-stu-id="0238f-110">If the range variable is not an immutable type, the query will only ignore a query result if all members of the type match an existing query result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0238f-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0238f-111">Example</span></span>  
 <span data-ttu-id="0238f-112">La expresión de consulta siguiente combina una lista de clientes y una lista de pedidos del cliente.</span><span class="sxs-lookup"><span data-stu-id="0238f-112">The following query expression joins a list of customers and a list of customer orders.</span></span> <span data-ttu-id="0238f-113">El `Distinct` cláusula se incluye para devolver una lista de nombres de cliente únicos y ordenar las fechas.</span><span class="sxs-lookup"><span data-stu-id="0238f-113">The `Distinct` clause is included to return a list of unique customer names and order dates.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#20)]  
  
## <a name="see-also"></a><span data-ttu-id="0238f-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="0238f-114">See also</span></span>
- [<span data-ttu-id="0238f-115">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0238f-115">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="0238f-116">Consultas</span><span class="sxs-lookup"><span data-stu-id="0238f-116">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="0238f-117">From (cláusula)</span><span class="sxs-lookup"><span data-stu-id="0238f-117">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="0238f-118">Select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="0238f-118">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="0238f-119">Where (cláusula)</span><span class="sxs-lookup"><span data-stu-id="0238f-119">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
