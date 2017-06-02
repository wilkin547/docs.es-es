---
title: "Polling for the Status of an Asynchronous Operation | Microsoft Docs"
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
  - "asynchronous programming, status polling"
  - "polling asynchronous operation status"
  - "status information [.NET Framework], asynchronous operations"
ms.assetid: b541af31-dacb-4e20-8847-1b1ff7c35363
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# Polling for the Status of an Asynchronous Operation
Aquellas aplicaciones que pueden realizar otra tarea mientras esperan los resultados de una operación asincrónica, no se deberían bloquear mientras esperan a que la operación finalice.  Utilice una de las siguientes opciones para seguir ejecutando instrucciones mientras se está a la espera de que una operación asincrónica finalice:  
  
-   Utilice la propiedad de <xref:System.IAsyncResult.IsCompleted%2A> de <xref:System.IAsyncResult> devuelto por el método de **Inicio** *OperationName* de la operación asincrónica para determinar si la operación se ha completado.  Este enfoque se conoce como sondeo y se muestra en este tema.  
  
-   Utilice un delegado <xref:System.AsyncCallback> para procesar los resultados de la operación asincrónica en un subproceso independiente.  Para obtener un ejemplo de este procedimiento, vea [Using an AsyncCallback Delegate to End an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).  
  
## Ejemplo  
 El siguiente ejemplo de código muestra cómo utilizar los métodos asincrónicos en la clase <xref:System.Net.Dns> con el fin de recuperar información sobre el Sistema de nombres de dominio para un equipo especificado por el usuario.  Este ejemplo inicia la operación asincrónica y, a continuación, imprime puntos \("."\) en la consola hasta que la operación se haya completado.  Hay que observar que se pasa **null** \(**Nothing** en Visual Basic\) para los parámetros <xref:System.Net.Dns.BeginGetHostByName%2A> <xref:System.AsyncCallback> y <xref:System.Object> ya que estos argumentos no son necesarios a la hora de utilizar este enfoque.  
  
 [!code-csharp[AsyncDesignPattern#3](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_Poll.cs#3)]
 [!code-vb[AsyncDesignPattern#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_Poll.vb#3)]  
  
## Vea también  
 [Event\-based Asynchronous Pattern \(EAP\)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)   
 [Event\-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)