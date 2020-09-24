---
title: Concatenar dos secuencias
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 76767e7c-0607-4e1d-9ca2-a94f311f45eb
ms.openlocfilehash: 87d341357b8d11eafbc3f3867c45ac5a32270688
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164407"
---
# <a name="concatenate-two-sequences"></a><span data-ttu-id="57e9f-102">Concatenar dos secuencias</span><span class="sxs-lookup"><span data-stu-id="57e9f-102">Concatenate Two Sequences</span></span>

<span data-ttu-id="57e9f-103">Utilice el operador <xref:System.Linq.Queryable.Concat%2A> para concatenar dos secuencias.</span><span class="sxs-lookup"><span data-stu-id="57e9f-103">Use the <xref:System.Linq.Queryable.Concat%2A> operator to concatenate two sequences.</span></span>  
  
 <span data-ttu-id="57e9f-104">El operador <xref:System.Linq.Queryable.Concat%2A> se define para conjuntos múltiples ordenados en los que el orden del receptor y del argumento son el mismo.</span><span class="sxs-lookup"><span data-stu-id="57e9f-104">The <xref:System.Linq.Queryable.Concat%2A> operator is defined for ordered multisets where the orders of the receiver and the argument are the same.</span></span>  
  
 <span data-ttu-id="57e9f-105">En SQL, la ordenación es el último paso antes de que se generen los resultados.</span><span class="sxs-lookup"><span data-stu-id="57e9f-105">Ordering in SQL is the final step before results are produced.</span></span> <span data-ttu-id="57e9f-106">Por esta razón, el operador <xref:System.Linq.Queryable.Concat%2A> se implementa utilizando `UNION ALL` y no conserva el orden de sus argumentos.</span><span class="sxs-lookup"><span data-stu-id="57e9f-106">For this reason, the <xref:System.Linq.Queryable.Concat%2A> operator is implemented by using `UNION ALL` and does not preserve the order of its arguments.</span></span> <span data-ttu-id="57e9f-107">Para garantizar que el orden de los resultados es correcto, no olvide ordenar los resultados explícitamente.</span><span class="sxs-lookup"><span data-stu-id="57e9f-107">To make sure ordering is correct in the results, make sure to explicitly order the results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="57e9f-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="57e9f-108">Example</span></span>  

 <span data-ttu-id="57e9f-109">En este ejemplo se utiliza <xref:System.Linq.Queryable.Concat%2A> para devolver una secuencia de todos los números de teléfono y fax de `Customer` y `Employee`.</span><span class="sxs-lookup"><span data-stu-id="57e9f-109">This example uses <xref:System.Linq.Queryable.Concat%2A> to return a sequence of all `Customer` and `Employee` telephone and fax numbers.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#39](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#39)]
 [!code-vb[DLinqQueryExamples#39](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#39)]  
  
## <a name="example"></a><span data-ttu-id="57e9f-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="57e9f-110">Example</span></span>  

 <span data-ttu-id="57e9f-111">En este ejemplo se utiliza <xref:System.Linq.Queryable.Concat%2A> para devolver una secuencia de todas las asignaciones de números de teléfono y nombres de `Customer` y `Employee`.</span><span class="sxs-lookup"><span data-stu-id="57e9f-111">This example uses <xref:System.Linq.Queryable.Concat%2A> to return a sequence of all `Customer` and `Employee` name and telephone number mappings.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#40](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#40)]
 [!code-vb[DLinqQueryExamples#40](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#40)]  
  
## <a name="see-also"></a><span data-ttu-id="57e9f-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="57e9f-112">See also</span></span>

- [<span data-ttu-id="57e9f-113">Ejemplos de consultas</span><span class="sxs-lookup"><span data-stu-id="57e9f-113">Query Examples</span></span>](query-examples.md)
- [<span data-ttu-id="57e9f-114">Traslación del operador de consulta estándar</span><span class="sxs-lookup"><span data-stu-id="57e9f-114">Standard Query Operator Translation</span></span>](standard-query-operator-translation.md)
