---
title: "Sondear el estado de una operación asincrónica"
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
- asynchronous programming, status polling
- polling asynchronous operation status
- status information [.NET Framework], asynchronous operations
ms.assetid: b541af31-dacb-4e20-8847-1b1ff7c35363
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e1f7f74a8b38c06f6a042d55c0def76ddfc5da77
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="polling-for-the-status-of-an-asynchronous-operation"></a><span data-ttu-id="c9d7a-102">Sondear el estado de una operación asincrónica</span><span class="sxs-lookup"><span data-stu-id="c9d7a-102">Polling for the Status of an Asynchronous Operation</span></span>
<span data-ttu-id="c9d7a-103">Las aplicaciones que pueden hacer otro trabajo mientras esperan los resultados de una operación asincrónica no deberían bloquear la espera hasta que se complete la operación.</span><span class="sxs-lookup"><span data-stu-id="c9d7a-103">Applications that can do other work while waiting for the results of an asynchronous operation should not block waiting until the operation completes.</span></span> <span data-ttu-id="c9d7a-104">Use una de las siguientes opciones para seguir ejecutando instrucciones mientras se espera que se complete una operación asincrónica:</span><span class="sxs-lookup"><span data-stu-id="c9d7a-104">Use one of the following options to continue executing instructions while waiting for an asynchronous operation to complete:</span></span>  
  
-   <span data-ttu-id="c9d7a-105">Use la <xref:System.IAsyncResult.IsCompleted%2A> propiedad de la <xref:System.IAsyncResult> devuelto por la operación asincrónica **comenzar** *OperationName* método para determinar si se ha completado la operación.</span><span class="sxs-lookup"><span data-stu-id="c9d7a-105">Use the <xref:System.IAsyncResult.IsCompleted%2A> property of the <xref:System.IAsyncResult> returned by the asynchronous operation's **Begin** *OperationName* method to determine whether the operation has completed.</span></span> <span data-ttu-id="c9d7a-106">Este enfoque se conoce como sondeo y se muestra en este tema.</span><span class="sxs-lookup"><span data-stu-id="c9d7a-106">This approach is known as polling and is demonstrated in this topic.</span></span>  
  
-   <span data-ttu-id="c9d7a-107">Use un <xref:System.AsyncCallback> delegado para procesar los resultados de la operación asincrónica en un subproceso independiente.</span><span class="sxs-lookup"><span data-stu-id="c9d7a-107">Use an <xref:System.AsyncCallback> delegate to process the results of the asynchronous operation in a separate thread.</span></span> <span data-ttu-id="c9d7a-108">Para obtener un ejemplo que muestra este enfoque, consulte [utilizar un delegado AsyncCallback para finalizar una operación asincrónica](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).</span><span class="sxs-lookup"><span data-stu-id="c9d7a-108">For an example that demonstrates this approach, see [Using an AsyncCallback Delegate to End an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c9d7a-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c9d7a-109">Example</span></span>  
 <span data-ttu-id="c9d7a-110">En el ejemplo de código siguiente se muestra cómo utilizar los métodos asincrónicos en el <xref:System.Net.Dns> clase para recuperar información de sistema de nombres de dominio para un equipo especificado por el usuario.</span><span class="sxs-lookup"><span data-stu-id="c9d7a-110">The following code example demonstrates using asynchronous methods in the <xref:System.Net.Dns> class to retrieve Domain Name System information for a user-specified computer.</span></span> <span data-ttu-id="c9d7a-111">En este ejemplo se inicia la operación asincrónica y, a continuación, imprime puntos (".") en la consola hasta que se complete la operación.</span><span class="sxs-lookup"><span data-stu-id="c9d7a-111">This example starts the asynchronous operation and then prints periods (".") at the console until the operation is complete.</span></span> <span data-ttu-id="c9d7a-112">Tenga en cuenta que **null** (**nada** en Visual Basic) se pasa para el <xref:System.Net.Dns.BeginGetHostByName%2A> <xref:System.AsyncCallback> y <xref:System.Object> parámetros porque estos argumentos no son necesarios cuando se usa este enfoque.</span><span class="sxs-lookup"><span data-stu-id="c9d7a-112">Note that **null** (**Nothing** in Visual Basic) is passed for the <xref:System.Net.Dns.BeginGetHostByName%2A><xref:System.AsyncCallback> and <xref:System.Object> parameters because these arguments are not required when using this approach.</span></span>  
  
 [!code-csharp[AsyncDesignPattern#3](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_Poll.cs#3)]
 [!code-vb[AsyncDesignPattern#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_Poll.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="c9d7a-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="c9d7a-113">See Also</span></span>  
 [<span data-ttu-id="c9d7a-114">Modelo asincrónico basado en eventos (EAP)</span><span class="sxs-lookup"><span data-stu-id="c9d7a-114">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 <span data-ttu-id="c9d7a-115">[Event-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md) (Información general sobre el modelo asincrónico basado en eventos)</span><span class="sxs-lookup"><span data-stu-id="c9d7a-115">[Event-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)</span></span>
