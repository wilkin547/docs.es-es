---
title: Convertir una secuencia en una lista genérica
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7ab76d93-6898-4e75-b76f-290a66ecead8
ms.openlocfilehash: 326b4360323f306d07a3b47df506c6427a980a32
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54630793"
---
# <a name="convert-a-sequence-to-a-generic-list"></a>Convertir una secuencia en una lista genérica
Utilice <xref:System.Linq.Enumerable.ToList%2A> para crear una lista genérica a partir de una secuencia.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza <xref:System.Linq.Enumerable.ToList%2A> para evaluar una consulta inmediatamente como una <xref:System.Collections.Generic.List%601> genérica.  
  
 [!code-csharp[DLinqQueryExamples#45](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#45)]
 [!code-vb[DLinqQueryExamples#45](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#45)]  
  
## <a name="see-also"></a>Vea también
- [Ejemplos de consultas](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
