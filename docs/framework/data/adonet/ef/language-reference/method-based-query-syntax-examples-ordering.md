---
title: 'Ejemplos de sintaxis de consulta basada en métodos: Ordenación'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5d21b178-d731-471a-8534-1f8184a2ef06
ms.openlocfilehash: 8da335bc2b45153aa00cd28f1a6baf58d11020ce
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70250105"
---
# <a name="method-based-query-syntax-examples-ordering"></a><span data-ttu-id="2426c-102">Ejemplos de sintaxis de consulta basada en métodos: Ordenación</span><span class="sxs-lookup"><span data-stu-id="2426c-102">Method-Based Query Syntax Examples: Ordering</span></span>
<span data-ttu-id="2426c-103">En los ejemplos de este tema se muestra cómo usar <xref:System.Linq.Enumerable.ThenBy%2A> el método para consultar el [modelo AdventureWorks Sales](https://archive.codeplex.com/?p=msftdbprodsamples) utilizando la sintaxis de consulta basada en métodos.</span><span class="sxs-lookup"><span data-stu-id="2426c-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.ThenBy%2A> method to query the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples) using method-based query syntax.</span></span> <span data-ttu-id="2426c-104">El modelo AdventureWorks Sales que se usa en estos ejemplos se crea a partir de las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="2426c-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="2426c-105">En los ejemplos de este tema se usan `using` las siguientes / `Imports` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="2426c-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="thenby"></a><span data-ttu-id="2426c-106">ThenBy</span><span class="sxs-lookup"><span data-stu-id="2426c-106">ThenBy</span></span>  
  
### <a name="example"></a><span data-ttu-id="2426c-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2426c-107">Example</span></span>  
 <span data-ttu-id="2426c-108">El siguiente ejemplo con la sintaxis de consulta basada en métodos usa <xref:System.Linq.Queryable.OrderBy%2A> y <xref:System.Linq.Queryable.ThenBy%2A> para devolver una lista de contactos ordenados primero por el apellido y después por el nombre:</span><span class="sxs-lookup"><span data-stu-id="2426c-108">The following example in method-based query syntax uses <xref:System.Linq.Queryable.OrderBy%2A> and <xref:System.Linq.Queryable.ThenBy%2A> to return a list of contacts ordered by last name and then by first name.</span></span>  
  
 [!code-csharp[DP L2E Examples#OrderByThenBy_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#orderbythenby_mq)]
 [!code-vb[DP L2E Examples#OrderByThenBy_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#orderbythenby_mq)]  
  
## <a name="thenbydescending"></a><span data-ttu-id="2426c-109">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="2426c-109">ThenByDescending</span></span>  
  
### <a name="example"></a><span data-ttu-id="2426c-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2426c-110">Example</span></span>  
 <span data-ttu-id="2426c-111">En el ejemplo siguiente se utilizan los métodos <xref:System.Linq.Queryable.OrderBy%2A> y <xref:System.Linq.Queryable.ThenByDescending%2A> para ordenar primero por precio de venta y después realizar una ordenación en orden descendente de los nombres de producto.</span><span class="sxs-lookup"><span data-stu-id="2426c-111">The following example uses the <xref:System.Linq.Queryable.OrderBy%2A> and <xref:System.Linq.Queryable.ThenByDescending%2A> methods to first sort by list price, and then perform a descending sort of the product names.</span></span>  
  
 [!code-csharp[DP L2E Examples#ThenByDescending_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#thenbydescending_mq)]
 [!code-vb[DP L2E Examples#ThenByDescending_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#thenbydescending_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="2426c-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="2426c-112">See also</span></span>

- [<span data-ttu-id="2426c-113">Consultas en LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="2426c-113">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
