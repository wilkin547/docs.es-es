---
title: Utilizar SpinLock para la sincronización de bajo nivel
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SpinLock, how to use
ms.assetid: a9ed3e4e-4f29-4207-b730-ed0a51ecbc19
ms.openlocfilehash: 148ef5e9d5c570ef04bc6e716a884db5e688d91a
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94826396"
---
# <a name="how-to-use-spinlock-for-low-level-synchronization"></a>Utilizar SpinLock para la sincronización de bajo nivel

En el siguiente ejemplo se muestra cómo usar <xref:System.Threading.SpinLock>. En este ejemplo, la sección crítica realiza una cantidad de trabajo mínima, lo que la convierte en una buena candidata para un elemento <xref:System.Threading.SpinLock>. Al aumentar ligeramente el trabajo, aumenta el rendimiento del elemento <xref:System.Threading.SpinLock> en comparación con un bloqueo estándar. Sin embargo, existe un punto en el que un elemento SpinLock es más caro que un bloqueo estándar. Puede usar la funcionalidad de generación de perfiles de simultaneidad de las herramientas de generación de perfiles para ver qué tipo de bloqueo proporciona mejor rendimiento en su programa. Para más información, consulte [Visualizador de simultaneidad](/visualstudio/profiling/concurrency-visualizer).  
  
 [!code-csharp[CDS_SpinLock#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinlock/cs/spinlockdemo.cs#02)]
 [!code-vb[CDS_SpinLock#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinlock/vb/spinlock_vb.vb#02)]  
  
 <xref:System.Threading.SpinLock> puede ser útil si un bloqueo en un recurso compartido no se va a mantener durante mucho tiempo. En estos casos, puede resultar eficaz en los equipos de varios núcleos que el subproceso bloqueado gire durante algunos ciclos hasta que se libere el bloqueo. Al girar, el subproceso no se bloquea, lo cual es un proceso intensivo de la CPU. <xref:System.Threading.SpinLock> dejará de girar en determinadas condiciones para impedir el colapso de procesadores lógicos o la inversión de prioridades en sistemas con Hyper-Threading.  
  
 En este ejemplo se usa la clase <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType>, que requiere la sincronización del usuario para el acceso multiproceso. Otra opción consiste en usar <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType>, que no requiere ningún bloqueo de usuario.  
  
 Tenga en cuenta el uso de `false` en la llamada a <xref:System.Threading.SpinLock.Exit%2A?displayProperty=nameWithType>. Esto proporciona el mejor rendimiento. Especifique `true` en las arquitecturas IA64 para usar la barrera de memoria, que vacía los búferes de escritura para garantizar que ahora el bloqueo esté disponible para que entren otros subprocesos.
  
## <a name="see-also"></a>Vea también

- [Objetos y características de subprocesos](threading-objects-and-features.md)
- [lock (Instrucción, C#)](../../csharp/language-reference/keywords/lock-statement.md)
- [SyncLock (Instrucción, Visual Basic)](../../visual-basic/language-reference/statements/synclock-statement.md)
