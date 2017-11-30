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
helpviewer_keywords: SpinLock, how to use
ms.assetid: a9ed3e4e-4f29-4207-b730-ed0a51ecbc19
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 30ddc7d340b210aaad4a04ea43e89555d2701f20
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-use-spinlock-for-low-level-synchronization"></a>Cómo: Utilizar SpinLock para la sincronización de bajo nivel
En el ejemplo siguiente se muestra cómo utilizar un <xref:System.Threading.SpinLock>.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, la sección crítica realiza una cantidad mínima de trabajo, lo que resulta una buena candidata para una <xref:System.Threading.SpinLock>. Al aumentar el trabajo una pequeña cantidad aumenta el rendimiento de la <xref:System.Threading.SpinLock> en comparación con un bloqueo estándar. Sin embargo, existe un punto en el que un elemento SpinLock es más caro que un bloqueo estándar. Puede usar la funcionalidad de generación de perfiles de simultaneidad de las herramientas de generación de perfiles para ver qué tipo de bloqueo proporciona mejor rendimiento en su programa. Para más información, consulte [Visualizador de simultaneidad](/visualstudio/profiling/concurrency-visualizer).  
  
 [!code-csharp[CDS_SpinLock#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinlock/cs/spinlockdemo.cs#02)]
 [!code-vb[CDS_SpinLock#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinlock/vb/spinlock_vb.vb#02)]  
  
 <xref:System.Threading.SpinLock>puede ser útil cuando un bloqueo en un recurso compartido no va a ser dure mucho. En estos casos, puede resultar eficaz en los equipos de varios núcleos que el subproceso bloqueado gire durante algunos ciclos hasta que se libere el bloqueo. Al girar, el subproceso no se bloquea, lo cual es un proceso intensivo de la CPU. <xref:System.Threading.SpinLock>dejará de girar en ciertas condiciones para evitar el colapso de los procesadores lógicos o la inversión de prioridad en sistemas con Hyper-Threading.  
  
 Este ejemplo se utiliza la <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType> (clase), que requiere la sincronización de usuario para el acceso multiproceso. En las aplicaciones que tienen como destino .NET Framework versión 4, otra opción es usar la <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType>, que no requiere ningún bloqueo de usuario.  
  
 Tenga en cuenta el uso de `false` (`False` en Visual Basic) en la llamada a <xref:System.Threading.SpinLock.Exit%2A>. Esto proporciona el mejor rendimiento. Especifique `true` (`True`) en las arquitecturas IA64 para usar la barrera de memoria, que vacía los búferes de escritura para garantizar que ahora el bloqueo esté disponible para que salgan otros subprocesos.  
  
## <a name="see-also"></a>Vea también  
 [Objetos y características de subprocesos](../../../docs/standard/threading/threading-objects-and-features.md)
