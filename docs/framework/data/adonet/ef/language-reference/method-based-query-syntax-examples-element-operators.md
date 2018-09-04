---
title: 'Ejemplos de sintaxis de consultas basadas en métodos: operadores de elementos'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8438b995-bd07-4223-b22d-13adadef33fb
ms.openlocfilehash: 4215dcddf44647d98ee70c6f2d06345737cba5de
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43503233"
---
# <a name="method-based-query-syntax-examples-element-operators"></a><span data-ttu-id="d2133-102">Ejemplos de sintaxis de consultas basadas en métodos: operadores de elementos</span><span class="sxs-lookup"><span data-stu-id="d2133-102">Method-Based Query Syntax Examples: Element Operators</span></span>
<span data-ttu-id="d2133-103">Los ejemplos de este tema muestran cómo usar el <xref:System.Linq.Enumerable.First%2A> método para consultar el [modelo AdventureWorks Sales](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) utilizando sintaxis de consulta basada en métodos.</span><span class="sxs-lookup"><span data-stu-id="d2133-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.First%2A> method to query the [AdventureWorks Sales Model](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) using method-based query syntax.</span></span> <span data-ttu-id="d2133-104">El modelo AdventureWorks Sales que se usa en estos ejemplos se crea a partir de las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="d2133-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="d2133-105">El ejemplo de este tema usa las siguientes `using` / `Imports` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="d2133-105">The example in this topic uses the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="first"></a><span data-ttu-id="d2133-106">First</span><span class="sxs-lookup"><span data-stu-id="d2133-106">First</span></span>  
  
### <a name="example"></a><span data-ttu-id="d2133-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d2133-107">Example</span></span>  
 <span data-ttu-id="d2133-108">En el ejemplo siguiente se usa el <xref:System.Linq.Enumerable.First%2A> método para buscar la primera dirección de correo electrónico que empieza por "caroline".</span><span class="sxs-lookup"><span data-stu-id="d2133-108">The following example uses the <xref:System.Linq.Enumerable.First%2A> method to find the first email address that starts with 'caroline'.</span></span>  
  
 [!code-csharp[DP L2E Examples#FirstCondition_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#firstcondition_mq)]
 [!code-vb[DP L2E Examples#FirstCondition_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#firstcondition_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="d2133-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="d2133-109">See Also</span></span>  
 [<span data-ttu-id="d2133-110">Consultas en LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="d2133-110">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
