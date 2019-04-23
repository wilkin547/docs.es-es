---
title: 'Ejemplos de sintaxis de expresiones de consulta: Filtrado'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c27cb89c-1c1d-4988-9f38-950eda3cb275
ms.openlocfilehash: eb1680ba8ca2fab5511dc20c94ad997ef04974fe
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59134555"
---
# <a name="query-expression-syntax-examples-filtering"></a><span data-ttu-id="c9ba1-102">Ejemplos de sintaxis de expresiones de consulta: Filtrado</span><span class="sxs-lookup"><span data-stu-id="c9ba1-102">Query Expression Syntax Examples: Filtering</span></span>
<span data-ttu-id="c9ba1-103">Los ejemplos de este tema muestran cómo usar el `Where` y `Where…Contains` métodos para consultar el [modelo AdventureWorks Sales](https://archive.codeplex.com/?p=msftdbprodsamples) con la sintaxis de expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="c9ba1-103">The examples in this topic demonstrate how to use the `Where` and `Where…Contains` methods to query the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples) using query expression syntax.</span></span> <span data-ttu-id="c9ba1-104">Note, Where…`Contains`</span><span class="sxs-lookup"><span data-stu-id="c9ba1-104">Note, Where…`Contains`</span></span> <span data-ttu-id="c9ba1-105">no se puede usar como parte de un [consulta compilada](../../../../../../docs/framework/data/adonet/ef/language-reference/compiled-queries-linq-to-entities.md).</span><span class="sxs-lookup"><span data-stu-id="c9ba1-105">cannot be used as a part of a [compiled query](../../../../../../docs/framework/data/adonet/ef/language-reference/compiled-queries-linq-to-entities.md).</span></span>  
  
 <span data-ttu-id="c9ba1-106">El modelo AdventureWorks Sales que se usa en estos ejemplos se crea a partir de las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="c9ba1-106">The AdventureWorks Sales model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="c9ba1-107">Los ejemplos de este tema usan los siguientes `using` / `Imports` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="c9ba1-107">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="where"></a><span data-ttu-id="c9ba1-108">Where</span><span class="sxs-lookup"><span data-stu-id="c9ba1-108">Where</span></span>  
  
### <a name="example"></a><span data-ttu-id="c9ba1-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c9ba1-109">Example</span></span>  
 <span data-ttu-id="c9ba1-110">En el ejemplo siguiente se devuelven todos los pedidos en línea.</span><span class="sxs-lookup"><span data-stu-id="c9ba1-110">The following example returns all online orders.</span></span>  
  
 [!code-csharp[DP L2E Examples#Where1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#where1)]
 [!code-vb[DP L2E Examples#Where1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#where1)]  
  
### <a name="example"></a><span data-ttu-id="c9ba1-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c9ba1-111">Example</span></span>  
 <span data-ttu-id="c9ba1-112">En el ejemplo siguiente se devuelven los pedidos en los que la cantidad de pedido es superior a 2 e inferior a 6.</span><span class="sxs-lookup"><span data-stu-id="c9ba1-112">The following example returns the orders where the order quantity is greater than 2 and less than 6.</span></span>  
  
 [!code-csharp[DP L2E Examples#Where2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#where2)]
 [!code-vb[DP L2E Examples#Where2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#where2)]  
  
### <a name="example"></a><span data-ttu-id="c9ba1-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c9ba1-113">Example</span></span>  
 <span data-ttu-id="c9ba1-114">En el ejemplo siguiente se devuelven todos los productos de color rojo.</span><span class="sxs-lookup"><span data-stu-id="c9ba1-114">The following example returns all red colored products.</span></span>  
  
 [!code-csharp[DP L2E Examples#Where3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#where3)]
 [!code-vb[DP L2E Examples#Where3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#where3)]  
  
### <a name="example"></a><span data-ttu-id="c9ba1-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c9ba1-115">Example</span></span>  
 <span data-ttu-id="c9ba1-116">En el ejemplo siguiente se utiliza el método `Where` para buscar los pedidos que se realizaron después del 1 de diciembre de 2003 y, a continuación, se utiliza la propiedad de navegación `order.SalesOrderDetail` para obtener los detalles de cada pedido.</span><span class="sxs-lookup"><span data-stu-id="c9ba1-116">The following example uses the `Where` method to find orders that were made after December 1, 2003, and then uses the `order.SalesOrderDetail` navigation property to get the details for each order.</span></span>  
  
 [!code-csharp[DP L2E Examples#WhereNavProperty](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#wherenavproperty)]
 [!code-vb[DP L2E Examples#WhereNavProperty](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#wherenavproperty)]  
  
## <a name="wherecontains"></a><span data-ttu-id="c9ba1-117">Where…Contains</span><span class="sxs-lookup"><span data-stu-id="c9ba1-117">Where…Contains</span></span>  
  
### <a name="example"></a><span data-ttu-id="c9ba1-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c9ba1-118">Example</span></span>  
 <span data-ttu-id="c9ba1-119">En el ejemplo siguiente se usa una matriz como parte de una cláusula `Where…Contains` para encontrar todos los productos que tienen un `ProductModelID` que coincide con un valor de la matriz.</span><span class="sxs-lookup"><span data-stu-id="c9ba1-119">The following example uses an array as part of a `Where…Contains` clause to find all products that have a `ProductModelID` that matches a value in the array.</span></span>  
  
 [!code-csharp[DP L2E ArraysAndListsInQueries#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e arraysandlistsinqueries/cs/program.cs#1)]
 [!code-vb[DP L2E ArraysAndListsInQueries#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e arraysandlistsinqueries/vb/module1.vb#1)]  
  
> [!NOTE]
>  <span data-ttu-id="c9ba1-120">Como parte del predicado de una cláusula `Where…Contains`, puede utilizar <xref:System.Array>, <xref:System.Collections.Generic.List%601> o una colección de cualquier tipo que implemente la interfaz <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="c9ba1-120">As part of the predicate in a `Where…Contains` clause, you can use an <xref:System.Array>, a <xref:System.Collections.Generic.List%601>, or a collection of any type that implements the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="c9ba1-121">También puede declarar e inicializar una colección en una consulta LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="c9ba1-121">You can also declare and initialize a collection within a LINQ to Entities query.</span></span> <span data-ttu-id="c9ba1-122">Para obtener más información, vea el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="c9ba1-122">See the next example for more information.</span></span>  
  
### <a name="example"></a><span data-ttu-id="c9ba1-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c9ba1-123">Example</span></span>  
 <span data-ttu-id="c9ba1-124">El ejemplo siguiente declara e inicializa las matrices en una cláusula `Where…Contains` para encontrar todos los productos que tienen un `ProductModelID` o `Size` que coinciden con los valores de las matrices.</span><span class="sxs-lookup"><span data-stu-id="c9ba1-124">The following example declares and initializes arrays in a `Where…Contains` clause to find all products that have a `ProductModelID` or `Size` that match values in the arrays.</span></span>  
  
 [!code-csharp[DP L2E ArraysAndListsInQueries#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e arraysandlistsinqueries/cs/program.cs#2)]
 [!code-vb[DP L2E ArraysAndListsInQueries#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e arraysandlistsinqueries/vb/module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="c9ba1-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="c9ba1-125">See also</span></span>

- [<span data-ttu-id="c9ba1-126">Consultas en LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="c9ba1-126">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
