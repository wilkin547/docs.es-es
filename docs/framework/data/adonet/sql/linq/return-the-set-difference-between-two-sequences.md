---
title: Devolver la diferencia de conjuntos entre dos secuencias
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 62efb546-c898-408f-af21-36e7c6fed217
ms.openlocfilehash: 49a8d22377ef1f7d0fde16880a82002754e1bbc4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91200334"
---
# <a name="return-the-set-difference-between-two-sequences"></a><span data-ttu-id="c0692-102">Devolver la diferencia de conjuntos entre dos secuencias</span><span class="sxs-lookup"><span data-stu-id="c0692-102">Return the Set Difference Between Two Sequences</span></span>

<span data-ttu-id="c0692-103">Utilice el operador <xref:System.Linq.Queryable.Except%2A> para devolver la diferencia de conjuntos entre dos secuencias.</span><span class="sxs-lookup"><span data-stu-id="c0692-103">Use the <xref:System.Linq.Queryable.Except%2A> operator to return the set difference between two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c0692-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c0692-104">Example</span></span>  

 <span data-ttu-id="c0692-105">En este ejemplo <xref:System.Linq.Queryable.Except%2A> se usa para devolver una secuencia de todos los países o regiones en los que se encuentran `Customers` activos, pero en los que no hay `Employees` activo.</span><span class="sxs-lookup"><span data-stu-id="c0692-105">This example uses <xref:System.Linq.Queryable.Except%2A> to return a sequence of all countries/regions in which `Customers` live but in which no `Employees` live.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#41](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#41)]
 [!code-vb[DLinqQueryExamples#41](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#41)]  
  
 <span data-ttu-id="c0692-106">En [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], la operación <xref:System.Linq.Queryable.Except%2A> se define correctamente sólo en conjuntos.</span><span class="sxs-lookup"><span data-stu-id="c0692-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Except%2A> operation is well defined only on sets.</span></span> <span data-ttu-id="c0692-107">La semántica de conjuntos múltiples no está definida.</span><span class="sxs-lookup"><span data-stu-id="c0692-107">The semantics for multisets is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0692-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c0692-108">See also</span></span>

- [<span data-ttu-id="c0692-109">Ejemplos de consultas</span><span class="sxs-lookup"><span data-stu-id="c0692-109">Query Examples</span></span>](query-examples.md)
- [<span data-ttu-id="c0692-110">Traslación del operador de consulta estándar</span><span class="sxs-lookup"><span data-stu-id="c0692-110">Standard Query Operator Translation</span></span>](standard-query-operator-translation.md)
