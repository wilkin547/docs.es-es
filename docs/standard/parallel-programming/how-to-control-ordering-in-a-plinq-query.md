---
title: "Cómo: Controlar la ordenación en una consulta PLINQ"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: PLINQ queries, how to control ordering
ms.assetid: c67eccc7-004d-4b2f-987e-919cbbd62ef7
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b9e29aa825a68154e32a34a23ca170258092b88a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-control-ordering-in-a-plinq-query"></a>Cómo: Controlar la ordenación en una consulta PLINQ
Estos ejemplos muestra cómo controlar la ordenación en una consulta PLINQ usando el <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> método de extensión.  
  
> [!WARNING]
>  Estos ejemplos están pensados principalmente para mostrar el uso y pueden o no pueden ejecutarse más rápido que LINQ secuencial equivalente a las consultas de objetos.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se conserva el orden de la secuencia de origen. Esto a veces es necesario; Por ejemplo, algunos operadores de consulta requieren una secuencia de origen ordenadas para generar resultados correctos.  
  
 [!code-csharp[PLINQ#12](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#12)]
 [!code-vb[PLINQ#12](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#12)]  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra algunas cuya secuencia de origen es muy probable que se ordenan de operadores de consulta. Estos operadores pueden funcionar en secuencias no ordenadas, pero podría producir resultados inesperados.  
  
 [!code-csharp[PLINQ#14](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#14)]
 [!code-vb[PLINQ#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#14)]  
  
 Para ejecutar este método, péguelo en la clase PLINQDataSample el [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) del proyecto y presione F5.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo se conserva el orden de la primera parte de una consulta, a continuación, quita el orden para aumentar el rendimiento de una cláusula de combinación y, a continuación, volver a aplicar el orden de la secuencia del resultado final.  
  
 [!code-csharp[PLINQ#15](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#15)]
 [!code-vb[PLINQ#15](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#15)]  
  
 Para ejecutar este método, péguelo en la clase PLINQDataSample el [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) del proyecto y presione F5.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Linq.ParallelEnumerable>  
 [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
