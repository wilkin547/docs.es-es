---
title: "Managed Threading Basics | Microsoft Docs"
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
  - "multiple threads"
  - "threading [.NET Framework], multiple threads"
  - "threading [.NET Framework], about threading"
  - "managed threading"
ms.assetid: b2944911-0e8f-427d-a8bb-077550618935
caps.latest.revision: 16
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 16
---
# Managed Threading Basics
En los cinco primeros temas de esta sección encontrará información que le ayudará a determinar cuándo se debe utilizar un subprocesamiento administrado, así como explicaciones de algunas de las características básicas.  Para obtener información sobre las clases que proporcionan características adicionales, vea [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md) y [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md).  
  
 En el resto de la sección se tratan temas más avanzados, incluida la interacción del subprocesamiento administrado con el sistema operativo Windows.  
  
> [!NOTE]
>  En [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], Task Parallel Library y PLINQ proporcionan API para el paralelismo de tareas y datos en programas multiproceso.  Para obtener más información, vea [Parallel Programming](../../../docs/standard/parallel-programming/index.md).  
  
## En esta sección  
 [Threads and Threading](../../../docs/standard/threading/threads-and-threading.md)  
 Explica las ventajas y desventajas de utilizar múltiples subprocesos, y describe los escenarios en los que puede crear subprocesos o utilizar los subprocesos del grupo de subprocesos.  
  
 [Exceptions in Managed Threads](../../../docs/standard/threading/exceptions-in-managed-threads.md)  
 Describe el comportamiento de las excepciones no controladas en los subprocesos de distintas versiones de .NET Framework, en particular las situaciones que pueden provocar que la aplicación se cierre.  
  
 [Synchronizing Data for Multithreading](../../../docs/standard/threading/synchronizing-data-for-multithreading.md)  
 Describe estrategias para sincronizar datos en las clases que se utilizarán con varios subprocesos.  
  
 [Estados de subprocesos administrados](../../../docs/standard/threading/managed-thread-states.md)  
 Describe los estados básicos de los subprocesos, y explica cómo detectar si un subproceso se está ejecutando.  
  
 [Foreground and Background Threads](../../../docs/standard/threading/foreground-and-background-threads.md)  
 Explica las diferencias entre los subprocesos que se ejecutan en primer y en segundo plano.  
  
 [Managed and Unmanaged Threading in Windows](../../../docs/standard/threading/managed-and-unmanaged-threading-in-windows.md)  
 Explica la relación existente entre subprocesamiento administrado y no administrado, enumera los administrados equivalentes para las API de subprocesamiento de Windows, y describe la interacción entre apartamentos COM y subprocesos administrados.  
  
 [Thread.Suspend, Garbage Collection, and Safe Points](../../../docs/standard/threading/thread-suspend-garbage-collection-and-safe-points.md)  
 Describe la suspensión de un subproceso y la recolección de elementos no utilizados.  
  
 [Thread Local Storage: Thread\-Relative Static Fields and Data Slots](../../../docs/standard/threading/thread-local-storage-thread-relative-static-fields-and-data-slots.md)  
 Describe los mecanismos de almacenamiento relacionados con subprocesos.  
  
 [Cancellation in Managed Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md)  
 Describe cómo se pueden cancelar las operaciones asincrónicas o las operaciones sincrónicas de ejecución prolongada utilizando un token de cancelación.  
  
## Referencia  
 <xref:System.Threading.Thread>  
 Proporciona documentación de referencia para la clase **Thread**, que representa un subproceso administrado, independientemente de que provenga de código no administrado o de que se haya creado en una aplicación administrada.  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 Proporciona una manera segura de implementar el multithreading junto con los objetos de la interfaz de usuario.  
  
## Secciones relacionadas  
 [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md)  
 Describe las clases administradas utilizadas para sincronizar las actividades de varios subprocesos.  
  
 [Managed Threading Best Practices](../../../docs/standard/threading/managed-threading-best-practices.md)  
 Describe los problemas comunes del multithreading y estrategias para evitar dichos problemas.  
  
 [Parallel Programming](../../../docs/standard/parallel-programming/index.md)  
 Describe Task Parallel Library \(TPL\) y PLINQ, que simplifican considerablemente la creación de aplicaciones .NET Framework asincrónicas y multiproceso.