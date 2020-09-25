---
title: 'Ejemplos de sintaxis de consulta basada en métodos: Conversión'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 19f66872-d5ab-49f8-969f-e53f9632a13d
ms.openlocfilehash: e2b5ae3b7c7733216f18914c497d080fe8d71a8e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91192092"
---
# <a name="method-based-query-syntax-examples-conversion"></a><span data-ttu-id="7b3d4-102">Ejemplos de sintaxis de consulta basada en métodos: Conversión</span><span class="sxs-lookup"><span data-stu-id="7b3d4-102">Method-Based Query Syntax Examples: Conversion</span></span>

<span data-ttu-id="7b3d4-103">En los ejemplos de este tema se muestra cómo usar <xref:System.Linq.Enumerable.ToArray%2A> los <xref:System.Linq.Enumerable.ToDictionary%2A> métodos, y <xref:System.Linq.Enumerable.ToList%2A> para consultar el [modelo AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) con la sintaxis de consulta basada en métodos.</span><span class="sxs-lookup"><span data-stu-id="7b3d4-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToDictionary%2A> and <xref:System.Linq.Enumerable.ToList%2A> methods to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using method-based query syntax.</span></span> <span data-ttu-id="7b3d4-104">El modelo AdventureWorks Sales que se usa en estos ejemplos se crea a partir de las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="7b3d4-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="7b3d4-105">En los ejemplos de este tema se usan las siguientes `using` / `Imports` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="7b3d4-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="toarray"></a><span data-ttu-id="7b3d4-106">ToArray</span><span class="sxs-lookup"><span data-stu-id="7b3d4-106">ToArray</span></span>  
  
### <a name="example"></a><span data-ttu-id="7b3d4-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7b3d4-107">Example</span></span>  

 <span data-ttu-id="7b3d4-108">En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.ToArray%2A> para evaluar de forma inmediata una secuencia en una matriz.</span><span class="sxs-lookup"><span data-stu-id="7b3d4-108">The following example uses the <xref:System.Linq.Enumerable.ToArray%2A> method to immediately evaluate a sequence into an array.</span></span>  
  
 [!code-csharp[DP L2E Examples#ToArray](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#toarray)]
 [!code-vb[DP L2E Examples#ToArray](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#toarray)]  
  
## <a name="todictionary"></a><span data-ttu-id="7b3d4-109">ToDictionary</span><span class="sxs-lookup"><span data-stu-id="7b3d4-109">ToDictionary</span></span>  
  
### <a name="example"></a><span data-ttu-id="7b3d4-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7b3d4-110">Example</span></span>  

 <span data-ttu-id="7b3d4-111">En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.ToDictionary%2A> para evaluar de forma inmediata una secuencia y una expresión de clave relacionada en un diccionario.</span><span class="sxs-lookup"><span data-stu-id="7b3d4-111">The following example uses the <xref:System.Linq.Enumerable.ToDictionary%2A> method to immediately evaluate a sequence and a related key expression into a dictionary.</span></span>  
  
 [!code-csharp[DP L2E Examples#ToDictionary](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#todictionary)]
 [!code-vb[DP L2E Examples#ToDictionary](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#todictionary)]  
  
## <a name="tolist"></a><span data-ttu-id="7b3d4-112">ToList</span><span class="sxs-lookup"><span data-stu-id="7b3d4-112">ToList</span></span>  
  
### <a name="example"></a><span data-ttu-id="7b3d4-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7b3d4-113">Example</span></span>  

 <span data-ttu-id="7b3d4-114">En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.ToList%2A> para evaluar inmediatamente una secuencia en <xref:System.Collections.Generic.List%601>, donde `T` es de tipo <xref:System.Data.DataRow>.</span><span class="sxs-lookup"><span data-stu-id="7b3d4-114">The following example uses the <xref:System.Linq.Enumerable.ToList%2A> method to immediately evaluate a sequence into a <xref:System.Collections.Generic.List%601>, where `T` is of type <xref:System.Data.DataRow>.</span></span>  
  
 [!code-csharp[DP L2E Examples#ToList](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#tolist)]
 [!code-vb[DP L2E Examples#ToList](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#tolist)]  
  
## <a name="see-also"></a><span data-ttu-id="7b3d4-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7b3d4-115">See also</span></span>

- [<span data-ttu-id="7b3d4-116">Consultas en LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="7b3d4-116">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
