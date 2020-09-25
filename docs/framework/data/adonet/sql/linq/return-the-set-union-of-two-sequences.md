---
title: Devolver la unión de conjuntos de dos secuencias
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8b8bd3cb-86d4-4a3b-9906-61f68726dd1f
ms.openlocfilehash: 0fe32d8c3c37e99a50ca03262dc6184337b4450e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91200213"
---
# <a name="return-the-set-union-of-two-sequences"></a>Devolver la unión de conjuntos de dos secuencias

Utilice el operador <xref:System.Linq.Queryable.Union%2A> para devolver la unión de conjuntos de dos secuencias.  
  
## <a name="example"></a>Ejemplo  

 En este ejemplo <xref:System.Linq.Queryable.Union%2A> se usa para devolver una secuencia de todos los países o regiones en los que hay `Customers` o `Employees` .  
  
 [!code-csharp[DLinqQueryExamples#43](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#43)]
 [!code-vb[DLinqQueryExamples#43](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#43)]  
  
 En [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] , el <xref:System.Linq.Queryable.Union%2A> operador se define para los conjuntos multiconjunto como la concatenación no ordenada de los conjuntos multiconjunto (de hecho, el resultado de la [`UNION ALL`](/sql/t-sql/language-elements/set-operators-union-transact-sql) cláusula en SQL).

Para obtener más información y ejemplos, vea <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType> .
  
## <a name="see-also"></a>Consulte también

- [Ejemplos de consultas](query-examples.md)
- [Traslación del operador de consulta estándar](standard-query-operator-translation.md)
