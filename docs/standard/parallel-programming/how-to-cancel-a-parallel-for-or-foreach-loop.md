---
title: "Cómo: Cancelar un bucle Parallel.For o ForEach"
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
helpviewer_keywords:
- parallel foreach loop, how to cancel
- parallel for loops, how to cancel
ms.assetid: 9d19b591-ea95-4418-8ea7-b6266af9905b
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3f82c5758e02b4beebf035fe8f43f856447855a3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-cancel-a-parallelfor-or-foreach-loop"></a>Cómo: Cancelar un bucle Parallel.For o ForEach
El <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> y <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> métodos admiten la cancelación mediante tokens de cancelación. Para obtener más información sobre la cancelación en general, vea [cancelación](../../../docs/standard/threading/cancellation-in-managed-threads.md). En un bucle paralelo, se proporciona el <xref:System.Threading.CancellationToken> al método en el <xref:System.Threading.Tasks.ParallelOptions> parámetro y, a continuación, incluya la llamada paralela en un bloque try-catch.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo cancelar una llamada a <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>. Puede aplicar el mismo enfoque a una <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> llamar.  
  
 [!code-csharp[TPL_Parallel#29](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/parallel_cancel.cs#29)]
 [!code-vb[TPL_Parallel#29](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/cancelloop.vb#29)]  
  
 Si el token que señala la cancelación es el mismo símbolo (token) que se especifica en el <xref:System.Threading.Tasks.ParallelOptions> de instancias, el bucle paralelo producirá una sola <xref:System.OperationCanceledException> de cancelación. Si algún otro token produce la cancelación, el bucle producirá una <xref:System.AggregateException> con un <xref:System.OperationCanceledException> como una excepción interna.  
  
## <a name="see-also"></a>Vea también  
 [Data Parallelism](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md) (Paralelismo de datos)  
 [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md) (Expresiones lambda en PLINQ y TPL)
