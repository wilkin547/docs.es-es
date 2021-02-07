---
description: 'Más información acerca de: ejemplos de sintaxis de expresiones de consulta: operadores de agregado'
title: 'Ejemplos de sintaxis de expresiones de consulta: Operadores de agregado'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d729120c-4c1b-4f34-bbe9-33694fca2dde
ms.openlocfilehash: c0fd9c3faf770a00a54341cf3718c2dda91a4d7b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99767939"
---
# <a name="query-expression-syntax-examples-aggregate-operators"></a><span data-ttu-id="0ab6f-103">Ejemplos de sintaxis de expresiones de consulta: Operadores de agregado</span><span class="sxs-lookup"><span data-stu-id="0ab6f-103">Query Expression Syntax Examples: Aggregate Operators</span></span>

<span data-ttu-id="0ab6f-104">Los ejemplos de este tema muestran cómo usar los <xref:System.Linq.Enumerable.Average%2A> métodos, <xref:System.Linq.Enumerable.Count%2A> , <xref:System.Linq.Enumerable.Max%2A> , <xref:System.Linq.Enumerable.Min%2A> y <xref:System.Linq.Enumerable.Sum%2A> para consultar el [modelo AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) con la sintaxis de las expresiones de consulta.</span><span class="sxs-lookup"><span data-stu-id="0ab6f-104">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Sum%2A> methods to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using query expression syntax.</span></span> <span data-ttu-id="0ab6f-105">El modelo AdventureWorks Sales que se usa en estos ejemplos se crea a partir de las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="0ab6f-105">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="0ab6f-106">En los ejemplos de este tema se usan las siguientes `using` / `Imports` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="0ab6f-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="average"></a><span data-ttu-id="0ab6f-107">Promedio</span><span class="sxs-lookup"><span data-stu-id="0ab6f-107">Average</span></span>  
  
### <a name="example"></a><span data-ttu-id="0ab6f-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0ab6f-108">Example</span></span>  

 <span data-ttu-id="0ab6f-109">En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.Average%2A> para encontrar el precio de venta promedio de los productos de cada estilo.</span><span class="sxs-lookup"><span data-stu-id="0ab6f-109">The following example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average list price of the products of each style.</span></span>  
  
 [!code-csharp[DP L2E Examples#Average2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#average2_mq)]
 [!code-vb[DP L2E Examples#Average2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#average2_mq)]  
  
### <a name="example"></a><span data-ttu-id="0ab6f-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0ab6f-110">Example</span></span>  

 <span data-ttu-id="0ab6f-111">En el ejemplo siguiente se utiliza <xref:System.Linq.Enumerable.Average%2A> para obtener el importe total a pagar promedio para cada identificador de contacto.</span><span class="sxs-lookup"><span data-stu-id="0ab6f-111">The following example uses <xref:System.Linq.Enumerable.Average%2A> to get the average total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#AverageGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#averagegrouped_mq)]
 [!code-vb[DP L2E Examples#AverageGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#averagegrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="0ab6f-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0ab6f-112">Example</span></span>  

 <span data-ttu-id="0ab6f-113">En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.Average%2A> para obtener el pedido con el importe total promedio a pagar de cada contacto.</span><span class="sxs-lookup"><span data-stu-id="0ab6f-113">The following example uses <xref:System.Linq.Enumerable.Average%2A> to get the orders with the average total due for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#AverageElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#averageelements_mq)]
 [!code-vb[DP L2E Examples#AverageElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#averageelements_mq)]  
  
## <a name="count"></a><span data-ttu-id="0ab6f-114">Count</span><span class="sxs-lookup"><span data-stu-id="0ab6f-114">Count</span></span>  
  
### <a name="example"></a><span data-ttu-id="0ab6f-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0ab6f-115">Example</span></span>  

 <span data-ttu-id="0ab6f-116">En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.Count%2A> para devolver una lista de identificadores de contactos y el número de pedidos que tiene cada uno.</span><span class="sxs-lookup"><span data-stu-id="0ab6f-116">The following example uses <xref:System.Linq.Enumerable.Count%2A> to return a list of contact IDs and how many orders each has.</span></span>  
  
 [!code-csharp[DP L2E Examples#CountNested](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#countnested)]
 [!code-vb[DP L2E Examples#CountNested](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#countnested)]  
  
### <a name="example"></a><span data-ttu-id="0ab6f-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0ab6f-117">Example</span></span>  

 <span data-ttu-id="0ab6f-118">En el ejemplo siguiente se agrupan los productos por colores y se utiliza <xref:System.Linq.Enumerable.Count%2A> para devolver el número de productos de cada grupo de color.</span><span class="sxs-lookup"><span data-stu-id="0ab6f-118">The following example groups products by color and uses <xref:System.Linq.Enumerable.Count%2A> to return the number of products in each color group.</span></span>  
  
 [!code-csharp[DP L2E Examples#CountGrouped](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#countgrouped)]
 [!code-vb[DP L2E Examples#CountGrouped](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#countgrouped)]  
  
## <a name="max"></a><span data-ttu-id="0ab6f-119">Max</span><span class="sxs-lookup"><span data-stu-id="0ab6f-119">Max</span></span>  
  
### <a name="example"></a><span data-ttu-id="0ab6f-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0ab6f-120">Example</span></span>  

 <span data-ttu-id="0ab6f-121">En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.Max%2A> para obtener el mayor importe total a pagar de cada identificador de contacto.</span><span class="sxs-lookup"><span data-stu-id="0ab6f-121">The following example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the largest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#MaxGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#maxgrouped_mq)]
 [!code-vb[DP L2E Examples#MaxGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#maxgrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="0ab6f-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0ab6f-122">Example</span></span>  

 <span data-ttu-id="0ab6f-123">En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.Max%2A> para obtener el pedido con el mayor importe total a pagar de cada identificador de contacto.</span><span class="sxs-lookup"><span data-stu-id="0ab6f-123">The following example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the orders with the largest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#MaxElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#maxelements_mq)]
 [!code-vb[DP L2E Examples#MaxElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#maxelements_mq)]  
  
## <a name="min"></a><span data-ttu-id="0ab6f-124">Min</span><span class="sxs-lookup"><span data-stu-id="0ab6f-124">Min</span></span>  
  
### <a name="example"></a><span data-ttu-id="0ab6f-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0ab6f-125">Example</span></span>  

 <span data-ttu-id="0ab6f-126">En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.Min%2A> para obtener el menor importe total a pagar de cada identificador de contacto.</span><span class="sxs-lookup"><span data-stu-id="0ab6f-126">The following example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the smallest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#MinGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#mingrouped_mq)]
 [!code-vb[DP L2E Examples#MinGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#mingrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="0ab6f-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0ab6f-127">Example</span></span>  

 <span data-ttu-id="0ab6f-128">En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.Min%2A> para obtener el pedido con el menor importe total a pagar de cada contacto.</span><span class="sxs-lookup"><span data-stu-id="0ab6f-128">The following example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the orders with the smallest total due for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#MinElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#minelements_mq)]
 [!code-vb[DP L2E Examples#MinElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#minelements_mq)]  
  
## <a name="sum"></a><span data-ttu-id="0ab6f-129">Sum</span><span class="sxs-lookup"><span data-stu-id="0ab6f-129">Sum</span></span>  
  
### <a name="example"></a><span data-ttu-id="0ab6f-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0ab6f-130">Example</span></span>  

 <span data-ttu-id="0ab6f-131">En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.Sum%2A> para obtener el menor importe total a pagar de cada identificador de contacto.</span><span class="sxs-lookup"><span data-stu-id="0ab6f-131">The following example uses the <xref:System.Linq.Enumerable.Sum%2A> method to get the total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#SumGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#sumgrouped_mq)]
 [!code-vb[DP L2E Examples#SumGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#sumgrouped_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="0ab6f-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="0ab6f-132">See also</span></span>

- [<span data-ttu-id="0ab6f-133">Consultas en LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="0ab6f-133">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
