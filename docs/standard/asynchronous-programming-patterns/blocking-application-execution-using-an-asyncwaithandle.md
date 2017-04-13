---
title: "Blocking Application Execution Using an AsyncWaitHandle | Microsoft Docs"
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
  - "ending asynchronous operations"
  - "asynchronous programming, ending operations"
  - "asynchronous programming, blocking applications"
  - "stopping asynchronous operations"
  - "blocking application execution"
ms.assetid: 3e32daf2-8161-4e8f-addd-9fd9ff101b03
caps.latest.revision: 6
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 6
---
# Blocking Application Execution Using an AsyncWaitHandle
Las aplicaciones que no pueden seguir realizando otra tarea mientras esperan los resultados de una operación asincrónica deben bloquearse hasta que la operación finalice.  Utilice una de las opciones siguientes para bloquear el subproceso principal de la aplicación en cuestión a la espera de que una operación asincrónica finalice:  
  
-   Utilice la propiedad de <xref:System.IAsyncResult.AsyncWaitHandle%2A> de <xref:System.IAsyncResult> devuelto por el método de **Inicio** *OperationName* de la operación asincrónica.  Este tema muestra la ejecución de dicho procedimiento.  
  
-   Llame al método de **Fin** *OperationName* de la operación asincrónica.  Para obtener un ejemplo de este procedimiento, vea [Blocking Application Execution by Ending an Async Operation](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-by-ending-an-async-operation.md).  
  
 Las aplicaciones que utilizan uno o más <xref:System.Threading.WaitHandle> objetos para bloquear hasta que se completa una operación asincrónica llamarán normalmente el método de **Begin** *OperationName* realizan el trabajo que se puede hacer con los resultados de la operación, y se bloquean hasta que la operación asincrónica.  Una aplicación se puede bloquear en una única operación llamando a uno de los métodos <xref:System.Threading.WaitHandle.WaitOne%2A> mediante <xref:System.IAsyncResult.AsyncWaitHandle%2A>.  Para bloquear la ejecución de una aplicación mientras espera que finalice un conjunto de operaciones asincrónicas, almacene los objetos <xref:System.IAsyncResult.AsyncWaitHandle%2A> asociados en una matriz y llame a uno de los métodos <xref:System.Threading.WaitHandle.WaitAll%2A>.  Para bloquear la ejecución de una aplicación mientras espera que finalice alguno de los conjuntos de operaciones asincrónicas, almacene los objetos <xref:System.IAsyncResult.AsyncWaitHandle%2A> asociados en una matriz y llame a uno de los métodos <xref:System.Threading.WaitHandle.WaitAny%2A>.  
  
## Ejemplo  
 El ejemplo de código siguiente muestra cómo utilizar los métodos asincrónicos en la clase DNS para recuperar información sobre el Sistema de nombres de dominio para un equipo especificado por el usuario.  El ejemplo muestra cómo realizar el bloqueo utilizando el objeto <xref:System.Threading.WaitHandle> asociado a la operación asincrónica.  Observe que se pasa el valor `null` \(`Nothing` en Visual Basic\) para los parámetros <xref:System.Net.Dns.BeginGetHostByName%2A>, `requestCallback` y `stateObject`, puesto que no son necesarios cuando se utiliza este procedimiento.  
  
 [!code-csharp[AsyncDesignPattern#2](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_EndBlockWait.cs#2)]
 [!code-vb[AsyncDesignPattern#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_EndBlockWait.vb#2)]  
  
## Vea también  
 [Event\-based Asynchronous Pattern \(EAP\)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)   
 [Event\-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)