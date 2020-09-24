---
title: 'Ejemplos de sintaxis de expresiones de consulta: Ordenación'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: bcbc9625-7cf7-476e-85d2-058f12682f54
ms.openlocfilehash: ed03fc248ed48f56998bc27f7e880b1e8aa443d2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91156789"
---
# <a name="query-expression-syntax-examples-ordering"></a><span data-ttu-id="d362f-102">Ejemplos de sintaxis de expresiones de consulta: Ordenación</span><span class="sxs-lookup"><span data-stu-id="d362f-102">Query Expression Syntax Examples: Ordering</span></span>

<span data-ttu-id="d362f-103">Los ejemplos de este tema muestran cómo usar los `OrderBy` métodos y `OrderByDescending` para consultar el [modelo AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) con la sintaxis de las expresiones de consulta.</span><span class="sxs-lookup"><span data-stu-id="d362f-103">The examples in this topic demonstrate how to use the `OrderBy` and `OrderByDescending` methods to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using query expression syntax.</span></span> <span data-ttu-id="d362f-104">El modelo AdventureWorks Sales que se usa en estos ejemplos se crea a partir de las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="d362f-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="d362f-105">En los ejemplos de este tema se usan las siguientes `using` / `Imports` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="d362f-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="orderby"></a><span data-ttu-id="d362f-106">OrderBy</span><span class="sxs-lookup"><span data-stu-id="d362f-106">OrderBy</span></span>  
  
### <a name="example"></a><span data-ttu-id="d362f-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d362f-107">Example</span></span>  

 <span data-ttu-id="d362f-108">En el ejemplo siguiente se utiliza <xref:System.Linq.Enumerable.OrderBy%2A> para devolver una lista de contactos organizados por apellido.</span><span class="sxs-lookup"><span data-stu-id="d362f-108">The following example uses <xref:System.Linq.Enumerable.OrderBy%2A> to return a list of contacts ordered by last name.</span></span>  
  
 [!code-csharp[DP L2E Examples#OrderBySimple1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#orderbysimple1)]
 [!code-vb[DP L2E Examples#OrderBySimple1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#orderbysimple1)]  
  
### <a name="example"></a><span data-ttu-id="d362f-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d362f-109">Example</span></span>  

 <span data-ttu-id="d362f-110">En el ejemplo siguiente se utiliza <xref:System.Linq.Enumerable.OrderBy%2A> para ordenar una lista de contactos por longitud del apellido.</span><span class="sxs-lookup"><span data-stu-id="d362f-110">The following example uses <xref:System.Linq.Enumerable.OrderBy%2A> to sort a list of contacts by length of last name.</span></span>  
  
 [!code-csharp[DP L2E Examples#OrderBySimple2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#orderbysimple2)]
 [!code-vb[DP L2E Examples#OrderBySimple2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#orderbysimple2)]  
  
## <a name="orderbydescending"></a><span data-ttu-id="d362f-111">OrderByDescending</span><span class="sxs-lookup"><span data-stu-id="d362f-111">OrderByDescending</span></span>  
  
### <a name="example"></a><span data-ttu-id="d362f-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d362f-112">Example</span></span>  

 <span data-ttu-id="d362f-113">En el ejemplo siguiente se utiliza `orderby… descending` (`Order By … Descending`) en Visual Basic, que es equivalente al método <xref:System.Linq.Enumerable.OrderByDescending%2A>, para ordenar el precio de venta de mayor a menor.</span><span class="sxs-lookup"><span data-stu-id="d362f-113">The following example uses `orderby… descending` (`Order By … Descending` in Visual Basic), which is equivalent to the <xref:System.Linq.Enumerable.OrderByDescending%2A> method, to sort the price list from highest to lowest.</span></span>  
  
 [!code-csharp[DP L2E Examples#OrderByDescendingSimple1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#orderbydescendingsimple1)]
 [!code-vb[DP L2E Examples#OrderByDescendingSimple1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#orderbydescendingsimple1)]  
  
## <a name="thenby"></a><span data-ttu-id="d362f-114">ThenBy</span><span class="sxs-lookup"><span data-stu-id="d362f-114">ThenBy</span></span>  
  
### <a name="example"></a><span data-ttu-id="d362f-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d362f-115">Example</span></span>  

 <span data-ttu-id="d362f-116">En el ejemplo siguiente se utiliza <xref:System.Linq.Queryable.OrderBy%2A> y <xref:System.Linq.Queryable.ThenBy%2A> para devolver una lista de contactos ordenados por apellido y luego por nombre.</span><span class="sxs-lookup"><span data-stu-id="d362f-116">The following example uses <xref:System.Linq.Queryable.OrderBy%2A> and <xref:System.Linq.Queryable.ThenBy%2A> to return a list of contacts ordered by last name and then by first name.</span></span>  
  
 [!code-csharp[DP L2E Examples#OrderByThenBy](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#orderbythenby)]
 [!code-vb[DP L2E Examples#OrderByThenBy](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#orderbythenby)]  
  
## <a name="thenbydescending"></a><span data-ttu-id="d362f-117">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="d362f-117">ThenByDescending</span></span>  
  
### <a name="example"></a><span data-ttu-id="d362f-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d362f-118">Example</span></span>  

 <span data-ttu-id="d362f-119">En el ejemplo siguiente se utiliza `OrderBy… Descending`, que es equivalente al método <xref:System.Linq.Enumerable.ThenByDescending%2A>, para ordenar una lista de productos, primero por nombre y después por precio de venta, de mayor a menor.</span><span class="sxs-lookup"><span data-stu-id="d362f-119">The following example uses `OrderBy… Descending`, which is equivalent to the <xref:System.Linq.Enumerable.ThenByDescending%2A> method, to sort a list of products, first by name and then by list price from highest to lowest.</span></span>  
  
 [!code-csharp[DP L2E Examples#ThenByDescendingSimple](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#thenbydescendingsimple)]
 [!code-vb[DP L2E Examples#ThenByDescendingSimple](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#thenbydescendingsimple)]  
  
## <a name="see-also"></a><span data-ttu-id="d362f-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="d362f-120">See also</span></span>

- [<span data-ttu-id="d362f-121">Consultas en LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="d362f-121">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
