---
title: Utilizar un delegado AsyncCallback y un objeto State
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- asynchronous programming, delegates
- AsyncCallback delegate, samples
- asynchronous programming, state objects
- IAsyncResult interface, samples
ms.assetid: e3e5475d-c5e9-43f0-928e-d18df8ca1f1d
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e8793a78289e9b58407038f41cc9d403ff9f9940
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="using-an-asynccallback-delegate-and-state-object"></a>Utilizar un delegado AsyncCallback y un objeto State
Cuando se usa un <xref:System.AsyncCallback> delegado para procesar los resultados de la operación asincrónica en un subproceso independiente, puede usar un objeto de estado para pasar información entre las devoluciones de llamada y recuperar un resultado final. Este tema muestra este procedimiento mediante la expansión en el ejemplo de [utilizar un delegado AsyncCallback para finalizar una operación asincrónica](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se muestra cómo utilizar los métodos asincrónicos en el <xref:System.Net.Dns> clase para recuperar información de sistema de nombres de dominio (DNS) para equipos especificados por el usuario. Este ejemplo define y utiliza la `HostRequest` clase para almacenar información de estado. Un `HostRequest` objeto se crea para cada nombre de equipo especificado por el usuario. Este objeto se pasa a la <xref:System.Net.Dns.BeginGetHostByName%2A> método. El `ProcessDnsInformation` método se llama cada vez que se completa una solicitud. El `HostRequest` objeto se recupera utilizando la <xref:System.IAsyncResult.AsyncState%2A> propiedad. El `ProcessDnsInformation` método usa la `HostRequest` objeto para almacenar el <xref:System.Net.IPHostEntry> devuelto por la solicitud o una <xref:System.Net.Sockets.SocketException> producida por la solicitud. Cuando complete todas las solicitudes, la aplicación recorre en iteración la `HostRequest` objetos y muestra la información de DNS o <xref:System.Net.Sockets.SocketException> mensaje de error.  
  
 [!code-csharp[AsyncDesignPattern#5](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/AsyncDelegateWithStateObject.cs#5)]
 [!code-vb[AsyncDesignPattern#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/AsyncDelegateWithStateObject.vb#5)]  
  
## <a name="see-also"></a>Vea también  
 [Modelo asincrónico basado en eventos (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [Event-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md) (Información general sobre el modelo asincrónico basado en eventos)  
 [Utilizar un delegado AsyncCallback para finalizar una operación asincrónica](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md)
