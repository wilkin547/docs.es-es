---
title: 'Ejemplos de sintaxis de consultas basadas en métodos: particionamiento'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b7b64874-c3c8-4bdb-862c-89a168d07827
ms.openlocfilehash: 5e2707463fd3cb9a5761805bc335104486ac44d7
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="method-based-query-syntax-examples-partitioning"></a><span data-ttu-id="3d9fa-102">Ejemplos de sintaxis de consultas basadas en métodos: particionamiento</span><span class="sxs-lookup"><span data-stu-id="3d9fa-102">Method-Based Query Syntax Examples: Partitioning</span></span>
<span data-ttu-id="3d9fa-103">Los ejemplos de este tema muestran cómo usar el <xref:System.Linq.Enumerable.Skip%2A>, y <xref:System.Linq.Enumerable.Take%2A> métodos para consultar el [modelo AdventureWorks Sales](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) utilizando la sintaxis de expresiones de consulta.</span><span class="sxs-lookup"><span data-stu-id="3d9fa-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Skip%2A>, and <xref:System.Linq.Enumerable.Take%2A> methods to query the [AdventureWorks Sales Model](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) using query expression syntax.</span></span> <span data-ttu-id="3d9fa-104">El modelo AdventureWorks Sales que se usa en estos ejemplos se crea a partir de las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="3d9fa-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="3d9fa-105">Los ejemplos de este tema usan los siguientes `using` / `Imports` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="3d9fa-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="skip"></a><span data-ttu-id="3d9fa-106">Skip</span><span class="sxs-lookup"><span data-stu-id="3d9fa-106">Skip</span></span>  
  
### <a name="example"></a><span data-ttu-id="3d9fa-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3d9fa-107">Example</span></span>  
 <span data-ttu-id="3d9fa-108">En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.Skip%2A> para obtener todos los contactos menos los cinco primeros de la tabla Contact.</span><span class="sxs-lookup"><span data-stu-id="3d9fa-108">The following example uses the <xref:System.Linq.Enumerable.Skip%2A> method to get all but the first five contacts of the Contact table.</span></span>  
  
 [!code-csharp[DP L2E Examples#SkipSimple](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#skipsimple)]
 [!code-vb[DP L2E Examples#SkipSimple](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#skipsimple)]  
  
### <a name="example"></a><span data-ttu-id="3d9fa-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3d9fa-109">Example</span></span>  
 <span data-ttu-id="3d9fa-110">En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.Skip%2A> para obtener las dos primeras direcciones de Seattle.</span><span class="sxs-lookup"><span data-stu-id="3d9fa-110">The following example uses the <xref:System.Linq.Enumerable.Skip%2A> method to get all but the first two addresses in Seattle.</span></span>  
  
 [!code-csharp[DP L2E Examples#SkipNested](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#skipnested)]
 [!code-vb[DP L2E Examples#SkipNested](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#skipnested)]  
  
## <a name="take"></a><span data-ttu-id="3d9fa-111">Take</span><span class="sxs-lookup"><span data-stu-id="3d9fa-111">Take</span></span>  
  
### <a name="example"></a><span data-ttu-id="3d9fa-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3d9fa-112">Example</span></span>  
 <span data-ttu-id="3d9fa-113">En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.Take%2A> para obtener únicamente los cinco primeros contactos de la tabla Contact.</span><span class="sxs-lookup"><span data-stu-id="3d9fa-113">The following example uses the <xref:System.Linq.Enumerable.Take%2A> method to get only the first five contacts from the Contact table.</span></span>  
  
 [!code-csharp[DP L2E Examples#TakeSimple](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#takesimple)]
 [!code-vb[DP L2E Examples#TakeSimple](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#takesimple)]  
  
### <a name="example"></a><span data-ttu-id="3d9fa-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3d9fa-114">Example</span></span>  
 <span data-ttu-id="3d9fa-115">En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.Take%2A> para obtener las tres primeras direcciones de Seattle.</span><span class="sxs-lookup"><span data-stu-id="3d9fa-115">The following example uses the <xref:System.Linq.Enumerable.Take%2A> method to get the first three addresses in Seattle.</span></span>  
  
 [!code-csharp[DP L2E Examples#TakeNested](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#takenested)]
 [!code-vb[DP L2E Examples#TakeNested](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#takenested)]  
  
## <a name="see-also"></a><span data-ttu-id="3d9fa-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="3d9fa-116">See Also</span></span>  
 [<span data-ttu-id="3d9fa-117">Consultas en LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="3d9fa-117">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
