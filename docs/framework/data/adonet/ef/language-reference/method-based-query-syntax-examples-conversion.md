---
description: 'Más información sobre: Method-Based ejemplos de sintaxis de consultas: conversión'
title: 'Ejemplos de sintaxis de consulta basada en métodos: Conversión'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 19f66872-d5ab-49f8-969f-e53f9632a13d
ms.openlocfilehash: 054ef9291a66216b14e2f03ecebd28fb24c6574d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99696755"
---
# <a name="method-based-query-syntax-examples-conversion"></a><span data-ttu-id="c2d3c-103">Ejemplos de sintaxis de consulta basada en métodos: Conversión</span><span class="sxs-lookup"><span data-stu-id="c2d3c-103">Method-Based Query Syntax Examples: Conversion</span></span>

<span data-ttu-id="c2d3c-104">En los ejemplos de este tema se muestra cómo usar <xref:System.Linq.Enumerable.ToArray%2A> los <xref:System.Linq.Enumerable.ToDictionary%2A> métodos, y <xref:System.Linq.Enumerable.ToList%2A> para consultar el [modelo AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) con la sintaxis de consulta basada en métodos.</span><span class="sxs-lookup"><span data-stu-id="c2d3c-104">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToDictionary%2A> and <xref:System.Linq.Enumerable.ToList%2A> methods to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using method-based query syntax.</span></span> <span data-ttu-id="c2d3c-105">El modelo AdventureWorks Sales que se usa en estos ejemplos se crea a partir de las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="c2d3c-105">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="c2d3c-106">En los ejemplos de este tema se usan las siguientes `using` / `Imports` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="c2d3c-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="toarray"></a><span data-ttu-id="c2d3c-107">ToArray</span><span class="sxs-lookup"><span data-stu-id="c2d3c-107">ToArray</span></span>  
  
### <a name="example"></a><span data-ttu-id="c2d3c-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c2d3c-108">Example</span></span>  

 <span data-ttu-id="c2d3c-109">En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.ToArray%2A> para evaluar de forma inmediata una secuencia en una matriz.</span><span class="sxs-lookup"><span data-stu-id="c2d3c-109">The following example uses the <xref:System.Linq.Enumerable.ToArray%2A> method to immediately evaluate a sequence into an array.</span></span>  
  
 [!code-csharp[DP L2E Examples#ToArray](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#toarray)]
 [!code-vb[DP L2E Examples#ToArray](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#toarray)]  
  
## <a name="todictionary"></a><span data-ttu-id="c2d3c-110">ToDictionary</span><span class="sxs-lookup"><span data-stu-id="c2d3c-110">ToDictionary</span></span>  
  
### <a name="example"></a><span data-ttu-id="c2d3c-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c2d3c-111">Example</span></span>  

 <span data-ttu-id="c2d3c-112">En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.ToDictionary%2A> para evaluar de forma inmediata una secuencia y una expresión de clave relacionada en un diccionario.</span><span class="sxs-lookup"><span data-stu-id="c2d3c-112">The following example uses the <xref:System.Linq.Enumerable.ToDictionary%2A> method to immediately evaluate a sequence and a related key expression into a dictionary.</span></span>  
  
 [!code-csharp[DP L2E Examples#ToDictionary](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#todictionary)]
 [!code-vb[DP L2E Examples#ToDictionary](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#todictionary)]  
  
## <a name="tolist"></a><span data-ttu-id="c2d3c-113">ToList</span><span class="sxs-lookup"><span data-stu-id="c2d3c-113">ToList</span></span>  
  
### <a name="example"></a><span data-ttu-id="c2d3c-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c2d3c-114">Example</span></span>  

 <span data-ttu-id="c2d3c-115">En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.ToList%2A> para evaluar inmediatamente una secuencia en <xref:System.Collections.Generic.List%601>, donde `T` es de tipo <xref:System.Data.DataRow>.</span><span class="sxs-lookup"><span data-stu-id="c2d3c-115">The following example uses the <xref:System.Linq.Enumerable.ToList%2A> method to immediately evaluate a sequence into a <xref:System.Collections.Generic.List%601>, where `T` is of type <xref:System.Data.DataRow>.</span></span>  
  
 [!code-csharp[DP L2E Examples#ToList](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#tolist)]
 [!code-vb[DP L2E Examples#ToList](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#tolist)]  
  
## <a name="see-also"></a><span data-ttu-id="c2d3c-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="c2d3c-116">See also</span></span>

- [<span data-ttu-id="c2d3c-117">Consultas en LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="c2d3c-117">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
