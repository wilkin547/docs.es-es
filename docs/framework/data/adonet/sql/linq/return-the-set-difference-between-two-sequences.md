---
description: 'Más información sobre: devolver la diferencia de conjuntos entre dos secuencias'
title: Devolver la diferencia de conjuntos entre dos secuencias
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 62efb546-c898-408f-af21-36e7c6fed217
ms.openlocfilehash: 6836195ac4e1ee678fd3e8089e7c341f7dd247e8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662992"
---
# <a name="return-the-set-difference-between-two-sequences"></a><span data-ttu-id="ff6af-103">Devolver la diferencia de conjuntos entre dos secuencias</span><span class="sxs-lookup"><span data-stu-id="ff6af-103">Return the Set Difference Between Two Sequences</span></span>

<span data-ttu-id="ff6af-104">Utilice el operador <xref:System.Linq.Queryable.Except%2A> para devolver la diferencia de conjuntos entre dos secuencias.</span><span class="sxs-lookup"><span data-stu-id="ff6af-104">Use the <xref:System.Linq.Queryable.Except%2A> operator to return the set difference between two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ff6af-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ff6af-105">Example</span></span>  

 <span data-ttu-id="ff6af-106">En este ejemplo <xref:System.Linq.Queryable.Except%2A> se usa para devolver una secuencia de todos los países o regiones en los que se encuentran `Customers` activos, pero en los que no hay `Employees` activo.</span><span class="sxs-lookup"><span data-stu-id="ff6af-106">This example uses <xref:System.Linq.Queryable.Except%2A> to return a sequence of all countries/regions in which `Customers` live but in which no `Employees` live.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#41](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#41)]
 [!code-vb[DLinqQueryExamples#41](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#41)]  
  
 <span data-ttu-id="ff6af-107">En [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], la operación <xref:System.Linq.Queryable.Except%2A> se define correctamente sólo en conjuntos.</span><span class="sxs-lookup"><span data-stu-id="ff6af-107">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Except%2A> operation is well defined only on sets.</span></span> <span data-ttu-id="ff6af-108">La semántica de conjuntos múltiples no está definida.</span><span class="sxs-lookup"><span data-stu-id="ff6af-108">The semantics for multisets is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff6af-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="ff6af-109">See also</span></span>

- [<span data-ttu-id="ff6af-110">Ejemplos de consultas</span><span class="sxs-lookup"><span data-stu-id="ff6af-110">Query Examples</span></span>](query-examples.md)
- [<span data-ttu-id="ff6af-111">Traslación del operador de consulta estándar</span><span class="sxs-lookup"><span data-stu-id="ff6af-111">Standard Query Operator Translation</span></span>](standard-query-operator-translation.md)
