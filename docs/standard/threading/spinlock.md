---
title: SpinLock
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: synchronization primitives, SpinLock
ms.assetid: f9af93bb-7a0d-4ba5-afe8-74f48b6b6958
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: efe9b3126b3c952ab156f9ca40752ad8d3fddcd1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="spinlock"></a>SpinLock
El <xref:System.Threading.SpinLock> estructura es una bajo nivel, la exclusión mutua primitiva de sincronización que itera en ciclos mientras espera adquirir un bloqueo. En los equipos con varios núcleos, cuando se prevea que los tiempos de espera deben ser breves y contención es mínima, <xref:System.Threading.SpinLock> puede funcionan mejor que otros tipos de bloqueos. Sin embargo, recomendamos que use <xref:System.Threading.SpinLock> sólo cuando determinar mediante la generación de perfiles que la <xref:System.Threading.Monitor?displayProperty=nameWithType> método o el <xref:System.Threading.Interlocked> métodos reducen significativamente el rendimiento del programa.  
  
 <xref:System.Threading.SpinLock>incluso si aún no ha adquirido el bloqueo se puede obtener el intervalo de tiempo del subproceso. Esto consigue para evitar la inversión de prioridad del subproceso y para habilitar el recolector de elementos no utilizados avanzar. Cuando se usa un <xref:System.Threading.SpinLock>, asegúrese de que ningún subproceso mantenga el bloqueo durante más de un intervalo de tiempo muy breve y que ningún subproceso puede bloquearse mientras mantiene el bloqueo.  
  
 Como SpinLock es un tipo de valor, explícitamente debe pasarlo por referencia si piensa que las dos copias para hacer referencia al mismo bloqueo.  
  
 Para obtener más información acerca de cómo usar este tipo, consulte <xref:System.Threading.SpinLock?displayProperty=nameWithType>. Para obtener un ejemplo, vea [Cómo: utilizar SpinLock para la sincronización de bajo nivel](../../../docs/standard/threading/how-to-use-spinlock-for-low-level-synchronization.md).  
  
 <xref:System.Threading.SpinLock>admite un *subproceso*-*seguimiento* modo que puede usar durante la fase de desarrollo para ayudar a realizar un seguimiento del subproceso que está reteniendo el bloqueo en un momento determinado. Modo de seguimiento de subprocesos es muy útil para la depuración, pero se recomienda que apagarlo en la versión de lanzamiento del programa porque puede ralentizar el rendimiento. Para obtener más información, consulte [Cómo: modo de seguimiento habilitar de subprocesos en el bloqueo SpinLock](../../../docs/standard/threading/how-to-enable-thread-tracking-mode-in-spinlock.md).  
  
## <a name="see-also"></a>Vea también  
 [Objetos y características de subprocesos](../../../docs/standard/threading/threading-objects-and-features.md)
