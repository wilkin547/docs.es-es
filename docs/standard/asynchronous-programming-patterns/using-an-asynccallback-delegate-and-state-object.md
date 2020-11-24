---
title: Utilizar un delegado AsyncCallback y un objeto State
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- asynchronous programming, delegates
- AsyncCallback delegate, samples
- asynchronous programming, state objects
- IAsyncResult interface, samples
ms.assetid: e3e5475d-c5e9-43f0-928e-d18df8ca1f1d
ms.openlocfilehash: 0a33c852d822e7d25d14ab17324459ec005853f9
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94829147"
---
# <a name="using-an-asynccallback-delegate-and-state-object"></a>Utilizar un delegado AsyncCallback y un objeto State
Cuando se usa un delegado <xref:System.AsyncCallback> para procesar los resultados de la operación asincrónica en un subproceso independiente, puede usar un objeto de estados para pasar información entre las devoluciones de llamada y recuperar un resultado final. En este tema se explica dicha práctica mediante la ampliación del ejemplo de [Utilizar un delegado AsyncCallback para finalizar una operación asincrónica](using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se explica cómo utilizar los métodos asincrónicos en la clase <xref:System.Net.Dns> para recuperar información del sistema de nombres de dominio (DNS) de equipos especificados por el usuario. Este ejemplo define y utiliza la clase `HostRequest` para almacenar información de estado. Se crea un objeto `HostRequest` para cada nombre de equipo especificado por el usuario. Este objeto se pasa al método <xref:System.Net.Dns.BeginGetHostByName%2A>. Se llama al método `ProcessDnsInformation` cada vez que se completa una solicitud. El objeto `HostRequest` se recupera con la propiedad <xref:System.IAsyncResult.AsyncState%2A>. El método `ProcessDnsInformation` usa el objeto `HostRequest` para almacenar la clase <xref:System.Net.IPHostEntry> devuelta por la solicitud o una clase <xref:System.Net.Sockets.SocketException> generada por la solicitud. Cuando se completan todas las solicitudes, la aplicación realiza una iteración por los objetos `HostRequest` y muestra la información de DNS o el mensaje de error <xref:System.Net.Sockets.SocketException>.  
  
 [!code-csharp[AsyncDesignPattern#5](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/AsyncDelegateWithStateObject.cs#5)]
 [!code-vb[AsyncDesignPattern#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/AsyncDelegateWithStateObject.vb#5)]  
  
## <a name="see-also"></a>Vea también

- [Modelo asincrónico basado en eventos (EAP)](event-based-asynchronous-pattern-eap.md)
- [Event-based Asynchronous Pattern Overview](event-based-asynchronous-pattern-overview.md) (Información general sobre el modelo asincrónico basado en eventos)
- [Utilizar un delegado AsyncCallback para finalizar una operación asincrónica](using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md)
