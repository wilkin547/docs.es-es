---
title: Sondear el estado de una operación asincrónica
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- asynchronous programming, status polling
- polling asynchronous operation status
- status information [.NET Framework], asynchronous operations
ms.assetid: b541af31-dacb-4e20-8847-1b1ff7c35363
ms.openlocfilehash: ff9cefc73adfe1ece1bf7545c75ccb6cc618e89f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73123960"
---
# <a name="polling-for-the-status-of-an-asynchronous-operation"></a><span data-ttu-id="ed9c0-102">Sondear el estado de una operación asincrónica</span><span class="sxs-lookup"><span data-stu-id="ed9c0-102">Polling for the Status of an Asynchronous Operation</span></span>
<span data-ttu-id="ed9c0-103">Las aplicaciones que pueden realizar otro trabajo mientras esperan los resultados de una operación asincrónica no deben bloquear la espera hasta que se complete la operación.</span><span class="sxs-lookup"><span data-stu-id="ed9c0-103">Applications that can do other work while waiting for the results of an asynchronous operation should not block waiting until the operation completes.</span></span> <span data-ttu-id="ed9c0-104">Use una de las siguientes opciones para continuar con la ejecución de instrucciones mientras espera a que la operación asincrónica se complete:</span><span class="sxs-lookup"><span data-stu-id="ed9c0-104">Use one of the following options to continue executing instructions while waiting for an asynchronous operation to complete:</span></span>  
  
- <span data-ttu-id="ed9c0-105">Use la propiedad <xref:System.IAsyncResult.IsCompleted%2A> de la interfaz <xref:System.IAsyncResult> devuelta por el método **Begin**_OperationName_ de la operación asincrónica para determinar si la operación se ha completado.</span><span class="sxs-lookup"><span data-stu-id="ed9c0-105">Use the <xref:System.IAsyncResult.IsCompleted%2A> property of the <xref:System.IAsyncResult> returned by the asynchronous operation's **Begin**_OperationName_ method to determine whether the operation has completed.</span></span> <span data-ttu-id="ed9c0-106">Este método se conoce como sondeo y se muestra en este tema.</span><span class="sxs-lookup"><span data-stu-id="ed9c0-106">This approach is known as polling and is demonstrated in this topic.</span></span>  
  
- <span data-ttu-id="ed9c0-107">Use un delegado <xref:System.AsyncCallback> para procesar los resultados de la operación asincrónica en un subproceso independiente.</span><span class="sxs-lookup"><span data-stu-id="ed9c0-107">Use an <xref:System.AsyncCallback> delegate to process the results of the asynchronous operation in a separate thread.</span></span> <span data-ttu-id="ed9c0-108">Para ver un ejemplo que muestre este enfoque, consulte [Utilizar un delegado AsyncCallback para finalizar una operación asincrónica](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).</span><span class="sxs-lookup"><span data-stu-id="ed9c0-108">For an example that demonstrates this approach, see [Using an AsyncCallback Delegate to End an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ed9c0-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ed9c0-109">Example</span></span>  
 <span data-ttu-id="ed9c0-110">En el ejemplo de código siguiente se explica cómo utilizar los métodos asincrónicos en la clase <xref:System.Net.Dns> para recuperar información del sistema de nombres de dominio de un equipo especificado por el usuario.</span><span class="sxs-lookup"><span data-stu-id="ed9c0-110">The following code example demonstrates using asynchronous methods in the <xref:System.Net.Dns> class to retrieve Domain Name System information for a user-specified computer.</span></span> <span data-ttu-id="ed9c0-111">En este ejemplo se inicia la operación asincrónica y, a continuación, se imprimen puntos (".") en la consola hasta que se completa la operación.</span><span class="sxs-lookup"><span data-stu-id="ed9c0-111">This example starts the asynchronous operation and then prints periods (".") at the console until the operation is complete.</span></span> <span data-ttu-id="ed9c0-112">Tenga en cuenta que **null** (**Nothing** en Visual Basic) se pasa para los parámetros <xref:System.Net.Dns.BeginGetHostByName%2A><xref:System.AsyncCallback> y <xref:System.Object>, porque estos argumentos no son necesarios cuando se usa este método.</span><span class="sxs-lookup"><span data-stu-id="ed9c0-112">Note that **null** (**Nothing** in Visual Basic) is passed for the <xref:System.Net.Dns.BeginGetHostByName%2A><xref:System.AsyncCallback> and <xref:System.Object> parameters because these arguments are not required when using this approach.</span></span>  
  
 [!code-csharp[AsyncDesignPattern#3](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_Poll.cs#3)]
 [!code-vb[AsyncDesignPattern#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_Poll.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="ed9c0-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="ed9c0-113">See also</span></span>

- [<span data-ttu-id="ed9c0-114">Modelo asincrónico basado en eventos (EAP)</span><span class="sxs-lookup"><span data-stu-id="ed9c0-114">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)
- <span data-ttu-id="ed9c0-115">[Event-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md) (Información general sobre el modelo asincrónico basado en eventos)</span><span class="sxs-lookup"><span data-stu-id="ed9c0-115">[Event-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)</span></span>
