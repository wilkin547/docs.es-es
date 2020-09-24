---
title: Convertir una secuencia en una lista genérica
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7ab76d93-6898-4e75-b76f-290a66ecead8
ms.openlocfilehash: 79e3ddaff0234dfb5f91e36bacd3279afa9ec265
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164394"
---
# <a name="convert-a-sequence-to-a-generic-list"></a>Convertir una secuencia en una lista genérica

Utilice <xref:System.Linq.Enumerable.ToList%2A> para crear una lista genérica a partir de una secuencia.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se utiliza <xref:System.Linq.Enumerable.ToList%2A> para evaluar una consulta inmediatamente como una <xref:System.Collections.Generic.List%601> genérica.  
  
 [!code-csharp[DLinqQueryExamples#45](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#45)]
 [!code-vb[DLinqQueryExamples#45](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#45)]  
  
## <a name="see-also"></a>Consulte también

- [Ejemplos de consultas](query-examples.md)
