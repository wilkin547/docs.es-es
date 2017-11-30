---
title: "Cómo: Usar SpinWait para implementar una operación de espera de dos fases"
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
helpviewer_keywords: SpinWait, how to synchronize two-phase wait
ms.assetid: b2ac4e4a-051a-4f65-b4b9-f8e103aff195
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2717ba2d63e4ecf40638c369b66f2c696e396a5e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-spinwait-to-implement-a-two-phase-wait-operation"></a>Cómo: Usar SpinWait para implementar una operación de espera de dos fases
En el ejemplo siguiente se muestra cómo utilizar un <xref:System.Threading.SpinWait?displayProperty=nameWithType> objeto para implementar una operación de espera de dos fases. En la primera fase, el objeto de sincronización, un `Latch`, gira durante unos ciclos mientras comprueba si el bloqueo esté disponible. En la segunda fase, si el bloqueo esté disponible, la `Wait` método devuelve sin usar la <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> para realizar la espera; en caso contrario, `Wait` realiza la espera.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo muestra una implementación muy básica de una sincronización de bloqueo temporal primitivo. Puede usar esta estructura de datos cuando se espera que los tiempos de espera sean muy cortos. En este ejemplo es solo con fines de demostración. Si necesita funcionalidad de tipo de bloqueo temporal en el programa, considere la posibilidad de usar <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>.  
  
 [!code-csharp[CDS_SpinWait#03](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinwait/cs/spinwait03.cs#03)]
 [!code-vb[CDS_SpinWait#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinwait/vb/spinwait2.vb#03)]  
  
 Utiliza el bloqueo la <xref:System.Threading.SpinWait> objeto que se va a girar en su posición solo hasta la siguiente llamada a `SpinOnce` hace que el <xref:System.Threading.SpinWait> para producir el intervalo de tiempo del subproceso. En ese momento, el bloqueo temporal produce su propio cambio de contexto mediante una llamada a <xref:System.Threading.WaitHandle.WaitOne%2A> en el <xref:System.Threading.ManualResetEvent> y pasar el resto del valor de tiempo de espera.  
  
 La salida del registro muestra la frecuencia con el bloqueo pudo aumentar el rendimiento al adquirir el bloqueo sin utilizar el <xref:System.Threading.ManualResetEvent>.  
  
## <a name="see-also"></a>Vea también  
 [SpinWait](../../../docs/standard/threading/spinwait.md)  
 [Objetos y características de subprocesos](../../../docs/standard/threading/threading-objects-and-features.md)
