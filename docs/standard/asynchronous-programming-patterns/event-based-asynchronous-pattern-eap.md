---
title: "Event-based Asynchronous Pattern (EAP) | Microsoft Docs"
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
  - "asynchronous calls"
  - "asynchronous programming, design patterns"
  - "asynchronous programming"
ms.assetid: c6baed9f-2a25-4728-9a9a-53b7b14840cf
caps.latest.revision: 20
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 20
---
# Event-based Asynchronous Pattern (EAP)
Hay varias maneras de exponer las características asincrónicas al código de cliente.  El modelo asincrónico basado en eventos prescribe una manera para que las clases presenten comportamiento asincrónico.  
  
> [!NOTE]
>  A partir de [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], la biblioteca TPL \(Task Parallel Library, biblioteca de procesamiento paralelo basado en tareas\) proporciona un nuevo modelo para programación asincrónica y paralela.  Para obtener más información, vea [Parallel Programming](../../../docs/standard/parallel-programming/index.md).  
  
## En esta sección  
 [Event\-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 Describe cómo el Modelo asincrónico basado en evento pone a su disposición las ventajas de las aplicaciones multithreading ocultando muchos de los problemas complejos inherentes al diseño multithreading.  
  
 [Implementing the Event\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md)  
 Describe la manera estándar de empaquetar una clase que tiene características asincrónicas.  
  
 [Procedimientos recomendados para implementar el modelo asincrónico basado en eventos](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)  
 Describe los requisitos para exponer las características asincrónicas según el Modelo asincrónico basado en evento.  
  
 [Deciding When to Implement the Event\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/deciding-when-to-implement-the-event-based-asynchronous-pattern.md)  
 Describe cómo determinar cuándo se debería decidir implementar el Modelo asincrónico basado en evento en lugar del modelo <xref:System.IAsyncResult>.  
  
 [Walkthrough: Implementing a Component That Supports the Event\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)  
 Explica cómo crear un componente que implementa el Modelo asincrónico basado en evento.  Se implementa utilizando las clases auxiliares del espacio de nombres <xref:System.ComponentModel?displayProperty=fullName>, que garantiza que el componente funciona correctamente bajo cualquier modelo de aplicación.  
  
 [How to: Use Components That Support the Event\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/how-to-use-components-that-support-the-event-based-asynchronous-pattern.md)  
 Describe cómo utilizar un componente que admite el Modelo asincrónico basado en evento.  
  
## Referencia  
 <xref:System.ComponentModel.AsyncOperation>  
 Describe la clase <xref:System.ComponentModel.AsyncOperation> y contiene vínculos a todos sus miembros.  
  
 <xref:System.ComponentModel.AsyncOperationManager>  
 Describe la clase <xref:System.ComponentModel.AsyncOperationManager> y contiene vínculos a todos sus miembros.  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 Describe el componente <xref:System.ComponentModel.BackgroundWorker> y contiene vínculos a todos sus miembros.  
  
## Secciones relacionadas  
 [Task Parallel Library \(TPL\)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)  
 Describe un modelo de programación para operaciones asincrónicas y paralelas.  
  
 [Threading](../../../docs/standard/threading/index.md)  
 Describe las características de multithreading en .NET Framework.  
  
 [Subprocesos](../Topic/Threading%20\(C%23%20and%20Visual%20Basic\).md)  
 Describe las características de multithreading en los lenguajes Visual Basic y C\#.  
  
## Vea también  
 [Managed Threading Best Practices](../../../docs/standard/threading/managed-threading-best-practices.md)   
 [Eventos](../../../docs/standard/events/index.md)   
 [Multithreading in Components](../Topic/Multithreading%20in%20Components.md)   
 [Asynchronous Programming Design Patterns](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)