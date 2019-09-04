---
title: Contar el número de elementos de una secuencia
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ccbe5d54-c9eb-4b14-b0ab-f628483c5f99
ms.openlocfilehash: 74e24aeb64b0097cba3975e76475034e6bb9544d
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70247698"
---
# <a name="count-the-number-of-elements-in-a-sequence"></a>Contar el número de elementos de una secuencia
Utilice al operador <xref:System.Linq.Enumerable.Count%2A> para contar el número de elementos de una secuencia.  
  
 Al ejecutar esta consulta en la base de datos de ejemplo Northwind, se genera un resultado de `91`.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se cuenta el número de `Customers` en la base de datos.  
  
 [!code-csharp[DLinqQueryExamples#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#4)]
 [!code-vb[DLinqQueryExamples#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#4)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se cuenta el número de productos de la base de datos que no han dejado de fabricarse.  
  
 Al ejecutar este ejemplo en la base de datos de ejemplo Northwind, se genera un resultado de `69`.  
  
 [!code-csharp[DLinqQueryExamples#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#5)]
 [!code-vb[DLinqQueryExamples#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#5)]  
  
## <a name="see-also"></a>Vea también

- [Consultas de agregado](aggregate-queries.md)
- [Descargar bases de datos de ejemplo](downloading-sample-databases.md)
