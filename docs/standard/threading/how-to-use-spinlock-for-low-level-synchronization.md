---
title: "Cómo: Utilizar SpinLock para la sincronización de bajo nivel"
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
- SpinLock, how to use
ms.assetid: a9ed3e4e-4f29-4207-b730-ed0a51ecbc19
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 11d41a1fd04039fd08d945a72a37a479f79449a5
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-use-spinlock-for-low-level-synchronization"></a>Cómo: Utilizar SpinLock para la sincronización de bajo nivel
En el siguiente ejemplo se muestra cómo usar <xref:System.Threading.SpinLock>.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, la sección crítica realiza una cantidad de trabajo mínima, lo que la convierte en una buena candidata para un elemento <xref:System.Threading.SpinLock>. Al aumentar ligeramente el trabajo, aumenta el rendimiento del elemento <xref:System.Threading.SpinLock> en comparación con un bloqueo estándar. Sin embargo, existe un punto en el que un elemento SpinLock es más caro que un bloqueo estándar. Puede usar la funcionalidad de generación de perfiles de simultaneidad de las herramientas de generación de perfiles para ver qué tipo de bloqueo proporciona mejor rendimiento en su programa. Para más información, consulte [Visualizador de simultaneidad](/visualstudio/profiling/concurrency-visualizer).  
  
 [!code-csharp[CDS_SpinLock#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinlock/cs/spinlockdemo.cs#02)]
 [!code-vb[CDS_SpinLock#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinlock/vb/spinlock_vb.vb#02)]  
  
 <xref:System.Threading.SpinLock> puede ser útil si un bloqueo en un recurso compartido no se va a mantener durante mucho tiempo. En estos casos, puede resultar eficaz en los equipos de varios núcleos que el subproceso bloqueado gire durante algunos ciclos hasta que se libere el bloqueo. Al girar, el subproceso no se bloquea, lo cual es un proceso intensivo de la CPU. <xref:System.Threading.SpinLock> dejará de girar en determinadas condiciones para impedir el colapso de procesadores lógicos o la inversión de prioridades en sistemas con Hyper-Threading.  
  
 En este ejemplo se usa la clase <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType>, que requiere la sincronización del usuario para el acceso multiproceso. En las aplicaciones que tienen como destino .NET Framework 4, otra opción es usar <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType>, que no requiere ningún bloqueo de usuario.  
  
 Tenga en cuenta el uso de `false` (`False` en Visual Basic) en la llamada a <xref:System.Threading.SpinLock.Exit%2A>. Esto proporciona el mejor rendimiento. Especifique `true` (`True`) en las arquitecturas IA64 para usar la barrera de memoria, que vacía los búferes de escritura para garantizar que ahora el bloqueo esté disponible para que salgan otros subprocesos.  
  
## <a name="see-also"></a>Vea también  
 [Objetos y características de subprocesos](../../../docs/standard/threading/threading-objects-and-features.md)
