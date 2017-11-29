---
title: "Devolver la unión de conjuntos de dos secuencias"
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
ms.assetid: 8b8bd3cb-86d4-4a3b-9906-61f68726dd1f
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 865aa82ebc119a3952124a93f9042c2732e3ab48
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="return-the-set-union-of-two-sequences"></a><span data-ttu-id="4dc5d-102">Devolver la unión de conjuntos de dos secuencias</span><span class="sxs-lookup"><span data-stu-id="4dc5d-102">Return the Set Union of Two Sequences</span></span>
<span data-ttu-id="4dc5d-103">Utilice el operador <xref:System.Linq.Queryable.Union%2A> para devolver la unión de conjuntos de dos secuencias.</span><span class="sxs-lookup"><span data-stu-id="4dc5d-103">Use the <xref:System.Linq.Queryable.Union%2A> operator to return the set union of two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4dc5d-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4dc5d-104">Example</span></span>  
 <span data-ttu-id="4dc5d-105">En este ejemplo se utiliza <xref:System.Linq.Queryable.Union%2A> para devolver una secuencia de todos los países en los que hay `Customers` o `Employees`.</span><span class="sxs-lookup"><span data-stu-id="4dc5d-105">This example uses <xref:System.Linq.Queryable.Union%2A> to return a sequence of all countries in which there are either `Customers` or `Employees`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#43](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#43)]
 [!code-vb[DLinqQueryExamples#43](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#43)]  
  
 <span data-ttu-id="4dc5d-106">En [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], <xref:System.Linq.Queryable.Union%2A> operador se define para conjuntos múltiples como la concatenación no ordenada de los conjuntos múltiples (hecho, el resultado de la `UNION ALL` cláusula de SQL).</span><span class="sxs-lookup"><span data-stu-id="4dc5d-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Union%2A> operator is defined for multisets as the unordered concatenation of the multisets (effectively the result of the `UNION ALL` clause in SQL).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dc5d-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="4dc5d-107">See Also</span></span>  
 [<span data-ttu-id="4dc5d-108">Ejemplos de consultas</span><span class="sxs-lookup"><span data-stu-id="4dc5d-108">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 [<span data-ttu-id="4dc5d-109">Conversión de operadores de consulta estándar</span><span class="sxs-lookup"><span data-stu-id="4dc5d-109">Standard Query Operator Translation</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
