---
title: Convertir un tipo en una interfaz IEnumerable genérica
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 64774fb5-7447-4296-ad3b-8a94346f99a1
ms.openlocfilehash: d75c9b9123b52b3e241bea1bbd1d302c406715e8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59190386"
---
# <a name="convert-a-type-to-a-generic-ienumerable"></a><span data-ttu-id="09b4b-102">Convertir un tipo en una interfaz IEnumerable genérica</span><span class="sxs-lookup"><span data-stu-id="09b4b-102">Convert a Type to a Generic IEnumerable</span></span>
<span data-ttu-id="09b4b-103">Utilice <xref:System.Linq.Enumerable.AsEnumerable%2A> para devolver el argumento cuyo tipo es una interfaz genérica `IEnumerable`.</span><span class="sxs-lookup"><span data-stu-id="09b4b-103">Use <xref:System.Linq.Enumerable.AsEnumerable%2A> to return the argument typed as a generic `IEnumerable`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="09b4b-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="09b4b-104">Example</span></span>  
 <span data-ttu-id="09b4b-105">En este ejemplo, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] (mediante la `Query` genérica predeterminada) intentaría convertir la consulta en SQL y ejecutarla en el servidor.</span><span class="sxs-lookup"><span data-stu-id="09b4b-105">In this example, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] (using the default generic `Query`) would try to convert the query to SQL and execute it on the server.</span></span> <span data-ttu-id="09b4b-106">Sin embargo, la cláusula `where` hace referencia a un método de cliente definido por el usuario (`isValidProduct`), que no se puede convertir a SQL.</span><span class="sxs-lookup"><span data-stu-id="09b4b-106">But the `where` clause references a user-defined client-side method (`isValidProduct`), which cannot be converted to SQL.</span></span>  
  
 <span data-ttu-id="09b4b-107">La solución es especificar la implementación de interfaz genérica <xref:System.Collections.Generic.IEnumerable%601> de `where` en el cliente para reemplazar la interfaz genérica <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="09b4b-107">The solution is to specify the client-side generic <xref:System.Collections.Generic.IEnumerable%601> implementation of `where` to replace the generic <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="09b4b-108">Para ello se invoca al operador <xref:System.Linq.Enumerable.AsEnumerable%2A>.</span><span class="sxs-lookup"><span data-stu-id="09b4b-108">You do this by invoking the <xref:System.Linq.Enumerable.AsEnumerable%2A> operator.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#46](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#46)]
 [!code-vb[DLinqQueryExamples#46](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#46)]  
  
## <a name="see-also"></a><span data-ttu-id="09b4b-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="09b4b-109">See also</span></span>

- [<span data-ttu-id="09b4b-110">Ejemplos de consultas</span><span class="sxs-lookup"><span data-stu-id="09b4b-110">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
