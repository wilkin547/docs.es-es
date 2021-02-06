---
description: 'Más información sobre: devolver la intersección de conjuntos de dos secuencias'
title: Devolver la intersección de conjuntos de dos secuencias
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d09c344e-3548-4944-a3ed-051880e3f5b8
ms.openlocfilehash: 163e138761caadb73b6dc5d672c02353a88a2c22
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662991"
---
# <a name="return-the-set-intersection-of-two-sequences"></a>Devolver la intersección de conjuntos de dos secuencias

Utilice el operador <xref:System.Linq.Queryable.Intersect%2A> para devolver la intersección de conjuntos de dos secuencias.  
  
## <a name="example"></a>Ejemplo  

 En este ejemplo <xref:System.Linq.Queryable.Intersect%2A> se usa para devolver una secuencia de todos los países o regiones en los que `Customers` y `Employees` Live.  
  
 [!code-csharp[DLinqQueryExamples#42](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#42)]
 [!code-vb[DLinqQueryExamples#42](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#42)]  
  
 En [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], la operación <xref:System.Linq.Queryable.Intersect%2A> se define correctamente sólo en conjuntos. La semántica de conjuntos múltiples no está definida.  
  
## <a name="see-also"></a>Vea también

- [Ejemplos de consultas](query-examples.md)
- [Traslación del operador de consulta estándar](standard-query-operator-translation.md)
