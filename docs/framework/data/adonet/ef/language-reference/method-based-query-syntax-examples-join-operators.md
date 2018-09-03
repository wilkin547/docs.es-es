---
title: 'Ejemplos de sintaxis de consultas basadas en métodos: operadores de combinación'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d00f0efa-9084-4c17-843f-54904fcb4204
ms.openlocfilehash: ee753f5101f525fc7d86a91f2aa3545d257a2be5
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2018
ms.locfileid: "43478122"
---
# <a name="method-based-query-syntax-examples-join-operators"></a><span data-ttu-id="ad24a-102">Ejemplos de sintaxis de consultas basadas en métodos: operadores de combinación</span><span class="sxs-lookup"><span data-stu-id="ad24a-102">Method-Based Query Syntax Examples: Join Operators</span></span>
<span data-ttu-id="ad24a-103">Los ejemplos de este tema muestran cómo usar el <xref:System.Linq.Enumerable.Join%2A> y <xref:System.Linq.Enumerable.GroupJoin%2A> métodos para consultar el [modelo AdventureWorks Sales](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) utilizando sintaxis de consulta basada en métodos.</span><span class="sxs-lookup"><span data-stu-id="ad24a-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Join%2A> and <xref:System.Linq.Enumerable.GroupJoin%2A> methods to query the [AdventureWorks Sales Model](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) using method-based query syntax.</span></span> <span data-ttu-id="ad24a-104">El modelo AdventureWorks Sales que se usa en estos ejemplos se crea a partir de las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="ad24a-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="ad24a-105">Los ejemplos de este tema usan los siguientes `using` / `Imports` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="ad24a-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="groupjoin"></a><span data-ttu-id="ad24a-106">GroupJoin</span><span class="sxs-lookup"><span data-stu-id="ad24a-106">GroupJoin</span></span>  
  
### <a name="example"></a><span data-ttu-id="ad24a-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ad24a-107">Example</span></span>  
 <span data-ttu-id="ad24a-108">El ejemplo siguiente realiza una <xref:System.Linq.Enumerable.GroupJoin%2A> en las tablas SalesOrderHeader y SalesOrderDetail para buscar el número de pedidos por cliente.</span><span class="sxs-lookup"><span data-stu-id="ad24a-108">The following example performs a <xref:System.Linq.Enumerable.GroupJoin%2A> over the SalesOrderHeader and SalesOrderDetail tables to find the number of orders per customer.</span></span> <span data-ttu-id="ad24a-109">Una combinación de grupo es el equivalente a una combinación externa izquierda, que devuelve cada elemento del primer origen de datos (izquierdo), incluso si no hay elementos correlacionados en el otro origen de datos.</span><span class="sxs-lookup"><span data-stu-id="ad24a-109">A group join is the equivalent of a left outer join, which returns each element of the first (left) data source, even if no correlated elements are in the other data source.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupJoin2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupjoin2_mq)]
 [!code-vb[DP L2E Examples#GroupJoin2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupjoin2_mq)]  
  
### <a name="example"></a><span data-ttu-id="ad24a-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ad24a-110">Example</span></span>  
 <span data-ttu-id="ad24a-111">En el ejemplo siguiente se realiza una operación <xref:System.Linq.Enumerable.GroupJoin%2A> en las tablas Contact y SalesOrderHeader para buscar el número de pedidos por contacto.</span><span class="sxs-lookup"><span data-stu-id="ad24a-111">The following example performs a <xref:System.Linq.Enumerable.GroupJoin%2A> over the Contact and SalesOrderHeader tables to find the number of orders per contact.</span></span> <span data-ttu-id="ad24a-112">Se muestran el recuento de pedidos y los identificadores para cada contacto.</span><span class="sxs-lookup"><span data-stu-id="ad24a-112">The order count and IDs for each contact are displayed.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupJoin_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupjoin_mq)]
 [!code-vb[DP L2E Examples#GroupJoin_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupjoin_mq)]  
  
## <a name="join"></a><span data-ttu-id="ad24a-113">Join</span><span class="sxs-lookup"><span data-stu-id="ad24a-113">Join</span></span>  
  
### <a name="example"></a><span data-ttu-id="ad24a-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ad24a-114">Example</span></span>  
 <span data-ttu-id="ad24a-115">En el ejemplo siguiente se realiza una combinación en las tablas Contact y SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="ad24a-115">The following example performs a join over the Contact and SalesOrderHeader tables.</span></span>  
  
 [!code-csharp[DP L2E Examples#JoinSimple_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#joinsimple_mq)]
 [!code-vb[DP L2E Examples#JoinSimple_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#joinsimple_mq)]  
  
### <a name="example"></a><span data-ttu-id="ad24a-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ad24a-116">Example</span></span>  
 <span data-ttu-id="ad24a-117">En el ejemplo siguiente se realiza una combinación en las tablas Contact y SalesOrderHeader, agrupando los resultados por identificador de contacto.</span><span class="sxs-lookup"><span data-stu-id="ad24a-117">The following example performs a join over the Contact and SalesOrderHeader tables, grouping the results by contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#JoinWithGroupedResults_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#joinwithgroupedresults_mq)]
 [!code-vb[DP L2E Examples#JoinWithGroupedResults_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#joinwithgroupedresults_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="ad24a-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="ad24a-118">See Also</span></span>  
 [<span data-ttu-id="ad24a-119">Consultas en LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="ad24a-119">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
