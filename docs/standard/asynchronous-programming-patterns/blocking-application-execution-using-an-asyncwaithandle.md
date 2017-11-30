---
title: "Bloquear la ejecución de una aplicación mediante AsyncWaitHandle"
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
- blocks, asynchronous operations
- ending asynchronous operations
- asynchronous programming, ending operations
- asynchronous programming, blocking applications
- stopping asynchronous operations
- blocking application execution
ms.assetid: 3e32daf2-8161-4e8f-addd-9fd9ff101b03
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2660b3cbf7e8ee43a22edbfb66a4262684983b87
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="blocking-application-execution-using-an-asyncwaithandle"></a><span data-ttu-id="4de1f-102">Bloquear la ejecución de una aplicación mediante AsyncWaitHandle</span><span class="sxs-lookup"><span data-stu-id="4de1f-102">Blocking Application Execution Using an AsyncWaitHandle</span></span>
<span data-ttu-id="4de1f-103">Las aplicaciones que no pueden seguir realizando otro trabajo mientras esperan los resultados de una operación asincrónica se deben bloquear hasta que se complete la operación.</span><span class="sxs-lookup"><span data-stu-id="4de1f-103">Applications that cannot continue to do other work while waiting for the results of an asynchronous operation must block until the operation completes.</span></span> <span data-ttu-id="4de1f-104">Para bloquear el subproceso principal de la aplicación mientras se espera que se complete una operación asincrónica, use una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="4de1f-104">Use one of the following options to block your application's main thread while waiting for an asynchronous operation to complete:</span></span>  
  
-   <span data-ttu-id="4de1f-105">Use la <xref:System.IAsyncResult.AsyncWaitHandle%2A> propiedad de la <xref:System.IAsyncResult> devuelto por la operación asincrónica **comenzar** *OperationName* método.</span><span class="sxs-lookup"><span data-stu-id="4de1f-105">Use the <xref:System.IAsyncResult.AsyncWaitHandle%2A> property of the <xref:System.IAsyncResult> returned by the asynchronous operation's **Begin** *OperationName* method.</span></span> <span data-ttu-id="4de1f-106">Este enfoque se muestra en este tema.</span><span class="sxs-lookup"><span data-stu-id="4de1f-106">This approach is demonstrated in this topic.</span></span>  
  
-   <span data-ttu-id="4de1f-107">Llame a la operación asincrónica **final** *OperationName* método.</span><span class="sxs-lookup"><span data-stu-id="4de1f-107">Call the asynchronous operation's **End** *OperationName* method.</span></span> <span data-ttu-id="4de1f-108">Para obtener un ejemplo que muestra este enfoque, consulte [bloquear ejecución de la aplicación al finalizar una operación asincrónica](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-by-ending-an-async-operation.md).</span><span class="sxs-lookup"><span data-stu-id="4de1f-108">For an example that demonstrates this approach, see [Blocking Application Execution by Ending an Async Operation](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-by-ending-an-async-operation.md).</span></span>  
  
 <span data-ttu-id="4de1f-109">Las aplicaciones que utilizan uno o varios <xref:System.Threading.WaitHandle> objetos para bloquear hasta que se complete una operación asincrónica normalmente llamarán a la **comenzar** *OperationName* método, realizar ningún trabajo que se pueden realizar sin los resultados de la operación y, a continuación, se bloquean hasta que la operación asincrónica se complete.</span><span class="sxs-lookup"><span data-stu-id="4de1f-109">Applications that use one or more <xref:System.Threading.WaitHandle> objects to block until an asynchronous operation is complete will typically call the **Begin** *OperationName* method, perform any work that can be done without the results of the operation, and then block until the asynchronous operation(s) completes.</span></span> <span data-ttu-id="4de1f-110">Una aplicación puede bloquear en una sola operación mediante una llamada a uno de los <xref:System.Threading.WaitHandle.WaitOne%2A> métodos mediante el <xref:System.IAsyncResult.AsyncWaitHandle%2A>.</span><span class="sxs-lookup"><span data-stu-id="4de1f-110">An application can block on a single operation by calling one of the <xref:System.Threading.WaitHandle.WaitOne%2A> methods using the <xref:System.IAsyncResult.AsyncWaitHandle%2A>.</span></span> <span data-ttu-id="4de1f-111">Para bloquear mientras se espera un conjunto de operaciones asincrónicas que se complete, almacenar asociado <xref:System.IAsyncResult.AsyncWaitHandle%2A> objetos en una matriz y llame a uno de los <xref:System.Threading.WaitHandle.WaitAll%2A> métodos.</span><span class="sxs-lookup"><span data-stu-id="4de1f-111">To block while waiting for a set of asynchronous operations to complete, store the associated <xref:System.IAsyncResult.AsyncWaitHandle%2A> objects in an array and call one of the <xref:System.Threading.WaitHandle.WaitAll%2A> methods.</span></span> <span data-ttu-id="4de1f-112">Para bloquear mientras se espera uno de un conjunto de operaciones asincrónicas que se complete, almacenar asociado <xref:System.IAsyncResult.AsyncWaitHandle%2A> objetos en una matriz y llame a uno de los <xref:System.Threading.WaitHandle.WaitAny%2A> métodos.</span><span class="sxs-lookup"><span data-stu-id="4de1f-112">To block while waiting for any one of a set of asynchronous operations to complete, store the associated <xref:System.IAsyncResult.AsyncWaitHandle%2A> objects in an array and call one of the <xref:System.Threading.WaitHandle.WaitAny%2A> methods.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4de1f-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4de1f-113">Example</span></span>  
 <span data-ttu-id="4de1f-114">En el ejemplo de código siguiente se muestra cómo utilizar métodos asincrónicos en la clase DNS para recuperar información de sistema de nombres de dominio para un equipo especificado por el usuario.</span><span class="sxs-lookup"><span data-stu-id="4de1f-114">The following code example demonstrates using asynchronous methods in the DNS class to retrieve Domain Name System information for a user-specified computer.</span></span> <span data-ttu-id="4de1f-115">En el ejemplo se muestra el bloqueo utilizando el <xref:System.Threading.WaitHandle> asociado a la operación asincrónica.</span><span class="sxs-lookup"><span data-stu-id="4de1f-115">The example demonstrates blocking using the <xref:System.Threading.WaitHandle> associated with the asynchronous operation.</span></span> <span data-ttu-id="4de1f-116">Tenga en cuenta que `null` (`Nothing` en Visual Basic) se pasa para el <xref:System.Net.Dns.BeginGetHostByName%2A> `requestCallback` y `stateObject` parámetros ya no son necesarios cuando se usa este enfoque.</span><span class="sxs-lookup"><span data-stu-id="4de1f-116">Note that `null` (`Nothing` in Visual Basic) is passed for the <xref:System.Net.Dns.BeginGetHostByName%2A>`requestCallback` and `stateObject` parameters because these are not required when using this approach.</span></span>  
  
 [!code-csharp[AsyncDesignPattern#2](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_EndBlockWait.cs#2)]
 [!code-vb[AsyncDesignPattern#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_EndBlockWait.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="4de1f-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="4de1f-117">See Also</span></span>  
 [<span data-ttu-id="4de1f-118">Modelo asincrónico basado en eventos (EAP)</span><span class="sxs-lookup"><span data-stu-id="4de1f-118">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 <span data-ttu-id="4de1f-119">[Event-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md) (Información general sobre el modelo asincrónico basado en eventos)</span><span class="sxs-lookup"><span data-stu-id="4de1f-119">[Event-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)</span></span>
