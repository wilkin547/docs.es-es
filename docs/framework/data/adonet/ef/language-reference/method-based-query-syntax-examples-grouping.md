---
title: 'Ejemplos de sintaxis de consulta basada en métodos: Agrupar'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cb23c25c-1075-4cc3-a8ff-4db72e536c0d
ms.openlocfilehash: 8f09983aa90be666cc13ae4eba018db2ae706daa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61760602"
---
# <a name="method-based-query-syntax-examples-grouping"></a><span data-ttu-id="0242b-102">Ejemplos de sintaxis de consulta basada en métodos: Agrupar</span><span class="sxs-lookup"><span data-stu-id="0242b-102">Method-Based Query Syntax Examples: Grouping</span></span>
<span data-ttu-id="0242b-103">Los ejemplos de este tema muestran cómo usar el `GroupBy` método para consultar el [modelo AdventureWorks Sales](https://archive.codeplex.com/?p=msftdbprodsamples) utilizando sintaxis de consulta basada en métodos.</span><span class="sxs-lookup"><span data-stu-id="0242b-103">The examples in this topic show you how to use the `GroupBy` method to query the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples) using method-based query syntax.</span></span> <span data-ttu-id="0242b-104">El modelo AdventureWorks Sales que se usa en estos ejemplos se crea a partir de las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail de la base de datos de ejemplo AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="0242b-104">The AdventureWorks Sales Model that is used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="0242b-105">Los ejemplos de este tema usan los siguientes `using` / `Imports` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="0242b-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="example"></a><span data-ttu-id="0242b-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0242b-106">Example</span></span>  
 <span data-ttu-id="0242b-107">En el ejemplo siguiente se utiliza el método `GroupBy` para devolver objetos `Address` agrupados por código postal.</span><span class="sxs-lookup"><span data-stu-id="0242b-107">The following example uses the `GroupBy` method to return `Address` objects that are grouped by postal code.</span></span> <span data-ttu-id="0242b-108">Los resultados se proyectan en un tipo anónimo.</span><span class="sxs-lookup"><span data-stu-id="0242b-108">The results are projected into an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupBySimple3_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbysimple3_mq)]
 [!code-vb[DP L2E Examples#GroupBySimple3_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbysimple3_mq)]  
  
## <a name="example"></a><span data-ttu-id="0242b-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0242b-109">Example</span></span>  
 <span data-ttu-id="0242b-110">En el ejemplo siguiente se utiliza el método `GroupBy` para devolver objetos `Contact` agrupados por la primera letra del apellido del contacto.</span><span class="sxs-lookup"><span data-stu-id="0242b-110">The following example uses the `GroupBy` method to return `Contact` objects that are grouped by the first letter of the contact's last name.</span></span> <span data-ttu-id="0242b-111">Los resultados se ordenan también por la primera letra del apellido y se proyectan en un tipo anónimo.</span><span class="sxs-lookup"><span data-stu-id="0242b-111">The results are also sorted by the first letter of the last name and projected into an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupBySimple2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbysimple2_mq)]
 [!code-vb[DP L2E Examples#GroupBySimple2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbysimple2_mq)]  
  
## <a name="example"></a><span data-ttu-id="0242b-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0242b-112">Example</span></span>  
 <span data-ttu-id="0242b-113">En el ejemplo siguiente se utiliza el método `GroupBy` para devolver objetos `SalesOrderHeader` agrupados por identificador de cliente.</span><span class="sxs-lookup"><span data-stu-id="0242b-113">The following example uses the `GroupBy` method to return `SalesOrderHeader` objects that are grouped by customer ID.</span></span> <span data-ttu-id="0242b-114">También se devuelve el número de ventas para cada cliente.</span><span class="sxs-lookup"><span data-stu-id="0242b-114">The number of sales for each customer is also returned.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupByCount_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbycount_mq)]
 [!code-vb[DP L2E Examples#GroupByCount_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbycount_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="0242b-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="0242b-115">See also</span></span>

- [<span data-ttu-id="0242b-116">Consultas en LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="0242b-116">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
