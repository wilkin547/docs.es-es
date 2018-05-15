---
title: 'Ejemplos de sintaxis de expresiones de consulta: proyección'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 079926c5-e6b5-4fb9-b4cf-9c63886dd626
ms.openlocfilehash: 69c807bdc052dda9e62216aa1611b4a6b2155a27
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="query-expression-syntax-examples-projection"></a><span data-ttu-id="a299e-102">Ejemplos de sintaxis de expresiones de consulta: proyección</span><span class="sxs-lookup"><span data-stu-id="a299e-102">Query Expression Syntax Examples: Projection</span></span>
<span data-ttu-id="a299e-103">Los ejemplos de este tema muestran cómo usar el `Select` método y `From … From …` palabras clave para consultar el [modelo AdventureWorks Sales](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) utilizando la sintaxis de expresiones de consulta.</span><span class="sxs-lookup"><span data-stu-id="a299e-103">The examples in this topic demonstrate how to use the `Select` method and the `From … From …` keywords to query the [AdventureWorks Sales Model](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) using query expression syntax.</span></span> <span data-ttu-id="a299e-104">`From … From …` es el equivalente basado en las consultas del método `SelectMany`.</span><span class="sxs-lookup"><span data-stu-id="a299e-104">`From … From …` is the query based equivalent of the `SelectMany` method.</span></span> <span data-ttu-id="a299e-105">El modelo AdventureWorks Sales que se usa en estos ejemplos se crea a partir de las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="a299e-105">The AdventureWorks Sales model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="a299e-106">Los ejemplos de este tema usan los siguientes `using` / `Imports` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="a299e-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="select"></a><span data-ttu-id="a299e-107">Seleccionar</span><span class="sxs-lookup"><span data-stu-id="a299e-107">Select</span></span>  
  
### <a name="example"></a><span data-ttu-id="a299e-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a299e-108">Example</span></span>  
 <span data-ttu-id="a299e-109">En el ejemplo siguiente se usa el método <xref:System.Linq.Enumerable.Select%2A> para devolver todas las filas de la tabla `Product` y mostrar los nombres de producto.</span><span class="sxs-lookup"><span data-stu-id="a299e-109">The following example uses the <xref:System.Linq.Enumerable.Select%2A> method to return all the rows from the `Product` table and display the product names.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectSimple1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectsimple1)]
 [!code-vb[DP L2E Examples#SelectSimple1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectsimple1)]  
  
### <a name="example"></a><span data-ttu-id="a299e-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a299e-110">Example</span></span>  
 <span data-ttu-id="a299e-111">El ejemplo siguiente utiliza <xref:System.Linq.Enumerable.Select%2A> para devolver una secuencia de nombres de producto solamente.</span><span class="sxs-lookup"><span data-stu-id="a299e-111">The following example uses <xref:System.Linq.Enumerable.Select%2A> to return a sequence of only product names.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectSimple2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectsimple2)]
 [!code-vb[DP L2E Examples#SelectSimple2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectsimple2)]  
  
### <a name="example"></a><span data-ttu-id="a299e-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a299e-112">Example</span></span>  
 <span data-ttu-id="a299e-113">En el ejemplo siguiente se usa el método <xref:System.Linq.Queryable.Select%2A> para proyectar las propiedades `Product.Name` y `Product.ProductID` en una secuencia de tipos anónimos.</span><span class="sxs-lookup"><span data-stu-id="a299e-113">The following example uses the <xref:System.Linq.Queryable.Select%2A> method to project the `Product.Name` and `Product.ProductID` properties into a sequence of anonymous types.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectAnonymousTypes](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectanonymoustypes)]
 [!code-vb[DP L2E Examples#SelectAnonymousTypes](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectanonymoustypes)]  
  
## <a name="from--from--selectmany"></a><span data-ttu-id="a299e-114">De...</span><span class="sxs-lookup"><span data-stu-id="a299e-114">From …</span></span> <span data-ttu-id="a299e-115">De...</span><span class="sxs-lookup"><span data-stu-id="a299e-115">From …</span></span> <span data-ttu-id="a299e-116">(SelectMany)</span><span class="sxs-lookup"><span data-stu-id="a299e-116">(SelectMany)</span></span>  
  
### <a name="example"></a><span data-ttu-id="a299e-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a299e-117">Example</span></span>  
 <span data-ttu-id="a299e-118">En el ejemplo siguiente se usa `From … From …` (el equivalente del método <xref:System.Linq.Enumerable.SelectMany%2A>) para seleccionar todos los pedidos en los que `TotalDue` es inferior a 500,00.</span><span class="sxs-lookup"><span data-stu-id="a299e-118">The following example uses `From … From …` (the equivalent of the <xref:System.Linq.Enumerable.SelectMany%2A> method) to select all orders where `TotalDue` is less than 500.00.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectManyCompoundFrom](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectmanycompoundfrom)]
 [!code-vb[DP L2E Examples#SelectManyCompoundFrom](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectmanycompoundfrom)]  
  
### <a name="example"></a><span data-ttu-id="a299e-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a299e-119">Example</span></span>  
 <span data-ttu-id="a299e-120">En el ejemplo siguiente se utiliza `From … From …` (el equivalente del método <xref:System.Linq.Enumerable.SelectMany%2A>) para seleccionar todos los pedidos efectuados a partir del 1 de octubre de 2002.</span><span class="sxs-lookup"><span data-stu-id="a299e-120">The following example uses `From … From …` (the equivalent of the <xref:System.Linq.Enumerable.SelectMany%2A> method) to select all orders where the order was made on October 1, 2002 or later.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectManyCompoundFrom2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectmanycompoundfrom2)]
 [!code-vb[DP L2E Examples#SelectManyCompoundFrom2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectmanycompoundfrom2)]  
  
### <a name="example"></a><span data-ttu-id="a299e-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a299e-121">Example</span></span>  
 <span data-ttu-id="a299e-122">En el ejemplo siguiente se utiliza `From … From …` (el equivalente al método <xref:System.Linq.Enumerable.SelectMany%2A>) para seleccionar todos los pedidos en los que el total del pedido es superior a 10000,00 y se utiliza la asignación `From` para evitar que se solicite dos veces el total.</span><span class="sxs-lookup"><span data-stu-id="a299e-122">The following example uses a `From … From …` (the equivalent of the <xref:System.Linq.Enumerable.SelectMany%2A> method) to select all orders where the order total is greater than 10000.00 and uses `From` assignment to avoid requesting the total twice.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectManyFromAssignment](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectmanyfromassignment)]
 [!code-vb[DP L2E Examples#SelectManyFromAssignment](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectmanyfromassignment)]  
  
## <a name="see-also"></a><span data-ttu-id="a299e-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="a299e-123">See Also</span></span>  
 [<span data-ttu-id="a299e-124">Consultas en LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="a299e-124">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
