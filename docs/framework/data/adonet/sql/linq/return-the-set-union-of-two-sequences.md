---
title: Devolver la unión de conjuntos de dos secuencias
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8b8bd3cb-86d4-4a3b-9906-61f68726dd1f
ms.openlocfilehash: 1b981d3002cf4a23897ce98927aebe96086f8a4a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781222"
---
# <a name="return-the-set-union-of-two-sequences"></a>Devolver la unión de conjuntos de dos secuencias
Utilice el operador <xref:System.Linq.Queryable.Union%2A> para devolver la unión de conjuntos de dos secuencias.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo <xref:System.Linq.Queryable.Union%2A> `Customers` se usa para devolver una secuencia de todos los países o regiones en los que `Employees`hay o.  
  
 [!code-csharp[DLinqQueryExamples#43](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#43)]
 [!code-vb[DLinqQueryExamples#43](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#43)]  
  
 En [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], el <xref:System.Linq.Queryable.Union%2A> operador se define para los conjuntos multiconjunto como la concatenación no ordenada de los conjuntos multiconjunto (de hecho, [`UNION ALL`](https://docs.microsoft.com/sql/t-sql/language-elements/set-operators-union-transact-sql?view=sql-server-2017) el resultado de la cláusula en SQL).

Para obtener más información y ejemplos, <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>vea.
  
## <a name="see-also"></a>Vea también

- [Ejemplos de consultas](query-examples.md)
- [Traslación del operador de consulta estándar](standard-query-operator-translation.md)
