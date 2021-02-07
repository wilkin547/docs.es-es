---
description: 'Más información acerca de: Method-Based ejemplos de sintaxis de consultas: operadores de agregado'
title: 'Ejemplos de sintaxis de consulta basada en métodos: Operadores de agregación'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0e306067-5720-4782-9719-2286570a7e47
ms.openlocfilehash: 26398af95398905f2e28c603ef90a04a4a2c56bb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99673620"
---
# <a name="method-based-query-syntax-examples-aggregate-operators"></a><span data-ttu-id="c47e4-103">Ejemplos de sintaxis de consulta basada en métodos: Operadores de agregación</span><span class="sxs-lookup"><span data-stu-id="c47e4-103">Method-Based Query Syntax Examples: Aggregate Operators</span></span>

<span data-ttu-id="c47e4-104">En los ejemplos de este tema se muestra cómo usar <xref:System.Linq.Enumerable.Aggregate%2A> los <xref:System.Linq.Enumerable.Average%2A> métodos,,,,, <xref:System.Linq.Enumerable.Count%2A> <xref:System.Linq.Enumerable.LongCount%2A> <xref:System.Linq.Enumerable.Max%2A> <xref:System.Linq.Enumerable.Min%2A> y <xref:System.Linq.Enumerable.Sum%2A> para consultar el [modelo AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) con la sintaxis de consulta basada en métodos.</span><span class="sxs-lookup"><span data-stu-id="c47e4-104">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Aggregate%2A>, <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.LongCount%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Sum%2A> methods to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using method-based query syntax.</span></span> <span data-ttu-id="c47e4-105">El modelo AdventureWorks Sales que se usa en estos ejemplos se crea a partir de las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="c47e4-105">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="c47e4-106">En los ejemplos de este tema se usan las siguientes `using` / `Imports` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="c47e4-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="average"></a><span data-ttu-id="c47e4-107">Promedio</span><span class="sxs-lookup"><span data-stu-id="c47e4-107">Average</span></span>  
  
### <a name="example"></a><span data-ttu-id="c47e4-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c47e4-108">Example</span></span>  

 <span data-ttu-id="c47e4-109">En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.Average%2A> para encontrar el precio de venta promedio de los productos.</span><span class="sxs-lookup"><span data-stu-id="c47e4-109">The following example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average list price of the products.</span></span>  
  
 [!code-csharp[DP L2E Examples#Average_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#average_mq)]
 [!code-vb[DP L2E Examples#Average_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#average_mq)]  
  
### <a name="example"></a><span data-ttu-id="c47e4-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c47e4-110">Example</span></span>  

 <span data-ttu-id="c47e4-111">En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.Average%2A> para encontrar el precio de venta promedio de los productos de cada estilo.</span><span class="sxs-lookup"><span data-stu-id="c47e4-111">The following example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average list price of the products of each style.</span></span>  
  
 [!code-csharp[DP L2E Examples#Average2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#average2_mq)]
 [!code-vb[DP L2E Examples#Average2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#average2_mq)]  
  
### <a name="example"></a><span data-ttu-id="c47e4-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c47e4-112">Example</span></span>  

 <span data-ttu-id="c47e4-113">En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.Average%2A> para encontrar el importe total promedio a pagar.</span><span class="sxs-lookup"><span data-stu-id="c47e4-113">The following example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average total due.</span></span>  
  
 [!code-csharp[DP L2E Examples#AverageProjection_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#averageprojection_mq)]
 [!code-vb[DP L2E Examples#AverageProjection_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#averageprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="c47e4-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c47e4-114">Example</span></span>  

 <span data-ttu-id="c47e4-115">En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.Average%2A> para obtener el importe total promedio a pagar de cada identificador de contacto.</span><span class="sxs-lookup"><span data-stu-id="c47e4-115">The following example uses the <xref:System.Linq.Enumerable.Average%2A> method to get the average total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#AverageGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#averagegrouped_mq)]
 [!code-vb[DP L2E Examples#AverageGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#averagegrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="c47e4-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c47e4-116">Example</span></span>  

 <span data-ttu-id="c47e4-117">En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.Average%2A> para obtener el pedido con el importe total promedio a pagar de cada contacto.</span><span class="sxs-lookup"><span data-stu-id="c47e4-117">The following example uses the <xref:System.Linq.Enumerable.Average%2A> method to get the orders with the average total due for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#AverageElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#averageelements_mq)]
 [!code-vb[DP L2E Examples#AverageElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#averageelements_mq)]  
  
## <a name="count"></a><span data-ttu-id="c47e4-118">Count</span><span class="sxs-lookup"><span data-stu-id="c47e4-118">Count</span></span>  
  
### <a name="example"></a><span data-ttu-id="c47e4-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c47e4-119">Example</span></span>  

 <span data-ttu-id="c47e4-120">En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.Count%2A> para devolver el número de productos de la tabla Product.</span><span class="sxs-lookup"><span data-stu-id="c47e4-120">The following example uses the <xref:System.Linq.Enumerable.Count%2A> method to return the number of products in the Product table.</span></span>  
  
 [!code-csharp[DP L2E Examples#Count](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#count)]
 [!code-vb[DP L2E Examples#Count](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#count)]  
  
### <a name="example"></a><span data-ttu-id="c47e4-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c47e4-121">Example</span></span>  

 <span data-ttu-id="c47e4-122">En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.Count%2A> para devolver una lista de identificadores de contactos y el número de pedidos que tiene cada uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="c47e4-122">The following example uses the <xref:System.Linq.Enumerable.Count%2A> method to return a list of contact IDs and how many orders each has.</span></span>  
  
 [!code-csharp[DP L2E Examples#CountNested](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#countnested)]
 [!code-vb[DP L2E Examples#CountNested](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#countnested)]  
  
### <a name="example"></a><span data-ttu-id="c47e4-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c47e4-123">Example</span></span>  

 <span data-ttu-id="c47e4-124">En el ejemplo siguiente se agrupan los productos por colores y se utiliza el método <xref:System.Linq.Enumerable.Count%2A> para devolver el número de productos de cada grupo de color.</span><span class="sxs-lookup"><span data-stu-id="c47e4-124">The following example groups products by color and uses the <xref:System.Linq.Enumerable.Count%2A> method to return the number of products in each color group.</span></span>  
  
 [!code-csharp[DP L2E Examples#CountGrouped](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#countgrouped)]
 [!code-vb[DP L2E Examples#CountGrouped](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#countgrouped)]  
  
## <a name="longcount"></a><span data-ttu-id="c47e4-125">LongCount</span><span class="sxs-lookup"><span data-stu-id="c47e4-125">LongCount</span></span>  
  
### <a name="example"></a><span data-ttu-id="c47e4-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c47e4-126">Example</span></span>  

 <span data-ttu-id="c47e4-127">En el ejemplo siguiente se obtiene el recuento de contactos como un entero largo.</span><span class="sxs-lookup"><span data-stu-id="c47e4-127">The following example gets the contact count as a long integer.</span></span>  
  
 [!code-csharp[DP L2E Examples#LongCountSimple](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#longcountsimple)]
 [!code-vb[DP L2E Examples#LongCountSimple](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#longcountsimple)]  
  
## <a name="max"></a><span data-ttu-id="c47e4-128">Max</span><span class="sxs-lookup"><span data-stu-id="c47e4-128">Max</span></span>  
  
### <a name="example"></a><span data-ttu-id="c47e4-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c47e4-129">Example</span></span>  

 <span data-ttu-id="c47e4-130">En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.Max%2A> para obtener el mayor importe total a pagar.</span><span class="sxs-lookup"><span data-stu-id="c47e4-130">The following example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the largest total due.</span></span>  
  
 [!code-csharp[DP L2E Examples#MaxProjection_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#maxprojection_mq)]
 [!code-vb[DP L2E Examples#MaxProjection_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#maxprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="c47e4-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c47e4-131">Example</span></span>  

 <span data-ttu-id="c47e4-132">En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.Max%2A> para obtener el mayor importe total a pagar de cada identificador de contacto.</span><span class="sxs-lookup"><span data-stu-id="c47e4-132">The following example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the largest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#MaxGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#maxgrouped_mq)]
 [!code-vb[DP L2E Examples#MaxGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#maxgrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="c47e4-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c47e4-133">Example</span></span>  

 <span data-ttu-id="c47e4-134">En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.Max%2A> para obtener el pedido con el mayor importe total a pagar de cada identificador de contacto.</span><span class="sxs-lookup"><span data-stu-id="c47e4-134">The following example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the orders with the largest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#MaxElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#maxelements_mq)]
 [!code-vb[DP L2E Examples#MaxElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#maxelements_mq)]  
  
## <a name="min"></a><span data-ttu-id="c47e4-135">Min</span><span class="sxs-lookup"><span data-stu-id="c47e4-135">Min</span></span>  
  
### <a name="example"></a><span data-ttu-id="c47e4-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c47e4-136">Example</span></span>  

 <span data-ttu-id="c47e4-137">En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.Min%2A> para obtener el menor importe total a pagar.</span><span class="sxs-lookup"><span data-stu-id="c47e4-137">The following example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the smallest total due.</span></span>  
  
 [!code-csharp[DP L2E Examples#MinProjection_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#minprojection_mq)]
 [!code-vb[DP L2E Examples#MinProjection_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#minprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="c47e4-138">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c47e4-138">Example</span></span>  

 <span data-ttu-id="c47e4-139">En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.Min%2A> para obtener el menor importe total a pagar de cada identificador de contacto.</span><span class="sxs-lookup"><span data-stu-id="c47e4-139">The following example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the smallest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#MinGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#mingrouped_mq)]
 [!code-vb[DP L2E Examples#MinGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#mingrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="c47e4-140">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c47e4-140">Example</span></span>  

 <span data-ttu-id="c47e4-141">En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.Min%2A> para obtener el pedido con el menor importe total a pagar de cada contacto.</span><span class="sxs-lookup"><span data-stu-id="c47e4-141">The following example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the orders with the smallest total due for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#MinElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#minelements_mq)]
 [!code-vb[DP L2E Examples#MinElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#minelements_mq)]  
  
## <a name="sum"></a><span data-ttu-id="c47e4-142">Sum</span><span class="sxs-lookup"><span data-stu-id="c47e4-142">Sum</span></span>  
  
### <a name="example"></a><span data-ttu-id="c47e4-143">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c47e4-143">Example</span></span>  

 <span data-ttu-id="c47e4-144">En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.Sum%2A> para obtener el número total de cantidades de pedido de la tabla SalesOrderDetail.</span><span class="sxs-lookup"><span data-stu-id="c47e4-144">The following example uses the <xref:System.Linq.Enumerable.Sum%2A> method to get the total number of order quantities in the SalesOrderDetail table.</span></span>  
  
 [!code-csharp[DP L2E Examples#SumProjection_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#sumprojection_mq)]
 [!code-vb[DP L2E Examples#SumProjection_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#sumprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="c47e4-145">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c47e4-145">Example</span></span>  

 <span data-ttu-id="c47e4-146">En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.Sum%2A> para obtener el menor importe total a pagar de cada identificador de contacto.</span><span class="sxs-lookup"><span data-stu-id="c47e4-146">The following example uses the <xref:System.Linq.Enumerable.Sum%2A> method to get the total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#SumGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#sumgrouped_mq)]
 [!code-vb[DP L2E Examples#SumGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#sumgrouped_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="c47e4-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="c47e4-147">See also</span></span>

- [<span data-ttu-id="c47e4-148">Consultas en LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="c47e4-148">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
