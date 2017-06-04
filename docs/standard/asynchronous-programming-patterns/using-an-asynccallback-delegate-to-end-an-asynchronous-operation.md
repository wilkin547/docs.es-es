---
title: "Using an AsyncCallback Delegate to End an Asynchronous Operation | Microsoft Docs"
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
  - "ending asynchronous operations"
  - "asynchronous programming, ending operations"
  - "AsyncCallback delegate"
  - "stopping asynchronous operations"
ms.assetid: 9d97206c-8917-406c-8961-7d0909d84eeb
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# Using an AsyncCallback Delegate to End an Asynchronous Operation
Aquellas aplicaciones que pueden realizar otra tarea mientras esperan los resultados de una operación asincrónica, no se deberían bloquear mientras esperan a que la operación finalice.  Utilice una de las siguientes opciones para seguir ejecutando instrucciones mientras se está a la espera de que una operación asincrónica finalice:  
  
-   Utilice un delegado <xref:System.AsyncCallback> para procesar los resultados de la operación asincrónica en un subproceso independiente.  Este tema muestra la ejecución de dicho procedimiento.  
  
-   Utilice la propiedad de <xref:System.IAsyncResult.IsCompleted%2A> de <xref:System.IAsyncResult> devuelto por el método de **Inicio** *OperationName* de la operación asincrónica para determinar si la operación se ha completado.  Para obtener un ejemplo de este procedimiento, vea [Polling for the Status of an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/polling-for-the-status-of-an-asynchronous-operation.md).  
  
## Ejemplo  
 El siguiente ejemplo de código muestra cómo utilizar los métodos asincrónicos en la clase <xref:System.Net.Dns> con el fin de recuperar información sobre el Sistema de nombres de dominio \(DNS\) para equipos especificados por el usuario.  En este ejemplo, se crea un delegado <xref:System.AsyncCallback> que hace referencia el método `ProcessDnsInformation`.  Se llama a este método una vez por cada solicitud asincrónica con el fin de obtener información DNS.  
  
 Obsérvese que el host especificado por el usuario se pasa al parámetro <xref:System.Net.Dns.BeginGetHostByName%2A> <xref:System.Object>.  Para obtener un ejemplo que muestra cómo definir y utilizar un objeto de estado más complejo, vea [Using an AsyncCallback Delegate and State Object](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-and-state-object.md).  
  
 [!code-csharp[AsyncDesignPattern#4](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/AsyncDelegateNoStateObject.cs#4)]
 [!code-vb[AsyncDesignPattern#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/AsyncDelegateNoState.vb#4)]  
  
## Vea también  
 [Event\-based Asynchronous Pattern \(EAP\)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)   
 [Event\-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)   
 [Calling Asynchronous Methods Using IAsyncResult](../../../docs/standard/asynchronous-programming-patterns/calling-asynchronous-methods-using-iasyncresult.md)   
 [Using an AsyncCallback Delegate and State Object](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-and-state-object.md)