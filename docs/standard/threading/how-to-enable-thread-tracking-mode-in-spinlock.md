---
title: "How to: Enable Thread-Tracking Mode in SpinLock | Microsoft Docs"
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
  - "SpinLock, how to enable thread-tracking"
ms.assetid: 62ee2e68-0bdd-4869-afc9-f0a57a11ae01
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# How to: Enable Thread-Tracking Mode in SpinLock
<xref:System.Threading.SpinLock?displayProperty=fullName> es un bloqueo de exclusión mutua de bajo nivel que se puede utilizar para los escenarios que tienen los tiempos de espera muy breves.  <xref:System.Threading.SpinLock> no permite volver a entrar.  Después de que un subproceso entra en el bloqueo, debe salir correctamente de él antes de poder volver a entrar.  Normalmente, cualquier intento de volver a entrar en el bloqueo produciría un interbloqueo; los interbloqueos pueden resultar muy difíciles de depurar.  Para ayudar en el desarrollo, <xref:System.Threading.SpinLock?displayProperty=fullName> admite un modo de seguimiento de subprocesos que produce una excepción cuando un subproceso intenta volver a entrar en un bloqueo en que ya se encuentra.  Esto permite localizar con mayor facilidad el punto en el que no se ha salido correctamente del bloqueo.  Para activar el modo de seguimiento de subprocesos, puede utilizar el constructor <xref:System.Threading.SpinLock> que toma un parámetro de entrada Boolean y pasar un argumento de `true`.  Después de completar las fases de desarrollo y pruebas, desactive modo de seguimiento de subprocesos para mejorar el rendimiento.  
  
## Ejemplo  
 En el siguiente ejemplo se muestra el modo de seguimiento de subprocesos.  Las líneas que salen correctamente del bloqueo están marcadas como comentario para simular un error de código que produce uno de los siguientes resultados:  
  
-   Se produce una excepción si <xref:System.Threading.SpinLock> se creó utilizando un argumento de `true` \(`True` en Visual Basic\).  
  
-   Se produce un interbloqueo si <xref:System.Threading.SpinLock> se creó utilizando un argumento de `false` \(`False` en Visual Basic\).  
  
 [!code-csharp[CDS_SpinLock#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinlock/cs/spinlockdemo.cs#01)]
 [!code-vb[CDS_SpinLock#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinlock/vb/spinlock_threadtracking.vb#01)]  
  
## Vea también  
 [SpinLock](../../../docs/standard/threading/spinlock.md)