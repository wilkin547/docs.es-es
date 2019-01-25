---
title: 'Ejemplos de sintaxis de consulta basada en métodos: Particionamiento'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b7b64874-c3c8-4bdb-862c-89a168d07827
ms.openlocfilehash: 2155d0cb9aa47e5940974db92077b51f8139e09d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54536079"
---
# <a name="method-based-query-syntax-examples-partitioning"></a><span data-ttu-id="8f300-102">Ejemplos de sintaxis de consulta basada en métodos: Particionamiento</span><span class="sxs-lookup"><span data-stu-id="8f300-102">Method-Based Query Syntax Examples: Partitioning</span></span>
<span data-ttu-id="8f300-103">Los ejemplos de este tema muestran cómo usar el <xref:System.Linq.Enumerable.Skip%2A>, y <xref:System.Linq.Enumerable.Take%2A> métodos para consultar el [modelo AdventureWorks Sales](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) con la sintaxis de expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="8f300-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Skip%2A>, and <xref:System.Linq.Enumerable.Take%2A> methods to query the [AdventureWorks Sales Model](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) using query expression syntax.</span></span> <span data-ttu-id="8f300-104">El modelo AdventureWorks Sales que se usa en estos ejemplos se crea a partir de las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="8f300-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="8f300-105">Los ejemplos de este tema usan los siguientes `using` / `Imports` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="8f300-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="skip"></a><span data-ttu-id="8f300-106">Skip</span><span class="sxs-lookup"><span data-stu-id="8f300-106">Skip</span></span>  
  
### <a name="example"></a><span data-ttu-id="8f300-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8f300-107">Example</span></span>  
 <span data-ttu-id="8f300-108">En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.Skip%2A> para obtener todos los contactos menos los cinco primeros de la tabla Contact.</span><span class="sxs-lookup"><span data-stu-id="8f300-108">The following example uses the <xref:System.Linq.Enumerable.Skip%2A> method to get all but the first five contacts of the Contact table.</span></span>  
  
 [!code-csharp[DP L2E Examples#SkipSimple](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#skipsimple)]
 [!code-vb[DP L2E Examples#SkipSimple](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#skipsimple)]  
  
### <a name="example"></a><span data-ttu-id="8f300-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8f300-109">Example</span></span>  
 <span data-ttu-id="8f300-110">En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.Skip%2A> para obtener las dos primeras direcciones de Seattle.</span><span class="sxs-lookup"><span data-stu-id="8f300-110">The following example uses the <xref:System.Linq.Enumerable.Skip%2A> method to get all but the first two addresses in Seattle.</span></span>  
  
 [!code-csharp[DP L2E Examples#SkipNested](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#skipnested)]
 [!code-vb[DP L2E Examples#SkipNested](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#skipnested)]  
  
## <a name="take"></a><span data-ttu-id="8f300-111">Take</span><span class="sxs-lookup"><span data-stu-id="8f300-111">Take</span></span>  
  
### <a name="example"></a><span data-ttu-id="8f300-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8f300-112">Example</span></span>  
 <span data-ttu-id="8f300-113">En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.Take%2A> para obtener únicamente los cinco primeros contactos de la tabla Contact.</span><span class="sxs-lookup"><span data-stu-id="8f300-113">The following example uses the <xref:System.Linq.Enumerable.Take%2A> method to get only the first five contacts from the Contact table.</span></span>  
  
 [!code-csharp[DP L2E Examples#TakeSimple](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#takesimple)]
 [!code-vb[DP L2E Examples#TakeSimple](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#takesimple)]  
  
### <a name="example"></a><span data-ttu-id="8f300-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8f300-114">Example</span></span>  
 <span data-ttu-id="8f300-115">En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.Take%2A> para obtener las tres primeras direcciones de Seattle.</span><span class="sxs-lookup"><span data-stu-id="8f300-115">The following example uses the <xref:System.Linq.Enumerable.Take%2A> method to get the first three addresses in Seattle.</span></span>  
  
 [!code-csharp[DP L2E Examples#TakeNested](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#takenested)]
 [!code-vb[DP L2E Examples#TakeNested](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#takenested)]  
  
## <a name="see-also"></a><span data-ttu-id="8f300-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="8f300-116">See also</span></span>
- [<span data-ttu-id="8f300-117">Consultas en LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="8f300-117">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
