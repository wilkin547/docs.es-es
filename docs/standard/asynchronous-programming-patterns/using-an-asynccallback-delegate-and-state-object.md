---
title: "Using an AsyncCallback Delegate and State Object | Microsoft Docs"
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
  - "asynchronous programming, delegates"
  - "AsyncCallback delegate, samples"
  - "asynchronous programming, state objects"
  - "IAsyncResult interface, samples"
ms.assetid: e3e5475d-c5e9-43f0-928e-d18df8ca1f1d
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Using an AsyncCallback Delegate and State Object
Cuando se utiliza un delegado de <xref:System.AsyncCallback> para procesar los resultados de la operación asincrónica en un subproceso independiente, se puede utilizar un objeto de estado para pasar información entre las devoluciones de llamada y recuperar un resultado final.  Este tema ilustra esta práctica con la expansión del ejemplo en [Using an AsyncCallback Delegate to End an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).  
  
## Ejemplo  
 El siguiente ejemplo de código muestra cómo utilizar los métodos asincrónicos en la clase <xref:System.Net.Dns> con el fin de recuperar información sobre el Sistema de nombres de dominio \(DNS\) para equipos especificados por el usuario.  Este ejemplo define y utiliza la clase `HostRequest` para almacenar información de estado.  Un objeto `HostRequest` se crea para cada nombre de equipo escrito por el usuario.  Este objeto se pasa al método <xref:System.Net.Dns.BeginGetHostByName%2A>.  Se llama al método `ProcessDnsInformation` cada vez que una solicitud finaliza.  El objeto `HostRequest` se recupera utilizando la propiedad <xref:System.IAsyncResult.AsyncState%2A>.  El método `ProcessDnsInformation` utiliza el objeto `HostRequest` para almacenar un <xref:System.Net.IPHostEntry> devuelto por la solicitud o un <xref:System.Net.Sockets.SocketException> producido por la solicitud.  Una vez que todas las solicitudes han finalizado, la aplicación recorre en iteración los objetos `HostRequest` y muestra la información DNS o mensaje de error <xref:System.Net.Sockets.SocketException>.  
  
 [!code-csharp[AsyncDesignPattern#5](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/AsyncDelegateWithStateObject.cs#5)]
 [!code-vb[AsyncDesignPattern#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/AsyncDelegateWithStateObject.vb#5)]  
  
## Vea también  
 [Event\-based Asynchronous Pattern \(EAP\)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)   
 [Event\-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)   
 [Using an AsyncCallback Delegate to End an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md)