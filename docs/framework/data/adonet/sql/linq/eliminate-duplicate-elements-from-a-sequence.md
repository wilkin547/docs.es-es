---
description: Más información acerca de cómo eliminar elementos duplicados de una secuencia
title: Eliminar elementos duplicados de una secuencia
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2b224a84-bad5-4843-adcc-14e784d280f5
ms.openlocfilehash: f371fc27794361e3ea92d342f845996d9291d30c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786100"
---
# <a name="eliminate-duplicate-elements-from-a-sequence"></a>Eliminar elementos duplicados de una secuencia

Utilice el operador <xref:System.Linq.Queryable.Distinct%2A> para eliminar los elementos duplicados de una secuencia.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se utiliza <xref:System.Linq.Queryable.Distinct%2A> para seleccionar una secuencia de las ciudades que tienen clientes.  
  
 [!code-csharp[DLinqQueryExamples#36](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#36)]
 [!code-vb[DLinqQueryExamples#36](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#36)]  
  
## <a name="see-also"></a>Vea también

- [Ejemplos de consultas](query-examples.md)
