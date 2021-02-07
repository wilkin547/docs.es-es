---
description: 'Más información acerca de: ejemplos de sintaxis de expresiones de consulta: operadores de elementos'
title: 'Ejemplos de sintaxis de expresiones de consulta: Operadores de elementos'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 32268fe2-de18-4065-8060-f250def83837
ms.openlocfilehash: 0dc6d49959abba712cef572eaa549138af646bd5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99696248"
---
# <a name="query-expression-syntax-examples-element-operators"></a><span data-ttu-id="0ba52-103">Ejemplos de sintaxis de expresiones de consulta: Operadores de elementos</span><span class="sxs-lookup"><span data-stu-id="0ba52-103">Query Expression Syntax Examples: Element Operators</span></span>

<span data-ttu-id="0ba52-104">En los ejemplos de este tema se muestra cómo usar el <xref:System.Linq.Enumerable.First%2A> método para consultar el [modelo AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) mediante la sintaxis de las expresiones de consulta.</span><span class="sxs-lookup"><span data-stu-id="0ba52-104">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.First%2A> method to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using the query expression syntax.</span></span> <span data-ttu-id="0ba52-105">El modelo AdventureWorks Sales que se usa en estos ejemplos se crea a partir de las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="0ba52-105">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="0ba52-106">En los ejemplos de este tema se usan las siguientes `using` / `Imports` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="0ba52-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="first"></a><span data-ttu-id="0ba52-107">First</span><span class="sxs-lookup"><span data-stu-id="0ba52-107">First</span></span>  
  
### <a name="example"></a><span data-ttu-id="0ba52-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0ba52-108">Example</span></span>  

 <span data-ttu-id="0ba52-109">En el ejemplo siguiente se usa el método <xref:System.Linq.Enumerable.First%2A> para devolver el primer contacto cuyo nombre es "Brooke".</span><span class="sxs-lookup"><span data-stu-id="0ba52-109">The following example uses the <xref:System.Linq.Enumerable.First%2A> method to return the first contact whose first name is "Brooke".</span></span>  
  
 [!code-csharp[DP L2E Examples#FirstSimple](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#firstsimple)]
 [!code-vb[DP L2E Examples#FirstSimple](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#firstsimple)]  
  
## <a name="see-also"></a><span data-ttu-id="0ba52-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="0ba52-110">See also</span></span>

- [<span data-ttu-id="0ba52-111">Consultas en LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="0ba52-111">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
