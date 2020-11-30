---
title: Utilizar un delegado AsyncCallback para finalizar una operación asincrónica
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ending asynchronous operations
- asynchronous programming, ending operations
- AsyncCallback delegate
- stopping asynchronous operations
ms.assetid: 9d97206c-8917-406c-8961-7d0909d84eeb
ms.openlocfilehash: 1da6bd95c79b25b5bbf6674cf7e9ef48d19cb708
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677965"
---
# <a name="using-an-asynccallback-delegate-to-end-an-asynchronous-operation"></a><span data-ttu-id="63d49-102">Utilizar un delegado AsyncCallback para finalizar una operación asincrónica</span><span class="sxs-lookup"><span data-stu-id="63d49-102">Using an AsyncCallback Delegate to End an Asynchronous Operation</span></span>

<span data-ttu-id="63d49-103">Las aplicaciones que pueden realizar otro trabajo mientras esperan los resultados de una operación asincrónica no deben bloquear la espera hasta que se complete la operación.</span><span class="sxs-lookup"><span data-stu-id="63d49-103">Applications that can do other work while waiting for the results of an asynchronous operation should not block waiting until the operation completes.</span></span> <span data-ttu-id="63d49-104">Use una de las siguientes opciones para continuar con la ejecución de instrucciones mientras espera a que la operación asincrónica se complete:</span><span class="sxs-lookup"><span data-stu-id="63d49-104">Use one of the following options to continue executing instructions while waiting for an asynchronous operation to complete:</span></span>  
  
- <span data-ttu-id="63d49-105">Use un delegado <xref:System.AsyncCallback> para procesar los resultados de la operación asincrónica en un subproceso independiente.</span><span class="sxs-lookup"><span data-stu-id="63d49-105">Use an <xref:System.AsyncCallback> delegate to process the results of the asynchronous operation in a separate thread.</span></span> <span data-ttu-id="63d49-106">Este método se muestra en este tema.</span><span class="sxs-lookup"><span data-stu-id="63d49-106">This approach is demonstrated in this topic.</span></span>  
  
- <span data-ttu-id="63d49-107">Use la propiedad <xref:System.IAsyncResult.IsCompleted%2A> de la interfaz <xref:System.IAsyncResult> devuelta por el método **Begin**_OperationName_ de la operación asincrónica para determinar si la operación se ha completado.</span><span class="sxs-lookup"><span data-stu-id="63d49-107">Use the <xref:System.IAsyncResult.IsCompleted%2A> property of the <xref:System.IAsyncResult> returned by the asynchronous operation's **Begin**_OperationName_ method to determine whether the operation has completed.</span></span> <span data-ttu-id="63d49-108">Para ver un ejemplo que muestre este enfoque, consulte [Sondear el estado de una operación asincrónica](polling-for-the-status-of-an-asynchronous-operation.md).</span><span class="sxs-lookup"><span data-stu-id="63d49-108">For an example that demonstrates this approach, see [Polling for the Status of an Asynchronous Operation](polling-for-the-status-of-an-asynchronous-operation.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="63d49-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="63d49-109">Example</span></span>  

 <span data-ttu-id="63d49-110">En el ejemplo de código siguiente se explica cómo utilizar los métodos asincrónicos en la clase <xref:System.Net.Dns> para recuperar información del sistema de nombres de dominio (DNS) de equipos especificados por el usuario.</span><span class="sxs-lookup"><span data-stu-id="63d49-110">The following code example demonstrates using asynchronous methods in the <xref:System.Net.Dns> class to retrieve Domain Name System (DNS) information for user-specified computers.</span></span> <span data-ttu-id="63d49-111">En este ejemplo se crea un delegado <xref:System.AsyncCallback> que hace referencia al método `ProcessDnsInformation`.</span><span class="sxs-lookup"><span data-stu-id="63d49-111">This example creates an <xref:System.AsyncCallback> delegate that references the `ProcessDnsInformation` method.</span></span> <span data-ttu-id="63d49-112">Se llama a este método una vez por cada solicitud asincrónica de información de DNS.</span><span class="sxs-lookup"><span data-stu-id="63d49-112">This method is called once for each asynchronous request for DNS information.</span></span>  
  
 <span data-ttu-id="63d49-113">Tenga en cuenta que el host especificado por el usuario se pasa al parámetro <xref:System.Net.Dns.BeginGetHostByName%2A><xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="63d49-113">Note that the user-specified host is passed to the <xref:System.Net.Dns.BeginGetHostByName%2A><xref:System.Object> parameter.</span></span> <span data-ttu-id="63d49-114">Para obtener un ejemplo que muestra cómo definir y usar un objeto state más complejo, vea [Utilizar un delegado AsyncCallback y un objeto State](using-an-asynccallback-delegate-and-state-object.md).</span><span class="sxs-lookup"><span data-stu-id="63d49-114">For an example that demonstrates defining and using a more complex state object, see [Using an AsyncCallback Delegate and State Object](using-an-asynccallback-delegate-and-state-object.md).</span></span>  
  
 [!code-csharp[AsyncDesignPattern#4](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/AsyncDelegateNoStateObject.cs#4)]
 [!code-vb[AsyncDesignPattern#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/AsyncDelegateNoState.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="63d49-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="63d49-115">See also</span></span>

- [<span data-ttu-id="63d49-116">Modelo asincrónico basado en eventos (EAP)</span><span class="sxs-lookup"><span data-stu-id="63d49-116">Event-based Asynchronous Pattern (EAP)</span></span>](event-based-asynchronous-pattern-eap.md)
- <span data-ttu-id="63d49-117">[Event-based Asynchronous Pattern Overview](event-based-asynchronous-pattern-overview.md) (Información general sobre el modelo asincrónico basado en eventos)</span><span class="sxs-lookup"><span data-stu-id="63d49-117">[Event-based Asynchronous Pattern Overview](event-based-asynchronous-pattern-overview.md)</span></span>
- [<span data-ttu-id="63d49-118">Llamar a métodos asincrónicos mediante IAsyncResult</span><span class="sxs-lookup"><span data-stu-id="63d49-118">Calling Asynchronous Methods Using IAsyncResult</span></span>](calling-asynchronous-methods-using-iasyncresult.md)
- [<span data-ttu-id="63d49-119">Utilizar un delegado AsyncCallback y un objeto State</span><span class="sxs-lookup"><span data-stu-id="63d49-119">Using an AsyncCallback Delegate and State Object</span></span>](using-an-asynccallback-delegate-and-state-object.md)
