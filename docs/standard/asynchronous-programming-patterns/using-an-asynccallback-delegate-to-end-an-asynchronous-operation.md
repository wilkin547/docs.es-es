---
title: "Utilizar un delegado AsyncCallback para finalizar una operación asincrónica"
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
- ending asynchronous operations
- asynchronous programming, ending operations
- AsyncCallback delegate
- stopping asynchronous operations
ms.assetid: 9d97206c-8917-406c-8961-7d0909d84eeb
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bbe170588776daa97fec4c736d4b1bdd871de518
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="using-an-asynccallback-delegate-to-end-an-asynchronous-operation"></a><span data-ttu-id="0d807-102">Utilizar un delegado AsyncCallback para finalizar una operación asincrónica</span><span class="sxs-lookup"><span data-stu-id="0d807-102">Using an AsyncCallback Delegate to End an Asynchronous Operation</span></span>
<span data-ttu-id="0d807-103">Las aplicaciones que pueden hacer otro trabajo mientras esperan los resultados de una operación asincrónica no deberían bloquear la espera hasta que se complete la operación.</span><span class="sxs-lookup"><span data-stu-id="0d807-103">Applications that can do other work while waiting for the results of an asynchronous operation should not block waiting until the operation completes.</span></span> <span data-ttu-id="0d807-104">Use una de las siguientes opciones para seguir ejecutando instrucciones mientras se espera que se complete una operación asincrónica:</span><span class="sxs-lookup"><span data-stu-id="0d807-104">Use one of the following options to continue executing instructions while waiting for an asynchronous operation to complete:</span></span>  
  
-   <span data-ttu-id="0d807-105">Use un <xref:System.AsyncCallback> delegado para procesar los resultados de la operación asincrónica en un subproceso independiente.</span><span class="sxs-lookup"><span data-stu-id="0d807-105">Use an <xref:System.AsyncCallback> delegate to process the results of the asynchronous operation in a separate thread.</span></span> <span data-ttu-id="0d807-106">Este enfoque se muestra en este tema.</span><span class="sxs-lookup"><span data-stu-id="0d807-106">This approach is demonstrated in this topic.</span></span>  
  
-   <span data-ttu-id="0d807-107">Use la <xref:System.IAsyncResult.IsCompleted%2A> propiedad de la <xref:System.IAsyncResult> devuelto por la operación asincrónica **comenzar** *OperationName* método para determinar si se ha completado la operación.</span><span class="sxs-lookup"><span data-stu-id="0d807-107">Use the <xref:System.IAsyncResult.IsCompleted%2A> property of the <xref:System.IAsyncResult> returned by the asynchronous operation's **Begin** *OperationName* method to determine whether the operation has completed.</span></span> <span data-ttu-id="0d807-108">Para obtener un ejemplo que muestra este enfoque, consulte [sondear el estado de una operación asincrónica](../../../docs/standard/asynchronous-programming-patterns/polling-for-the-status-of-an-asynchronous-operation.md).</span><span class="sxs-lookup"><span data-stu-id="0d807-108">For an example that demonstrates this approach, see [Polling for the Status of an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/polling-for-the-status-of-an-asynchronous-operation.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d807-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0d807-109">Example</span></span>  
 <span data-ttu-id="0d807-110">En el ejemplo de código siguiente se muestra cómo utilizar los métodos asincrónicos en el <xref:System.Net.Dns> clase para recuperar información de sistema de nombres de dominio (DNS) para equipos especificados por el usuario.</span><span class="sxs-lookup"><span data-stu-id="0d807-110">The following code example demonstrates using asynchronous methods in the <xref:System.Net.Dns> class to retrieve Domain Name System (DNS) information for user-specified computers.</span></span> <span data-ttu-id="0d807-111">Este ejemplo se crea un <xref:System.AsyncCallback> delegado que hace referencia el `ProcessDnsInformation` método.</span><span class="sxs-lookup"><span data-stu-id="0d807-111">This example creates an <xref:System.AsyncCallback> delegate that references the `ProcessDnsInformation` method.</span></span> <span data-ttu-id="0d807-112">Este método se llama una vez por cada solicitud asincrónica para obtener información de DNS.</span><span class="sxs-lookup"><span data-stu-id="0d807-112">This method is called once for each asynchronous request for DNS information.</span></span>  
  
 <span data-ttu-id="0d807-113">Tenga en cuenta que el host especificado por el usuario se pasa a la <xref:System.Net.Dns.BeginGetHostByName%2A> <xref:System.Object> parámetro.</span><span class="sxs-lookup"><span data-stu-id="0d807-113">Note that the user-specified host is passed to the <xref:System.Net.Dns.BeginGetHostByName%2A><xref:System.Object> parameter.</span></span> <span data-ttu-id="0d807-114">Para obtener un ejemplo que muestra cómo definir y utilizar un objeto de estado más complejo, consulte [mediante un delegado AsyncCallback y un objeto de estado](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-and-state-object.md).</span><span class="sxs-lookup"><span data-stu-id="0d807-114">For an example that demonstrates defining and using a more complex state object, see [Using an AsyncCallback Delegate and State Object](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-and-state-object.md).</span></span>  
  
 [!code-csharp[AsyncDesignPattern#4](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/AsyncDelegateNoStateObject.cs#4)]
 [!code-vb[AsyncDesignPattern#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/AsyncDelegateNoState.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="0d807-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="0d807-115">See Also</span></span>  
 [<span data-ttu-id="0d807-116">Modelo asincrónico basado en eventos (EAP)</span><span class="sxs-lookup"><span data-stu-id="0d807-116">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 <span data-ttu-id="0d807-117">[Event-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md) (Información general sobre el modelo asincrónico basado en eventos)</span><span class="sxs-lookup"><span data-stu-id="0d807-117">[Event-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)</span></span>  
 [<span data-ttu-id="0d807-118">Llamar a métodos asincrónicos mediante IAsyncResult</span><span class="sxs-lookup"><span data-stu-id="0d807-118">Calling Asynchronous Methods Using IAsyncResult</span></span>](../../../docs/standard/asynchronous-programming-patterns/calling-asynchronous-methods-using-iasyncresult.md)  
 [<span data-ttu-id="0d807-119">Utilizar un delegado AsyncCallback y un objeto State</span><span class="sxs-lookup"><span data-stu-id="0d807-119">Using an AsyncCallback Delegate and State Object</span></span>](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-and-state-object.md)
