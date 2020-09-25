---
title: 'Ejemplos de sintaxis de consulta basada en métodos: Operadores de combinación'
description: Use estos ejemplos para obtener información sobre cómo usar los métodos join y GroupJoin para consultar un modelo mediante la sintaxis de consulta basada en métodos en LINQ to Entities.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d00f0efa-9084-4c17-843f-54904fcb4204
ms.openlocfilehash: 7f02379f4ececb75981ab262f22ebdeb510739ed
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91191963"
---
# <a name="method-based-query-syntax-examples-join-operators"></a><span data-ttu-id="3f22e-103">Ejemplos de sintaxis de consulta basada en métodos: Operadores de combinación</span><span class="sxs-lookup"><span data-stu-id="3f22e-103">Method-Based Query Syntax Examples: Join Operators</span></span>

<span data-ttu-id="3f22e-104">En los ejemplos de este tema se muestra cómo usar <xref:System.Linq.Enumerable.Join%2A> los <xref:System.Linq.Enumerable.GroupJoin%2A> métodos y para consultar el [modelo AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) con la sintaxis de consulta basada en métodos.</span><span class="sxs-lookup"><span data-stu-id="3f22e-104">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Join%2A> and <xref:System.Linq.Enumerable.GroupJoin%2A> methods to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using method-based query syntax.</span></span> <span data-ttu-id="3f22e-105">El modelo AdventureWorks Sales que se usa en estos ejemplos se crea a partir de las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="3f22e-105">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="3f22e-106">En los ejemplos de este tema se usan las siguientes `using` / `Imports` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="3f22e-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="groupjoin"></a><span data-ttu-id="3f22e-107">GroupJoin</span><span class="sxs-lookup"><span data-stu-id="3f22e-107">GroupJoin</span></span>  
  
### <a name="example"></a><span data-ttu-id="3f22e-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3f22e-108">Example</span></span>  

 <span data-ttu-id="3f22e-109">El ejemplo siguiente realiza una <xref:System.Linq.Enumerable.GroupJoin%2A> en las tablas SalesOrderHeader y SalesOrderDetail para buscar el número de pedidos por cliente.</span><span class="sxs-lookup"><span data-stu-id="3f22e-109">The following example performs a <xref:System.Linq.Enumerable.GroupJoin%2A> over the SalesOrderHeader and SalesOrderDetail tables to find the number of orders per customer.</span></span> <span data-ttu-id="3f22e-110">Una combinación de grupo es el equivalente a una combinación externa izquierda, que devuelve cada elemento del primer origen de datos (izquierdo), incluso si no hay elementos correlacionados en el otro origen de datos.</span><span class="sxs-lookup"><span data-stu-id="3f22e-110">A group join is the equivalent of a left outer join, which returns each element of the first (left) data source, even if no correlated elements are in the other data source.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupJoin2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupjoin2_mq)]
 [!code-vb[DP L2E Examples#GroupJoin2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupjoin2_mq)]  
  
### <a name="example"></a><span data-ttu-id="3f22e-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3f22e-111">Example</span></span>  

 <span data-ttu-id="3f22e-112">En el ejemplo siguiente se realiza una operación <xref:System.Linq.Enumerable.GroupJoin%2A> en las tablas Contact y SalesOrderHeader para buscar el número de pedidos por contacto.</span><span class="sxs-lookup"><span data-stu-id="3f22e-112">The following example performs a <xref:System.Linq.Enumerable.GroupJoin%2A> over the Contact and SalesOrderHeader tables to find the number of orders per contact.</span></span> <span data-ttu-id="3f22e-113">Se muestran el recuento de pedidos y los identificadores para cada contacto.</span><span class="sxs-lookup"><span data-stu-id="3f22e-113">The order count and IDs for each contact are displayed.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupJoin_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupjoin_mq)]
 [!code-vb[DP L2E Examples#GroupJoin_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupjoin_mq)]  
  
## <a name="join"></a><span data-ttu-id="3f22e-114">Join</span><span class="sxs-lookup"><span data-stu-id="3f22e-114">Join</span></span>  
  
### <a name="example"></a><span data-ttu-id="3f22e-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3f22e-115">Example</span></span>  

 <span data-ttu-id="3f22e-116">En el ejemplo siguiente se realiza una combinación en las tablas Contact y SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="3f22e-116">The following example performs a join over the Contact and SalesOrderHeader tables.</span></span>  
  
 [!code-csharp[DP L2E Examples#JoinSimple_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#joinsimple_mq)]
 [!code-vb[DP L2E Examples#JoinSimple_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#joinsimple_mq)]  
  
### <a name="example"></a><span data-ttu-id="3f22e-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3f22e-117">Example</span></span>  

 <span data-ttu-id="3f22e-118">En el ejemplo siguiente se realiza una combinación en las tablas Contact y SalesOrderHeader, agrupando los resultados por identificador de contacto.</span><span class="sxs-lookup"><span data-stu-id="3f22e-118">The following example performs a join over the Contact and SalesOrderHeader tables, grouping the results by contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#JoinWithGroupedResults_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#joinwithgroupedresults_mq)]
 [!code-vb[DP L2E Examples#JoinWithGroupedResults_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#joinwithgroupedresults_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="3f22e-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3f22e-119">See also</span></span>

- [<span data-ttu-id="3f22e-120">Consultas en LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="3f22e-120">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
