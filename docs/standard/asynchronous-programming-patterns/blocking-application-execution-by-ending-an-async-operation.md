---
title: "Blocking Application Execution by Ending an Async Operation | Microsoft Docs"
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
  - "blocks, asynchronous operations"
  - "AsyncWaitHandle property"
  - "asynchronous programming, blocking applications"
  - "blocking application execution"
ms.assetid: cc5e2834-a65b-4df8-b750-7bdb79997fee
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# Blocking Application Execution by Ending an Async Operation
Las aplicaciones que no pueden seguir realizando otra tarea mientras esperan los resultados de una operación asincrónica deben bloquearse hasta que la operación finalice.  Utilice una de las opciones siguientes para bloquear el subproceso principal de la aplicación en cuestión a la espera de que una operación asincrónica finalice:  
  
-   Llame al método de **Fin** *OperationName* de operaciones asincrónicas.  Este tema muestra la ejecución de dicho procedimiento.  
  
-   Utilice la propiedad de <xref:System.IAsyncResult.AsyncWaitHandle%2A> de <xref:System.IAsyncResult> devuelto por el método de **Inicio** *OperationName* de la operación asincrónica.  Para obtener un ejemplo de este procedimiento, vea [Blocking Application Execution Using an AsyncWaitHandle](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md).  
  
 Las aplicaciones que utilizan el método de **Fin** *OperationName* para establecer bloqueos hasta que se completa una operación asincrónica suelen llamar al método de **Inicio** *OperationName* , realizan todas las tareas que se puede hacer sin los resultados de la operación, y después llama a **Fin** *OperationName*.  
  
## Ejemplo  
 El siguiente ejemplo de código muestra cómo utilizar los métodos asincrónicos en la clase <xref:System.Net.Dns> con el fin de recuperar información sobre el Sistema de nombres de dominio para un equipo especificado por el usuario.  Hay que observar que se pasa `null` \(`Nothing` en Visual Basic\) para los parámetros <xref:System.Net.Dns.BeginGetHostByName%2A> `requestCallback` y `stateObject` ya que estos argumentos no son necesarios a la hora de utilizar este enfoque.  
  
 [!code-csharp[AsyncDesignPattern#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_EndBlock.cs#1)]
 [!code-vb[AsyncDesignPattern#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_EndBlock.vb#1)]  
  
## Vea también  
 [Event\-based Asynchronous Pattern \(EAP\)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)   
 [Event\-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)