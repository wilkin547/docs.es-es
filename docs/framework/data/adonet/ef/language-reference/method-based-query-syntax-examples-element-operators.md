---
description: 'Más información acerca de: Method-Based ejemplos de sintaxis de consultas: operadores de elementos'
title: 'Ejemplos de sintaxis de consulta basada en métodos: Operadores de elementos'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8438b995-bd07-4223-b22d-13adadef33fb
ms.openlocfilehash: 8a83602c4d374ae02b4f39ee75821718f8b53f3e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99673588"
---
# <a name="method-based-query-syntax-examples-element-operators"></a><span data-ttu-id="6a415-103">Ejemplos de sintaxis de consulta basada en métodos: Operadores de elementos</span><span class="sxs-lookup"><span data-stu-id="6a415-103">Method-Based Query Syntax Examples: Element Operators</span></span>

<span data-ttu-id="6a415-104">En los ejemplos de este tema se muestra cómo usar el <xref:System.Linq.Enumerable.First%2A> método para consultar el [modelo AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) utilizando la sintaxis de consulta basada en métodos.</span><span class="sxs-lookup"><span data-stu-id="6a415-104">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.First%2A> method to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using method-based query syntax.</span></span> <span data-ttu-id="6a415-105">El modelo AdventureWorks Sales que se usa en estos ejemplos se crea a partir de las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="6a415-105">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="6a415-106">En el ejemplo de este tema se usan las siguientes `using` / `Imports` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="6a415-106">The example in this topic uses the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="first"></a><span data-ttu-id="6a415-107">First</span><span class="sxs-lookup"><span data-stu-id="6a415-107">First</span></span>  
  
### <a name="example"></a><span data-ttu-id="6a415-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6a415-108">Example</span></span>  

 <span data-ttu-id="6a415-109">En el ejemplo siguiente se usa el <xref:System.Linq.Enumerable.First%2A> método para buscar la primera dirección de correo electrónico que empieza por "Caroline".</span><span class="sxs-lookup"><span data-stu-id="6a415-109">The following example uses the <xref:System.Linq.Enumerable.First%2A> method to find the first email address that starts with 'caroline'.</span></span>  
  
 [!code-csharp[DP L2E Examples#FirstCondition_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#firstcondition_mq)]
 [!code-vb[DP L2E Examples#FirstCondition_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#firstcondition_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="6a415-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="6a415-110">See also</span></span>

- [<span data-ttu-id="6a415-111">Consultas en LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="6a415-111">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
