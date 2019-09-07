---
title: 'Ejemplos de sintaxis de consulta basada en métodos: Operadores de combinación'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d00f0efa-9084-4c17-843f-54904fcb4204
ms.openlocfilehash: c7dafae846a30424f008cce5f597efbdefa4bdf8
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397353"
---
# <a name="method-based-query-syntax-examples-join-operators"></a><span data-ttu-id="4db23-102">Ejemplos de sintaxis de consulta basada en métodos: Operadores de combinación</span><span class="sxs-lookup"><span data-stu-id="4db23-102">Method-Based Query Syntax Examples: Join Operators</span></span>
<span data-ttu-id="4db23-103">En los ejemplos de este tema se muestra cómo usar <xref:System.Linq.Enumerable.Join%2A> los <xref:System.Linq.Enumerable.GroupJoin%2A> métodos y para consultar el [modelo AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) con la sintaxis de consulta basada en métodos.</span><span class="sxs-lookup"><span data-stu-id="4db23-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Join%2A> and <xref:System.Linq.Enumerable.GroupJoin%2A> methods to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using method-based query syntax.</span></span> <span data-ttu-id="4db23-104">El modelo AdventureWorks Sales que se usa en estos ejemplos se crea a partir de las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="4db23-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="4db23-105">En los ejemplos de este tema se usan `using` las siguientes / `Imports` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="4db23-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="groupjoin"></a><span data-ttu-id="4db23-106">GroupJoin</span><span class="sxs-lookup"><span data-stu-id="4db23-106">GroupJoin</span></span>  
  
### <a name="example"></a><span data-ttu-id="4db23-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4db23-107">Example</span></span>  
 <span data-ttu-id="4db23-108">El ejemplo siguiente realiza una <xref:System.Linq.Enumerable.GroupJoin%2A> en las tablas SalesOrderHeader y SalesOrderDetail para buscar el número de pedidos por cliente.</span><span class="sxs-lookup"><span data-stu-id="4db23-108">The following example performs a <xref:System.Linq.Enumerable.GroupJoin%2A> over the SalesOrderHeader and SalesOrderDetail tables to find the number of orders per customer.</span></span> <span data-ttu-id="4db23-109">Una combinación de grupo es el equivalente a una combinación externa izquierda, que devuelve cada elemento del primer origen de datos (izquierdo), incluso si no hay elementos correlacionados en el otro origen de datos.</span><span class="sxs-lookup"><span data-stu-id="4db23-109">A group join is the equivalent of a left outer join, which returns each element of the first (left) data source, even if no correlated elements are in the other data source.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupJoin2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupjoin2_mq)]
 [!code-vb[DP L2E Examples#GroupJoin2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupjoin2_mq)]  
  
### <a name="example"></a><span data-ttu-id="4db23-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4db23-110">Example</span></span>  
 <span data-ttu-id="4db23-111">En el ejemplo siguiente se realiza una operación <xref:System.Linq.Enumerable.GroupJoin%2A> en las tablas Contact y SalesOrderHeader para buscar el número de pedidos por contacto.</span><span class="sxs-lookup"><span data-stu-id="4db23-111">The following example performs a <xref:System.Linq.Enumerable.GroupJoin%2A> over the Contact and SalesOrderHeader tables to find the number of orders per contact.</span></span> <span data-ttu-id="4db23-112">Se muestran el recuento de pedidos y los identificadores para cada contacto.</span><span class="sxs-lookup"><span data-stu-id="4db23-112">The order count and IDs for each contact are displayed.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupJoin_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupjoin_mq)]
 [!code-vb[DP L2E Examples#GroupJoin_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupjoin_mq)]  
  
## <a name="join"></a><span data-ttu-id="4db23-113">Unir</span><span class="sxs-lookup"><span data-stu-id="4db23-113">Join</span></span>  
  
### <a name="example"></a><span data-ttu-id="4db23-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4db23-114">Example</span></span>  
 <span data-ttu-id="4db23-115">En el ejemplo siguiente se realiza una combinación en las tablas Contact y SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="4db23-115">The following example performs a join over the Contact and SalesOrderHeader tables.</span></span>  
  
 [!code-csharp[DP L2E Examples#JoinSimple_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#joinsimple_mq)]
 [!code-vb[DP L2E Examples#JoinSimple_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#joinsimple_mq)]  
  
### <a name="example"></a><span data-ttu-id="4db23-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4db23-116">Example</span></span>  
 <span data-ttu-id="4db23-117">En el ejemplo siguiente se realiza una combinación en las tablas Contact y SalesOrderHeader, agrupando los resultados por identificador de contacto.</span><span class="sxs-lookup"><span data-stu-id="4db23-117">The following example performs a join over the Contact and SalesOrderHeader tables, grouping the results by contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#JoinWithGroupedResults_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#joinwithgroupedresults_mq)]
 [!code-vb[DP L2E Examples#JoinWithGroupedResults_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#joinwithgroupedresults_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="4db23-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="4db23-118">See also</span></span>

- [<span data-ttu-id="4db23-119">Consultas en LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="4db23-119">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
