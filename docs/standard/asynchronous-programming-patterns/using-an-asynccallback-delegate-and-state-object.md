---
title: Utilizar un delegado AsyncCallback y un objeto State
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- asynchronous programming, delegates
- AsyncCallback delegate, samples
- asynchronous programming, state objects
- IAsyncResult interface, samples
ms.assetid: e3e5475d-c5e9-43f0-928e-d18df8ca1f1d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 259f7de52dff04af043554382a5bad35355d9926
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="using-an-asynccallback-delegate-and-state-object"></a><span data-ttu-id="774b0-102">Utilizar un delegado AsyncCallback y un objeto State</span><span class="sxs-lookup"><span data-stu-id="774b0-102">Using an AsyncCallback Delegate and State Object</span></span>
<span data-ttu-id="774b0-103">Cuando se usa un delegado <xref:System.AsyncCallback> para procesar los resultados de la operación asincrónica en un subproceso independiente, puede usar un objeto de estados para pasar información entre las devoluciones de llamada y recuperar un resultado final.</span><span class="sxs-lookup"><span data-stu-id="774b0-103">When you use an <xref:System.AsyncCallback> delegate to process the results of the asynchronous operation in a separate thread, you can use a state object to pass information between the callbacks and to retrieve a final result.</span></span> <span data-ttu-id="774b0-104">En este tema se explica dicha práctica mediante la ampliación del ejemplo de [Utilizar un delegado AsyncCallback para finalizar una operación asincrónica](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).</span><span class="sxs-lookup"><span data-stu-id="774b0-104">This topic demonstrates that practice by expanding the example in [Using an AsyncCallback Delegate to End an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="774b0-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="774b0-105">Example</span></span>  
 <span data-ttu-id="774b0-106">En el ejemplo de código siguiente se explica cómo utilizar los métodos asincrónicos en la clase <xref:System.Net.Dns> para recuperar información del sistema de nombres de dominio (DNS) de equipos especificados por el usuario.</span><span class="sxs-lookup"><span data-stu-id="774b0-106">The following code example demonstrates using asynchronous methods in the <xref:System.Net.Dns> class to retrieve Domain Name System (DNS) information for user-specified computers.</span></span> <span data-ttu-id="774b0-107">Este ejemplo define y utiliza la clase `HostRequest` para almacenar información de estado.</span><span class="sxs-lookup"><span data-stu-id="774b0-107">This example defines and uses the `HostRequest` class to store state information.</span></span> <span data-ttu-id="774b0-108">Se crea un objeto `HostRequest` para cada nombre de equipo especificado por el usuario.</span><span class="sxs-lookup"><span data-stu-id="774b0-108">A `HostRequest` object gets created for each computer name entered by the user.</span></span> <span data-ttu-id="774b0-109">Este objeto se pasa al método <xref:System.Net.Dns.BeginGetHostByName%2A>.</span><span class="sxs-lookup"><span data-stu-id="774b0-109">This object is passed to the <xref:System.Net.Dns.BeginGetHostByName%2A> method.</span></span> <span data-ttu-id="774b0-110">Se llama al método `ProcessDnsInformation` cada vez que se completa una solicitud.</span><span class="sxs-lookup"><span data-stu-id="774b0-110">The `ProcessDnsInformation` method is called each time a request completes.</span></span> <span data-ttu-id="774b0-111">El objeto `HostRequest` se recupera con la propiedad <xref:System.IAsyncResult.AsyncState%2A>.</span><span class="sxs-lookup"><span data-stu-id="774b0-111">The `HostRequest` object is retrieved using the <xref:System.IAsyncResult.AsyncState%2A> property.</span></span> <span data-ttu-id="774b0-112">El método `ProcessDnsInformation` usa el objeto `HostRequest` para almacenar la clase <xref:System.Net.IPHostEntry> devuelta por la solicitud o una clase <xref:System.Net.Sockets.SocketException> generada por la solicitud.</span><span class="sxs-lookup"><span data-stu-id="774b0-112">The `ProcessDnsInformation` method uses the `HostRequest` object to store the <xref:System.Net.IPHostEntry> returned by the request or a <xref:System.Net.Sockets.SocketException> thrown by the request.</span></span> <span data-ttu-id="774b0-113">Cuando se completan todas las solicitudes, la aplicación realiza una iteración por los objetos `HostRequest` y muestra la información de DNS o el mensaje de error <xref:System.Net.Sockets.SocketException>.</span><span class="sxs-lookup"><span data-stu-id="774b0-113">When all requests are complete, the application iterates over the `HostRequest` objects and displays the DNS information or <xref:System.Net.Sockets.SocketException> error message.</span></span>  
  
 [!code-csharp[AsyncDesignPattern#5](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/AsyncDelegateWithStateObject.cs#5)]
 [!code-vb[AsyncDesignPattern#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/AsyncDelegateWithStateObject.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="774b0-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="774b0-114">See Also</span></span>  
 [<span data-ttu-id="774b0-115">Modelo asincrónico basado en eventos (EAP)</span><span class="sxs-lookup"><span data-stu-id="774b0-115">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [<span data-ttu-id="774b0-116">Información general sobre el modelo asincrónico basado en eventos</span><span class="sxs-lookup"><span data-stu-id="774b0-116">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 [<span data-ttu-id="774b0-117">Utilizar un delegado AsyncCallback para finalizar una operación asincrónica</span><span class="sxs-lookup"><span data-stu-id="774b0-117">Using an AsyncCallback Delegate to End an Asynchronous Operation</span></span>](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md)
