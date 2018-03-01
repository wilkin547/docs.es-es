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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
dev_langs:
- csharp
- vb
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 3ec7bfe6fe2cef20a6d74030802113a47e8679e1
ms.sourcegitcommit: 957c696f25e39f923a827fc3ad5e8ab72768838c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2018
---
# <a name="blocking-application-execution-by-ending-an-async-operation"></a><span data-ttu-id="aff68-102">Bloquear la ejecución de una aplicación al finalizar una operación asincrónica</span><span class="sxs-lookup"><span data-stu-id="aff68-102">Blocking Application Execution by Ending an Async Operation</span></span>
<span data-ttu-id="aff68-103">Las aplicaciones que no pueden seguir realizando otro trabajo mientras esperan los resultados de una operación asincrónica se deben bloquear hasta que se complete la operación.</span><span class="sxs-lookup"><span data-stu-id="aff68-103">Applications that cannot continue to do other work while waiting for the results of an asynchronous operation must block until the operation completes.</span></span> <span data-ttu-id="aff68-104">Use una de las opciones siguientes para bloquear el subproceso principal de la aplicación mientras se espera a que se complete una operación asincrónica:</span><span class="sxs-lookup"><span data-stu-id="aff68-104">Use one of the following options to block your application's main thread while waiting for an asynchronous operation to complete:</span></span>  
  
-   <span data-ttu-id="aff68-105">Llamar al método **End***OperationName* para operaciones asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="aff68-105">Call the asynchronous operations **End***OperationName* method.</span></span> <span data-ttu-id="aff68-106">Este método se muestra en este tema.</span><span class="sxs-lookup"><span data-stu-id="aff68-106">This approach is demonstrated in this topic.</span></span>  
  
-   <span data-ttu-id="aff68-107">Use la propiedad <xref:System.IAsyncResult.AsyncWaitHandle%2A> de la interfaz <xref:System.IAsyncResult> devuelta por el método **Begin***OperationName* de la operación asincrónica.</span><span class="sxs-lookup"><span data-stu-id="aff68-107">Use the <xref:System.IAsyncResult.AsyncWaitHandle%2A> property of the <xref:System.IAsyncResult> returned by the asynchronous operation's **Begin***OperationName* method.</span></span> <span data-ttu-id="aff68-108">Para ver un ejemplo que ilustre este método, consulte [Bloquear la ejecución de una aplicación mediante AsyncWaitHandle](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md).</span><span class="sxs-lookup"><span data-stu-id="aff68-108">For an example that demonstrates this approach, see [Blocking Application Execution Using an AsyncWaitHandle](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md).</span></span>  
  
 <span data-ttu-id="aff68-109">Las aplicaciones que utilizan el método **End***OperationName* para el bloqueo hasta que se completa una operación asincrónica normalmente llamarán al método **Begin***OperationName*, realizarán cualquier trabajo que se pueda realizar sin los resultados de la operación y luego llamarán a **End***OperationName*.</span><span class="sxs-lookup"><span data-stu-id="aff68-109">Applications that use the **End***OperationName* method to block until an asynchronous operation is complete will typically call the **Begin***OperationName* method, perform any work that can be done without the results of the operation, and then call **End***OperationName*.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aff68-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="aff68-110">Example</span></span>  
 <span data-ttu-id="aff68-111">En el ejemplo de código siguiente se explica cómo utilizar los métodos asincrónicos en la clase <xref:System.Net.Dns> para recuperar información del sistema de nombres de dominio de un equipo especificado por el usuario.</span><span class="sxs-lookup"><span data-stu-id="aff68-111">The following code example demonstrates using asynchronous methods in the <xref:System.Net.Dns> class to retrieve Domain Name System information for a user-specified computer.</span></span> <span data-ttu-id="aff68-112">Tenga en cuenta que `null` (`Nothing` en Visual Basic) se pasa para los parámetros <xref:System.Net.Dns.BeginGetHostByName%2A>`requestCallback` y `stateObject`, porque estos argumentos no son necesarios cuando se usa este método.</span><span class="sxs-lookup"><span data-stu-id="aff68-112">Note that `null` (`Nothing` in Visual Basic) is passed for the <xref:System.Net.Dns.BeginGetHostByName%2A>`requestCallback` and `stateObject` parameters because these arguments are not required when using this approach.</span></span>  
  
 [!code-csharp[AsyncDesignPattern#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_EndBlock.cs#1)]
 [!code-vb[AsyncDesignPattern#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_EndBlock.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="aff68-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="aff68-113">See Also</span></span>  
 [<span data-ttu-id="aff68-114">Modelo asincrónico basado en eventos (EAP)</span><span class="sxs-lookup"><span data-stu-id="aff68-114">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [<span data-ttu-id="aff68-115">Información general sobre el modelo asincrónico basado en eventos</span><span class="sxs-lookup"><span data-stu-id="aff68-115">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
