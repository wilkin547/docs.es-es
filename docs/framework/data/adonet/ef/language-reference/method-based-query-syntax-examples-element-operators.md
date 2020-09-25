---
title: 'Ejemplos de sintaxis de consulta basada en métodos: Operadores de elementos'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8438b995-bd07-4223-b22d-13adadef33fb
ms.openlocfilehash: 96d393a34af69935e75582ef1954ddd661a355f0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91192053"
---
# <a name="method-based-query-syntax-examples-element-operators"></a><span data-ttu-id="237a4-102">Ejemplos de sintaxis de consulta basada en métodos: Operadores de elementos</span><span class="sxs-lookup"><span data-stu-id="237a4-102">Method-Based Query Syntax Examples: Element Operators</span></span>

<span data-ttu-id="237a4-103">En los ejemplos de este tema se muestra cómo usar el <xref:System.Linq.Enumerable.First%2A> método para consultar el [modelo AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) utilizando la sintaxis de consulta basada en métodos.</span><span class="sxs-lookup"><span data-stu-id="237a4-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.First%2A> method to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using method-based query syntax.</span></span> <span data-ttu-id="237a4-104">El modelo AdventureWorks Sales que se usa en estos ejemplos se crea a partir de las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="237a4-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="237a4-105">En el ejemplo de este tema se usan las siguientes `using` / `Imports` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="237a4-105">The example in this topic uses the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="first"></a><span data-ttu-id="237a4-106">First</span><span class="sxs-lookup"><span data-stu-id="237a4-106">First</span></span>  
  
### <a name="example"></a><span data-ttu-id="237a4-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="237a4-107">Example</span></span>  

 <span data-ttu-id="237a4-108">En el ejemplo siguiente se usa el <xref:System.Linq.Enumerable.First%2A> método para buscar la primera dirección de correo electrónico que empieza por "Caroline".</span><span class="sxs-lookup"><span data-stu-id="237a4-108">The following example uses the <xref:System.Linq.Enumerable.First%2A> method to find the first email address that starts with 'caroline'.</span></span>  
  
 [!code-csharp[DP L2E Examples#FirstCondition_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#firstcondition_mq)]
 [!code-vb[DP L2E Examples#FirstCondition_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#firstcondition_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="237a4-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="237a4-109">See also</span></span>

- [<span data-ttu-id="237a4-110">Consultas en LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="237a4-110">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
