---
title: "How to: Cancel a Task and Its Children | Microsoft Docs"
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
  - "tasks, how to cancel"
ms.assetid: 08574301-8331-4719-ad50-9cf7f6ff3048
caps.latest.revision: 16
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 16
---
# How to: Cancel a Task and Its Children
En estos ejemplos se muestra cómo realizar las tareas siguientes:  
  
1.  Crear e iniciar una tarea cancelable.  
  
2.  Pasar un token de cancelación a un delegado de usuario y, opcionalmente, a la instancia de la tarea.  
  
3.  Observar y responder a la solicitud de cancelación en el delegado de usuario.  
  
4.  Opcionalmente, observar en el subproceso que realiza la llamada que la tarea se canceló.  
  
 El subproceso que realiza la llamada no finaliza la tarea forzosamente, sino que solo señala que se solicita la cancelación.  Si la tarea ya se está ejecutando, es el delegado de usuario el que debe observar la solicitud y responder según corresponda.  Si la cancelación se solicita antes de ejecutarse la tarea, el delegado de usuario nunca se ejecuta y el objeto de tarea pasa al estado Cancelado.  
  
## Ejemplo  
 En este ejemplo se muestra cómo finalizar un objeto <xref:System.Threading.Tasks.Task> y sus elementos secundarios en respuesta a una solicitud de cancelación.  También se muestra que, cuando un delegado de usuario finaliza con una excepción <xref:System.Threading.Tasks.TaskCanceledException>, el subproceso que realiza la llamada puede usar opcionalmente el método <xref:System.Threading.Tasks.Task.Wait%2A> o el método <xref:System.Threading.Tasks.Task.WaitAll%2A> para esperar a que las tareas finalicen.  En este caso, se debe usar un bloque `try/catch` para controlar las excepciones en el subproceso que realiza la llamada.  
  
 [!code-csharp[TPL_Cancellation#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_cancellation/cs/cancel1.cs#04)]
 [!code-vb[TPL_Cancellation#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_cancellation/vb/cancel1.vb#04)]  
  
 La clase <xref:System.Threading.Tasks.Task?displayProperty=fullName> está totalmente integrada con el modelo de cancelación basado en los tipos <xref:System.Threading.CancellationToken?displayProperty=fullName> y <xref:System.Threading.CancellationTokenSource?displayProperty=fullName>.  Para obtener más información, vea [Cancellation in Managed Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md) y [Task Cancellation](../../../docs/standard/parallel-programming/task-cancellation.md).  
  
## Vea también  
 <xref:System.Threading.CancellationTokenSource?displayProperty=fullName>   
 <xref:System.Threading.CancellationToken?displayProperty=fullName>   
 <xref:System.Threading.Tasks.Task?displayProperty=fullName>   
 <xref:System.Threading.Tasks.Task%601?displayProperty=fullName>   
 [Task Parallelism](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)   
 [Attached and Detached Child Tasks](../../../docs/standard/parallel-programming/attached-and-detached-child-tasks.md)   
 [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)