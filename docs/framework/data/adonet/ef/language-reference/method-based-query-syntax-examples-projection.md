---
description: 'Más información sobre: Method-Based ejemplos de sintaxis de consultas: proyección'
title: 'Ejemplos de sintaxis de consulta basada en métodos: Proyección'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 505491fa-5920-43ce-8a96-c25389e125d8
ms.openlocfilehash: ed4d53166f15f5a2b618ccae92b40fc07d370299
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99696664"
---
# <a name="method-based-query-syntax-examples-projection"></a><span data-ttu-id="47612-103">Ejemplos de sintaxis de consulta basada en métodos: Proyección</span><span class="sxs-lookup"><span data-stu-id="47612-103">Method-Based Query Syntax Examples: Projection</span></span>

<span data-ttu-id="47612-104">En los ejemplos de este tema se muestra cómo usar <xref:System.Linq.Enumerable.Select%2A> los <xref:System.Linq.Enumerable.SelectMany%2A> métodos y para consultar el [modelo AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) con la sintaxis de consulta basada en métodos.</span><span class="sxs-lookup"><span data-stu-id="47612-104">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Select%2A> and <xref:System.Linq.Enumerable.SelectMany%2A> methods to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using method-based query syntax.</span></span> <span data-ttu-id="47612-105">El modelo AdventureWorks Sales que se usa en estos ejemplos se crea a partir de las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="47612-105">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="47612-106">En los ejemplos de este tema se usan las siguientes `using` / `Imports` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="47612-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="select"></a><span data-ttu-id="47612-107">Seleccionar</span><span class="sxs-lookup"><span data-stu-id="47612-107">Select</span></span>  
  
### <a name="example"></a><span data-ttu-id="47612-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="47612-108">Example</span></span>  

 <span data-ttu-id="47612-109">En el ejemplo siguiente se usa el método <xref:System.Linq.Queryable.Select%2A> para proyectar las propiedades `Product.Name` y `Product.ProductID` en una secuencia de tipos anónimos.</span><span class="sxs-lookup"><span data-stu-id="47612-109">The following example uses the <xref:System.Linq.Queryable.Select%2A> method to project the `Product.Name` and `Product.ProductID` properties into a sequence of anonymous types.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectAnonymousTypes_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectanonymoustypes_mq)]
 [!code-vb[DP L2E Examples#SelectAnonymousTypes_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectanonymoustypes_mq)]  
  
### <a name="example"></a><span data-ttu-id="47612-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="47612-110">Example</span></span>  

 <span data-ttu-id="47612-111">En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.Select%2A> para devolver una secuencia de nombres de producto solamente.</span><span class="sxs-lookup"><span data-stu-id="47612-111">The following example uses the <xref:System.Linq.Enumerable.Select%2A> method to return a sequence of only product names.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectSimple2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectsimple2_mq)]
 [!code-vb[DP L2E Examples#SelectSimple2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectsimple2_mq)]  
  
## <a name="selectmany"></a><span data-ttu-id="47612-112">SelectMany</span><span class="sxs-lookup"><span data-stu-id="47612-112">SelectMany</span></span>  
  
### <a name="example"></a><span data-ttu-id="47612-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="47612-113">Example</span></span>  

 <span data-ttu-id="47612-114">En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.SelectMany%2A> para seleccionar todos los pedidos en los que `TotalDue` es inferior a 500,00.</span><span class="sxs-lookup"><span data-stu-id="47612-114">The following example uses the <xref:System.Linq.Enumerable.SelectMany%2A> method to select all orders where `TotalDue` is less than 500.00.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectManyCompoundFrom_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectmanycompoundfrom_mq)]
 [!code-vb[DP L2E Examples#SelectManyCompoundFrom_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectmanycompoundfrom_mq)]  
  
### <a name="example"></a><span data-ttu-id="47612-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="47612-115">Example</span></span>  

 <span data-ttu-id="47612-116">En este ejemplo se utiliza el método <xref:System.Linq.Enumerable.SelectMany%2A> para seleccionar todos los pedidos efectuados a partir del 1 de octubre de 2002.</span><span class="sxs-lookup"><span data-stu-id="47612-116">The following example uses the <xref:System.Linq.Enumerable.SelectMany%2A> method to select all orders where the order was made on October 1, 2002 or later.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectManyCompoundFrom2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectmanycompoundfrom2_mq)]
 [!code-vb[DP L2E Examples#SelectManyCompoundFrom2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectmanycompoundfrom2_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="47612-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="47612-117">See also</span></span>

- [<span data-ttu-id="47612-118">Consultas en LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="47612-118">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
