---
title: "Cómo: Cancelar una consulta PLINQ"
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
- PLINQ queries, how to cancel
- cancellation, PLINQ
ms.assetid: 80b14640-edfa-4153-be1b-3e003d3e9c1a
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d8031758462df45c030b8b75a3507f1bfb44bfd0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-cancel-a-plinq-query"></a>Cómo: Cancelar una consulta PLINQ
Los ejemplos siguientes muestran dos mecanismos para cancelar una consulta PLINQ. El primer ejemplo muestra cómo cancelar una consulta que se compone principalmente de cruce seguro de datos. El segundo ejemplo muestra cómo cancelar una consulta que contenga una función de usuario que es cara.  
  
> [!NOTE]
>  Cuando se habilita "Solo mi código", Visual Studio se interrumpe en la línea que produce la excepción y mostrar un mensaje de error "excepción no controlada por código de usuario". Este error es benigno. Puede presionar F5 para continuar y ver el comportamiento de control de excepciones que se muestra en estos ejemplos. Para evitar que Visual Studio se interrumpa con el primer error, desactive la casilla «Solo mi código» en **herramientas, opciones, depuración, General**.  
>   
>  La finalidad de este ejemplo es mostrar el uso, y puede que su ejecución no sea tan rápida como la de la consulta LINQ to Objects secuencial equivalente. Para obtener más información acerca de la velocidad, consulte [Introducción a la velocidad en PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[PLINQ#16](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#16)]
 [!code-vb[PLINQ#16](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#16)]  
  
 El marco PLINQ no revierte una sola <xref:System.OperationCanceledException> en un <xref:System.AggregateException?displayProperty=nameWithType>; el <xref:System.OperationCanceledException> debe controlarse en un bloque catch independiente. Si uno o varios de los delegados de usuario produce una OperationCanceledException(externalCT) (mediante el uso de una referencia externa <xref:System.Threading.CancellationToken?displayProperty=nameWithType>), pero ninguna otra excepción y la consulta se ha definido como `AsParallel().WithCancellation(externalCT)`, a continuación, PLINQ emitirá una única <xref:System.OperationCanceledException> (OperationCanceledException externalCT) en lugar de una <xref:System.AggregateException?displayProperty=nameWithType>. Sin embargo, si un usuario delegado inicia un <xref:System.OperationCanceledException>y otro delegado inicia otro tipo de excepción, ambas excepciones se propagará a un <xref:System.AggregateException>.  
  
 Las instrucciones generales sobre la cancelación es como sigue:  
  
1.  Si lleva a cabo cancelación del delegado de usuario debe informar a PLINQ sobre la externa <xref:System.Threading.CancellationToken> y producir un <xref:System.OperationCanceledException>(OperationCanceledException externalCT).  
  
2.  Si se produce la cancelación y se produce ninguna otra excepción, a continuación, debe controlar un <xref:System.OperationCanceledException> en lugar de un <xref:System.AggregateException>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo controlar la cancelación cuando se tiene una función cara en código de usuario.  
  
 [!code-csharp[PLINQ#17](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#17)]
 [!code-vb[PLINQ#17](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#17)]  
  
 Al controlar la cancelación en el código de usuario, no tiene que usar <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> en la definición de consulta. Sin embargo, se recomienda hacerlo porque <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> no tiene ningún efecto en el rendimiento de las consultas y permite la cancelación se ocuparán de operadores de consulta y el código de usuario.  
  
 Con el fin de garantizar la capacidad de respuesta del sistema, le recomendamos que compruebe cancelación alrededor de una vez por cada milisegundo; Sin embargo, cualquier período que transcurre hasta 10 milisegundos se considera aceptable. Esta frecuencia no debe tener un impacto negativo en el rendimiento del código.  
  
 Cuando se elimina un enumerador, por ejemplo cuando el código sale un bucle foreach (For Each en Visual Basic) que está iterando los resultados de la consulta, a continuación, se cancela la consulta, pero se inicia ninguna excepción.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Linq.ParallelEnumerable>  
 [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)  
 [Cancelación en subprocesos administrados](../../../docs/standard/threading/cancellation-in-managed-threads.md)
