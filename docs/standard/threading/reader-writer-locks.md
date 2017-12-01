---
title: Bloqueos de lector y escritor
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ReaderWriterLock class, about ReaderWriterLock class
- threading [.NET Framework], ReaderWriterLock class
ms.assetid: 8c71acf2-2c18-4f4d-8cdb-0728639265fd
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: df06e83165906199774f99de4140ace9b7396cbb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="reader-writer-locks"></a>Bloqueos de lector y escritor
La <xref:System.Threading.ReaderWriterLockSlim> clase permite que varios subprocesos leer un recurso al mismo tiempo, pero requiere que un subproceso debe esperar a un bloqueo exclusivo para poder escribir en el recurso.  
  
 Puede usar un <xref:System.Threading.ReaderWriterLockSlim> en la aplicación para proporcionar una sincronización conjunta entre los subprocesos que tienen acceso a un recurso compartido. Los bloqueos se han realizado en el <xref:System.Threading.ReaderWriterLockSlim> propio.  
  
 Como con cualquier mecanismo de sincronización de subprocesos, debe asegurarse de que ningún subproceso omite el bloqueo proporcionado por <xref:System.Threading.ReaderWriterLockSlim>. Una manera de asegurarse de esto consiste en diseñar una clase que encapsula el recurso compartido. Esta clase proporcionaría los miembros que tener acceso al recurso compartido privado y que utilicen una privada <xref:System.Threading.ReaderWriterLockSlim> para la sincronización. Para obtener un ejemplo, vea el ejemplo de código para el <xref:System.Threading.ReaderWriterLockSlim> clase. <xref:System.Threading.ReaderWriterLockSlim>es lo suficientemente eficaz para sincronizar objetos individuales.  
  
 Estructurar la aplicación para minimizar la duración de lectura y las operaciones de escritura. Las operaciones de escritura de larga duración afectan al rendimiento porque el bloqueo de escritura es exclusivo. Los escritores de espera de bloque de operaciones de lectura de larga duración y, si al menos un subproceso está esperando el acceso de escritura, también se bloquearán los subprocesos que soliciten acceso de lectura.  
  
> [!NOTE]
>  El [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] tiene dos bloqueos de lector y escritor, <xref:System.Threading.ReaderWriterLockSlim> y <xref:System.Threading.ReaderWriterLock>. <xref:System.Threading.ReaderWriterLockSlim>se recomienda para todos los nuevos desarrollos. <xref:System.Threading.ReaderWriterLockSlim>es similar a <xref:System.Threading.ReaderWriterLock>, pero se han simplificado las reglas para que la recursividad y para actualizar y degradar el estado de bloqueo. <xref:System.Threading.ReaderWriterLockSlim>evita muchos casos de interbloqueo potencial. Además, el rendimiento de <xref:System.Threading.ReaderWriterLockSlim> es significativamente mejores que <xref:System.Threading.ReaderWriterLock>.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Threading.ReaderWriterLockSlim>  
 <xref:System.Threading.ReaderWriterLock>  
 [Subprocesamiento](../../../docs/standard/threading/index.md)  
 [Objetos y características de subprocesos](../../../docs/standard/threading/threading-objects-and-features.md)
