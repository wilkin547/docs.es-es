---
title: "SpinLock | Microsoft Docs"
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
  - "synchronization primitives, SpinLock"
ms.assetid: f9af93bb-7a0d-4ba5-afe8-74f48b6b6958
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# SpinLock
La estructura <xref:System.Threading.SpinLock> es una primitiva de sincronización de exclusión mutua y bajo nivel que itera en ciclos mientras espera adquirir un bloqueo.  En equipos con varios núcleos, en que los períodos de tiempo de espera deben ser breves y en que la contención es mínima, el comportamiento de <xref:System.Threading.SpinLock> puede ser mejor que el de otros tipos de bloqueos.  Sin embargo, se recomienda utilizar <xref:System.Threading.SpinLock> solamente si se determina mediante la generación de perfiles que los métodos <xref:System.Threading.Monitor?displayProperty=fullName> o <xref:System.Threading.Interlocked> están reduciendo el rendimiento del programa de forma significativa.  
  
 <xref:System.Threading.SpinLock> puede proporcionar el intervalo de tiempo del subproceso aunque no haya adquirido el bloqueo todavía.  El motivo es evitar la inversión de la prioridad del subproceso y permitir el progreso del recolector de elementos no utilizados.  Cuando se utiliza <xref:System.Threading.SpinLock>, conviene asegurarse de que ningún subproceso mantenga el bloqueo durante más de un brevísimo intervalo de tiempo, y que ningún subproceso se pueda bloquear mientras mantiene el bloqueo.  
  
 Como SpinLock es un tipo de valor, se debe pasar explícitamente por referencia si se pretende que las dos copias hagan referencia al mismo bloqueo.  
  
 Para obtener más información acerca de cómo utilizar este tipo, vea <xref:System.Threading.SpinLock?displayProperty=fullName>.  Para obtener un ejemplo, vea [How to: Use SpinLock for Low\-Level Synchronization](../../../docs/standard/threading/how-to-use-spinlock-for-low-level-synchronization.md).  
  
 <xref:System.Threading.SpinLock> admite un modo de *seguimiento de subprocesos* que se puede utilizar durante la fase de desarrollo para ayudar a realizar el seguimiento del subproceso que está manteniendo el bloqueo en un momento concreto.  El modo de seguimiento de subprocesos es muy útil para la depuración, pero se recomienda desactivarlo en la versión de lanzamiento del programa porque puede reducir el rendimiento.  Para obtener más información, vea [How to: Enable Thread\-Tracking Mode in SpinLock](../../../docs/standard/threading/how-to-enable-thread-tracking-mode-in-spinlock.md).  
  
## Vea también  
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md)