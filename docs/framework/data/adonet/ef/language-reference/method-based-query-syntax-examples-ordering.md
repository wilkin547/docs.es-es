---
description: 'Más información acerca de: Method-Based ejemplos de sintaxis de consultas: ordenación'
title: 'Ejemplos de sintaxis de consulta basada en métodos: Ordenación'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5d21b178-d731-471a-8534-1f8184a2ef06
ms.openlocfilehash: 7b1c67ba66f549e82a57b5b34c645d36d1255a14
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99696703"
---
# <a name="method-based-query-syntax-examples-ordering"></a><span data-ttu-id="b6b8b-103">Ejemplos de sintaxis de consulta basada en métodos: Ordenación</span><span class="sxs-lookup"><span data-stu-id="b6b8b-103">Method-Based Query Syntax Examples: Ordering</span></span>

<span data-ttu-id="b6b8b-104">En los ejemplos de este tema se muestra cómo usar el <xref:System.Linq.Enumerable.ThenBy%2A> método para consultar el [modelo AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) utilizando la sintaxis de consulta basada en métodos.</span><span class="sxs-lookup"><span data-stu-id="b6b8b-104">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.ThenBy%2A> method to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using method-based query syntax.</span></span> <span data-ttu-id="b6b8b-105">El modelo AdventureWorks Sales que se usa en estos ejemplos se crea a partir de las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="b6b8b-105">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="b6b8b-106">En los ejemplos de este tema se usan las siguientes `using` / `Imports` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="b6b8b-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="thenby"></a><span data-ttu-id="b6b8b-107">ThenBy</span><span class="sxs-lookup"><span data-stu-id="b6b8b-107">ThenBy</span></span>  
  
### <a name="example"></a><span data-ttu-id="b6b8b-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b6b8b-108">Example</span></span>  

 <span data-ttu-id="b6b8b-109">El siguiente ejemplo con la sintaxis de consulta basada en métodos usa <xref:System.Linq.Queryable.OrderBy%2A> y <xref:System.Linq.Queryable.ThenBy%2A> para devolver una lista de contactos ordenados primero por el apellido y después por el nombre:</span><span class="sxs-lookup"><span data-stu-id="b6b8b-109">The following example in method-based query syntax uses <xref:System.Linq.Queryable.OrderBy%2A> and <xref:System.Linq.Queryable.ThenBy%2A> to return a list of contacts ordered by last name and then by first name.</span></span>  
  
 [!code-csharp[DP L2E Examples#OrderByThenBy_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#orderbythenby_mq)]
 [!code-vb[DP L2E Examples#OrderByThenBy_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#orderbythenby_mq)]  
  
## <a name="thenbydescending"></a><span data-ttu-id="b6b8b-110">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="b6b8b-110">ThenByDescending</span></span>  
  
### <a name="example"></a><span data-ttu-id="b6b8b-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b6b8b-111">Example</span></span>  

 <span data-ttu-id="b6b8b-112">En el ejemplo siguiente se utilizan los métodos <xref:System.Linq.Queryable.OrderBy%2A> y <xref:System.Linq.Queryable.ThenByDescending%2A> para ordenar primero por precio de venta y después realizar una ordenación en orden descendente de los nombres de producto.</span><span class="sxs-lookup"><span data-stu-id="b6b8b-112">The following example uses the <xref:System.Linq.Queryable.OrderBy%2A> and <xref:System.Linq.Queryable.ThenByDescending%2A> methods to first sort by list price, and then perform a descending sort of the product names.</span></span>  
  
 [!code-csharp[DP L2E Examples#ThenByDescending_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#thenbydescending_mq)]
 [!code-vb[DP L2E Examples#ThenByDescending_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#thenbydescending_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="b6b8b-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="b6b8b-113">See also</span></span>

- [<span data-ttu-id="b6b8b-114">Consultas en LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="b6b8b-114">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
