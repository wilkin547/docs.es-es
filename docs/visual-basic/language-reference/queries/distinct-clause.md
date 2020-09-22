---
title: Cláusula Distinct
ms.date: 07/20/2015
f1_keywords:
- vb.QueryDistinct
helpviewer_keywords:
- Distinct clause [Visual Basic]
- Distinct statement [Visual Basic]
- queries [Visual Basic], Distinct
ms.assetid: 86f42614-0d8f-4ffc-b888-ce8a37a8d36a
ms.openlocfilehash: 49eaab2e6a8c48d61518ea51ef2f644b6eb48314
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875281"
---
# <a name="distinct-clause-visual-basic"></a><span data-ttu-id="0af40-102">Distinct (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0af40-102">Distinct Clause (Visual Basic)</span></span>

<span data-ttu-id="0af40-103">Restringe los valores de la variable de rango actual para eliminar los valores duplicados en las cláusulas de consulta subsiguientes.</span><span class="sxs-lookup"><span data-stu-id="0af40-103">Restricts the values of the current range variable to eliminate duplicate values in subsequent query clauses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0af40-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0af40-104">Syntax</span></span>  
  
```vb  
Distinct  
```  
  
## <a name="remarks"></a><span data-ttu-id="0af40-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0af40-105">Remarks</span></span>  

 <span data-ttu-id="0af40-106">Puede utilizar la `Distinct` cláusula para devolver una lista de elementos únicos.</span><span class="sxs-lookup"><span data-stu-id="0af40-106">You can use the `Distinct` clause to return a list of unique items.</span></span> <span data-ttu-id="0af40-107">La `Distinct` cláusula hace que la consulta omita los resultados de la consulta duplicada.</span><span class="sxs-lookup"><span data-stu-id="0af40-107">The `Distinct` clause causes the query to ignore duplicate query results.</span></span> <span data-ttu-id="0af40-108">La `Distinct` cláusula se aplica a los valores duplicados para todos los campos devueltos especificados por la `Select` cláusula.</span><span class="sxs-lookup"><span data-stu-id="0af40-108">The `Distinct` clause applies to duplicate values for all return fields specified by the `Select` clause.</span></span> <span data-ttu-id="0af40-109">Si no `Select` se especifica ninguna cláusula, la `Distinct` cláusula se aplica a la variable de rango de la consulta identificada en la `From` cláusula.</span><span class="sxs-lookup"><span data-stu-id="0af40-109">If no `Select` clause is specified, the `Distinct` clause is applied to the range variable for the query identified in the `From` clause.</span></span> <span data-ttu-id="0af40-110">Si la variable de rango no es un tipo inmutable, la consulta solo omitirá el resultado de una consulta si todos los miembros del tipo coinciden con el resultado de una consulta existente.</span><span class="sxs-lookup"><span data-stu-id="0af40-110">If the range variable is not an immutable type, the query will only ignore a query result if all members of the type match an existing query result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0af40-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0af40-111">Example</span></span>  

 <span data-ttu-id="0af40-112">La siguiente expresión de consulta combina una lista de clientes y una lista de pedidos de cliente.</span><span class="sxs-lookup"><span data-stu-id="0af40-112">The following query expression joins a list of customers and a list of customer orders.</span></span> <span data-ttu-id="0af40-113">La `Distinct` cláusula se incluye para devolver una lista de nombres de cliente únicos y fechas de pedido.</span><span class="sxs-lookup"><span data-stu-id="0af40-113">The `Distinct` clause is included to return a list of unique customer names and order dates.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#20)]  
  
## <a name="see-also"></a><span data-ttu-id="0af40-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0af40-114">See also</span></span>

- [<span data-ttu-id="0af40-115">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0af40-115">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="0af40-116">Consultas</span><span class="sxs-lookup"><span data-stu-id="0af40-116">Queries</span></span>](index.md)
- [<span data-ttu-id="0af40-117">Cláusula FROM</span><span class="sxs-lookup"><span data-stu-id="0af40-117">From Clause</span></span>](from-clause.md)
- [<span data-ttu-id="0af40-118">Select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="0af40-118">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="0af40-119">Cláusula WHERE</span><span class="sxs-lookup"><span data-stu-id="0af40-119">Where Clause</span></span>](where-clause.md)
