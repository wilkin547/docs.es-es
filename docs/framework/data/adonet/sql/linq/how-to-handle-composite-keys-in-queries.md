---
title: Procedimiento Administrar claves compuestas en consultas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ce2f14fd-1038-458a-91e3-a078c61f0d10
ms.openlocfilehash: 0ee0bda8c3ee46cb6e08ee415def68a4a9832617
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54523486"
---
# <a name="how-to-handle-composite-keys-in-queries"></a>Procedimiento Administrar claves compuestas en consultas
Algunos operadores sólo pueden aceptar un argumento. Si su argumento debe incluir más de una columna de la base de datos, debe crear un tipo anónimo para representar la combinación.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra una consulta que invoca al operador `GroupBy`, que sólo acepta un argumento `key`.  
  
 [!code-csharp[DLinqCompositeKeys#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCompositeKeys/cs/Program.cs#1)]
 [!code-vb[DLinqCompositeKeys#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCompositeKeys/vb/Module1.vb#1)]  
  
## <a name="example"></a>Ejemplo  
 La misma situación se da con las combinaciones, como en el ejemplo siguiente:  
  
 [!code-csharp[DLinqCompositeKeys#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCompositeKeys/cs/Program.cs#2)]
 [!code-vb[DLinqCompositeKeys#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCompositeKeys/vb/Module1.vb#2)]  
  
## <a name="see-also"></a>Vea también
- [Conceptos sobre consultas](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
