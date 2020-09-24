---
title: 'Ejemplos de sintaxis de expresiones de consulta: operadores de agregado (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 85dafa07-e102-46e7-ab78-37bf06f257a6
ms.openlocfilehash: 2277058c4dad4632f4f47a39e32463eaf77dcd5e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164576"
---
# <a name="query-expression-syntax-examples-aggregate-operators-linq-to-dataset"></a><span data-ttu-id="0c8f7-102">Ejemplos de sintaxis de expresiones de consulta: operadores de agregado (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="0c8f7-102">Query Expression Syntax Examples: Aggregate Operators (LINQ to DataSet)</span></span>

<span data-ttu-id="0c8f7-103">Los ejemplos de este tema muestran cómo utilizar los métodos <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A> y <xref:System.Linq.Enumerable.Sum%2A> para consultar un <xref:System.Data.DataSet> y agregar datos utilizando sintaxis de expresiones de consulta.</span><span class="sxs-lookup"><span data-stu-id="0c8f7-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Sum%2A> methods to query a <xref:System.Data.DataSet> and aggregate data using query expression syntax.</span></span>  
  
 <span data-ttu-id="0c8f7-104">El `FillDataSet` método utilizado en estos ejemplos se especifica en [cargar datos en un conjunto de datos](loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="0c8f7-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="0c8f7-105">Los ejemplos de este tema utilizan las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="0c8f7-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="0c8f7-106">En los ejemplos de este tema se usan las siguientes `using` / `Imports` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="0c8f7-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="0c8f7-107">Para obtener más información, vea [Cómo: crear un proyecto de LINQ to DataSet en Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="0c8f7-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="average"></a><span data-ttu-id="0c8f7-108">Average</span><span class="sxs-lookup"><span data-stu-id="0c8f7-108">Average</span></span>  
  
### <a name="example"></a><span data-ttu-id="0c8f7-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0c8f7-109">Example</span></span>  

 <span data-ttu-id="0c8f7-110">En este ejemplo se utiliza el método <xref:System.Linq.Enumerable.Average%2A> para encontrar el precio de venta promedio de cada estilo de productos.</span><span class="sxs-lookup"><span data-stu-id="0c8f7-110">This example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average list price of the products of each style.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Average2_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#average2_mq)]
 [!code-vb[DP LINQ to DataSet Examples#Average2_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#average2_mq)]  
  
### <a name="example"></a><span data-ttu-id="0c8f7-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0c8f7-111">Example</span></span>  

 <span data-ttu-id="0c8f7-112">En este ejemplo se utiliza <xref:System.Linq.Enumerable.Average%2A> para obtener el importe total a pagar promedio para cada id. de contacto.</span><span class="sxs-lookup"><span data-stu-id="0c8f7-112">This example uses <xref:System.Linq.Enumerable.Average%2A> to get the average total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#AverageGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#averagegrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#AverageGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#averagegrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="0c8f7-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0c8f7-113">Example</span></span>  

 <span data-ttu-id="0c8f7-114">En este ejemplo se utiliza <xref:System.Linq.Enumerable.Average%2A> para obtener los pedidos con el `TotalDue` promedio para cada de contacto.</span><span class="sxs-lookup"><span data-stu-id="0c8f7-114">This example uses <xref:System.Linq.Enumerable.Average%2A> to get the orders with the average `TotalDue` for each contact.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#AverageElements_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#averageelements_mq)]
 [!code-vb[DP LINQ to DataSet Examples#AverageElements_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#averageelements_mq)]  
  
## <a name="count"></a><span data-ttu-id="0c8f7-115">Count</span><span class="sxs-lookup"><span data-stu-id="0c8f7-115">Count</span></span>  
  
### <a name="example"></a><span data-ttu-id="0c8f7-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0c8f7-116">Example</span></span>  

 <span data-ttu-id="0c8f7-117">En este ejemplo se utiliza <xref:System.Linq.Enumerable.Count%2A> para devolver una lista de id. de contactos y el número de pedidos que tiene cada uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="0c8f7-117">This example uses <xref:System.Linq.Enumerable.Count%2A> to return a list of contact IDs and how many orders each has.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#CountNested](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#countnested)]
 [!code-vb[DP LINQ to DataSet Examples#CountNested](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#countnested)]  
  
### <a name="example"></a><span data-ttu-id="0c8f7-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0c8f7-118">Example</span></span>  

 <span data-ttu-id="0c8f7-119">En este ejemplo se agrupan los productos por colores y se utiliza <xref:System.Linq.Enumerable.Count%2A> para devolver el número de productos de cada grupo de color.</span><span class="sxs-lookup"><span data-stu-id="0c8f7-119">This example groups products by color and uses <xref:System.Linq.Enumerable.Count%2A> to return the number of products in each color group.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#CountGrouped](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#countgrouped)]
 [!code-vb[DP LINQ to DataSet Examples#CountGrouped](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#countgrouped)]  
  
## <a name="max"></a><span data-ttu-id="0c8f7-120">Max</span><span class="sxs-lookup"><span data-stu-id="0c8f7-120">Max</span></span>  
  
### <a name="example"></a><span data-ttu-id="0c8f7-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0c8f7-121">Example</span></span>  

 <span data-ttu-id="0c8f7-122">En este ejemplo se utiliza el método <xref:System.Linq.Enumerable.Max%2A> para obtener el mayor importe total a pagar de cada id. de contacto.</span><span class="sxs-lookup"><span data-stu-id="0c8f7-122">This example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the largest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MaxGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#maxgrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MaxGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#maxgrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="0c8f7-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0c8f7-123">Example</span></span>  

 <span data-ttu-id="0c8f7-124">En este ejemplo se utiliza el método <xref:System.Linq.Enumerable.Max%2A> para obtener los pedidos con el `TotalDue` mayor de cada id. contacto.</span><span class="sxs-lookup"><span data-stu-id="0c8f7-124">This example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the orders with the largest `TotalDue` for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MaxElements_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#maxelements_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MaxElements_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#maxelements_mq)]  
  
## <a name="min"></a><span data-ttu-id="0c8f7-125">Min</span><span class="sxs-lookup"><span data-stu-id="0c8f7-125">Min</span></span>  
  
### <a name="example"></a><span data-ttu-id="0c8f7-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0c8f7-126">Example</span></span>  

 <span data-ttu-id="0c8f7-127">En este ejemplo se utiliza el método <xref:System.Linq.Enumerable.Min%2A> para obtener el menor importe total a pagar de cada id. de contacto.</span><span class="sxs-lookup"><span data-stu-id="0c8f7-127">This example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the smallest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MinGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#mingrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MinGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#mingrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="0c8f7-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0c8f7-128">Example</span></span>  

 <span data-ttu-id="0c8f7-129">En este ejemplo se utiliza el método <xref:System.Linq.Enumerable.Min%2A> para obtener el pedido con el menor importe total a pagar de cada contacto.</span><span class="sxs-lookup"><span data-stu-id="0c8f7-129">This example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the orders with the smallest total due for each contact.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MinElements_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#minelements_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MinElements_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#minelements_mq)]  
  
## <a name="sum"></a><span data-ttu-id="0c8f7-130">Sum</span><span class="sxs-lookup"><span data-stu-id="0c8f7-130">Sum</span></span>  
  
### <a name="example"></a><span data-ttu-id="0c8f7-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0c8f7-131">Example</span></span>  

 <span data-ttu-id="0c8f7-132">En este ejemplo se utiliza el método <xref:System.Linq.Enumerable.Sum%2A> para obtener el importe total a pagar de cada id. de contacto.</span><span class="sxs-lookup"><span data-stu-id="0c8f7-132">This example uses the <xref:System.Linq.Enumerable.Sum%2A> method to get the total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SumGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#sumgrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#SumGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#sumgrouped_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="0c8f7-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0c8f7-133">See also</span></span>

- [<span data-ttu-id="0c8f7-134">Cargar datos en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="0c8f7-134">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
- [<span data-ttu-id="0c8f7-135">Ejemplos de LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="0c8f7-135">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
- [<span data-ttu-id="0c8f7-136">Información general sobre operadores de consulta estándar (C#)</span><span class="sxs-lookup"><span data-stu-id="0c8f7-136">Standard Query Operators Overview (C#)</span></span>](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="0c8f7-137">Información general sobre operadores de consulta estándar (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0c8f7-137">Standard Query Operators Overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
