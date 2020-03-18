---
title: 'Cómo: Registrar devoluciones de llamadas de solicitudes de cancelación'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cancellation, how to register callbacks
ms.assetid: 8838dd75-18ed-4b8b-b322-cd4531faac64
ms.openlocfilehash: 87ba1ab9ac095c733a53f766d00ebb7530a8d9c4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73137997"
---
# <a name="how-to-register-callbacks-for-cancellation-requests"></a><span data-ttu-id="af706-102">Cómo: Registrar devoluciones de llamadas de solicitudes de cancelación</span><span class="sxs-lookup"><span data-stu-id="af706-102">How to: Register Callbacks for Cancellation Requests</span></span>
<span data-ttu-id="af706-103">En el ejemplo siguiente se muestra cómo registrar un delegado que se invoca cuando una propiedad <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> pasa a ser true debido a una llamada a <xref:System.Threading.CancellationTokenSource.Cancel%2A> en el objeto que creó el token.</span><span class="sxs-lookup"><span data-stu-id="af706-103">The following example shows how to register a delegate that will be invoked when a <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> property becomes true due to a call to <xref:System.Threading.CancellationTokenSource.Cancel%2A> on the object that created the token.</span></span> <span data-ttu-id="af706-104">Use esta técnica para cancelar operaciones asincrónicas que no admiten el marco de cancelación unificado de forma nativa, y para desbloquear métodos que podrían estar esperando que una operación asincrónica finalice.</span><span class="sxs-lookup"><span data-stu-id="af706-104">Use this technique for cancelling asynchronous operations that do not natively support the unified cancellation framework, and for unblocking methods that might be waiting for an asynchronous operation to finish.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="af706-105">Cuando está habilitada la opción "Solo mi código", en algunos casos, Visual Studio se interrumpe en la línea que produce la excepción y muestra el mensaje de error "Excepción no controlada por el código de usuario".</span><span class="sxs-lookup"><span data-stu-id="af706-105">When "Just My Code" is enabled, Visual Studio in some cases will break on the line that throws the exception and display an error message that says "exception not handled by user code."</span></span> <span data-ttu-id="af706-106">Este error es benigno.</span><span class="sxs-lookup"><span data-stu-id="af706-106">This error is benign.</span></span> <span data-ttu-id="af706-107">Puede presionar F5 para continuar y ver el comportamiento de control de excepciones que se muestra en estos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="af706-107">You can press F5 to continue from it, and see the exception-handling behavior that is demonstrated in the examples below.</span></span> <span data-ttu-id="af706-108">Para evitar que Visual Studio se interrumpa con el primer error, desactive la casilla "Solo mi código" en **Herramientas, Opciones, Depurar, General**.</span><span class="sxs-lookup"><span data-stu-id="af706-108">To prevent Visual Studio from breaking on the first error, just uncheck the "Just My Code" checkbox under **Tools, Options, Debugging, General**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="af706-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="af706-109">Example</span></span>  
 <span data-ttu-id="af706-110">En el ejemplo siguiente, el método <xref:System.Net.WebClient.CancelAsync%2A> se registra como el método que se invocará cuando se solicite la cancelación mediante el token de cancelación.</span><span class="sxs-lookup"><span data-stu-id="af706-110">In the following example, the <xref:System.Net.WebClient.CancelAsync%2A> method is registered as the method to be invoked when cancellation is requested through the cancellation token.</span></span>  
  
 [!code-csharp[Conceptual.Cancellation.Callback#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.cancellation.callback/cs/howtoexample1.cs#1)]
 [!code-vb[Conceptual.Cancellation.Callback#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.cancellation.callback/vb/howtoexample1.vb#1)]  
  
 <span data-ttu-id="af706-111">Si ya ha solicitado la cancelación al registrar la devolución de llamada, aún se garantiza que se llamará a la devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="af706-111">If cancellation has already been requested when the callback is registered, the callback is still guaranteed to be called.</span></span> <span data-ttu-id="af706-112">En este caso, el método <xref:System.Net.WebClient.CancelAsync%2A> no hará nada si no hay ninguna operación asincrónica en curso, por lo que siempre es seguro llamar al método.</span><span class="sxs-lookup"><span data-stu-id="af706-112">In this particular case, the <xref:System.Net.WebClient.CancelAsync%2A> method will do nothing if no asynchronous operation is in progress, so it is always safe to call the method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af706-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="af706-113">See also</span></span>

- [<span data-ttu-id="af706-114">Cancelación en subprocesos administrados</span><span class="sxs-lookup"><span data-stu-id="af706-114">Cancellation in Managed Threads</span></span>](../../../docs/standard/threading/cancellation-in-managed-threads.md)
