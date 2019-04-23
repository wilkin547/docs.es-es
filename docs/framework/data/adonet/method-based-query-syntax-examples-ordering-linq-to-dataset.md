---
title: 'Ejemplos de sintaxis de consulta basada en métodos: Ordenación (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8f9ce4fd-e84f-48c0-bb64-89e217236d3e
ms.openlocfilehash: 76bc4751a25e82a731e136f838d12b8d1c1d691f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59119566"
---
# <a name="method-based-query-syntax-examples-ordering-linq-to-dataset"></a><span data-ttu-id="4b8d4-102">Ejemplos de sintaxis de consulta basada en métodos: Ordenación (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="4b8d4-102">Method-Based Query Syntax Examples: Ordering (LINQ to DataSet)</span></span>
<span data-ttu-id="4b8d4-103">Los ejemplos de este tema muestran cómo se utilizan los métodos <xref:System.Linq.Enumerable.OrderBy%2A>,  <xref:System.Linq.Enumerable.Reverse%2A> y <xref:System.Linq.Enumerable.ThenBy%2A> para consultar <xref:System.Data.DataSet> y ordenar los resultados utilizando la sintaxis de consulta basada en métodos.</span><span class="sxs-lookup"><span data-stu-id="4b8d4-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.OrderBy%2A>,  <xref:System.Linq.Enumerable.Reverse%2A>, and <xref:System.Linq.Enumerable.ThenBy%2A> methods to query a <xref:System.Data.DataSet> and order the results using the method query syntax.</span></span>  
  
 <span data-ttu-id="4b8d4-104">El `FillDataSet` método usado en estos ejemplos se especifica en [cargar datos en un conjunto de datos](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="4b8d4-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="4b8d4-105">Los ejemplos de este tema utilizan las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="4b8d4-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="4b8d4-106">Los ejemplos de este tema usan los siguientes `using` / `Imports` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="4b8d4-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="4b8d4-107">Para obtener más información, vea [Cómo: Crear un proyecto de LINQ to DataSet en Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="4b8d4-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="orderby"></a><span data-ttu-id="4b8d4-108">OrderBy</span><span class="sxs-lookup"><span data-stu-id="4b8d4-108">OrderBy</span></span>  
  
### <a name="example"></a><span data-ttu-id="4b8d4-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4b8d4-109">Example</span></span>  
 <span data-ttu-id="4b8d4-110">Este ejemplo utiliza el método <xref:System.Linq.Enumerable.OrderBy%2A> con un comparador personalizado para realizar una ordenación con distinción de mayúsculas y minúsculas de apellidos.</span><span class="sxs-lookup"><span data-stu-id="4b8d4-110">This example uses the <xref:System.Linq.Enumerable.OrderBy%2A> method with a custom comparer to do a case-insensitive sort of last names.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#OrderByComparer_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#orderbycomparer_mq)]
 [!code-vb[DP LINQ to DataSet Examples#OrderByComparer_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#orderbycomparer_mq)]  
  
## <a name="reverse"></a><span data-ttu-id="4b8d4-111">Reverse</span><span class="sxs-lookup"><span data-stu-id="4b8d4-111">Reverse</span></span>  
  
### <a name="example"></a><span data-ttu-id="4b8d4-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4b8d4-112">Example</span></span>  
 <span data-ttu-id="4b8d4-113">En este ejemplo se utiliza el método <xref:System.Linq.Enumerable.Reverse%2A> para crear una lista de pedidos en los que `OrderDate` es anterior al 20 de febrero de 2002.</span><span class="sxs-lookup"><span data-stu-id="4b8d4-113">This example uses the <xref:System.Linq.Enumerable.Reverse%2A> method to create a list of orders where `OrderDate` is earlier than Feb 20, 2002.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Reverse](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#reverse)]
 [!code-vb[DP LINQ to DataSet Examples#Reverse](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#reverse)]  
  
## <a name="thenby"></a><span data-ttu-id="4b8d4-114">ThenBy</span><span class="sxs-lookup"><span data-stu-id="4b8d4-114">ThenBy</span></span>  
  
### <a name="example"></a><span data-ttu-id="4b8d4-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4b8d4-115">Example</span></span>  
 <span data-ttu-id="4b8d4-116">En este ejemplo se utilizan los métodos <xref:System.Linq.Enumerable.OrderBy%2A> y <xref:System.Linq.Enumerable.ThenBy%2A> con un comparador personalizado para ordenar primero por precio de venta y después realizar una ordenación con distinción de mayúsculas y minúsculas en orden descendente de nombres de producto.</span><span class="sxs-lookup"><span data-stu-id="4b8d4-116">This example uses <xref:System.Linq.Enumerable.OrderBy%2A> and <xref:System.Linq.Enumerable.ThenBy%2A> methods with a custom comparer to first sort by list price, and then perform a case-insensitive descending sort of the product names.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ThenByDescendingComparer_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#thenbydescendingcomparer_mq)]
 [!code-vb[DP LINQ to DataSet Examples#ThenByDescendingComparer_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#thenbydescendingcomparer_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="4b8d4-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="4b8d4-117">See also</span></span>

- [<span data-ttu-id="4b8d4-118">Carga de datos en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="4b8d4-118">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)
- [<span data-ttu-id="4b8d4-119">Ejemplos de LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="4b8d4-119">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
- <span data-ttu-id="4b8d4-120">[Standard Query Operators Overview (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) (Información general sobre operadores de consulta estándar (C#))</span><span class="sxs-lookup"><span data-stu-id="4b8d4-120">[Standard Query Operators Overview (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)</span></span>
- [<span data-ttu-id="4b8d4-121">Información general sobre operadores de consulta estándar (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4b8d4-121">Standard Query Operators Overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
