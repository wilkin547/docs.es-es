---
description: 'Más información acerca de: ejemplos de sintaxis de expresiones de consulta: agrupación'
title: 'Ejemplos de sintaxis de expresiones de consulta: Agrupar'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2d83d7c0-b3be-4c92-a630-25cd1285de31
ms.openlocfilehash: 1d8bd51a783cbd53716daebfa9b547f5e4fffc1f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99696222"
---
# <a name="query-expression-syntax-examples-grouping"></a><span data-ttu-id="239d6-103">Ejemplos de sintaxis de expresiones de consulta: Agrupar</span><span class="sxs-lookup"><span data-stu-id="239d6-103">Query Expression Syntax Examples: Grouping</span></span>

<span data-ttu-id="239d6-104">En los ejemplos de este tema se muestra cómo usar el `GroupBy` método para consultar el [modelo AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) con la sintaxis de las expresiones de consulta.</span><span class="sxs-lookup"><span data-stu-id="239d6-104">The examples in this topic demonstrate how to use the `GroupBy` method to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using query expression syntax.</span></span> <span data-ttu-id="239d6-105">El modelo AdventureWorks Sales que se usa en estos ejemplos se crea a partir de las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="239d6-105">The AdventureWorks Sales model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="239d6-106">En los ejemplos de este tema se usan las siguientes `using` / `Imports` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="239d6-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="example"></a><span data-ttu-id="239d6-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="239d6-107">Example</span></span>  

 <span data-ttu-id="239d6-108">El ejemplo siguiente devuelve los objetos `Address` agrupados por código postal.</span><span class="sxs-lookup"><span data-stu-id="239d6-108">The following example returns `Address` objects grouped by postal code.</span></span> <span data-ttu-id="239d6-109">Los resultados se proyectan en un tipo anónimo.</span><span class="sxs-lookup"><span data-stu-id="239d6-109">The results are projected into an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupBySimple3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbysimple3)]
 [!code-vb[DP L2E Examples#GroupBySimple3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbysimple3)]  
  
## <a name="example"></a><span data-ttu-id="239d6-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="239d6-110">Example</span></span>  

 <span data-ttu-id="239d6-111">El ejemplo siguiente devuelve los objetos `Contact` agrupados por la primera letra del apellido del contacto.</span><span class="sxs-lookup"><span data-stu-id="239d6-111">The following example returns `Contact` objects grouped by the first letter of the contact's last name.</span></span> <span data-ttu-id="239d6-112">Los resultados se ordenan también por la primera letra del apellido y se proyectan en un tipo anónimo.</span><span class="sxs-lookup"><span data-stu-id="239d6-112">The results are also sorted by the first letter of last name and projected into an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupBySimple2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbysimple2)]
 [!code-vb[DP L2E Examples#GroupBySimple2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbysimple2)]  
  
## <a name="example"></a><span data-ttu-id="239d6-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="239d6-113">Example</span></span>  

 <span data-ttu-id="239d6-114">En el ejemplo siguiente se devuelven objetos `SalesOrderHeader` agrupados por identificador de cliente.</span><span class="sxs-lookup"><span data-stu-id="239d6-114">The following example returns `SalesOrderHeader` objects grouped by customer ID.</span></span> <span data-ttu-id="239d6-115">También se devuelve el número de ventas para cada cliente.</span><span class="sxs-lookup"><span data-stu-id="239d6-115">The number of sales for each customer is also returned.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupByCount](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbycount)]
 [!code-vb[DP L2E Examples#GroupByCount](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbycount)]  
  
## <a name="see-also"></a><span data-ttu-id="239d6-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="239d6-116">See also</span></span>

- [<span data-ttu-id="239d6-117">Consultas en LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="239d6-117">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
