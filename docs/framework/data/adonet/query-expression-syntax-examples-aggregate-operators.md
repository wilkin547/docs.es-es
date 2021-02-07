---
description: 'Más información acerca de: ejemplos de sintaxis de expresiones de consulta: operadores de agregado (LINQ to DataSet)'
title: 'Ejemplos de sintaxis de expresiones de consulta: operadores de agregado (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 85dafa07-e102-46e7-ab78-37bf06f257a6
ms.openlocfilehash: 9076f81a21892f467355c86871e49ae3e1a793e9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99663643"
---
# <a name="query-expression-syntax-examples-aggregate-operators-linq-to-dataset"></a><span data-ttu-id="03202-103">Ejemplos de sintaxis de expresiones de consulta: operadores de agregado (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="03202-103">Query Expression Syntax Examples: Aggregate Operators (LINQ to DataSet)</span></span>

<span data-ttu-id="03202-104">Los ejemplos de este tema muestran cómo utilizar los métodos <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A> y <xref:System.Linq.Enumerable.Sum%2A> para consultar un <xref:System.Data.DataSet> y agregar datos utilizando sintaxis de expresiones de consulta.</span><span class="sxs-lookup"><span data-stu-id="03202-104">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Sum%2A> methods to query a <xref:System.Data.DataSet> and aggregate data using query expression syntax.</span></span>  
  
 <span data-ttu-id="03202-105">El `FillDataSet` método utilizado en estos ejemplos se especifica en [cargar datos en un conjunto de datos](loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="03202-105">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="03202-106">Los ejemplos de este tema utilizan las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="03202-106">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="03202-107">En los ejemplos de este tema se usan las siguientes `using` / `Imports` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="03202-107">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="03202-108">Para obtener más información, vea [Cómo: crear un proyecto de LINQ to DataSet en Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="03202-108">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="average"></a><span data-ttu-id="03202-109">Promedio</span><span class="sxs-lookup"><span data-stu-id="03202-109">Average</span></span>  
  
### <a name="example"></a><span data-ttu-id="03202-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="03202-110">Example</span></span>  

 <span data-ttu-id="03202-111">En este ejemplo se utiliza el método <xref:System.Linq.Enumerable.Average%2A> para encontrar el precio de venta promedio de cada estilo de productos.</span><span class="sxs-lookup"><span data-stu-id="03202-111">This example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average list price of the products of each style.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Average2_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#average2_mq)]
 [!code-vb[DP LINQ to DataSet Examples#Average2_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#average2_mq)]  
  
### <a name="example"></a><span data-ttu-id="03202-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="03202-112">Example</span></span>  

 <span data-ttu-id="03202-113">En este ejemplo se utiliza <xref:System.Linq.Enumerable.Average%2A> para obtener el importe total a pagar promedio para cada id. de contacto.</span><span class="sxs-lookup"><span data-stu-id="03202-113">This example uses <xref:System.Linq.Enumerable.Average%2A> to get the average total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#AverageGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#averagegrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#AverageGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#averagegrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="03202-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="03202-114">Example</span></span>  

 <span data-ttu-id="03202-115">En este ejemplo se utiliza <xref:System.Linq.Enumerable.Average%2A> para obtener los pedidos con el `TotalDue` promedio para cada de contacto.</span><span class="sxs-lookup"><span data-stu-id="03202-115">This example uses <xref:System.Linq.Enumerable.Average%2A> to get the orders with the average `TotalDue` for each contact.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#AverageElements_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#averageelements_mq)]
 [!code-vb[DP LINQ to DataSet Examples#AverageElements_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#averageelements_mq)]  
  
## <a name="count"></a><span data-ttu-id="03202-116">Count</span><span class="sxs-lookup"><span data-stu-id="03202-116">Count</span></span>  
  
### <a name="example"></a><span data-ttu-id="03202-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="03202-117">Example</span></span>  

 <span data-ttu-id="03202-118">En este ejemplo se utiliza <xref:System.Linq.Enumerable.Count%2A> para devolver una lista de id. de contactos y el número de pedidos que tiene cada uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="03202-118">This example uses <xref:System.Linq.Enumerable.Count%2A> to return a list of contact IDs and how many orders each has.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#CountNested](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#countnested)]
 [!code-vb[DP LINQ to DataSet Examples#CountNested](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#countnested)]  
  
### <a name="example"></a><span data-ttu-id="03202-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="03202-119">Example</span></span>  

 <span data-ttu-id="03202-120">En este ejemplo se agrupan los productos por colores y se utiliza <xref:System.Linq.Enumerable.Count%2A> para devolver el número de productos de cada grupo de color.</span><span class="sxs-lookup"><span data-stu-id="03202-120">This example groups products by color and uses <xref:System.Linq.Enumerable.Count%2A> to return the number of products in each color group.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#CountGrouped](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#countgrouped)]
 [!code-vb[DP LINQ to DataSet Examples#CountGrouped](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#countgrouped)]  
  
## <a name="max"></a><span data-ttu-id="03202-121">Max</span><span class="sxs-lookup"><span data-stu-id="03202-121">Max</span></span>  
  
### <a name="example"></a><span data-ttu-id="03202-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="03202-122">Example</span></span>  

 <span data-ttu-id="03202-123">En este ejemplo se utiliza el método <xref:System.Linq.Enumerable.Max%2A> para obtener el mayor importe total a pagar de cada id. de contacto.</span><span class="sxs-lookup"><span data-stu-id="03202-123">This example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the largest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MaxGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#maxgrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MaxGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#maxgrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="03202-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="03202-124">Example</span></span>  

 <span data-ttu-id="03202-125">En este ejemplo se utiliza el método <xref:System.Linq.Enumerable.Max%2A> para obtener los pedidos con el `TotalDue` mayor de cada id. contacto.</span><span class="sxs-lookup"><span data-stu-id="03202-125">This example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the orders with the largest `TotalDue` for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MaxElements_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#maxelements_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MaxElements_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#maxelements_mq)]  
  
## <a name="min"></a><span data-ttu-id="03202-126">Min</span><span class="sxs-lookup"><span data-stu-id="03202-126">Min</span></span>  
  
### <a name="example"></a><span data-ttu-id="03202-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="03202-127">Example</span></span>  

 <span data-ttu-id="03202-128">En este ejemplo se utiliza el método <xref:System.Linq.Enumerable.Min%2A> para obtener el menor importe total a pagar de cada id. de contacto.</span><span class="sxs-lookup"><span data-stu-id="03202-128">This example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the smallest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MinGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#mingrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MinGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#mingrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="03202-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="03202-129">Example</span></span>  

 <span data-ttu-id="03202-130">En este ejemplo se utiliza el método <xref:System.Linq.Enumerable.Min%2A> para obtener el pedido con el menor importe total a pagar de cada contacto.</span><span class="sxs-lookup"><span data-stu-id="03202-130">This example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the orders with the smallest total due for each contact.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MinElements_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#minelements_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MinElements_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#minelements_mq)]  
  
## <a name="sum"></a><span data-ttu-id="03202-131">Sum</span><span class="sxs-lookup"><span data-stu-id="03202-131">Sum</span></span>  
  
### <a name="example"></a><span data-ttu-id="03202-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="03202-132">Example</span></span>  

 <span data-ttu-id="03202-133">En este ejemplo se utiliza el método <xref:System.Linq.Enumerable.Sum%2A> para obtener el importe total a pagar de cada id. de contacto.</span><span class="sxs-lookup"><span data-stu-id="03202-133">This example uses the <xref:System.Linq.Enumerable.Sum%2A> method to get the total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SumGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#sumgrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#SumGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#sumgrouped_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="03202-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="03202-134">See also</span></span>

- [<span data-ttu-id="03202-135">Cargar datos en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="03202-135">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
- [<span data-ttu-id="03202-136">Ejemplos de LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="03202-136">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
- [<span data-ttu-id="03202-137">Información general sobre operadores de consulta estándar (C#)</span><span class="sxs-lookup"><span data-stu-id="03202-137">Standard Query Operators Overview (C#)</span></span>](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="03202-138">Información general sobre operadores de consulta estándar (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="03202-138">Standard Query Operators Overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
