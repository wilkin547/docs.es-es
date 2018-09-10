---
title: Bloqueos de lector y escritor
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- ReaderWriterLock class, about ReaderWriterLock class
- threading [.NET Framework], ReaderWriterLock class
ms.assetid: 8c71acf2-2c18-4f4d-8cdb-0728639265fd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8be9b4eef30333fbbdc26915635d17157176d6fc
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44208184"
---
# <a name="reader-writer-locks"></a>Bloqueos de lector y escritor
La clase <xref:System.Threading.ReaderWriterLockSlim> permite que varios subprocesos lean un recurso al mismo tiempo, pero requiere que un subproceso espere a un bloqueo exclusivo para poder escribir en el recurso.  
  
 Puede usar <xref:System.Threading.ReaderWriterLockSlim> en la aplicación para proporcionar una sincronización conjunta entre los subprocesos que acceden a un recurso compartido. Los bloqueos se realizan en <xref:System.Threading.ReaderWriterLockSlim>.  
  
 Como con cualquier mecanismo de sincronización de subprocesos, debe asegurarse de que ningún subproceso omite el bloqueo proporcionado por <xref:System.Threading.ReaderWriterLockSlim>. Una manera de asegurarse de esto consiste en diseñar una clase que encapsula el recurso compartido. Esta clase proporcionaría miembros que acceden al recurso compartido privado y que usan una clase privada <xref:System.Threading.ReaderWriterLockSlim> para la sincronización. Para obtener un ejemplo, vea el ejemplo de código de la clase <xref:System.Threading.ReaderWriterLockSlim>. <xref:System.Threading.ReaderWriterLockSlim> es lo suficientemente eficaz para sincronizar objetos individuales.  
  
 Estructure la aplicación para minimizar la duración de las operaciones de lectura y escritura. Las operaciones de escritura de larga duración afectan al rendimiento porque el bloqueo de escritura es exclusivo. Los escritores de espera del bloque de operaciones de lectura de larga duración, y si al menos un subproceso espera el acceso de escritura, los subprocesos que solicitan acceso de lectura también se bloquearán.  
  
> [!NOTE]
>  [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] tiene dos bloqueos de lector y escritor, <xref:System.Threading.ReaderWriterLockSlim> y <xref:System.Threading.ReaderWriterLock>. <xref:System.Threading.ReaderWriterLockSlim> se recomienda para todos los nuevos desarrollos. <xref:System.Threading.ReaderWriterLockSlim> es similar a <xref:System.Threading.ReaderWriterLock>, pero se han simplificado las reglas para la recursividad y para actualizar y degradar el estado de bloqueo. <xref:System.Threading.ReaderWriterLockSlim> evita muchos casos de interbloqueo potencial. Además, el rendimiento de <xref:System.Threading.ReaderWriterLockSlim> es significativamente mayor que <xref:System.Threading.ReaderWriterLock>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Threading.ReaderWriterLockSlim>  
- <xref:System.Threading.ReaderWriterLock>  
- [Subprocesamiento](../../../docs/standard/threading/index.md)  
- [Objetos y características de subprocesos](../../../docs/standard/threading/threading-objects-and-features.md)
