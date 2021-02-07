---
description: 'Más información sobre: ejemplos de sintaxis de expresiones de consulta: creación de particiones'
title: 'Ejemplos de sintaxis de expresiones de consulta: Particionamiento'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7e41aed0-3be9-4f75-98de-860a85552a3c
ms.openlocfilehash: 9322f43874054ac864bda5c84ae02dfe0a49ec4f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99696001"
---
# <a name="query-expression-syntax-examples-partitioning"></a><span data-ttu-id="6265e-103">Ejemplos de sintaxis de expresiones de consulta: Particionamiento</span><span class="sxs-lookup"><span data-stu-id="6265e-103">Query Expression Syntax Examples: Partitioning</span></span>

<span data-ttu-id="6265e-104">Los ejemplos de este tema muestran cómo usar los <xref:System.Linq.Enumerable.Skip%2A> métodos y <xref:System.Linq.Enumerable.Take%2A> para consultar el [modelo AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) con la sintaxis de las expresiones de consulta.</span><span class="sxs-lookup"><span data-stu-id="6265e-104">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Skip%2A> and <xref:System.Linq.Enumerable.Take%2A> methods to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using query expression syntax.</span></span> <span data-ttu-id="6265e-105">El modelo AdventureWorks Sales que se usa en estos ejemplos se crea a partir de las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="6265e-105">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="6265e-106">En los ejemplos de este tema se usan las siguientes `using` / `Imports` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="6265e-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="skip"></a><span data-ttu-id="6265e-107">Omitir</span><span class="sxs-lookup"><span data-stu-id="6265e-107">Skip</span></span>  
  
### <a name="example"></a><span data-ttu-id="6265e-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6265e-108">Example</span></span>  

 <span data-ttu-id="6265e-109">En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.Skip%2A> para obtener las dos primeras direcciones de Seattle.</span><span class="sxs-lookup"><span data-stu-id="6265e-109">The following example uses the <xref:System.Linq.Enumerable.Skip%2A> method to get all but the first two addresses in Seattle.</span></span>  
  
 [!code-csharp[DP L2E Examples#SkipNested](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#skipnested)]
 [!code-vb[DP L2E Examples#SkipNested](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#skipnested)]  
  
## <a name="take"></a><span data-ttu-id="6265e-110">Take</span><span class="sxs-lookup"><span data-stu-id="6265e-110">Take</span></span>  
  
### <a name="example"></a><span data-ttu-id="6265e-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6265e-111">Example</span></span>  

 <span data-ttu-id="6265e-112">En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.Take%2A> para obtener las tres primeras direcciones de Seattle.</span><span class="sxs-lookup"><span data-stu-id="6265e-112">The following example uses the <xref:System.Linq.Enumerable.Take%2A> method to get the first three addresses in Seattle.</span></span>  
  
 [!code-csharp[DP L2E Examples#TakeNested](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#takenested)]
 [!code-vb[DP L2E Examples#TakeNested](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#takenested)]  
  
## <a name="see-also"></a><span data-ttu-id="6265e-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="6265e-113">See also</span></span>

- [<span data-ttu-id="6265e-114">Consultas en LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="6265e-114">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
