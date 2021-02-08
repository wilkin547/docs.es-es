---
description: 'Más información sobre: concatenar dos secuencias'
title: Concatenar dos secuencias
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 76767e7c-0607-4e1d-9ca2-a94f311f45eb
ms.openlocfilehash: 5e48f3e2900bf53d042eb9c2aad6535bad9ec7e9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99773178"
---
# <a name="concatenate-two-sequences"></a><span data-ttu-id="f0d91-103">Concatenar dos secuencias</span><span class="sxs-lookup"><span data-stu-id="f0d91-103">Concatenate Two Sequences</span></span>

<span data-ttu-id="f0d91-104">Utilice el operador <xref:System.Linq.Queryable.Concat%2A> para concatenar dos secuencias.</span><span class="sxs-lookup"><span data-stu-id="f0d91-104">Use the <xref:System.Linq.Queryable.Concat%2A> operator to concatenate two sequences.</span></span>  
  
 <span data-ttu-id="f0d91-105">El operador <xref:System.Linq.Queryable.Concat%2A> se define para conjuntos múltiples ordenados en los que el orden del receptor y del argumento son el mismo.</span><span class="sxs-lookup"><span data-stu-id="f0d91-105">The <xref:System.Linq.Queryable.Concat%2A> operator is defined for ordered multisets where the orders of the receiver and the argument are the same.</span></span>  
  
 <span data-ttu-id="f0d91-106">En SQL, la ordenación es el último paso antes de que se generen los resultados.</span><span class="sxs-lookup"><span data-stu-id="f0d91-106">Ordering in SQL is the final step before results are produced.</span></span> <span data-ttu-id="f0d91-107">Por esta razón, el operador <xref:System.Linq.Queryable.Concat%2A> se implementa utilizando `UNION ALL` y no conserva el orden de sus argumentos.</span><span class="sxs-lookup"><span data-stu-id="f0d91-107">For this reason, the <xref:System.Linq.Queryable.Concat%2A> operator is implemented by using `UNION ALL` and does not preserve the order of its arguments.</span></span> <span data-ttu-id="f0d91-108">Para garantizar que el orden de los resultados es correcto, no olvide ordenar los resultados explícitamente.</span><span class="sxs-lookup"><span data-stu-id="f0d91-108">To make sure ordering is correct in the results, make sure to explicitly order the results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0d91-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f0d91-109">Example</span></span>  

 <span data-ttu-id="f0d91-110">En este ejemplo se utiliza <xref:System.Linq.Queryable.Concat%2A> para devolver una secuencia de todos los números de teléfono y fax de `Customer` y `Employee`.</span><span class="sxs-lookup"><span data-stu-id="f0d91-110">This example uses <xref:System.Linq.Queryable.Concat%2A> to return a sequence of all `Customer` and `Employee` telephone and fax numbers.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#39](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#39)]
 [!code-vb[DLinqQueryExamples#39](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#39)]  
  
## <a name="example"></a><span data-ttu-id="f0d91-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f0d91-111">Example</span></span>  

 <span data-ttu-id="f0d91-112">En este ejemplo se utiliza <xref:System.Linq.Queryable.Concat%2A> para devolver una secuencia de todas las asignaciones de números de teléfono y nombres de `Customer` y `Employee`.</span><span class="sxs-lookup"><span data-stu-id="f0d91-112">This example uses <xref:System.Linq.Queryable.Concat%2A> to return a sequence of all `Customer` and `Employee` name and telephone number mappings.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#40](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#40)]
 [!code-vb[DLinqQueryExamples#40](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#40)]  
  
## <a name="see-also"></a><span data-ttu-id="f0d91-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="f0d91-113">See also</span></span>

- [<span data-ttu-id="f0d91-114">Ejemplos de consultas</span><span class="sxs-lookup"><span data-stu-id="f0d91-114">Query Examples</span></span>](query-examples.md)
- [<span data-ttu-id="f0d91-115">Traslación del operador de consulta estándar</span><span class="sxs-lookup"><span data-stu-id="f0d91-115">Standard Query Operator Translation</span></span>](standard-query-operator-translation.md)
