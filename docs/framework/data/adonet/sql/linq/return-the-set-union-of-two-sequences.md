---
title: Devolver la unión de conjuntos de dos secuencias
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8b8bd3cb-86d4-4a3b-9906-61f68726dd1f
ms.openlocfilehash: c7d7a267df13cfa54d682ab9b65953f2c0a85a27
ms.sourcegitcommit: fd8d4587cc26e53f0e27e230d6e27d828ef4306b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2018
ms.locfileid: "49347551"
---
# <a name="return-the-set-union-of-two-sequences"></a><span data-ttu-id="3fd1f-102">Devolver la unión de conjuntos de dos secuencias</span><span class="sxs-lookup"><span data-stu-id="3fd1f-102">Return the Set Union of Two Sequences</span></span>
<span data-ttu-id="3fd1f-103">Utilice el operador <xref:System.Linq.Queryable.Union%2A> para devolver la unión de conjuntos de dos secuencias.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-103">Use the <xref:System.Linq.Queryable.Union%2A> operator to return the set union of two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3fd1f-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3fd1f-104">Example</span></span>  
 <span data-ttu-id="3fd1f-105">En este ejemplo se utiliza <xref:System.Linq.Queryable.Union%2A> para devolver una secuencia de todos los países en los que hay `Customers` o `Employees`.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-105">This example uses <xref:System.Linq.Queryable.Union%2A> to return a sequence of all countries in which there are either `Customers` or `Employees`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#43](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#43)]
 [!code-vb[DLinqQueryExamples#43](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#43)]  
  
 <span data-ttu-id="3fd1f-106">En [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], <xref:System.Linq.Queryable.Union%2A> operador se define para conjuntos múltiples como la concatenación no ordenada de los conjuntos múltiples (hecho, el resultado de la [ `UNION ALL` ](https://docs.microsoft.com/sql/t-sql/language-elements/set-operators-union-transact-sql?view=sql-server-2017) cláusula de SQL).</span><span class="sxs-lookup"><span data-stu-id="3fd1f-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Union%2A> operator is defined for multisets as the unordered concatenation of the multisets (effectively the result of the [`UNION ALL`](https://docs.microsoft.com/sql/t-sql/language-elements/set-operators-union-transact-sql?view=sql-server-2017) clause in SQL).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fd1f-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="3fd1f-107">See Also</span></span>  
 [<span data-ttu-id="3fd1f-108">Ejemplos de consultas</span><span class="sxs-lookup"><span data-stu-id="3fd1f-108">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 [<span data-ttu-id="3fd1f-109">Traslación del operador de consulta estándar</span><span class="sxs-lookup"><span data-stu-id="3fd1f-109">Standard Query Operator Translation</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
