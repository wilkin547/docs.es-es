---
title: "Ejemplos de sintaxis de consulta basada en métodos: operadores de agregado (LINQ to DataSet)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 5ed5f01d-acb2-4dd4-be60-f04c2d570fa8
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: bfb558c1904af7ba5f0cbfeaf63ee02b1c736553
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="method-based-query-syntax-examples-aggregate-operators-linq-to-dataset"></a><span data-ttu-id="21ba6-102">Ejemplos de sintaxis de consulta basada en métodos: operadores de agregado (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="21ba6-102">Method-Based Query Syntax Examples: Aggregate Operators (LINQ to DataSet)</span></span>
<span data-ttu-id="21ba6-103">Los ejemplos de este tema muestran cómo utilizar los operadores <xref:System.Linq.Enumerable.Aggregate%2A>, <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.LongCount%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A> y <xref:System.Linq.Enumerable.Sum%2A> para consultar <xref:System.Data.DataSet> y agregar datos utilizando sintaxis de consulta basada en métodos.</span><span class="sxs-lookup"><span data-stu-id="21ba6-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Aggregate%2A>, <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.LongCount%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Sum%2A> operators to query a <xref:System.Data.DataSet> and aggregate data using method query syntax.</span></span>  
  
 <span data-ttu-id="21ba6-104">El `FillDataSet` método que se usa en estos ejemplos se especifica en [cargar datos en un conjunto de datos](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="21ba6-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="21ba6-105">Los ejemplos de este tema utilizan las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="21ba6-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="21ba6-106">Los ejemplos de este tema usan los siguientes `using` / `Imports` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="21ba6-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="21ba6-107">Para obtener más información, consulte [Cómo: crear un LINQ to DataSet proyecto en Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="21ba6-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="aggregate"></a><span data-ttu-id="21ba6-108">Agregar</span><span class="sxs-lookup"><span data-stu-id="21ba6-108">Aggregate</span></span>  
  
### <a name="example"></a><span data-ttu-id="21ba6-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="21ba6-109">Example</span></span>  
 <span data-ttu-id="21ba6-110">En este ejemplo se utiliza el método <xref:System.Linq.Enumerable.Aggregate%2A> para obtener los cinco primeros contactos de la tabla `Contact` y compilar una lista de apellidos delimitada por comas.</span><span class="sxs-lookup"><span data-stu-id="21ba6-110">This example uses the <xref:System.Linq.Enumerable.Aggregate%2A> method to get the first 5 contacts from the `Contact` table and build a comma-delimited list of the last names.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Aggregate_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#aggregate_mq)]
 [!code-vb[DP LINQ to DataSet Examples#Aggregate_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#aggregate_mq)]  
  
## <a name="average"></a><span data-ttu-id="21ba6-111">Average</span><span class="sxs-lookup"><span data-stu-id="21ba6-111">Average</span></span>  
  
### <a name="example"></a><span data-ttu-id="21ba6-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="21ba6-112">Example</span></span>  
 <span data-ttu-id="21ba6-113">En este ejemplo se utiliza el método <xref:System.Linq.Enumerable.Average%2A> para encontrar el precio de venta promedio de los productos.</span><span class="sxs-lookup"><span data-stu-id="21ba6-113">This example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average list price of the products.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Average_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#average_mq)]
 [!code-vb[DP LINQ to DataSet Examples#Average_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#average_mq)]  
  
### <a name="example"></a><span data-ttu-id="21ba6-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="21ba6-114">Example</span></span>  
 <span data-ttu-id="21ba6-115">En este ejemplo se utiliza el método <xref:System.Linq.Enumerable.Average%2A> para encontrar el precio de venta promedio de cada estilo de productos.</span><span class="sxs-lookup"><span data-stu-id="21ba6-115">This example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average list price of the products of each style.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Average2_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#average2_mq)]
 [!code-vb[DP LINQ to DataSet Examples#Average2_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#average2_mq)]  
  
### <a name="example"></a><span data-ttu-id="21ba6-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="21ba6-116">Example</span></span>  
 <span data-ttu-id="21ba6-117">En este ejemplo se utiliza el método <xref:System.Linq.Enumerable.Average%2A> para encontrar el importe total a pagar promedio.</span><span class="sxs-lookup"><span data-stu-id="21ba6-117">This example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average total due.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#AverageProjection_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#averageprojection_mq)]
 [!code-vb[DP LINQ to DataSet Examples#AverageProjection_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#averageprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="21ba6-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="21ba6-118">Example</span></span>  
 <span data-ttu-id="21ba6-119">En este ejemplo se utiliza el método <xref:System.Linq.Enumerable.Average%2A> para obtener el importe total a pagar promedio de cada id. de contacto.</span><span class="sxs-lookup"><span data-stu-id="21ba6-119">This example uses the <xref:System.Linq.Enumerable.Average%2A> method to get the average total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#AverageGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#averagegrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#AverageGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#averagegrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="21ba6-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="21ba6-120">Example</span></span>  
 <span data-ttu-id="21ba6-121">En este ejemplo se utiliza el método <xref:System.Linq.Enumerable.Average%2A> para obtener los pedidos con el `TotalDue` promedio de cada contacto.</span><span class="sxs-lookup"><span data-stu-id="21ba6-121">This example uses the <xref:System.Linq.Enumerable.Average%2A> method to get the orders with the average `TotalDue` for each contact.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#AverageElements_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#averageelements_mq)]
 [!code-vb[DP LINQ to DataSet Examples#AverageElements_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#averageelements_mq)]  
  
## <a name="count"></a><span data-ttu-id="21ba6-122">Count</span><span class="sxs-lookup"><span data-stu-id="21ba6-122">Count</span></span>  
  
### <a name="example"></a><span data-ttu-id="21ba6-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="21ba6-123">Example</span></span>  
 <span data-ttu-id="21ba6-124">En este ejemplo se utiliza el método <xref:System.Linq.Enumerable.Count%2A> para devolver el número de productos de la tabla `Product`.</span><span class="sxs-lookup"><span data-stu-id="21ba6-124">This example uses the <xref:System.Linq.Enumerable.Count%2A> method to return the number of products in the `Product` table.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Count](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#count)]
 [!code-vb[DP LINQ to DataSet Examples#Count](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#count)]  
  
### <a name="example"></a><span data-ttu-id="21ba6-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="21ba6-125">Example</span></span>  
 <span data-ttu-id="21ba6-126">En este ejemplo se utiliza el método <xref:System.Linq.Enumerable.Count%2A> para devolver una lista de id. de contactos y el número de pedidos que tiene cada uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="21ba6-126">This example uses the <xref:System.Linq.Enumerable.Count%2A> method to return a list of contact IDs and how many orders each has.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#CountNested](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#countnested)]
 [!code-vb[DP LINQ to DataSet Examples#CountNested](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#countnested)]  
  
### <a name="example"></a><span data-ttu-id="21ba6-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="21ba6-127">Example</span></span>  
 <span data-ttu-id="21ba6-128">En este ejemplo se agrupan los productos por colores y se utiliza el método <xref:System.Linq.Enumerable.Count%2A> para devolver el número de productos de cada grupo de color.</span><span class="sxs-lookup"><span data-stu-id="21ba6-128">This example groups products by color and uses the <xref:System.Linq.Enumerable.Count%2A> method to return the number of products in each color group.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#CountGrouped](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#countgrouped)]
 [!code-vb[DP LINQ to DataSet Examples#CountGrouped](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#countgrouped)]  
  
## <a name="longcount"></a><span data-ttu-id="21ba6-129">LongCount</span><span class="sxs-lookup"><span data-stu-id="21ba6-129">LongCount</span></span>  
  
### <a name="example"></a><span data-ttu-id="21ba6-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="21ba6-130">Example</span></span>  
 <span data-ttu-id="21ba6-131">En este ejemplo se obtiene el recuento de contactos como un entero largo.</span><span class="sxs-lookup"><span data-stu-id="21ba6-131">This example gets the contact count as a long integer.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#LongCountSimple](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#longcountsimple)]
 [!code-vb[DP LINQ to DataSet Examples#LongCountSimple](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#longcountsimple)]  
  
## <a name="max"></a><span data-ttu-id="21ba6-132">Max</span><span class="sxs-lookup"><span data-stu-id="21ba6-132">Max</span></span>  
  
### <a name="example"></a><span data-ttu-id="21ba6-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="21ba6-133">Example</span></span>  
 <span data-ttu-id="21ba6-134">En este ejemplo se utiliza el método <xref:System.Linq.Enumerable.Max%2A> para obtener el mayor importe total a pagar.</span><span class="sxs-lookup"><span data-stu-id="21ba6-134">This example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the largest total due.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MaxProjection_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#maxprojection_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MaxProjection_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#maxprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="21ba6-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="21ba6-135">Example</span></span>  
 <span data-ttu-id="21ba6-136">En este ejemplo se utiliza el método <xref:System.Linq.Enumerable.Max%2A> para obtener el mayor importe total a pagar de cada id. de contacto.</span><span class="sxs-lookup"><span data-stu-id="21ba6-136">This example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the largest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MaxGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#maxgrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MaxGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#maxgrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="21ba6-137">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="21ba6-137">Example</span></span>  
 <span data-ttu-id="21ba6-138">En este ejemplo se utiliza el método <xref:System.Linq.Enumerable.Max%2A> para obtener los pedidos con el `TotalDue` mayor de cada id. contacto.</span><span class="sxs-lookup"><span data-stu-id="21ba6-138">This example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the orders with the largest `TotalDue` for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MaxElements_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#maxelements_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MaxElements_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#maxelements_mq)]  
  
## <a name="min"></a><span data-ttu-id="21ba6-139">Min</span><span class="sxs-lookup"><span data-stu-id="21ba6-139">Min</span></span>  
  
### <a name="example"></a><span data-ttu-id="21ba6-140">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="21ba6-140">Example</span></span>  
 <span data-ttu-id="21ba6-141">En este ejemplo se utiliza el método <xref:System.Linq.Enumerable.Min%2A> para obtener el menor importe total a pagar.</span><span class="sxs-lookup"><span data-stu-id="21ba6-141">This example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the smallest total due.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MinProjection_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#minprojection_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MinProjection_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#minprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="21ba6-142">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="21ba6-142">Example</span></span>  
 <span data-ttu-id="21ba6-143">En este ejemplo se utiliza el método <xref:System.Linq.Enumerable.Min%2A> para obtener el menor importe total a pagar de cada id. de contacto.</span><span class="sxs-lookup"><span data-stu-id="21ba6-143">This example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the smallest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MinGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#mingrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MinGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#mingrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="21ba6-144">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="21ba6-144">Example</span></span>  
 <span data-ttu-id="21ba6-145">En este ejemplo se utiliza el método <xref:System.Linq.Enumerable.Min%2A> para obtener el pedido con el menor importe total a pagar de cada contacto.</span><span class="sxs-lookup"><span data-stu-id="21ba6-145">This example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the orders with the smallest total due for each contact.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MinElements_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#minelements_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MinElements_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#minelements_mq)]  
  
## <a name="sum"></a><span data-ttu-id="21ba6-146">Sum</span><span class="sxs-lookup"><span data-stu-id="21ba6-146">Sum</span></span>  
  
### <a name="example"></a><span data-ttu-id="21ba6-147">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="21ba6-147">Example</span></span>  
 <span data-ttu-id="21ba6-148">En este ejemplo se utiliza el método <xref:System.Linq.Enumerable.Sum%2A> para obtener el número total de cantidades de pedido de la tabla `SalesOrderDetail`.</span><span class="sxs-lookup"><span data-stu-id="21ba6-148">This example uses the <xref:System.Linq.Enumerable.Sum%2A> method to get the total number of order quantities in the `SalesOrderDetail` table.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SumProjection_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#sumprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="21ba6-149">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="21ba6-149">Example</span></span>  
 <span data-ttu-id="21ba6-150">En este ejemplo se utiliza el método <xref:System.Linq.Enumerable.Sum%2A> para obtener el importe total a pagar de cada id. de contacto.</span><span class="sxs-lookup"><span data-stu-id="21ba6-150">This example uses the <xref:System.Linq.Enumerable.Sum%2A> method to get the total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SumGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#sumgrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#SumGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#sumgrouped_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="21ba6-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="21ba6-151">See Also</span></span>  
 [<span data-ttu-id="21ba6-152">Carga de datos en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="21ba6-152">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [<span data-ttu-id="21ba6-153">Ejemplos de LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="21ba6-153">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 [<span data-ttu-id="21ba6-154">Información general sobre operadores de consulta estándar</span><span class="sxs-lookup"><span data-stu-id="21ba6-154">Standard Query Operators Overview</span></span>](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)
