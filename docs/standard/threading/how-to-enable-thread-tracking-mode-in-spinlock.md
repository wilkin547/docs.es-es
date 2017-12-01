---
title: "Cómo: Habilitar el modo de seguimiento de subproceso en el bloqueo SpinLock"
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
helpviewer_keywords: SpinLock, how to enable thread-tracking
ms.assetid: 62ee2e68-0bdd-4869-afc9-f0a57a11ae01
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ca5f1b6eace7a24a6bbb7fd541858246828fa757
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-enable-thread-tracking-mode-in-spinlock"></a>Cómo: Habilitar el modo de seguimiento de subproceso en el bloqueo SpinLock
<xref:System.Threading.SpinLock?displayProperty=nameWithType>es un bloqueo de exclusión mutua bajo nivel que se puede usar para escenarios que tienen los tiempos de espera muy breve. <xref:System.Threading.SpinLock>no es reentrante. Después de que un subproceso entra en el bloqueo, debe salir correctamente el bloqueo antes de que pueda introducir de nuevo. Por lo general, cualquier intento de volver a entrar en el bloqueo produciría un interbloqueo y los interbloqueos pueden ser muy difíciles de depurar. Como ayuda para el desarrollo, <xref:System.Threading.SpinLock?displayProperty=nameWithType> admite un modo de seguimiento de subprocesos que provoca que se produce cuando un subproceso intenta volver a entrar en un bloqueo que ya tenía una excepción. Esto le permite que localizar con mayor facilidad el punto en el que el bloqueo no se cerró correctamente. Puede activar el modo de seguimiento de subprocesos mediante el uso de la <xref:System.Threading.SpinLock> constructor que toma un valor booleano de entrada y pasando un argumento de entrada de `true`. Después de completar las fases de pruebas y desarrollo, desactiva el modo de seguimiento de subprocesos para mejorar el rendimiento.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra el modo de seguimiento de subprocesos. Las líneas que salen correctamente del bloqueo están comentadas para simular un error de código que hace que uno de los siguientes resultados:  
  
-   Se produce una excepción si el <xref:System.Threading.SpinLock> se creó mediante un argumento de `true` (`True` en Visual Basic).  
  
-   Produce un interbloqueo si el <xref:System.Threading.SpinLock> se creó mediante un argumento de `false` (`False` en Visual Basic).  
  
 [!code-csharp[CDS_SpinLock#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinlock/cs/spinlockdemo.cs#01)]
 [!code-vb[CDS_SpinLock#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinlock/vb/spinlock_threadtracking.vb#01)]  
  
## <a name="see-also"></a>Vea también  
 [SpinLock](../../../docs/standard/threading/spinlock.md)
