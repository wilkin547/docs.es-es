---
description: 'Más información sobre: devolver la intersección de conjuntos de dos secuencias'
title: Devolver la intersección de conjuntos de dos secuencias
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d09c344e-3548-4944-a3ed-051880e3f5b8
ms.openlocfilehash: 163e138761caadb73b6dc5d672c02353a88a2c22
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662991"
---
# <a name="return-the-set-intersection-of-two-sequences"></a><span data-ttu-id="7a4ad-103">Devolver la intersección de conjuntos de dos secuencias</span><span class="sxs-lookup"><span data-stu-id="7a4ad-103">Return the Set Intersection of Two Sequences</span></span>

<span data-ttu-id="7a4ad-104">Utilice el operador <xref:System.Linq.Queryable.Intersect%2A> para devolver la intersección de conjuntos de dos secuencias.</span><span class="sxs-lookup"><span data-stu-id="7a4ad-104">Use the <xref:System.Linq.Queryable.Intersect%2A> operator to return the set intersection of two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a4ad-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7a4ad-105">Example</span></span>  

 <span data-ttu-id="7a4ad-106">En este ejemplo <xref:System.Linq.Queryable.Intersect%2A> se usa para devolver una secuencia de todos los países o regiones en los que `Customers` y `Employees` Live.</span><span class="sxs-lookup"><span data-stu-id="7a4ad-106">This example uses <xref:System.Linq.Queryable.Intersect%2A> to return a sequence of all countries/regions in which both `Customers` and `Employees` live.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#42](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#42)]
 [!code-vb[DLinqQueryExamples#42](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#42)]  
  
 <span data-ttu-id="7a4ad-107">En [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], la operación <xref:System.Linq.Queryable.Intersect%2A> se define correctamente sólo en conjuntos.</span><span class="sxs-lookup"><span data-stu-id="7a4ad-107">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Intersect%2A> operation is well defined only on sets.</span></span> <span data-ttu-id="7a4ad-108">La semántica de conjuntos múltiples no está definida.</span><span class="sxs-lookup"><span data-stu-id="7a4ad-108">The semantics for multisets is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a4ad-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="7a4ad-109">See also</span></span>

- [<span data-ttu-id="7a4ad-110">Ejemplos de consultas</span><span class="sxs-lookup"><span data-stu-id="7a4ad-110">Query Examples</span></span>](query-examples.md)
- [<span data-ttu-id="7a4ad-111">Traslación del operador de consulta estándar</span><span class="sxs-lookup"><span data-stu-id="7a4ad-111">Standard Query Operator Translation</span></span>](standard-query-operator-translation.md)
