---
title: "Convertir una secuencia en una lista genérica"
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
ms.assetid: 7ab76d93-6898-4e75-b76f-290a66ecead8
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: e563e0ed46bfdadca9923b582f2c30e12701d992
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="convert-a-sequence-to-a-generic-list"></a>Convertir una secuencia en una lista genérica
Utilice <xref:System.Linq.Enumerable.ToList%2A> para crear una lista genérica a partir de una secuencia.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza <xref:System.Linq.Enumerable.ToList%2A> para evaluar una consulta inmediatamente como una <xref:System.Collections.Generic.List%601> genérica.  
  
 [!code-csharp[DLinqQueryExamples#45](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#45)]
 [!code-vb[DLinqQueryExamples#45](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#45)]  
  
## <a name="see-also"></a>Vea también  
 [Ejemplos de consultas](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
