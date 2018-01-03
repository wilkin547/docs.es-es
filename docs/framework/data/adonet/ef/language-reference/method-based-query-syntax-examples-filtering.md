---
title: "Ejemplos de sintaxis de consultas basadas en métodos: filtrado"
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
ms.assetid: e40e314c-eb30-4f44-a054-41e511e35832
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 3362dbbe433d4224445057b8aacf6a98473cc213
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="method-based-query-syntax-examples-filtering"></a><span data-ttu-id="34d1f-102">Ejemplos de sintaxis de consultas basadas en métodos: filtrado</span><span class="sxs-lookup"><span data-stu-id="34d1f-102">Method-Based Query Syntax Examples: Filtering</span></span>
<span data-ttu-id="34d1f-103">Los ejemplos de este tema muestran cómo usar el `Where` y `Where…Contains` métodos para consultar el [modelo AdventureWorks Sales](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832) utilizando sintaxis de consulta basada en métodos.</span><span class="sxs-lookup"><span data-stu-id="34d1f-103">The examples in this topic demonstrate how to use the `Where` and `Where…Contains` methods to query the [AdventureWorks Sales Model](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832) using method-based query syntax.</span></span> <span data-ttu-id="34d1f-104">Tenga en cuenta que...`Contains`</span><span class="sxs-lookup"><span data-stu-id="34d1f-104">Note, Where…`Contains`</span></span> <span data-ttu-id="34d1f-105">no se puede usar como parte de un [consulta compilada](../../../../../../docs/framework/data/adonet/ef/language-reference/compiled-queries-linq-to-entities.md).</span><span class="sxs-lookup"><span data-stu-id="34d1f-105">cannot be used as a part of a [compiled query](../../../../../../docs/framework/data/adonet/ef/language-reference/compiled-queries-linq-to-entities.md).</span></span>  
  
 <span data-ttu-id="34d1f-106">El modelo AdventureWorks Sales que se usa en estos ejemplos se crea a partir de las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="34d1f-106">The AdventureWorks Sales model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="34d1f-107">Los ejemplos de este tema usan los siguientes `using` / `Imports` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="34d1f-107">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="where"></a><span data-ttu-id="34d1f-108">Where</span><span class="sxs-lookup"><span data-stu-id="34d1f-108">Where</span></span>  
  
### <a name="example"></a><span data-ttu-id="34d1f-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="34d1f-109">Example</span></span>  
 <span data-ttu-id="34d1f-110">En el ejemplo siguiente se devuelven todos los pedidos en línea.</span><span class="sxs-lookup"><span data-stu-id="34d1f-110">The following example returns all online orders.</span></span>  
  
 [!code-csharp[DP L2E Examples#Where1_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#where1_mq)]
 [!code-vb[DP L2E Examples#Where1_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#where1_mq)]  
  
### <a name="example"></a><span data-ttu-id="34d1f-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="34d1f-111">Example</span></span>  
 <span data-ttu-id="34d1f-112">En el ejemplo siguiente se devuelven los pedidos en los que la cantidad de pedido es superior a 2 e inferior a 6.</span><span class="sxs-lookup"><span data-stu-id="34d1f-112">The following example returns the orders where the order quantity is greater than 2 and less than 6.</span></span>  
  
 [!code-csharp[DP L2E Examples#Where2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#where2_mq)]
 [!code-vb[DP L2E Examples#Where2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#where2_mq)]  
  
### <a name="example"></a><span data-ttu-id="34d1f-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="34d1f-113">Example</span></span>  
 <span data-ttu-id="34d1f-114">En el ejemplo siguiente se devuelven todos los productos de color rojo.</span><span class="sxs-lookup"><span data-stu-id="34d1f-114">The following example returns all red colored products.</span></span>  
  
 [!code-csharp[DP L2E Examples#Where3_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#where3_mq)]
 [!code-vb[DP L2E Examples#Where3_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#where3_mq)]  
  
### <a name="example"></a><span data-ttu-id="34d1f-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="34d1f-115">Example</span></span>  
 <span data-ttu-id="34d1f-116">En el ejemplo siguiente se utiliza el método `Where` para buscar los pedidos que se realizaron después del 1 de diciembre de 2003 y, a continuación, se utiliza la propiedad de navegación `order.SalesOrderDetail` para obtener los detalles de cada pedido.</span><span class="sxs-lookup"><span data-stu-id="34d1f-116">The following example uses the `Where` method to find orders that were made after December 1, 2003 and then uses the `order.SalesOrderDetail` navigation property to get the details for each order.</span></span>  
  
 [!code-csharp[DP L2E Examples#WhereNavProperty_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#wherenavproperty_mq)]
 [!code-vb[DP L2E Examples#WhereNavProperty_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#wherenavproperty_mq)]  
  
## <a name="wherecontains"></a><span data-ttu-id="34d1f-117">Where…Contains</span><span class="sxs-lookup"><span data-stu-id="34d1f-117">Where…Contains</span></span>  
  
### <a name="example"></a><span data-ttu-id="34d1f-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="34d1f-118">Example</span></span>  
 <span data-ttu-id="34d1f-119">En el ejemplo siguiente se usa una matriz como parte de una cláusula `Where…Contains` para encontrar todos los productos que tienen un `ProductModelID` que coincide con un valor de la matriz.</span><span class="sxs-lookup"><span data-stu-id="34d1f-119">The following example uses an array as part of a `Where…Contains` clause to find all products that have a `ProductModelID` that matches a value in the array.</span></span>  
  
 [!code-csharp[DP L2E ArraysAndListsInQueries#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e arraysandlistsinqueries/cs/program.cs#3)]
 [!code-vb[DP L2E ArraysAndListsInQueries#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e arraysandlistsinqueries/vb/module1.vb#3)]  
  
> [!NOTE]
>  <span data-ttu-id="34d1f-120">Como parte del predicado de una cláusula `Where…Contains`, puede utilizar <xref:System.Array>, <xref:System.Collections.Generic.List%601> o una colección de cualquier tipo que implemente la interfaz <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="34d1f-120">As part of the predicate in a `Where…Contains` clause, you can use an <xref:System.Array>, a <xref:System.Collections.Generic.List%601>, or a collection of any type that implements the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="34d1f-121">También puede declarar e inicializar una colección en una consulta LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="34d1f-121">You can also declare and initialize a collection within a LINQ to Entities query.</span></span> <span data-ttu-id="34d1f-122">Para obtener más información, vea el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="34d1f-122">See the next example for more information.</span></span>  
  
### <a name="example"></a><span data-ttu-id="34d1f-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="34d1f-123">Example</span></span>  
 <span data-ttu-id="34d1f-124">El ejemplo siguiente declara e inicializa las matrices en una cláusula `Where…Contains` para encontrar todos los productos que tienen un `ProductModelID` o `Size` que coincide con un valor de las matrices.</span><span class="sxs-lookup"><span data-stu-id="34d1f-124">The following example declares and initializes arrays in a `Where…Contains` clause to find all products that have a `ProductModelID` or a `Size` that matches a value in the arrays.</span></span>  
  
 [!code-csharp[DP L2E ArraysAndListsInQueries#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e arraysandlistsinqueries/cs/program.cs#4)]
 [!code-vb[DP L2E ArraysAndListsInQueries#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e arraysandlistsinqueries/vb/module1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="34d1f-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="34d1f-125">See Also</span></span>  
 [<span data-ttu-id="34d1f-126">Consultas en LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="34d1f-126">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
