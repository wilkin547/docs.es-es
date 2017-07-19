---
title: "How to: Use SpinLock for Low-Level Synchronization | Microsoft Docs"
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
  - "SpinLock, how to use"
ms.assetid: a9ed3e4e-4f29-4207-b730-ed0a51ecbc19
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# How to: Use SpinLock for Low-Level Synchronization
En el siguiente ejemplo se muestra cómo utilizar <xref:System.Threading.SpinLock>.  
  
## Ejemplo  
 En este ejemplo, la sección crítica realiza una cantidad de trabajo mínima, lo que lo convierte en un buen candidato para <xref:System.Threading.SpinLock>.  Al aumentar ligeramente el trabajo aumenta el rendimiento de <xref:System.Threading.SpinLock> en comparación con un bloqueo estándar.  Sin embargo, hay un punto en el que un bloqueo por subproceso es más caro que un bloqueo estándar.  Se puede usar la nueva funcionalidad de generación de perfiles de simultaneidad de las Herramientas de generación de perfiles para ver qué tipo de bloqueo proporciona mayor rendimiento en su programa.  Para obtener más información, vea [Visualizador de simultaneidad](../Topic/Concurrency%20Visualizer.md).  
  
 [!code-csharp[CDS_SpinLock#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinlock/cs/spinlockdemo.cs#02)]
 [!code-vb[CDS_SpinLock#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinlock/vb/spinlock_vb.vb#02)]  
  
 <xref:System.Threading.SpinLock> puede resultar útil cuando un bloqueo en un recurso compartido no se va a mantener durante mucho tiempo.  En esos casos, en equipos con varios núcleos puede ser eficaz que el subproceso bloqueado gire durante unos ciclos hasta que se libere el bloqueo.  Al girar, el subproceso no se bloquea, lo cual es un proceso que consume muchos recursos de la CPU.  <xref:System.Threading.SpinLock> dejará de girar en ciertas condiciones para evitar el colapso de los procesadores lógicos o la inversión de la prioridad en sistemas con Hyper\-Threading.  
  
 En este ejemplo se usa la clase <xref:System.Collections.Generic.Queue%601?displayProperty=fullName>, que necesita sincronización de usuarios para el acceso multiproceso.  En aplicaciones destinadas a .NET Framework 4, otra opción consiste en usar <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=fullName>, que no necesita ningún bloqueo de usuario.  
  
 Fíjese en el uso de `false` \(`False` en Visual Basic\) en la llamada a <xref:System.Threading.SpinLock.Exit%2A>.  Este valor proporciona el mayor rendimiento.  Especifique `true` \(`True`\) en las arquitecturas IA64 para utilizar la barrera de memoria; de este modo, se vacían los búferes de escritura a fin de garantizar que el bloqueo está disponible para otros subprocesos que van a salir.  
  
## Vea también  
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md)