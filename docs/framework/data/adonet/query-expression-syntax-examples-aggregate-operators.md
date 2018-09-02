---
title: 'Ejemplos de sintaxis de expresiones de consulta: operadores de agregado (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 85dafa07-e102-46e7-ab78-37bf06f257a6
ms.openlocfilehash: fe3bd69b17b98e923c6c31fec2611e7390894e4a
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43398542"
---
# <a name="query-expression-syntax-examples-aggregate-operators-linq-to-dataset"></a><span data-ttu-id="8bdd0-102">Ejemplos de sintaxis de expresiones de consulta: operadores de agregado (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="8bdd0-102">Query Expression Syntax Examples: Aggregate Operators (LINQ to DataSet)</span></span>
<span data-ttu-id="8bdd0-103">Los ejemplos de este tema muestran cómo utilizar los métodos <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A> y <xref:System.Linq.Enumerable.Sum%2A> para consultar un <xref:System.Data.DataSet> y agregar datos utilizando sintaxis de expresiones de consulta.</span><span class="sxs-lookup"><span data-stu-id="8bdd0-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Sum%2A> methods to query a <xref:System.Data.DataSet> and aggregate data using query expression syntax.</span></span>  
  
 <span data-ttu-id="8bdd0-104">El `FillDataSet` método usado en estos ejemplos se especifica en [cargar datos en un conjunto de datos](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="8bdd0-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="8bdd0-105">Los ejemplos de este tema utilizan las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="8bdd0-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="8bdd0-106">Los ejemplos de este tema usan los siguientes `using` / `Imports` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="8bdd0-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="8bdd0-107">Para obtener más información, consulte [Cómo: crear un LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="8bdd0-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="average"></a><span data-ttu-id="8bdd0-108">Average</span><span class="sxs-lookup"><span data-stu-id="8bdd0-108">Average</span></span>  
  
### <a name="example"></a><span data-ttu-id="8bdd0-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8bdd0-109">Example</span></span>  
 <span data-ttu-id="8bdd0-110">En este ejemplo se utiliza el método <xref:System.Linq.Enumerable.Average%2A> para encontrar el precio de venta promedio de cada estilo de productos.</span><span class="sxs-lookup"><span data-stu-id="8bdd0-110">This example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average list price of the products of each style.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Average2_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#average2_mq)]
 [!code-vb[DP LINQ to DataSet Examples#Average2_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#average2_mq)]  
  
### <a name="example"></a><span data-ttu-id="8bdd0-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8bdd0-111">Example</span></span>  
 <span data-ttu-id="8bdd0-112">En este ejemplo se utiliza <xref:System.Linq.Enumerable.Average%2A> para obtener el importe total a pagar promedio para cada id. de contacto.</span><span class="sxs-lookup"><span data-stu-id="8bdd0-112">This example uses <xref:System.Linq.Enumerable.Average%2A> to get the average total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#AverageGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#averagegrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#AverageGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#averagegrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="8bdd0-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8bdd0-113">Example</span></span>  
 <span data-ttu-id="8bdd0-114">En este ejemplo se utiliza <xref:System.Linq.Enumerable.Average%2A> para obtener los pedidos con el `TotalDue` promedio para cada de contacto.</span><span class="sxs-lookup"><span data-stu-id="8bdd0-114">This example uses <xref:System.Linq.Enumerable.Average%2A> to get the orders with the average `TotalDue` for each contact.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#AverageElements_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#averageelements_mq)]
 [!code-vb[DP LINQ to DataSet Examples#AverageElements_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#averageelements_mq)]  
  
## <a name="count"></a><span data-ttu-id="8bdd0-115">Count</span><span class="sxs-lookup"><span data-stu-id="8bdd0-115">Count</span></span>  
  
### <a name="example"></a><span data-ttu-id="8bdd0-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8bdd0-116">Example</span></span>  
 <span data-ttu-id="8bdd0-117">En este ejemplo se utiliza <xref:System.Linq.Enumerable.Count%2A> para devolver una lista de id. de contactos y el número de pedidos que tiene cada uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="8bdd0-117">This example uses <xref:System.Linq.Enumerable.Count%2A> to return a list of contact IDs and how many orders each has.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#CountNested](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#countnested)]
 [!code-vb[DP LINQ to DataSet Examples#CountNested](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#countnested)]  
  
### <a name="example"></a><span data-ttu-id="8bdd0-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8bdd0-118">Example</span></span>  
 <span data-ttu-id="8bdd0-119">En este ejemplo se agrupan los productos por colores y se utiliza <xref:System.Linq.Enumerable.Count%2A> para devolver el número de productos de cada grupo de color.</span><span class="sxs-lookup"><span data-stu-id="8bdd0-119">This example groups products by color and uses <xref:System.Linq.Enumerable.Count%2A> to return the number of products in each color group.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#CountGrouped](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#countgrouped)]
 [!code-vb[DP LINQ to DataSet Examples#CountGrouped](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#countgrouped)]  
  
## <a name="max"></a><span data-ttu-id="8bdd0-120">Max</span><span class="sxs-lookup"><span data-stu-id="8bdd0-120">Max</span></span>  
  
### <a name="example"></a><span data-ttu-id="8bdd0-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8bdd0-121">Example</span></span>  
 <span data-ttu-id="8bdd0-122">En este ejemplo se utiliza el método <xref:System.Linq.Enumerable.Max%2A> para obtener el mayor importe total a pagar de cada id. de contacto.</span><span class="sxs-lookup"><span data-stu-id="8bdd0-122">This example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the largest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MaxGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#maxgrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MaxGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#maxgrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="8bdd0-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8bdd0-123">Example</span></span>  
 <span data-ttu-id="8bdd0-124">En este ejemplo se utiliza el método <xref:System.Linq.Enumerable.Max%2A> para obtener los pedidos con el `TotalDue` mayor de cada id. contacto.</span><span class="sxs-lookup"><span data-stu-id="8bdd0-124">This example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the orders with the largest `TotalDue` for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MaxElements_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#maxelements_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MaxElements_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#maxelements_mq)]  
  
## <a name="min"></a><span data-ttu-id="8bdd0-125">Min</span><span class="sxs-lookup"><span data-stu-id="8bdd0-125">Min</span></span>  
  
### <a name="example"></a><span data-ttu-id="8bdd0-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8bdd0-126">Example</span></span>  
 <span data-ttu-id="8bdd0-127">En este ejemplo se utiliza el método <xref:System.Linq.Enumerable.Min%2A> para obtener el menor importe total a pagar de cada id. de contacto.</span><span class="sxs-lookup"><span data-stu-id="8bdd0-127">This example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the smallest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MinGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#mingrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MinGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#mingrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="8bdd0-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8bdd0-128">Example</span></span>  
 <span data-ttu-id="8bdd0-129">En este ejemplo se utiliza el método <xref:System.Linq.Enumerable.Min%2A> para obtener el pedido con el menor importe total a pagar de cada contacto.</span><span class="sxs-lookup"><span data-stu-id="8bdd0-129">This example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the orders with the smallest total due for each contact.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MinElements_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#minelements_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MinElements_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#minelements_mq)]  
  
## <a name="sum"></a><span data-ttu-id="8bdd0-130">Sum</span><span class="sxs-lookup"><span data-stu-id="8bdd0-130">Sum</span></span>  
  
### <a name="example"></a><span data-ttu-id="8bdd0-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8bdd0-131">Example</span></span>  
 <span data-ttu-id="8bdd0-132">En este ejemplo se utiliza el método <xref:System.Linq.Enumerable.Sum%2A> para obtener el importe total a pagar de cada id. de contacto.</span><span class="sxs-lookup"><span data-stu-id="8bdd0-132">This example uses the <xref:System.Linq.Enumerable.Sum%2A> method to get the total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SumGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#sumgrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#SumGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#sumgrouped_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="8bdd0-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="8bdd0-133">See Also</span></span>  
 [<span data-ttu-id="8bdd0-134">Carga de datos en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="8bdd0-134">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [<span data-ttu-id="8bdd0-135">Ejemplos de LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="8bdd0-135">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 [<span data-ttu-id="8bdd0-136">Información general sobre operadores de consulta estándar</span><span class="sxs-lookup"><span data-stu-id="8bdd0-136">Standard Query Operators Overview</span></span>](https://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)
