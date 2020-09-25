---
title: Devolver la diferencia de conjuntos entre dos secuencias
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 62efb546-c898-408f-af21-36e7c6fed217
ms.openlocfilehash: 49a8d22377ef1f7d0fde16880a82002754e1bbc4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91200334"
---
# <a name="return-the-set-difference-between-two-sequences"></a>Devolver la diferencia de conjuntos entre dos secuencias

Utilice el operador <xref:System.Linq.Queryable.Except%2A> para devolver la diferencia de conjuntos entre dos secuencias.  
  
## <a name="example"></a>Ejemplo  

 En este ejemplo <xref:System.Linq.Queryable.Except%2A> se usa para devolver una secuencia de todos los países o regiones en los que se encuentran `Customers` activos, pero en los que no hay `Employees` activo.  
  
 [!code-csharp[DLinqQueryExamples#41](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#41)]
 [!code-vb[DLinqQueryExamples#41](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#41)]  
  
 En [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], la operación <xref:System.Linq.Queryable.Except%2A> se define correctamente sólo en conjuntos. La semántica de conjuntos múltiples no está definida.  
  
## <a name="see-also"></a>Consulte también

- [Ejemplos de consultas](query-examples.md)
- [Traslación del operador de consulta estándar](standard-query-operator-translation.md)
