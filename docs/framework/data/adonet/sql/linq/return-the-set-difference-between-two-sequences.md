---
title: Devolver la diferencia de conjuntos entre dos secuencias
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 62efb546-c898-408f-af21-36e7c6fed217
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 7156e6a60527f4fd33e9b8d56504b4697152261e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="return-the-set-difference-between-two-sequences"></a><span data-ttu-id="60da9-102">Devolver la diferencia de conjuntos entre dos secuencias</span><span class="sxs-lookup"><span data-stu-id="60da9-102">Return the Set Difference Between Two Sequences</span></span>
<span data-ttu-id="60da9-103">Utilice el operador <xref:System.Linq.Queryable.Except%2A> para devolver la diferencia de conjuntos entre dos secuencias.</span><span class="sxs-lookup"><span data-stu-id="60da9-103">Use the <xref:System.Linq.Queryable.Except%2A> operator to return the set difference between two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="60da9-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="60da9-104">Example</span></span>  
 <span data-ttu-id="60da9-105">En este ejemplo se utiliza <xref:System.Linq.Queryable.Except%2A> para devolver una secuencia de todos los países en los que viven `Customers` pero no `Employees`.</span><span class="sxs-lookup"><span data-stu-id="60da9-105">This example uses <xref:System.Linq.Queryable.Except%2A> to return a sequence of all countries in which `Customers` live but in which no `Employees` live.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#41](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#41)]
 [!code-vb[DLinqQueryExamples#41](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#41)]  
  
 <span data-ttu-id="60da9-106">En [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], la operación <xref:System.Linq.Queryable.Except%2A> se define correctamente sólo en conjuntos.</span><span class="sxs-lookup"><span data-stu-id="60da9-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Except%2A> operation is well defined only on sets.</span></span> <span data-ttu-id="60da9-107">La semántica de conjuntos múltiples no está definida.</span><span class="sxs-lookup"><span data-stu-id="60da9-107">The semantics for multisets is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60da9-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="60da9-108">See Also</span></span>  
 [<span data-ttu-id="60da9-109">Ejemplos de consultas</span><span class="sxs-lookup"><span data-stu-id="60da9-109">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 [<span data-ttu-id="60da9-110">Traslación del operador de consulta estándar</span><span class="sxs-lookup"><span data-stu-id="60da9-110">Standard Query Operator Translation</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
