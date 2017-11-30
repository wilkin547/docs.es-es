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
# <a name="using-an-asynccallback-delegate-and-state-object"></a><span data-ttu-id="1853d-102">Utilizar un delegado AsyncCallback y un objeto State</span><span class="sxs-lookup"><span data-stu-id="1853d-102">Using an AsyncCallback Delegate and State Object</span></span>
<span data-ttu-id="1853d-103">Cuando se usa un <xref:System.AsyncCallback> delegado para procesar los resultados de la operación asincrónica en un subproceso independiente, puede usar un objeto de estado para pasar información entre las devoluciones de llamada y recuperar un resultado final.</span><span class="sxs-lookup"><span data-stu-id="1853d-103">When you use an <xref:System.AsyncCallback> delegate to process the results of the asynchronous operation in a separate thread, you can use a state object to pass information between the callbacks and to retrieve a final result.</span></span> <span data-ttu-id="1853d-104">Este tema muestra este procedimiento mediante la expansión en el ejemplo de [utilizar un delegado AsyncCallback para finalizar una operación asincrónica](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).</span><span class="sxs-lookup"><span data-stu-id="1853d-104">This topic demonstrates that practice by expanding the example in [Using an AsyncCallback Delegate to End an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1853d-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1853d-105">Example</span></span>  
 <span data-ttu-id="1853d-106">En el ejemplo de código siguiente se muestra cómo utilizar los métodos asincrónicos en el <xref:System.Net.Dns> clase para recuperar información de sistema de nombres de dominio (DNS) para equipos especificados por el usuario.</span><span class="sxs-lookup"><span data-stu-id="1853d-106">The following code example demonstrates using asynchronous methods in the <xref:System.Net.Dns> class to retrieve Domain Name System (DNS) information for user-specified computers.</span></span> <span data-ttu-id="1853d-107">Este ejemplo define y utiliza la `HostRequest` clase para almacenar información de estado.</span><span class="sxs-lookup"><span data-stu-id="1853d-107">This example defines and uses the `HostRequest` class to store state information.</span></span> <span data-ttu-id="1853d-108">Un `HostRequest` objeto se crea para cada nombre de equipo especificado por el usuario.</span><span class="sxs-lookup"><span data-stu-id="1853d-108">A `HostRequest` object gets created for each computer name entered by the user.</span></span> <span data-ttu-id="1853d-109">Este objeto se pasa a la <xref:System.Net.Dns.BeginGetHostByName%2A> método.</span><span class="sxs-lookup"><span data-stu-id="1853d-109">This object is passed to the <xref:System.Net.Dns.BeginGetHostByName%2A> method.</span></span> <span data-ttu-id="1853d-110">El `ProcessDnsInformation` método se llama cada vez que se completa una solicitud.</span><span class="sxs-lookup"><span data-stu-id="1853d-110">The `ProcessDnsInformation` method is called each time a request completes.</span></span> <span data-ttu-id="1853d-111">El `HostRequest` objeto se recupera utilizando la <xref:System.IAsyncResult.AsyncState%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="1853d-111">The `HostRequest` object is retrieved using the <xref:System.IAsyncResult.AsyncState%2A> property.</span></span> <span data-ttu-id="1853d-112">El `ProcessDnsInformation` método usa la `HostRequest` objeto para almacenar el <xref:System.Net.IPHostEntry> devuelto por la solicitud o una <xref:System.Net.Sockets.SocketException> producida por la solicitud.</span><span class="sxs-lookup"><span data-stu-id="1853d-112">The `ProcessDnsInformation` method uses the `HostRequest` object to store the <xref:System.Net.IPHostEntry> returned by the request or a <xref:System.Net.Sockets.SocketException> thrown by the request.</span></span> <span data-ttu-id="1853d-113">Cuando complete todas las solicitudes, la aplicación recorre en iteración la `HostRequest` objetos y muestra la información de DNS o <xref:System.Net.Sockets.SocketException> mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="1853d-113">When all requests are complete, the application iterates over the `HostRequest` objects and displays the DNS information or <xref:System.Net.Sockets.SocketException> error message.</span></span>  
  
 [!code-csharp[AsyncDesignPattern#5](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/AsyncDelegateWithStateObject.cs#5)]
 [!code-vb[AsyncDesignPattern#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/AsyncDelegateWithStateObject.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="1853d-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="1853d-114">See Also</span></span>  
 [<span data-ttu-id="1853d-115">Modelo asincrónico basado en eventos (EAP)</span><span class="sxs-lookup"><span data-stu-id="1853d-115">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 <span data-ttu-id="1853d-116">[Event-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md) (Información general sobre el modelo asincrónico basado en eventos)</span><span class="sxs-lookup"><span data-stu-id="1853d-116">[Event-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)</span></span>  
 [<span data-ttu-id="1853d-117">Utilizar un delegado AsyncCallback para finalizar una operación asincrónica</span><span class="sxs-lookup"><span data-stu-id="1853d-117">Using an AsyncCallback Delegate to End an Asynchronous Operation</span></span>](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md)
