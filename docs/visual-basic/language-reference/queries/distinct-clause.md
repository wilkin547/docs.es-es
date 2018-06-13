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
ms.openlocfilehash: 4b0ce12f6361d3dc6e5cc3601e96fc3a9bcf3841
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603982"
---
# <a name="distinct-clause-visual-basic"></a><span data-ttu-id="e24a0-102">Distinct (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e24a0-102">Distinct Clause (Visual Basic)</span></span>
<span data-ttu-id="e24a0-103">Restringe los valores de la variable de rango actual para eliminar los valores duplicados en las cláusulas de consulta subsiguientes.</span><span class="sxs-lookup"><span data-stu-id="e24a0-103">Restricts the values of the current range variable to eliminate duplicate values in subsequent query clauses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e24a0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e24a0-104">Syntax</span></span>  
  
```  
Distinct  
```  
  
## <a name="remarks"></a><span data-ttu-id="e24a0-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e24a0-105">Remarks</span></span>  
 <span data-ttu-id="e24a0-106">Puede usar el `Distinct` cláusula para devolver una lista de elementos únicos.</span><span class="sxs-lookup"><span data-stu-id="e24a0-106">You can use the `Distinct` clause to return a list of unique items.</span></span> <span data-ttu-id="e24a0-107">El `Distinct` cláusula hace que la consulta pasar por alto los resultados de consulta duplicada.</span><span class="sxs-lookup"><span data-stu-id="e24a0-107">The `Distinct` clause causes the query to ignore duplicate query results.</span></span> <span data-ttu-id="e24a0-108">El `Distinct` cláusula se aplica a valores duplicados para todos los devueltos de los campos especificados por el `Select` cláusula.</span><span class="sxs-lookup"><span data-stu-id="e24a0-108">The `Distinct` clause applies to duplicate values for all return fields specified by the `Select` clause.</span></span> <span data-ttu-id="e24a0-109">Si no hay ningún `Select` se especifica la cláusula, el `Distinct` cláusula se aplica a la variable de rango de la consulta identificada en el `From` cláusula.</span><span class="sxs-lookup"><span data-stu-id="e24a0-109">If no `Select` clause is specified, the `Distinct` clause is applied to the range variable for the query identified in the `From` clause.</span></span> <span data-ttu-id="e24a0-110">Si la variable de rango no es un tipo inmutable, la consulta omitirá únicamente un resultado de consulta si todos los miembros del tipo coinciden con un resultado de consulta existente.</span><span class="sxs-lookup"><span data-stu-id="e24a0-110">If the range variable is not an immutable type, the query will only ignore a query result if all members of the type match an existing query result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e24a0-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e24a0-111">Example</span></span>  
 <span data-ttu-id="e24a0-112">La siguiente expresión de consulta combina una lista de clientes y una lista de pedidos de cliente.</span><span class="sxs-lookup"><span data-stu-id="e24a0-112">The following query expression joins a list of customers and a list of customer orders.</span></span> <span data-ttu-id="e24a0-113">El `Distinct` cláusula se incluye para devolver una lista de nombres de cliente único y las fechas de pedidos.</span><span class="sxs-lookup"><span data-stu-id="e24a0-113">The `Distinct` clause is included to return a list of unique customer names and order dates.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#20](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/distinct-clause_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="e24a0-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="e24a0-114">See Also</span></span>  
 [<span data-ttu-id="e24a0-115">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e24a0-115">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="e24a0-116">Consultas</span><span class="sxs-lookup"><span data-stu-id="e24a0-116">Queries</span></span>](../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="e24a0-117">From (cláusula)</span><span class="sxs-lookup"><span data-stu-id="e24a0-117">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="e24a0-118">Select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="e24a0-118">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="e24a0-119">Where (cláusula)</span><span class="sxs-lookup"><span data-stu-id="e24a0-119">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
