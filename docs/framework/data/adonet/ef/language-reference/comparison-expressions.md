---
title: Expresiones de comparación
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ec7637a9-01d5-4a95-8bb0-478311cd263b
ms.openlocfilehash: d92020f353393eee683e578f4306cd4a2f214152
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197851"
---
# <a name="comparison-expressions"></a><span data-ttu-id="e310f-102">Expresiones de comparación</span><span class="sxs-lookup"><span data-stu-id="e310f-102">Comparison Expressions</span></span>

<span data-ttu-id="e310f-103">Una expresión de comparación comprueba si un valor constante, el valor de propiedad o el resultado de un método es igual, no igual, superior a o inferior a otro valor.</span><span class="sxs-lookup"><span data-stu-id="e310f-103">A comparison expression checks whether a constant value, property value, or method result is equal, not equal, greater than, or less than another value.</span></span> <span data-ttu-id="e310f-104">Si una comparación determinada no es válida para LINQ to Entities, se producirá una excepción.</span><span class="sxs-lookup"><span data-stu-id="e310f-104">If a particular comparison is not valid for LINQ to Entities, an exception will be thrown.</span></span> <span data-ttu-id="e310f-105">Todas las comparaciones, tanto implícitas como explícitas, requieren que todos los componentes sean comparables en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="e310f-105">All comparisons, both implicit and explicit, require that all components are comparable in the data source.</span></span> <span data-ttu-id="e310f-106">Las expresiones de comparación se utilizan frecuentemente en cláusulas `Where` para restringir los resultados de las consultas.</span><span class="sxs-lookup"><span data-stu-id="e310f-106">Comparison expressions are frequently used in `Where` clauses for restricting the query results.</span></span>  
  
 <span data-ttu-id="e310f-107">El ejemplo siguiente en la sintaxis de expresiones de consulta muestra los resultados de una consulta en los que el número de pedido de ventas es igual a "SO43663":</span><span class="sxs-lookup"><span data-stu-id="e310f-107">The following example in query expression syntax shows a query that returns results where the sales order number is equal to "SO43663":</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#RestrictionExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#restrictionexpression)]
 [!code-vb[DP L2E Conceptual Examples#RestrictionExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#restrictionexpression)]  
  
 <span data-ttu-id="e310f-108">El ejemplo siguiente en la sintaxis de consultas basadas en métodos muestra los resultados de una consulta en los que el número de pedido de ventas es igual a "SO43663":</span><span class="sxs-lookup"><span data-stu-id="e310f-108">The following example in method-based query syntax shows a query that returns results where the sales order number is equal to "SO43663":</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#RestrictionExpression_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#restrictionexpression_mq)]
 [!code-vb[DP L2E Conceptual Examples#RestrictionExpression_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#restrictionexpression_mq)]  
  
 <span data-ttu-id="e310f-109">El ejemplo siguiente en la sintaxis de expresiones de consulta muestra los resultados de información de pedidos de ventas en los que la fecha de envío es igual al 8 de julio de 2001:</span><span class="sxs-lookup"><span data-stu-id="e310f-109">The following example in query expression syntax shows a query that returns sales order information where the ship date is equal to July 8, 2001:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#DateTimeComparison](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#datetimecomparison)]
 [!code-vb[DP L2E Conceptual Examples#DateTimeComparison](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#datetimecomparison)]  
  
 <span data-ttu-id="e310f-110">El ejemplo siguiente en la sintaxis de consultas basadas en métodos muestra los resultados de información de pedidos de ventas en los que la fecha de envío es igual al 8 de julio de 2001:</span><span class="sxs-lookup"><span data-stu-id="e310f-110">The following example in method-based query syntax shows a query that returns sales order information where the ship date is equal to July 8, 2001:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#DateTimeComparison_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#datetimecomparison_mq)]
 [!code-vb[DP L2E Conceptual Examples#DateTimeComparison_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#datetimecomparison_mq)]  
  
 <span data-ttu-id="e310f-111">Las expresiones que producen una constante se convierten en el servidor y no se intenta realizar evaluaciones locales.</span><span class="sxs-lookup"><span data-stu-id="e310f-111">Expressions that yield a constant are converted at the server, and no attempt to do local evaluation is performed.</span></span> <span data-ttu-id="e310f-112">En el ejemplo siguiente se utiliza una expresión en la cláusula `Where` que produce una constante.</span><span class="sxs-lookup"><span data-stu-id="e310f-112">The following example uses an expression in the `Where` clause that yields a constant.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#ConstantExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#constantexpression)]
 [!code-vb[DP L2E Conceptual Examples#ConstantExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#constantexpression)]  
  
 <span data-ttu-id="e310f-113">LINQ to Entities no admite el uso de una clase de usuario como constante.</span><span class="sxs-lookup"><span data-stu-id="e310f-113">LINQ to Entities does not support using a user class as a constant.</span></span> <span data-ttu-id="e310f-114">Sin embargo, una referencia de propiedad en una clase de usuario se considera una constante, se convertirá en una expresión constante de árbol de comandos y se ejecutará en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="e310f-114">However, a property reference on a user class is considered a constant, and will be converted to a command tree constant expression and executed on the data source.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#MyClass](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#myclass)]
 [!code-vb[DP L2E Conceptual Examples#MyClass](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#myclass)]  
  
 [!code-csharp[DP L2E Conceptual Examples#PropertyAsConstant](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#propertyasconstant)]
 [!code-vb[DP L2E Conceptual Examples#PropertyAsConstant](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#propertyasconstant)]  
  
 <span data-ttu-id="e310f-115">No se admiten los métodos cuyos resultados producen expresiones constantes.</span><span class="sxs-lookup"><span data-stu-id="e310f-115">Methods that return a constant expression are not supported.</span></span> <span data-ttu-id="e310f-116">El ejemplo siguiente contiene un método en la cláusula `Where` que devuelve una constante.</span><span class="sxs-lookup"><span data-stu-id="e310f-116">The following example contains a method in the `Where` clause that returns a constant.</span></span> <span data-ttu-id="e310f-117">Este ejemplo producirá una excepción en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="e310f-117">This example will throw an exception at run time.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#MethodAsConstantFails](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#methodasconstantfails)]
 [!code-vb[DP L2E Conceptual Examples#MethodAsConstantFails](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#methodasconstantfails)]  
  
## <a name="see-also"></a><span data-ttu-id="e310f-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e310f-118">See also</span></span>

- [<span data-ttu-id="e310f-119">Expresiones en consultas de LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="e310f-119">Expressions in LINQ to Entities Queries</span></span>](expressions-in-linq-to-entities-queries.md)
