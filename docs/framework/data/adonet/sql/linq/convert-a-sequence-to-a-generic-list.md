---
title: Convertir una secuencia en una lista genérica
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7ab76d93-6898-4e75-b76f-290a66ecead8
ms.openlocfilehash: 2c83a744e26fabb6f3e6ddd0a31c7cdd0c7139a8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59140600"
---
# <a name="convert-a-sequence-to-a-generic-list"></a>Convertir una secuencia en una lista genérica
Utilice <xref:System.Linq.Enumerable.ToList%2A> para crear una lista genérica a partir de una secuencia.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza <xref:System.Linq.Enumerable.ToList%2A> para evaluar una consulta inmediatamente como una <xref:System.Collections.Generic.List%601> genérica.  
  
 [!code-csharp[DLinqQueryExamples#45](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#45)]
 [!code-vb[DLinqQueryExamples#45](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#45)]  
  
## <a name="see-also"></a>Vea también

- [Ejemplos de consultas](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
