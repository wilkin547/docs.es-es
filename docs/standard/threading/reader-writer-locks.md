---
title: "Reader-Writer Locks | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ReaderWriterLock class, about ReaderWriterLock class"
  - "threading [.NET Framework], ReaderWriterLock class"
ms.assetid: 8c71acf2-2c18-4f4d-8cdb-0728639265fd
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Reader-Writer Locks
La clase <xref:System.Threading.ReaderWriterLockSlim> habilita a varios subprocesos para leer un recurso de forma simultánea, aunque para escribir en el recurso, el subproceso debe esperar a un bloqueo exclusivo.  
  
 Dentro de la aplicación se puede utilizar un <xref:System.Threading.ReaderWriterLockSlim> para proporcionar una sincronización conjunta entre los subprocesos que tienen acceso a un recurso compartido.  Los bloqueos se toman en el mismo <xref:System.Threading.ReaderWriterLockSlim>.  
  
 Al igual que con cualquier mecanismo de sincronización de subprocesos, se debe comprobar que ningún subproceso omite el bloqueo proporcionado por <xref:System.Threading.ReaderWriterLockSlim>.  Una manera de asegurarse es diseñar una clase que encapsule el recurso compartido.  Esta clase proporcionaría los miembros que tienen acceso al recurso compartido privado y que utilizan un <xref:System.Threading.ReaderWriterLockSlim> privado para la sincronización.  Para obtener un ejemplo, vea el código de ejemplo que se proporciona para la clase <xref:System.Threading.ReaderWriterLockSlim>.  <xref:System.Threading.ReaderWriterLockSlim> es bastante eficaz para utilizarse en la sincronización de objetos individuales.  
  
 Organice su aplicación con el fin de reducir al mínimo la duración de las operaciones de lectura y escritura.  Las operaciones de escritura de larga duración afectan al rendimiento porque el bloqueo de escritura es exclusivo.  Las operaciones de lectura de larga duración bloquean el sistema de escritura en espera y, si hay al menos un subproceso en espera de acceso de escritura, entonces los subprocesos que soliciten acceso de lectura también se bloquearán.  
  
> [!NOTE]
>  [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] dispone de dos bloqueos de lector y escritor, <xref:System.Threading.ReaderWriterLockSlim> y <xref:System.Threading.ReaderWriterLock>.  <xref:System.Threading.ReaderWriterLockSlim> se recomienda para todos los trabajos de desarrollo nuevos.  <xref:System.Threading.ReaderWriterLockSlim> es similar a <xref:System.Threading.ReaderWriterLock>, pero tiene reglas simplificadas para la recursividad y para actualizar y degradar el estado del bloqueo.  <xref:System.Threading.ReaderWriterLockSlim> evita muchos casos de interbloqueo potencial.  Además, el rendimiento de <xref:System.Threading.ReaderWriterLockSlim> es significativamente mejor que <xref:System.Threading.ReaderWriterLock>.  
  
## Vea también  
 <xref:System.Threading.ReaderWriterLockSlim>   
 <xref:System.Threading.ReaderWriterLock>   
 [Threading](../../../docs/standard/threading/index.md)   
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md)