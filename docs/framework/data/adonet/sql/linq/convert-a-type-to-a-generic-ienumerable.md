---
description: 'Más información sobre: convertir un tipo en un IEnumerable genérico'
title: Convertir un tipo en una interfaz IEnumerable genérica
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 64774fb5-7447-4296-ad3b-8a94346f99a1
ms.openlocfilehash: 9be9022bce84808e18514937116ea962065dc1a8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99712524"
---
# <a name="convert-a-type-to-a-generic-ienumerable"></a><span data-ttu-id="e4cf0-103">Convertir un tipo en una interfaz IEnumerable genérica</span><span class="sxs-lookup"><span data-stu-id="e4cf0-103">Convert a Type to a Generic IEnumerable</span></span>

<span data-ttu-id="e4cf0-104">Utilice <xref:System.Linq.Enumerable.AsEnumerable%2A> para devolver el argumento cuyo tipo es una interfaz genérica `IEnumerable`.</span><span class="sxs-lookup"><span data-stu-id="e4cf0-104">Use <xref:System.Linq.Enumerable.AsEnumerable%2A> to return the argument typed as a generic `IEnumerable`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e4cf0-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e4cf0-105">Example</span></span>  

 <span data-ttu-id="e4cf0-106">En este ejemplo, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] (mediante la `Query` genérica predeterminada) intentaría convertir la consulta en SQL y ejecutarla en el servidor.</span><span class="sxs-lookup"><span data-stu-id="e4cf0-106">In this example, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] (using the default generic `Query`) would try to convert the query to SQL and execute it on the server.</span></span> <span data-ttu-id="e4cf0-107">Sin embargo, la cláusula `where` hace referencia a un método de cliente definido por el usuario (`isValidProduct`), que no se puede convertir a SQL.</span><span class="sxs-lookup"><span data-stu-id="e4cf0-107">But the `where` clause references a user-defined client-side method (`isValidProduct`), which cannot be converted to SQL.</span></span>  
  
 <span data-ttu-id="e4cf0-108">La solución es especificar la implementación de interfaz genérica <xref:System.Collections.Generic.IEnumerable%601> de `where` en el cliente para reemplazar la interfaz genérica <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="e4cf0-108">The solution is to specify the client-side generic <xref:System.Collections.Generic.IEnumerable%601> implementation of `where` to replace the generic <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="e4cf0-109">Para ello se invoca al operador <xref:System.Linq.Enumerable.AsEnumerable%2A>.</span><span class="sxs-lookup"><span data-stu-id="e4cf0-109">You do this by invoking the <xref:System.Linq.Enumerable.AsEnumerable%2A> operator.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#46](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#46)]
 [!code-vb[DLinqQueryExamples#46](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#46)]  
  
## <a name="see-also"></a><span data-ttu-id="e4cf0-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="e4cf0-110">See also</span></span>

- [<span data-ttu-id="e4cf0-111">Ejemplos de consultas</span><span class="sxs-lookup"><span data-stu-id="e4cf0-111">Query Examples</span></span>](query-examples.md)
