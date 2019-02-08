---
title: 'Ejemplos de sintaxis de consulta basada en métodos: Operadores de elementos'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8438b995-bd07-4223-b22d-13adadef33fb
ms.openlocfilehash: 89cbda4d049b30ee50accf94d5b7ec172bc25ae2
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/07/2019
ms.locfileid: "55826504"
---
# <a name="method-based-query-syntax-examples-element-operators"></a><span data-ttu-id="d4098-102">Ejemplos de sintaxis de consulta basada en métodos: Operadores de elementos</span><span class="sxs-lookup"><span data-stu-id="d4098-102">Method-Based Query Syntax Examples: Element Operators</span></span>
<span data-ttu-id="d4098-103">Los ejemplos de este tema muestran cómo usar el <xref:System.Linq.Enumerable.First%2A> método para consultar el [modelo AdventureWorks Sales](https://archive.codeplex.com/?p=msftdbprodsamples) utilizando sintaxis de consulta basada en métodos.</span><span class="sxs-lookup"><span data-stu-id="d4098-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.First%2A> method to query the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples) using method-based query syntax.</span></span> <span data-ttu-id="d4098-104">El modelo AdventureWorks Sales que se usa en estos ejemplos se crea a partir de las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="d4098-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="d4098-105">El ejemplo de este tema usa las siguientes `using` / `Imports` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="d4098-105">The example in this topic uses the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="first"></a><span data-ttu-id="d4098-106">First</span><span class="sxs-lookup"><span data-stu-id="d4098-106">First</span></span>  
  
### <a name="example"></a><span data-ttu-id="d4098-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d4098-107">Example</span></span>  
 <span data-ttu-id="d4098-108">En el ejemplo siguiente se usa el <xref:System.Linq.Enumerable.First%2A> método para buscar la primera dirección de correo electrónico que empieza por "caroline".</span><span class="sxs-lookup"><span data-stu-id="d4098-108">The following example uses the <xref:System.Linq.Enumerable.First%2A> method to find the first email address that starts with 'caroline'.</span></span>  
  
 [!code-csharp[DP L2E Examples#FirstCondition_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#firstcondition_mq)]
 [!code-vb[DP L2E Examples#FirstCondition_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#firstcondition_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="d4098-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="d4098-109">See also</span></span>
- [<span data-ttu-id="d4098-110">Consultas en LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="d4098-110">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
