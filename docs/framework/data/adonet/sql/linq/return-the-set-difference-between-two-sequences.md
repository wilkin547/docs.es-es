---
title: Devolver la diferencia de conjuntos entre dos secuencias
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 62efb546-c898-408f-af21-36e7c6fed217
ms.openlocfilehash: 7edc60c7ab8510aadd9ac273529a88adeb41352a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59124285"
---
# <a name="return-the-set-difference-between-two-sequences"></a>Devolver la diferencia de conjuntos entre dos secuencias
Utilice el operador <xref:System.Linq.Queryable.Except%2A> para devolver la diferencia de conjuntos entre dos secuencias.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se utiliza <xref:System.Linq.Queryable.Except%2A> para devolver una secuencia de todos los países en los que viven `Customers` pero no `Employees`.  
  
 [!code-csharp[DLinqQueryExamples#41](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#41)]
 [!code-vb[DLinqQueryExamples#41](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#41)]  
  
 En [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], la operación <xref:System.Linq.Queryable.Except%2A> se define correctamente sólo en conjuntos. La semántica de conjuntos múltiples no está definida.  
  
## <a name="see-also"></a>Vea también

- [Ejemplos de consultas](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
- [Traslación del operador de consulta estándar](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
