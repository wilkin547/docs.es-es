---
description: 'Más información sobre: cláusula DISTINCT (Visual Basic)'
title: Cláusula Distinct
ms.date: 07/20/2015
f1_keywords:
- vb.QueryDistinct
helpviewer_keywords:
- Distinct clause [Visual Basic]
- Distinct statement [Visual Basic]
- queries [Visual Basic], Distinct
ms.assetid: 86f42614-0d8f-4ffc-b888-ce8a37a8d36a
ms.openlocfilehash: df1cdc58f7af406533e67a396a958a26b0c79635
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99700655"
---
# <a name="distinct-clause-visual-basic"></a><span data-ttu-id="8dc58-103">Distinct (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8dc58-103">Distinct Clause (Visual Basic)</span></span>

<span data-ttu-id="8dc58-104">Restringe los valores de la variable de rango actual para eliminar los valores duplicados en las cláusulas de consulta subsiguientes.</span><span class="sxs-lookup"><span data-stu-id="8dc58-104">Restricts the values of the current range variable to eliminate duplicate values in subsequent query clauses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8dc58-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8dc58-105">Syntax</span></span>  
  
```vb  
Distinct  
```  
  
## <a name="remarks"></a><span data-ttu-id="8dc58-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8dc58-106">Remarks</span></span>  

 <span data-ttu-id="8dc58-107">Puede utilizar la `Distinct` cláusula para devolver una lista de elementos únicos.</span><span class="sxs-lookup"><span data-stu-id="8dc58-107">You can use the `Distinct` clause to return a list of unique items.</span></span> <span data-ttu-id="8dc58-108">La `Distinct` cláusula hace que la consulta omita los resultados de la consulta duplicada.</span><span class="sxs-lookup"><span data-stu-id="8dc58-108">The `Distinct` clause causes the query to ignore duplicate query results.</span></span> <span data-ttu-id="8dc58-109">La `Distinct` cláusula se aplica a los valores duplicados para todos los campos devueltos especificados por la `Select` cláusula.</span><span class="sxs-lookup"><span data-stu-id="8dc58-109">The `Distinct` clause applies to duplicate values for all return fields specified by the `Select` clause.</span></span> <span data-ttu-id="8dc58-110">Si no `Select` se especifica ninguna cláusula, la `Distinct` cláusula se aplica a la variable de rango de la consulta identificada en la `From` cláusula.</span><span class="sxs-lookup"><span data-stu-id="8dc58-110">If no `Select` clause is specified, the `Distinct` clause is applied to the range variable for the query identified in the `From` clause.</span></span> <span data-ttu-id="8dc58-111">Si la variable de rango no es un tipo inmutable, la consulta solo omitirá el resultado de una consulta si todos los miembros del tipo coinciden con el resultado de una consulta existente.</span><span class="sxs-lookup"><span data-stu-id="8dc58-111">If the range variable is not an immutable type, the query will only ignore a query result if all members of the type match an existing query result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8dc58-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8dc58-112">Example</span></span>  

 <span data-ttu-id="8dc58-113">La siguiente expresión de consulta combina una lista de clientes y una lista de pedidos de cliente.</span><span class="sxs-lookup"><span data-stu-id="8dc58-113">The following query expression joins a list of customers and a list of customer orders.</span></span> <span data-ttu-id="8dc58-114">La `Distinct` cláusula se incluye para devolver una lista de nombres de cliente únicos y fechas de pedido.</span><span class="sxs-lookup"><span data-stu-id="8dc58-114">The `Distinct` clause is included to return a list of unique customer names and order dates.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#20)]  
  
## <a name="see-also"></a><span data-ttu-id="8dc58-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="8dc58-115">See also</span></span>

- [<span data-ttu-id="8dc58-116">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8dc58-116">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="8dc58-117">Consultas</span><span class="sxs-lookup"><span data-stu-id="8dc58-117">Queries</span></span>](index.md)
- [<span data-ttu-id="8dc58-118">Cláusula From</span><span class="sxs-lookup"><span data-stu-id="8dc58-118">From Clause</span></span>](from-clause.md)
- [<span data-ttu-id="8dc58-119">Select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="8dc58-119">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="8dc58-120">Cláusula WHERE</span><span class="sxs-lookup"><span data-stu-id="8dc58-120">Where Clause</span></span>](where-clause.md)
