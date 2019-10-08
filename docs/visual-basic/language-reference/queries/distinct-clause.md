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
ms.openlocfilehash: e8d3e38261a04c4d29faab351d24d6710413b09a
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004792"
---
# <a name="distinct-clause-visual-basic"></a><span data-ttu-id="53d54-102">Distinct (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="53d54-102">Distinct Clause (Visual Basic)</span></span>
<span data-ttu-id="53d54-103">Restringe los valores de la variable de rango actual para eliminar los valores duplicados en las cláusulas de consulta subsiguientes.</span><span class="sxs-lookup"><span data-stu-id="53d54-103">Restricts the values of the current range variable to eliminate duplicate values in subsequent query clauses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53d54-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="53d54-104">Syntax</span></span>  
  
```vb  
Distinct  
```  
  
## <a name="remarks"></a><span data-ttu-id="53d54-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="53d54-105">Remarks</span></span>  
 <span data-ttu-id="53d54-106">Puede usar la cláusula `Distinct` para devolver una lista de elementos únicos.</span><span class="sxs-lookup"><span data-stu-id="53d54-106">You can use the `Distinct` clause to return a list of unique items.</span></span> <span data-ttu-id="53d54-107">La cláusula `Distinct` hace que la consulta omita los resultados de la consulta duplicada.</span><span class="sxs-lookup"><span data-stu-id="53d54-107">The `Distinct` clause causes the query to ignore duplicate query results.</span></span> <span data-ttu-id="53d54-108">La cláusula `Distinct` se aplica a los valores duplicados para todos los campos devueltos especificados por la cláusula `Select`.</span><span class="sxs-lookup"><span data-stu-id="53d54-108">The `Distinct` clause applies to duplicate values for all return fields specified by the `Select` clause.</span></span> <span data-ttu-id="53d54-109">Si no se especifica ninguna cláusula `Select`, se aplica la cláusula `Distinct` a la variable de rango de la consulta identificada en la cláusula `From`.</span><span class="sxs-lookup"><span data-stu-id="53d54-109">If no `Select` clause is specified, the `Distinct` clause is applied to the range variable for the query identified in the `From` clause.</span></span> <span data-ttu-id="53d54-110">Si la variable de rango no es un tipo inmutable, la consulta solo omitirá el resultado de una consulta si todos los miembros del tipo coinciden con el resultado de una consulta existente.</span><span class="sxs-lookup"><span data-stu-id="53d54-110">If the range variable is not an immutable type, the query will only ignore a query result if all members of the type match an existing query result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="53d54-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="53d54-111">Example</span></span>  
 <span data-ttu-id="53d54-112">La siguiente expresión de consulta combina una lista de clientes y una lista de pedidos de cliente.</span><span class="sxs-lookup"><span data-stu-id="53d54-112">The following query expression joins a list of customers and a list of customer orders.</span></span> <span data-ttu-id="53d54-113">La cláusula `Distinct` se incluye para devolver una lista de nombres de cliente únicos y fechas de pedido.</span><span class="sxs-lookup"><span data-stu-id="53d54-113">The `Distinct` clause is included to return a list of unique customer names and order dates.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#20)]  
  
## <a name="see-also"></a><span data-ttu-id="53d54-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="53d54-114">See also</span></span>

- [<span data-ttu-id="53d54-115">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="53d54-115">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="53d54-116">Consultas</span><span class="sxs-lookup"><span data-stu-id="53d54-116">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="53d54-117">From (cláusula)</span><span class="sxs-lookup"><span data-stu-id="53d54-117">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="53d54-118">Select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="53d54-118">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="53d54-119">Where (cláusula)</span><span class="sxs-lookup"><span data-stu-id="53d54-119">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
