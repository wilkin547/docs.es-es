---
title: 'Ejemplos de sintaxis de expresiones de consulta: Operadores de elementos'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 32268fe2-de18-4065-8060-f250def83837
ms.openlocfilehash: 5736828a629368a5b9abea9e63f7df2d2de3ca8d
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249521"
---
# <a name="query-expression-syntax-examples-element-operators"></a><span data-ttu-id="9ae98-102">Ejemplos de sintaxis de expresiones de consulta: Operadores de elementos</span><span class="sxs-lookup"><span data-stu-id="9ae98-102">Query Expression Syntax Examples: Element Operators</span></span>
<span data-ttu-id="9ae98-103">En los ejemplos de este tema se muestra cómo usar <xref:System.Linq.Enumerable.First%2A> el método para consultar el [modelo AdventureWorks Sales](https://archive.codeplex.com/?p=msftdbprodsamples) mediante la sintaxis de las expresiones de consulta.</span><span class="sxs-lookup"><span data-stu-id="9ae98-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.First%2A> method to query the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples) using the query expression syntax.</span></span> <span data-ttu-id="9ae98-104">El modelo AdventureWorks Sales que se usa en estos ejemplos se crea a partir de las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="9ae98-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="9ae98-105">En los ejemplos de este tema se usan `using` las siguientes / `Imports` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="9ae98-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="first"></a><span data-ttu-id="9ae98-106">Primero</span><span class="sxs-lookup"><span data-stu-id="9ae98-106">First</span></span>  
  
### <a name="example"></a><span data-ttu-id="9ae98-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9ae98-107">Example</span></span>  
 <span data-ttu-id="9ae98-108">En el ejemplo siguiente se usa el método <xref:System.Linq.Enumerable.First%2A> para devolver el primer contacto cuyo nombre es "Brooke".</span><span class="sxs-lookup"><span data-stu-id="9ae98-108">The following example uses the <xref:System.Linq.Enumerable.First%2A> method to return the first contact whose first name is "Brooke".</span></span>  
  
 [!code-csharp[DP L2E Examples#FirstSimple](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#firstsimple)]
 [!code-vb[DP L2E Examples#FirstSimple](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#firstsimple)]  
  
## <a name="see-also"></a><span data-ttu-id="9ae98-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="9ae98-109">See also</span></span>

- [<span data-ttu-id="9ae98-110">Consultas en LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="9ae98-110">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
