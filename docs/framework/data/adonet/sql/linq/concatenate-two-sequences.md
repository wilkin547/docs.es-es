---
title: Concatenar dos secuencias
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 76767e7c-0607-4e1d-9ca2-a94f311f45eb
ms.openlocfilehash: a2f2510cb334f4e22a7b0c6015a0a93b4dc11579
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59142784"
---
# <a name="concatenate-two-sequences"></a>Concatenar dos secuencias
Utilice el operador <xref:System.Linq.Queryable.Concat%2A> para concatenar dos secuencias.  
  
 El operador <xref:System.Linq.Queryable.Concat%2A> se define para conjuntos múltiples ordenados en los que el orden del receptor y del argumento son el mismo.  
  
 En SQL, la ordenación es el último paso antes de que se generen los resultados. Por esta razón, el operador <xref:System.Linq.Queryable.Concat%2A> se implementa utilizando `UNION ALL` y no conserva el orden de sus argumentos. Para garantizar que el orden de los resultados es correcto, no olvide ordenar los resultados explícitamente.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se utiliza <xref:System.Linq.Queryable.Concat%2A> para devolver una secuencia de todos los números de teléfono y fax de `Customer` y `Employee`.  
  
 [!code-csharp[DLinqQueryExamples#39](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#39)]
 [!code-vb[DLinqQueryExamples#39](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#39)]  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se utiliza <xref:System.Linq.Queryable.Concat%2A> para devolver una secuencia de todas las asignaciones de números de teléfono y nombres de `Customer` y `Employee`.  
  
 [!code-csharp[DLinqQueryExamples#40](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#40)]
 [!code-vb[DLinqQueryExamples#40](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#40)]  
  
## <a name="see-also"></a>Vea también

- [Ejemplos de consultas](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
- [Traslación del operador de consulta estándar](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
