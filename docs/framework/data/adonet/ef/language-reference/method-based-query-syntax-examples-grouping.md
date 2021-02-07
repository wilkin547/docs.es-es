---
description: 'Más información acerca de: Method-Based ejemplos de sintaxis de consultas: agrupación'
title: 'Ejemplos de sintaxis de consulta basada en métodos: Agrupar'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cb23c25c-1075-4cc3-a8ff-4db72e536c0d
ms.openlocfilehash: dd605076a425207aa379216a9e8dba60eaeebc29
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99673510"
---
# <a name="method-based-query-syntax-examples-grouping"></a><span data-ttu-id="9dd39-103">Ejemplos de sintaxis de consulta basada en métodos: Agrupar</span><span class="sxs-lookup"><span data-stu-id="9dd39-103">Method-Based Query Syntax Examples: Grouping</span></span>

<span data-ttu-id="9dd39-104">En los ejemplos de este tema se muestra cómo usar el `GroupBy` método para consultar el [modelo AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) con la sintaxis de consulta basada en métodos.</span><span class="sxs-lookup"><span data-stu-id="9dd39-104">The examples in this topic show you how to use the `GroupBy` method to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using method-based query syntax.</span></span> <span data-ttu-id="9dd39-105">El modelo AdventureWorks Sales que se usa en estos ejemplos se crea a partir de las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail de la base de datos de ejemplo AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="9dd39-105">The AdventureWorks Sales Model that is used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="9dd39-106">En los ejemplos de este tema se usan las siguientes `using` / `Imports` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="9dd39-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="example"></a><span data-ttu-id="9dd39-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9dd39-107">Example</span></span>  

 <span data-ttu-id="9dd39-108">En el ejemplo siguiente se utiliza el método `GroupBy` para devolver objetos `Address` agrupados por código postal.</span><span class="sxs-lookup"><span data-stu-id="9dd39-108">The following example uses the `GroupBy` method to return `Address` objects that are grouped by postal code.</span></span> <span data-ttu-id="9dd39-109">Los resultados se proyectan en un tipo anónimo.</span><span class="sxs-lookup"><span data-stu-id="9dd39-109">The results are projected into an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupBySimple3_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbysimple3_mq)]
 [!code-vb[DP L2E Examples#GroupBySimple3_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbysimple3_mq)]  
  
## <a name="example"></a><span data-ttu-id="9dd39-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9dd39-110">Example</span></span>  

 <span data-ttu-id="9dd39-111">En el ejemplo siguiente se utiliza el método `GroupBy` para devolver objetos `Contact` agrupados por la primera letra del apellido del contacto.</span><span class="sxs-lookup"><span data-stu-id="9dd39-111">The following example uses the `GroupBy` method to return `Contact` objects that are grouped by the first letter of the contact's last name.</span></span> <span data-ttu-id="9dd39-112">Los resultados se ordenan también por la primera letra del apellido y se proyectan en un tipo anónimo.</span><span class="sxs-lookup"><span data-stu-id="9dd39-112">The results are also sorted by the first letter of the last name and projected into an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupBySimple2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbysimple2_mq)]
 [!code-vb[DP L2E Examples#GroupBySimple2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbysimple2_mq)]  
  
## <a name="example"></a><span data-ttu-id="9dd39-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9dd39-113">Example</span></span>  

 <span data-ttu-id="9dd39-114">En el ejemplo siguiente se utiliza el método `GroupBy` para devolver objetos `SalesOrderHeader` agrupados por identificador de cliente.</span><span class="sxs-lookup"><span data-stu-id="9dd39-114">The following example uses the `GroupBy` method to return `SalesOrderHeader` objects that are grouped by customer ID.</span></span> <span data-ttu-id="9dd39-115">También se devuelve el número de ventas para cada cliente.</span><span class="sxs-lookup"><span data-stu-id="9dd39-115">The number of sales for each customer is also returned.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupByCount_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbycount_mq)]
 [!code-vb[DP L2E Examples#GroupByCount_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbycount_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="9dd39-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="9dd39-116">See also</span></span>

- [<span data-ttu-id="9dd39-117">Consultas en LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="9dd39-117">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
