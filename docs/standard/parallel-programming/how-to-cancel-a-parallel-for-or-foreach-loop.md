---
title: Procedimiento para cancelar un bucle Parallel.For o ForEach
description: Cancele un bucle Parallel.For o Parallel.ForEach en .NET proporcionando un objeto de token de cancelación al método en el parámetro ParallelOptions.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel foreach loop, how to cancel
- parallel for loops, how to cancel
ms.assetid: 9d19b591-ea95-4418-8ea7-b6266af9905b
ms.openlocfilehash: 0a22794f3c45e685a80d36a42ecd849461936c7b
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2020
ms.locfileid: "84769007"
---
# <a name="how-to-cancel-a-parallelfor-or-foreach-loop"></a>Procedimiento para cancelar un bucle Parallel.For o ForEach
Los métodos <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> y <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> admiten la cancelación mediante tokens de cancelación. Para obtener más información sobre la cancelación, vea [Cancelación](../threading/cancellation-in-managed-threads.md). En un bucle paralelo, se proporciona <xref:System.Threading.CancellationToken> al método en el parámetro <xref:System.Threading.Tasks.ParallelOptions> y, a continuación, incluye la llamada paralela en un bloque try-catch.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo cancelar una llamada a <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>. Puede aplicar el mismo enfoque a una llamada <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>.  
  
 [!code-csharp[TPL_Parallel#29](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/parallel_cancel.cs#29)]
 [!code-vb[TPL_Parallel#29](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/cancelloop.vb#29)]  
  
 Si el token que señala la cancelación es el mismo token que se especifica en la instancia <xref:System.Threading.Tasks.ParallelOptions>, el bucle paralelo producirá una sola clase <xref:System.OperationCanceledException> en la cancelación. Si algún otro token produce la cancelación, el bucle producirá una clase <xref:System.AggregateException> con una clase <xref:System.OperationCanceledException> como una excepción interna.  
  
## <a name="see-also"></a>Vea también

- [Paralelismo de datos](data-parallelism-task-parallel-library.md)
- [Expresiones lambda en PLINQ y TPL](lambda-expressions-in-plinq-and-tpl.md)
