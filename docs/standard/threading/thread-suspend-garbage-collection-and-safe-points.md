---
title: "Thread.Suspend, Garbage Collection, and Safe Points | Microsoft Docs"
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
  - "suspending threads"
  - "safe points"
  - "threading [.NET Framework], suspending"
  - "threading [.NET Framework], garbage collection"
  - "garbage collection, threads"
ms.assetid: e8f58e17-2714-4821-802a-f8eb3b2baa62
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# Thread.Suspend, Garbage Collection, and Safe Points
Cuando se llama a <xref:System.Threading.Thread.Suspend%2A?displayProperty=fullName> en un subproceso, el sistema detecta que se ha solicitado la suspensión de un subproceso y permite que el subproceso se ejecute hasta que alcance un punto seguro antes de suspenderlo.  En un subproceso, un punto seguro es un punto en su ejecución en el que es posible realizar la recolección de elementos no utilizados.  
  
 Una vez que se alcanza un punto seguro, el motor en tiempo de ejecución garantiza que el subproceso suspendido no seguirá avanzando en código administrado.  Un subproceso que se ejecute fuera de código administrado es siempre seguro para la recolección de elementos no utilizados, y su ejecución continúa hasta que intenta reanudar la ejecución de código administrado.  
  
> [!NOTE]
>  Para realizar una recolección de elementos no utilizados, el motor en tiempo de ejecución debe suspender todos los subprocesos, salvo el subproceso que realiza la recolección.  Cada subproceso debe llevarse a un punto de seguridad para que se pueda suspender.  
  
## Vea también  
 <xref:System.Threading.Thread>   
 <xref:System.GC>   
 [Threading](../../../docs/standard/threading/index.md)   
 [Administración de memoria automática](../../../docs/standard/automatic-memory-management.md)