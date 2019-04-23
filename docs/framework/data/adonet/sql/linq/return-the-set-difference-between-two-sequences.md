---
title: Devolver la diferencia de conjuntos entre dos secuencias
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 62efb546-c898-408f-af21-36e7c6fed217
ms.openlocfilehash: 7edc60c7ab8510aadd9ac273529a88adeb41352a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59124285"
---
# <a name="return-the-set-difference-between-two-sequences"></a><span data-ttu-id="1d733-102">Devolver la diferencia de conjuntos entre dos secuencias</span><span class="sxs-lookup"><span data-stu-id="1d733-102">Return the Set Difference Between Two Sequences</span></span>
<span data-ttu-id="1d733-103">Utilice el operador <xref:System.Linq.Queryable.Except%2A> para devolver la diferencia de conjuntos entre dos secuencias.</span><span class="sxs-lookup"><span data-stu-id="1d733-103">Use the <xref:System.Linq.Queryable.Except%2A> operator to return the set difference between two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1d733-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1d733-104">Example</span></span>  
 <span data-ttu-id="1d733-105">En este ejemplo se utiliza <xref:System.Linq.Queryable.Except%2A> para devolver una secuencia de todos los países en los que viven `Customers` pero no `Employees`.</span><span class="sxs-lookup"><span data-stu-id="1d733-105">This example uses <xref:System.Linq.Queryable.Except%2A> to return a sequence of all countries in which `Customers` live but in which no `Employees` live.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#41](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#41)]
 [!code-vb[DLinqQueryExamples#41](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#41)]  
  
 <span data-ttu-id="1d733-106">En [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], la operación <xref:System.Linq.Queryable.Except%2A> se define correctamente sólo en conjuntos.</span><span class="sxs-lookup"><span data-stu-id="1d733-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Except%2A> operation is well defined only on sets.</span></span> <span data-ttu-id="1d733-107">La semántica de conjuntos múltiples no está definida.</span><span class="sxs-lookup"><span data-stu-id="1d733-107">The semantics for multisets is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d733-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="1d733-108">See also</span></span>

- [<span data-ttu-id="1d733-109">Ejemplos de consultas</span><span class="sxs-lookup"><span data-stu-id="1d733-109">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
- [<span data-ttu-id="1d733-110">Traslación del operador de consulta estándar</span><span class="sxs-lookup"><span data-stu-id="1d733-110">Standard Query Operator Translation</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
