---
title: "Bloquear la ejecución de una aplicación al finalizar una operación asincrónica"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- blocks, asynchronous operations
- AsyncWaitHandle property
- asynchronous programming, blocking applications
- blocking application execution
ms.assetid: cc5e2834-a65b-4df8-b750-7bdb79997fee
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
dev_langs:
- csharp
- vb
ms.openlocfilehash: ccca6e1e4f6b5cdf098018b59426fb2262e2b346
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="blocking-application-execution-by-ending-an-async-operation"></a><span data-ttu-id="37a15-102">Bloquear la ejecución de una aplicación al finalizar una operación asincrónica</span><span class="sxs-lookup"><span data-stu-id="37a15-102">Blocking Application Execution by Ending an Async Operation</span></span>
<span data-ttu-id="37a15-103">Las aplicaciones que no pueden seguir realizando otro trabajo mientras esperan los resultados de una operación asincrónica se deben bloquear hasta que se complete la operación.</span><span class="sxs-lookup"><span data-stu-id="37a15-103">Applications that cannot continue to do other work while waiting for the results of an asynchronous operation must block until the operation completes.</span></span> <span data-ttu-id="37a15-104">Para bloquear el subproceso principal de la aplicación mientras se espera que se complete una operación asincrónica, use una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="37a15-104">Use one of the following options to block your application's main thread while waiting for an asynchronous operation to complete:</span></span>  
  
-   <span data-ttu-id="37a15-105">Llamar a las operaciones asincrónicas **final** *OperationName* método.</span><span class="sxs-lookup"><span data-stu-id="37a15-105">Call the asynchronous operations **End** *OperationName* method.</span></span> <span data-ttu-id="37a15-106">Este enfoque se muestra en este tema.</span><span class="sxs-lookup"><span data-stu-id="37a15-106">This approach is demonstrated in this topic.</span></span>  
  
-   <span data-ttu-id="37a15-107">Use la <xref:System.IAsyncResult.AsyncWaitHandle%2A> propiedad de la <xref:System.IAsyncResult> devuelto por la operación asincrónica **comenzar** *OperationName* método.</span><span class="sxs-lookup"><span data-stu-id="37a15-107">Use the <xref:System.IAsyncResult.AsyncWaitHandle%2A> property of the <xref:System.IAsyncResult> returned by the asynchronous operation's **Begin** *OperationName* method.</span></span> <span data-ttu-id="37a15-108">Para obtener un ejemplo que muestra este enfoque, consulte [bloqueo de aplicación de ejecución mediante un AsyncWaitHandle](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md).</span><span class="sxs-lookup"><span data-stu-id="37a15-108">For an example that demonstrates this approach, see [Blocking Application Execution Using an AsyncWaitHandle](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md).</span></span>  
  
 <span data-ttu-id="37a15-109">Las aplicaciones que utilizan el **final** *OperationName* método para bloquear hasta que se complete una operación asincrónica normalmente llamará el **comenzar**  *OperationName* método, realizar ningún trabajo que se puede realizar sin los resultados de la operación y, a continuación, llame a **final** *OperationName*.</span><span class="sxs-lookup"><span data-stu-id="37a15-109">Applications that use the **End** *OperationName* method to block until an asynchronous operation is complete will typically call the **Begin** *OperationName* method, perform any work that can be done without the results of the operation, and then call **End** *OperationName*.</span></span>  
  
## <a name="example"></a><span data-ttu-id="37a15-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="37a15-110">Example</span></span>  
 <span data-ttu-id="37a15-111">En el ejemplo de código siguiente se muestra cómo utilizar los métodos asincrónicos en el <xref:System.Net.Dns> clase para recuperar información de sistema de nombres de dominio para un equipo especificado por el usuario.</span><span class="sxs-lookup"><span data-stu-id="37a15-111">The following code example demonstrates using asynchronous methods in the <xref:System.Net.Dns> class to retrieve Domain Name System information for a user-specified computer.</span></span> <span data-ttu-id="37a15-112">Tenga en cuenta que `null` (`Nothing` en Visual Basic) se pasa para el <xref:System.Net.Dns.BeginGetHostByName%2A> `requestCallback` y `stateObject` parámetros porque estos argumentos no son necesarios cuando se usa este enfoque.</span><span class="sxs-lookup"><span data-stu-id="37a15-112">Note that `null` (`Nothing` in Visual Basic) is passed for the <xref:System.Net.Dns.BeginGetHostByName%2A>`requestCallback` and `stateObject` parameters because these arguments are not required when using this approach.</span></span>  
  
 [!code-csharp[AsyncDesignPattern#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_EndBlock.cs#1)]
 [!code-vb[AsyncDesignPattern#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_EndBlock.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="37a15-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="37a15-113">See Also</span></span>  
 [<span data-ttu-id="37a15-114">Modelo asincrónico basado en eventos (EAP)</span><span class="sxs-lookup"><span data-stu-id="37a15-114">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 <span data-ttu-id="37a15-115">[Event-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md) (Información general sobre el modelo asincrónico basado en eventos)</span><span class="sxs-lookup"><span data-stu-id="37a15-115">[Event-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)</span></span>
