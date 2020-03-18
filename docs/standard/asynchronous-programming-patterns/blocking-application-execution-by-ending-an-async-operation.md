---
title: Bloquear la ejecución de una aplicación al finalizar una operación asincrónica
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- blocks, asynchronous operations
- AsyncWaitHandle property
- asynchronous programming, blocking applications
- blocking application execution
ms.assetid: cc5e2834-a65b-4df8-b750-7bdb79997fee
dev_langs:
- csharp
- vb
ms.openlocfilehash: aed3b18c154d4b7a4390b28fb1f14536690f6b3a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73121328"
---
# <a name="blocking-application-execution-by-ending-an-async-operation"></a><span data-ttu-id="45844-102">Bloquear la ejecución de una aplicación al finalizar una operación asincrónica</span><span class="sxs-lookup"><span data-stu-id="45844-102">Blocking Application Execution by Ending an Async Operation</span></span>
<span data-ttu-id="45844-103">Las aplicaciones que no pueden seguir realizando otro trabajo mientras esperan los resultados de una operación asincrónica se deben bloquear hasta que se complete la operación.</span><span class="sxs-lookup"><span data-stu-id="45844-103">Applications that cannot continue to do other work while waiting for the results of an asynchronous operation must block until the operation completes.</span></span> <span data-ttu-id="45844-104">Use una de las opciones siguientes para bloquear el subproceso principal de la aplicación mientras se espera a que se complete una operación asincrónica:</span><span class="sxs-lookup"><span data-stu-id="45844-104">Use one of the following options to block your application's main thread while waiting for an asynchronous operation to complete:</span></span>  
  
- <span data-ttu-id="45844-105">Llame al método **End**_NombreDeLaOperación_ para operaciones asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="45844-105">Call the asynchronous operations **End**_OperationName_ method.</span></span> <span data-ttu-id="45844-106">Este método se muestra en este tema.</span><span class="sxs-lookup"><span data-stu-id="45844-106">This approach is demonstrated in this topic.</span></span>  
  
- <span data-ttu-id="45844-107">Use la propiedad <xref:System.IAsyncResult.AsyncWaitHandle%2A> de la interfaz <xref:System.IAsyncResult> devuelta por el método **Begin**_OperationName_ de la operación asincrónica.</span><span class="sxs-lookup"><span data-stu-id="45844-107">Use the <xref:System.IAsyncResult.AsyncWaitHandle%2A> property of the <xref:System.IAsyncResult> returned by the asynchronous operation's **Begin**_OperationName_ method.</span></span> <span data-ttu-id="45844-108">Para ver un ejemplo que ilustre este método, consulte [Bloquear la ejecución de una aplicación mediante AsyncWaitHandle](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md).</span><span class="sxs-lookup"><span data-stu-id="45844-108">For an example that demonstrates this approach, see [Blocking Application Execution Using an AsyncWaitHandle](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md).</span></span>  
  
 <span data-ttu-id="45844-109">Las aplicaciones que usan el método **End**_NombreDeLaOperación_ para el bloqueo hasta que se completa una operación asincrónica normalmente llamarán al método **Begin**_NombreDeLaOperación_, realizarán cualquier trabajo que se pueda realizar sin los resultados de la operación y luego llamarán a **End**_NombreDeLaOperación_.</span><span class="sxs-lookup"><span data-stu-id="45844-109">Applications that use the **End**_OperationName_ method to block until an asynchronous operation is complete will typically call the **Begin**_OperationName_ method, perform any work that can be done without the results of the operation, and then call **End**_OperationName_.</span></span>  
  
## <a name="example"></a><span data-ttu-id="45844-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="45844-110">Example</span></span>  
 <span data-ttu-id="45844-111">En el ejemplo de código siguiente se explica cómo utilizar los métodos asincrónicos en la clase <xref:System.Net.Dns> para recuperar información del sistema de nombres de dominio de un equipo especificado por el usuario.</span><span class="sxs-lookup"><span data-stu-id="45844-111">The following code example demonstrates using asynchronous methods in the <xref:System.Net.Dns> class to retrieve Domain Name System information for a user-specified computer.</span></span> <span data-ttu-id="45844-112">Tenga en cuenta que `null` (`Nothing` en Visual Basic) se pasa para los parámetros <xref:System.Net.Dns.BeginGetHostByName%2A>`requestCallback` y `stateObject`, porque estos argumentos no son necesarios cuando se usa este método.</span><span class="sxs-lookup"><span data-stu-id="45844-112">Note that `null` (`Nothing` in Visual Basic) is passed for the <xref:System.Net.Dns.BeginGetHostByName%2A>`requestCallback` and `stateObject` parameters because these arguments are not required when using this approach.</span></span>  
  
 [!code-csharp[AsyncDesignPattern#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_EndBlock.cs#1)]
 [!code-vb[AsyncDesignPattern#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_EndBlock.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="45844-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="45844-113">See also</span></span>

- [<span data-ttu-id="45844-114">Modelo asincrónico basado en eventos (EAP)</span><span class="sxs-lookup"><span data-stu-id="45844-114">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)
- <span data-ttu-id="45844-115">[Event-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md) (Información general sobre el modelo asincrónico basado en eventos)</span><span class="sxs-lookup"><span data-stu-id="45844-115">[Event-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)</span></span>
