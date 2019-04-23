---
title: 'Ejemplos de sintaxis de expresiones de consulta: Agrupar'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2d83d7c0-b3be-4c92-a630-25cd1285de31
ms.openlocfilehash: 0a4aa57ba709852c30223598b9d1af146eaf6013
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59212003"
---
# <a name="query-expression-syntax-examples-grouping"></a><span data-ttu-id="99d60-102">Ejemplos de sintaxis de expresiones de consulta: Agrupar</span><span class="sxs-lookup"><span data-stu-id="99d60-102">Query Expression Syntax Examples: Grouping</span></span>
<span data-ttu-id="99d60-103">Los ejemplos de este tema muestran cómo usar el `GroupBy` método para consultar el [modelo AdventureWorks Sales](https://archive.codeplex.com/?p=msftdbprodsamples) con la sintaxis de expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="99d60-103">The examples in this topic demonstrate how to use the `GroupBy` method to query the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples) using query expression syntax.</span></span> <span data-ttu-id="99d60-104">El modelo AdventureWorks Sales que se usa en estos ejemplos se crea a partir de las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="99d60-104">The AdventureWorks Sales model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="99d60-105">Los ejemplos de este tema usan los siguientes `using` / `Imports` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="99d60-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="example"></a><span data-ttu-id="99d60-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="99d60-106">Example</span></span>  
 <span data-ttu-id="99d60-107">El ejemplo siguiente devuelve los objetos `Address` agrupados por código postal.</span><span class="sxs-lookup"><span data-stu-id="99d60-107">The following example returns `Address` objects grouped by postal code.</span></span> <span data-ttu-id="99d60-108">Los resultados se proyectan en un tipo anónimo.</span><span class="sxs-lookup"><span data-stu-id="99d60-108">The results are projected into an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupBySimple3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbysimple3)]
 [!code-vb[DP L2E Examples#GroupBySimple3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbysimple3)]  
  
## <a name="example"></a><span data-ttu-id="99d60-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="99d60-109">Example</span></span>  
 <span data-ttu-id="99d60-110">El ejemplo siguiente devuelve los objetos `Contact` agrupados por la primera letra del apellido del contacto.</span><span class="sxs-lookup"><span data-stu-id="99d60-110">The following example returns `Contact` objects grouped by the first letter of the contact's last name.</span></span> <span data-ttu-id="99d60-111">Los resultados se ordenan también por la primera letra del apellido y se proyectan en un tipo anónimo.</span><span class="sxs-lookup"><span data-stu-id="99d60-111">The results are also sorted by the first letter of last name and projected into an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupBySimple2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbysimple2)]
 [!code-vb[DP L2E Examples#GroupBySimple2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbysimple2)]  
  
## <a name="example"></a><span data-ttu-id="99d60-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="99d60-112">Example</span></span>  
 <span data-ttu-id="99d60-113">En el ejemplo siguiente se devuelven objetos `SalesOrderHeader` agrupados por identificador de cliente.</span><span class="sxs-lookup"><span data-stu-id="99d60-113">The following example returns `SalesOrderHeader` objects grouped by customer ID.</span></span> <span data-ttu-id="99d60-114">También se devuelve el número de ventas para cada cliente.</span><span class="sxs-lookup"><span data-stu-id="99d60-114">The number of sales for each customer is also returned.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupByCount](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbycount)]
 [!code-vb[DP L2E Examples#GroupByCount](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbycount)]  
  
## <a name="see-also"></a><span data-ttu-id="99d60-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="99d60-115">See also</span></span>

- [<span data-ttu-id="99d60-116">Consultas en LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="99d60-116">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
