---
title: Eliminar elementos duplicados de una secuencia
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 2b224a84-bad5-4843-adcc-14e784d280f5
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 844b9cc43755041ebccae63f477b4f1b21bd69c5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="eliminate-duplicate-elements-from-a-sequence"></a>Eliminar elementos duplicados de una secuencia
Utilice el operador <xref:System.Linq.Queryable.Distinct%2A> para eliminar los elementos duplicados de una secuencia.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza <xref:System.Linq.Queryable.Distinct%2A> para seleccionar una secuencia de las ciudades que tienen clientes.  
  
 [!code-csharp[DLinqQueryExamples#36](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#36)]
 [!code-vb[DLinqQueryExamples#36](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#36)]  
  
## <a name="see-also"></a>Vea también  
 [Ejemplos de consultas](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
