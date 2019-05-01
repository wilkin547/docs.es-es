---
title: Convertir un tipo en una interfaz IEnumerable genérica
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 64774fb5-7447-4296-ad3b-8a94346f99a1
ms.openlocfilehash: d75c9b9123b52b3e241bea1bbd1d302c406715e8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62032713"
---
# <a name="convert-a-type-to-a-generic-ienumerable"></a><span data-ttu-id="21dce-102">Convertir un tipo en una interfaz IEnumerable genérica</span><span class="sxs-lookup"><span data-stu-id="21dce-102">Convert a Type to a Generic IEnumerable</span></span>
<span data-ttu-id="21dce-103">Utilice <xref:System.Linq.Enumerable.AsEnumerable%2A> para devolver el argumento cuyo tipo es una interfaz genérica `IEnumerable`.</span><span class="sxs-lookup"><span data-stu-id="21dce-103">Use <xref:System.Linq.Enumerable.AsEnumerable%2A> to return the argument typed as a generic `IEnumerable`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="21dce-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="21dce-104">Example</span></span>  
 <span data-ttu-id="21dce-105">En este ejemplo, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] (mediante la `Query` genérica predeterminada) intentaría convertir la consulta en SQL y ejecutarla en el servidor.</span><span class="sxs-lookup"><span data-stu-id="21dce-105">In this example, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] (using the default generic `Query`) would try to convert the query to SQL and execute it on the server.</span></span> <span data-ttu-id="21dce-106">Sin embargo, la cláusula `where` hace referencia a un método de cliente definido por el usuario (`isValidProduct`), que no se puede convertir a SQL.</span><span class="sxs-lookup"><span data-stu-id="21dce-106">But the `where` clause references a user-defined client-side method (`isValidProduct`), which cannot be converted to SQL.</span></span>  
  
 <span data-ttu-id="21dce-107">La solución es especificar la implementación de interfaz genérica <xref:System.Collections.Generic.IEnumerable%601> de `where` en el cliente para reemplazar la interfaz genérica <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="21dce-107">The solution is to specify the client-side generic <xref:System.Collections.Generic.IEnumerable%601> implementation of `where` to replace the generic <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="21dce-108">Para ello se invoca al operador <xref:System.Linq.Enumerable.AsEnumerable%2A>.</span><span class="sxs-lookup"><span data-stu-id="21dce-108">You do this by invoking the <xref:System.Linq.Enumerable.AsEnumerable%2A> operator.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#46](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#46)]
 [!code-vb[DLinqQueryExamples#46](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#46)]  
  
## <a name="see-also"></a><span data-ttu-id="21dce-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="21dce-109">See also</span></span>

- [<span data-ttu-id="21dce-110">Ejemplos de consultas</span><span class="sxs-lookup"><span data-stu-id="21dce-110">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
