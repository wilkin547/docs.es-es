---
description: 'Más información acerca de: ejemplos de sintaxis de expresiones de consulta: operadores de combinación'
title: 'Ejemplos de sintaxis de expresiones de consulta: Operadores de combinación'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 343e8dda-70b2-409d-9334-ce9a880c3cea
ms.openlocfilehash: 01ca3157ef13097c5c89ac1e6bafd03873c05977
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99696209"
---
# <a name="query-expression-syntax-examples-join-operators"></a><span data-ttu-id="54d7d-103">Ejemplos de sintaxis de expresiones de consulta: Operadores de combinación</span><span class="sxs-lookup"><span data-stu-id="54d7d-103">Query Expression Syntax Examples: Join Operators</span></span>

<span data-ttu-id="54d7d-104">La combinación es una operación importante de las consultas dirigidas a orígenes de datos que no tienen relaciones navegables entre ellos, como las tablas de bases de datos relacionales.</span><span class="sxs-lookup"><span data-stu-id="54d7d-104">Joining is an important operation in queries that target data sources that have no navigable relationships to each other, such as relational database tables.</span></span> <span data-ttu-id="54d7d-105">Una combinación de dos orígenes de datos es la asociación de objetos en un origen de datos con objetos que comparten un atributo común en el otro origen de datos.</span><span class="sxs-lookup"><span data-stu-id="54d7d-105">A join of two data sources is the association of objects in one data source with objects that share a common attribute in the other data source.</span></span> <span data-ttu-id="54d7d-106">Para obtener más información, vea [información general sobre operadores de consulta estándar](/previous-versions/visualstudio/visual-studio-2013/bb397896(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="54d7d-106">For more information, see [Standard Query Operators Overview](/previous-versions/visualstudio/visual-studio-2013/bb397896(v=vs.120)).</span></span>  
  
 <span data-ttu-id="54d7d-107">Los ejemplos de este tema muestran cómo usar los <xref:System.Linq.Enumerable.GroupJoin%2A> métodos y <xref:System.Linq.Enumerable.Join%2A> para consultar el [modelo AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) con la sintaxis de las expresiones de consulta.</span><span class="sxs-lookup"><span data-stu-id="54d7d-107">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.GroupJoin%2A> and <xref:System.Linq.Enumerable.Join%2A> methods to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using query expression syntax.</span></span> <span data-ttu-id="54d7d-108">El modelo AdventureWorks Sales que se usa en estos ejemplos se crea a partir de las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="54d7d-108">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="54d7d-109">En los ejemplos de este tema se usan las siguientes `using` / `Imports` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="54d7d-109">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="groupjoin"></a><span data-ttu-id="54d7d-110">GroupJoin</span><span class="sxs-lookup"><span data-stu-id="54d7d-110">GroupJoin</span></span>  
  
### <a name="example"></a><span data-ttu-id="54d7d-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="54d7d-111">Example</span></span>  

 <span data-ttu-id="54d7d-112">El ejemplo siguiente realiza una <xref:System.Linq.Enumerable.GroupJoin%2A> en las tablas SalesOrderHeader y SalesOrderDetail para buscar el número de pedidos por cliente.</span><span class="sxs-lookup"><span data-stu-id="54d7d-112">The following example performs a <xref:System.Linq.Enumerable.GroupJoin%2A> over the SalesOrderHeader and SalesOrderDetail tables to find the number of orders per customer.</span></span> <span data-ttu-id="54d7d-113">Una combinación de grupo es el equivalente a una combinación externa izquierda, que devuelve cada elemento del primer origen de datos (izquierdo), incluso si no hay elementos correlacionados en el otro origen de datos.</span><span class="sxs-lookup"><span data-stu-id="54d7d-113">A group join is the equivalent of a left outer join, which returns each element of the first (left) data source, even if no correlated elements are in the other data source.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupJoin2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupjoin2)]
 [!code-vb[DP L2E Examples#GroupJoin2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupjoin2)]  
  
### <a name="example"></a><span data-ttu-id="54d7d-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="54d7d-114">Example</span></span>  

 <span data-ttu-id="54d7d-115">En el ejemplo siguiente se realiza una operación <xref:System.Linq.Enumerable.GroupJoin%2A> en las tablas Contact y SalesOrderHeader para buscar el número de pedidos por contacto.</span><span class="sxs-lookup"><span data-stu-id="54d7d-115">The following example performs a <xref:System.Linq.Enumerable.GroupJoin%2A> over the Contact and SalesOrderHeader tables to find the number of orders per contact.</span></span> <span data-ttu-id="54d7d-116">Se muestran el recuento de pedidos y los identificadores para cada contacto.</span><span class="sxs-lookup"><span data-stu-id="54d7d-116">The order count and IDs for each contact are displayed.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupJoin](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupjoin)]
 [!code-vb[DP L2E Examples#GroupJoin](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupjoin)]  
  
## <a name="join"></a><span data-ttu-id="54d7d-117">Join</span><span class="sxs-lookup"><span data-stu-id="54d7d-117">Join</span></span>  
  
### <a name="example"></a><span data-ttu-id="54d7d-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="54d7d-118">Example</span></span>  

 <span data-ttu-id="54d7d-119">El ejemplo siguiente realiza una combinación en las tablas SalesOrderHeader y SalesOrderDetail para obtener los pedidos en línea del mes de agosto.</span><span class="sxs-lookup"><span data-stu-id="54d7d-119">The following example performs a join over the SalesOrderHeader and SalesOrderDetail tables to get online orders from the month of August.</span></span>  
  
 [!code-csharp[DP L2E Examples#Join](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#join)]
 [!code-vb[DP L2E Examples#Join](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#join)]  
  
## <a name="see-also"></a><span data-ttu-id="54d7d-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="54d7d-120">See also</span></span>

- [<span data-ttu-id="54d7d-121">Consultas en LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="54d7d-121">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
