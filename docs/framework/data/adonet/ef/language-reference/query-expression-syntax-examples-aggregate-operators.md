---
title: 'Ejemplos de sintaxis de expresiones de consulta: operadores de agregado'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d729120c-4c1b-4f34-bbe9-33694fca2dde
ms.openlocfilehash: 4717f7fe438f67a0d40c64724700f7ea78c4c887
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43522731"
---
# <a name="query-expression-syntax-examples-aggregate-operators"></a><span data-ttu-id="0aabb-102">Ejemplos de sintaxis de expresiones de consulta: operadores de agregado</span><span class="sxs-lookup"><span data-stu-id="0aabb-102">Query Expression Syntax Examples: Aggregate Operators</span></span>
<span data-ttu-id="0aabb-103">Los ejemplos de este tema muestran cómo usar el <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, y <xref:System.Linq.Enumerable.Sum%2A> métodos para consultar el [modelo AdventureWorks Sales](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) con la sintaxis de expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="0aabb-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Sum%2A> methods to query the [AdventureWorks Sales Model](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) using query expression syntax.</span></span> <span data-ttu-id="0aabb-104">El modelo AdventureWorks Sales que se usa en estos ejemplos se crea a partir de las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="0aabb-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="0aabb-105">Los ejemplos de este tema usan los siguientes `using` / `Imports` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="0aabb-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="average"></a><span data-ttu-id="0aabb-106">Average</span><span class="sxs-lookup"><span data-stu-id="0aabb-106">Average</span></span>  
  
### <a name="example"></a><span data-ttu-id="0aabb-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0aabb-107">Example</span></span>  
 <span data-ttu-id="0aabb-108">En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.Average%2A> para encontrar el precio de venta promedio de los productos de cada estilo.</span><span class="sxs-lookup"><span data-stu-id="0aabb-108">The following example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average list price of the products of each style.</span></span>  
  
 [!code-csharp[DP L2E Examples#Average2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#average2_mq)]
 [!code-vb[DP L2E Examples#Average2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#average2_mq)]  
  
### <a name="example"></a><span data-ttu-id="0aabb-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0aabb-109">Example</span></span>  
 <span data-ttu-id="0aabb-110">En el ejemplo siguiente se utiliza <xref:System.Linq.Enumerable.Average%2A> para obtener el importe total a pagar promedio para cada identificador de contacto.</span><span class="sxs-lookup"><span data-stu-id="0aabb-110">The following example uses <xref:System.Linq.Enumerable.Average%2A> to get the average total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#AverageGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#averagegrouped_mq)]
 [!code-vb[DP L2E Examples#AverageGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#averagegrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="0aabb-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0aabb-111">Example</span></span>  
 <span data-ttu-id="0aabb-112">En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.Average%2A> para obtener el pedido con el importe total promedio a pagar de cada contacto.</span><span class="sxs-lookup"><span data-stu-id="0aabb-112">The following example uses <xref:System.Linq.Enumerable.Average%2A> to get the orders with the average total due for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#AverageElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#averageelements_mq)]
 [!code-vb[DP L2E Examples#AverageElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#averageelements_mq)]  
  
## <a name="count"></a><span data-ttu-id="0aabb-113">Count</span><span class="sxs-lookup"><span data-stu-id="0aabb-113">Count</span></span>  
  
### <a name="example"></a><span data-ttu-id="0aabb-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0aabb-114">Example</span></span>  
 <span data-ttu-id="0aabb-115">En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.Count%2A> para devolver una lista de identificadores de contactos y el número de pedidos que tiene cada uno.</span><span class="sxs-lookup"><span data-stu-id="0aabb-115">The following example uses <xref:System.Linq.Enumerable.Count%2A> to return a list of contact IDs and how many orders each has.</span></span>  
  
 [!code-csharp[DP L2E Examples#CountNested](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#countnested)]
 [!code-vb[DP L2E Examples#CountNested](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#countnested)]  
  
### <a name="example"></a><span data-ttu-id="0aabb-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0aabb-116">Example</span></span>  
 <span data-ttu-id="0aabb-117">En el ejemplo siguiente se agrupan los productos por colores y se utiliza <xref:System.Linq.Enumerable.Count%2A> para devolver el número de productos de cada grupo de color.</span><span class="sxs-lookup"><span data-stu-id="0aabb-117">The following example groups products by color and uses <xref:System.Linq.Enumerable.Count%2A> to return the number of products in each color group.</span></span>  
  
 [!code-csharp[DP L2E Examples#CountGrouped](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#countgrouped)]
 [!code-vb[DP L2E Examples#CountGrouped](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#countgrouped)]  
  
## <a name="max"></a><span data-ttu-id="0aabb-118">Max</span><span class="sxs-lookup"><span data-stu-id="0aabb-118">Max</span></span>  
  
### <a name="example"></a><span data-ttu-id="0aabb-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0aabb-119">Example</span></span>  
 <span data-ttu-id="0aabb-120">En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.Max%2A> para obtener el mayor importe total a pagar de cada identificador de contacto.</span><span class="sxs-lookup"><span data-stu-id="0aabb-120">The following example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the largest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#MaxGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#maxgrouped_mq)]
 [!code-vb[DP L2E Examples#MaxGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#maxgrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="0aabb-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0aabb-121">Example</span></span>  
 <span data-ttu-id="0aabb-122">En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.Max%2A> para obtener el pedido con el mayor importe total a pagar de cada identificador de contacto.</span><span class="sxs-lookup"><span data-stu-id="0aabb-122">The following example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the orders with the largest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#MaxElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#maxelements_mq)]
 [!code-vb[DP L2E Examples#MaxElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#maxelements_mq)]  
  
## <a name="min"></a><span data-ttu-id="0aabb-123">Min</span><span class="sxs-lookup"><span data-stu-id="0aabb-123">Min</span></span>  
  
### <a name="example"></a><span data-ttu-id="0aabb-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0aabb-124">Example</span></span>  
 <span data-ttu-id="0aabb-125">En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.Min%2A> para obtener el menor importe total a pagar de cada identificador de contacto.</span><span class="sxs-lookup"><span data-stu-id="0aabb-125">The following example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the smallest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#MinGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#mingrouped_mq)]
 [!code-vb[DP L2E Examples#MinGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#mingrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="0aabb-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0aabb-126">Example</span></span>  
 <span data-ttu-id="0aabb-127">En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.Min%2A> para obtener el pedido con el menor importe total a pagar de cada contacto.</span><span class="sxs-lookup"><span data-stu-id="0aabb-127">The following example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the orders with the smallest total due for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#MinElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#minelements_mq)]
 [!code-vb[DP L2E Examples#MinElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#minelements_mq)]  
  
## <a name="sum"></a><span data-ttu-id="0aabb-128">Sum</span><span class="sxs-lookup"><span data-stu-id="0aabb-128">Sum</span></span>  
  
### <a name="example"></a><span data-ttu-id="0aabb-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0aabb-129">Example</span></span>  
 <span data-ttu-id="0aabb-130">En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.Sum%2A> para obtener el menor importe total a pagar de cada identificador de contacto.</span><span class="sxs-lookup"><span data-stu-id="0aabb-130">The following example uses the <xref:System.Linq.Enumerable.Sum%2A> method to get the total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#SumGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#sumgrouped_mq)]
 [!code-vb[DP L2E Examples#SumGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#sumgrouped_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="0aabb-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="0aabb-131">See Also</span></span>  
 [<span data-ttu-id="0aabb-132">Consultas en LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="0aabb-132">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
