---
title: Devolver la intersección de conjuntos de dos secuencias
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d09c344e-3548-4944-a3ed-051880e3f5b8
ms.openlocfilehash: 944d0b2efe1e74f901a493d1c3202d0f180d599d
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70792705"
---
# <a name="return-the-set-intersection-of-two-sequences"></a><span data-ttu-id="9ac4a-102">Devolver la intersección de conjuntos de dos secuencias</span><span class="sxs-lookup"><span data-stu-id="9ac4a-102">Return the Set Intersection of Two Sequences</span></span>
<span data-ttu-id="9ac4a-103">Utilice el operador <xref:System.Linq.Queryable.Intersect%2A> para devolver la intersección de conjuntos de dos secuencias.</span><span class="sxs-lookup"><span data-stu-id="9ac4a-103">Use the <xref:System.Linq.Queryable.Intersect%2A> operator to return the set intersection of two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9ac4a-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9ac4a-104">Example</span></span>  
 <span data-ttu-id="9ac4a-105">En este ejemplo <xref:System.Linq.Queryable.Intersect%2A> se usa para devolver una secuencia de todos los países o regiones `Customers` en `Employees` los que y Live.</span><span class="sxs-lookup"><span data-stu-id="9ac4a-105">This example uses <xref:System.Linq.Queryable.Intersect%2A> to return a sequence of all countries/regions in which both `Customers` and `Employees` live.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#42](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#42)]
 [!code-vb[DLinqQueryExamples#42](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#42)]  
  
 <span data-ttu-id="9ac4a-106">En [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], la operación <xref:System.Linq.Queryable.Intersect%2A> se define correctamente sólo en conjuntos.</span><span class="sxs-lookup"><span data-stu-id="9ac4a-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Intersect%2A> operation is well defined only on sets.</span></span> <span data-ttu-id="9ac4a-107">La semántica de conjuntos múltiples no está definida.</span><span class="sxs-lookup"><span data-stu-id="9ac4a-107">The semantics for multisets is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ac4a-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="9ac4a-108">See also</span></span>

- [<span data-ttu-id="9ac4a-109">Ejemplos de consultas</span><span class="sxs-lookup"><span data-stu-id="9ac4a-109">Query Examples</span></span>](query-examples.md)
- [<span data-ttu-id="9ac4a-110">Traslación del operador de consulta estándar</span><span class="sxs-lookup"><span data-stu-id="9ac4a-110">Standard Query Operator Translation</span></span>](standard-query-operator-translation.md)
