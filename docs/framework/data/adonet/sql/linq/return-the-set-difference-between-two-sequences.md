---
title: Devolver la diferencia de conjuntos entre dos secuencias
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 62efb546-c898-408f-af21-36e7c6fed217
ms.openlocfilehash: 92513ed33e2afb785edbdd462ba7bc14923aa6b0
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781147"
---
# <a name="return-the-set-difference-between-two-sequences"></a><span data-ttu-id="14a26-102">Devolver la diferencia de conjuntos entre dos secuencias</span><span class="sxs-lookup"><span data-stu-id="14a26-102">Return the Set Difference Between Two Sequences</span></span>
<span data-ttu-id="14a26-103">Utilice el operador <xref:System.Linq.Queryable.Except%2A> para devolver la diferencia de conjuntos entre dos secuencias.</span><span class="sxs-lookup"><span data-stu-id="14a26-103">Use the <xref:System.Linq.Queryable.Except%2A> operator to return the set difference between two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="14a26-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="14a26-104">Example</span></span>  
 <span data-ttu-id="14a26-105">En este ejemplo <xref:System.Linq.Queryable.Except%2A> se usa para devolver una secuencia de todos los países o `Customers` regiones en los que se `Employees` encuentran activos, pero en los que no hay activo.</span><span class="sxs-lookup"><span data-stu-id="14a26-105">This example uses <xref:System.Linq.Queryable.Except%2A> to return a sequence of all countries/regions in which `Customers` live but in which no `Employees` live.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#41](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#41)]
 [!code-vb[DLinqQueryExamples#41](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#41)]  
  
 <span data-ttu-id="14a26-106">En [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], la operación <xref:System.Linq.Queryable.Except%2A> se define correctamente sólo en conjuntos.</span><span class="sxs-lookup"><span data-stu-id="14a26-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Except%2A> operation is well defined only on sets.</span></span> <span data-ttu-id="14a26-107">La semántica de conjuntos múltiples no está definida.</span><span class="sxs-lookup"><span data-stu-id="14a26-107">The semantics for multisets is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14a26-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="14a26-108">See also</span></span>

- [<span data-ttu-id="14a26-109">Ejemplos de consultas</span><span class="sxs-lookup"><span data-stu-id="14a26-109">Query Examples</span></span>](query-examples.md)
- [<span data-ttu-id="14a26-110">Traslación del operador de consulta estándar</span><span class="sxs-lookup"><span data-stu-id="14a26-110">Standard Query Operator Translation</span></span>](standard-query-operator-translation.md)
