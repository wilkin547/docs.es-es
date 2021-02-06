---
description: 'Más información sobre: devolver la Unión de conjuntos de dos secuencias'
title: Devolver la unión de conjuntos de dos secuencias
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8b8bd3cb-86d4-4a3b-9906-61f68726dd1f
ms.openlocfilehash: 5541316560c05712e22c54f706b02d868fadb381
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662967"
---
# <a name="return-the-set-union-of-two-sequences"></a>Devolver la unión de conjuntos de dos secuencias

Utilice el operador <xref:System.Linq.Queryable.Union%2A> para devolver la unión de conjuntos de dos secuencias.  
  
## <a name="example"></a>Ejemplo  

 En este ejemplo <xref:System.Linq.Queryable.Union%2A> se usa para devolver una secuencia de todos los países o regiones en los que hay `Customers` o `Employees` .  
  
 [!code-csharp[DLinqQueryExamples#43](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#43)]
 [!code-vb[DLinqQueryExamples#43](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#43)]  
  
 En [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] , el <xref:System.Linq.Queryable.Union%2A> operador se define para los conjuntos multiconjunto como la concatenación no ordenada de los conjuntos multiconjunto (de hecho, el resultado de la [`UNION ALL`](/sql/t-sql/language-elements/set-operators-union-transact-sql) cláusula en SQL).

Para obtener más información y ejemplos, vea <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType> .
  
## <a name="see-also"></a>Vea también

- [Ejemplos de consultas](query-examples.md)
- [Traslación del operador de consulta estándar](standard-query-operator-translation.md)
