---
title: 'Ejemplos de sintaxis de expresiones de consulta: Ordenación (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 653a4a97-1e4a-4b2d-8d24-7dbe1f2a5c84
ms.openlocfilehash: 932f5e4f6073844a951d06dabec45e5ff3e743bf
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782994"
---
# <a name="query-expression-syntax-examples-ordering-linq-to-dataset"></a><span data-ttu-id="c6f32-102">Ejemplos de sintaxis de expresiones de consulta: Ordenación (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="c6f32-102">Query Expression Syntax Examples: Ordering (LINQ to DataSet)</span></span>
<span data-ttu-id="c6f32-103">Los ejemplos de este tema muestran cómo se utilizan los métodos <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.OrderByDescending%2A>, <xref:System.Linq.Enumerable.Reverse%2A> y <xref:System.Linq.Enumerable.ThenByDescending%2A> para consultar <xref:System.Data.DataSet> y ordenar los resultados utilizando la sintaxis de expresiones de consultas.</span><span class="sxs-lookup"><span data-stu-id="c6f32-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.OrderByDescending%2A>, <xref:System.Linq.Enumerable.Reverse%2A>, and <xref:System.Linq.Enumerable.ThenByDescending%2A> methods to query a <xref:System.Data.DataSet> and order the results using the query expression syntax.</span></span>  
  
 <span data-ttu-id="c6f32-104">El `FillDataSet` método utilizado en estos ejemplos se especifica en [cargar datos en un conjunto de datos](loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="c6f32-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="c6f32-105">Los ejemplos de este tema utilizan las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="c6f32-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="c6f32-106">En los ejemplos de este tema se usan `using` las siguientes / `Imports` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="c6f32-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="c6f32-107">Para obtener más información, vea [Cómo: Cree un proyecto de LINQ to DataSet en Visual](how-to-create-a-linq-to-dataset-project-in-vs.md)Studio.</span><span class="sxs-lookup"><span data-stu-id="c6f32-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="orderby"></a><span data-ttu-id="c6f32-108">OrderBy</span><span class="sxs-lookup"><span data-stu-id="c6f32-108">OrderBy</span></span>  
  
### <a name="example"></a><span data-ttu-id="c6f32-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c6f32-109">Example</span></span>  
 <span data-ttu-id="c6f32-110">En este ejemplo se utiliza <xref:System.Linq.Enumerable.OrderBy%2A> para devolver una lista de contactos organizados por apellido.</span><span class="sxs-lookup"><span data-stu-id="c6f32-110">This example uses <xref:System.Linq.Enumerable.OrderBy%2A> to return a list of contacts ordered by last name.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#OrderBySimple1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#orderbysimple1)]
 [!code-vb[DP LINQ to DataSet Examples#OrderBySimple1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#orderbysimple1)]  
  
### <a name="example"></a><span data-ttu-id="c6f32-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c6f32-111">Example</span></span>  
 <span data-ttu-id="c6f32-112">En este ejemplo se utiliza <xref:System.Linq.Enumerable.OrderBy%2A> para ordenar una lista de contactos por longitud del apellido.</span><span class="sxs-lookup"><span data-stu-id="c6f32-112">This example uses <xref:System.Linq.Enumerable.OrderBy%2A> to sort a list of contacts by length of last name.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#OrderBySimple2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#orderbysimple2)]
 [!code-vb[DP LINQ to DataSet Examples#OrderBySimple2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#orderbysimple2)]  
  
## <a name="orderbydescending"></a><span data-ttu-id="c6f32-113">OrderByDescending</span><span class="sxs-lookup"><span data-stu-id="c6f32-113">OrderByDescending</span></span>  
  
### <a name="example"></a><span data-ttu-id="c6f32-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c6f32-114">Example</span></span>  
 <span data-ttu-id="c6f32-115">En este ejemplo se utiliza `orderby… descending` (`Order By … Descending`), equivalente al método <xref:System.Linq.Enumerable.OrderByDescending%2A>, para ordenar el precio de venta de mayor a menor.</span><span class="sxs-lookup"><span data-stu-id="c6f32-115">This example uses `orderby… descending` (`Order By … Descending`), which is equivalent to the <xref:System.Linq.Enumerable.OrderByDescending%2A> method, to sort the price list from highest to lowest.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#OrderByDescendingSimple1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#orderbydescendingsimple1)]
 [!code-vb[DP LINQ to DataSet Examples#OrderByDescendingSimple1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#orderbydescendingsimple1)]  
  
## <a name="reverse"></a><span data-ttu-id="c6f32-116">Reverse</span><span class="sxs-lookup"><span data-stu-id="c6f32-116">Reverse</span></span>  
  
### <a name="example"></a><span data-ttu-id="c6f32-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c6f32-117">Example</span></span>  
 <span data-ttu-id="c6f32-118">En este ejemplo se utiliza <xref:System.Linq.Enumerable.Reverse%2A> para crear una lista de pedidos en los que `OrderDate` es anterior al 20 de febrero de 2002.</span><span class="sxs-lookup"><span data-stu-id="c6f32-118">This example uses <xref:System.Linq.Enumerable.Reverse%2A> to create a list of orders where `OrderDate` is earlier than Feb 20, 2002.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Reverse](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#reverse)]
 [!code-vb[DP LINQ to DataSet Examples#Reverse](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#reverse)]  
  
## <a name="thenbydescending"></a><span data-ttu-id="c6f32-119">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="c6f32-119">ThenByDescending</span></span>  
  
### <a name="example"></a><span data-ttu-id="c6f32-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c6f32-120">Example</span></span>  
 <span data-ttu-id="c6f32-121">En este ejemplo se utiliza `OrderBy… Descending`, que es equivalente al método <xref:System.Linq.Enumerable.ThenByDescending%2A>, para ordenar una lista de productos, primero por nombre y después por precio de venta, de mayor a menor.</span><span class="sxs-lookup"><span data-stu-id="c6f32-121">This example uses `OrderBy… Descending` , which is equivalent to the <xref:System.Linq.Enumerable.ThenByDescending%2A> method, to sort a list of products, first by name and then by list price, from highest to lowest.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ThenByDescendingSimple](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#thenbydescendingsimple)]
 [!code-vb[DP LINQ to DataSet Examples#ThenByDescendingSimple](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#thenbydescendingsimple)]  
  
## <a name="see-also"></a><span data-ttu-id="c6f32-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="c6f32-122">See also</span></span>

- [<span data-ttu-id="c6f32-123">Carga de datos en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="c6f32-123">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
- [<span data-ttu-id="c6f32-124">Ejemplos de LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="c6f32-124">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
- <span data-ttu-id="c6f32-125">[Standard Query Operators Overview (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) (Información general sobre operadores de consulta estándar (C#))</span><span class="sxs-lookup"><span data-stu-id="c6f32-125">[Standard Query Operators Overview (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)</span></span>
- [<span data-ttu-id="c6f32-126">Información general sobre operadores de consulta estándar (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c6f32-126">Standard Query Operators Overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
