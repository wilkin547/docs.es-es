---
title: Convertir un tipo en una interfaz IEnumerable genérica
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 64774fb5-7447-4296-ad3b-8a94346f99a1
ms.openlocfilehash: c2d34ae708f79d9f920679b3714a100fe8943c38
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164420"
---
# <a name="convert-a-type-to-a-generic-ienumerable"></a><span data-ttu-id="eb969-102">Convertir un tipo en una interfaz IEnumerable genérica</span><span class="sxs-lookup"><span data-stu-id="eb969-102">Convert a Type to a Generic IEnumerable</span></span>

<span data-ttu-id="eb969-103">Utilice <xref:System.Linq.Enumerable.AsEnumerable%2A> para devolver el argumento cuyo tipo es una interfaz genérica `IEnumerable`.</span><span class="sxs-lookup"><span data-stu-id="eb969-103">Use <xref:System.Linq.Enumerable.AsEnumerable%2A> to return the argument typed as a generic `IEnumerable`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb969-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="eb969-104">Example</span></span>  

 <span data-ttu-id="eb969-105">En este ejemplo, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] (mediante la `Query` genérica predeterminada) intentaría convertir la consulta en SQL y ejecutarla en el servidor.</span><span class="sxs-lookup"><span data-stu-id="eb969-105">In this example, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] (using the default generic `Query`) would try to convert the query to SQL and execute it on the server.</span></span> <span data-ttu-id="eb969-106">Sin embargo, la cláusula `where` hace referencia a un método de cliente definido por el usuario (`isValidProduct`), que no se puede convertir a SQL.</span><span class="sxs-lookup"><span data-stu-id="eb969-106">But the `where` clause references a user-defined client-side method (`isValidProduct`), which cannot be converted to SQL.</span></span>  
  
 <span data-ttu-id="eb969-107">La solución es especificar la implementación de interfaz genérica <xref:System.Collections.Generic.IEnumerable%601> de `where` en el cliente para reemplazar la interfaz genérica <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="eb969-107">The solution is to specify the client-side generic <xref:System.Collections.Generic.IEnumerable%601> implementation of `where` to replace the generic <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="eb969-108">Para ello se invoca al operador <xref:System.Linq.Enumerable.AsEnumerable%2A>.</span><span class="sxs-lookup"><span data-stu-id="eb969-108">You do this by invoking the <xref:System.Linq.Enumerable.AsEnumerable%2A> operator.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#46](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#46)]
 [!code-vb[DLinqQueryExamples#46](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#46)]  
  
## <a name="see-also"></a><span data-ttu-id="eb969-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="eb969-109">See also</span></span>

- [<span data-ttu-id="eb969-110">Ejemplos de consultas</span><span class="sxs-lookup"><span data-stu-id="eb969-110">Query Examples</span></span>](query-examples.md)
