---
title: Registro de devoluciones de llamada como solicitudes de cancelación
ms.date: 08/14/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cancellation, how to register callbacks
ms.assetid: 8838dd75-18ed-4b8b-b322-cd4531faac64
ms.openlocfilehash: faa8dada5779f6eaee7a60e6210ec604f5fb4680
ms.sourcegitcommit: cbb19e56d48cf88375d35d0c27554d4722761e0d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2020
ms.locfileid: "88608455"
---
# <a name="register-callbacks-for-cancellation-requests"></a><span data-ttu-id="d4b4e-102">Registro de devoluciones de llamada como solicitudes de cancelación</span><span class="sxs-lookup"><span data-stu-id="d4b4e-102">Register callbacks for cancellation requests</span></span>

<span data-ttu-id="d4b4e-103">Obtenga información sobre cómo registrar un delegado que se invocará cuando una propiedad <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> se convierta en "true".</span><span class="sxs-lookup"><span data-stu-id="d4b4e-103">Learn how to register a delegate that will be invoked when a <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> property becomes true.</span></span> <span data-ttu-id="d4b4e-104">El valor cambia de "false" a "true" cuando se realiza una llamada a <xref:System.Threading.CancellationTokenSource.Cancel%2A> en el objeto que creó el token.</span><span class="sxs-lookup"><span data-stu-id="d4b4e-104">The value changes from false to true when a call to <xref:System.Threading.CancellationTokenSource.Cancel%2A> on the object that created the token is made.</span></span> <span data-ttu-id="d4b4e-105">Use esta técnica para cancelar operaciones asincrónicas que no admiten el marco de cancelación unificado de forma nativa, y para desbloquear métodos que podrían estar esperando que una operación asincrónica finalice.</span><span class="sxs-lookup"><span data-stu-id="d4b4e-105">Use this technique for canceling asynchronous operations that do not natively support the unified cancellation framework, and for unblocking methods that might be waiting for an asynchronous operation to finish.</span></span>

> [!NOTE]
> <span data-ttu-id="d4b4e-106">Cuando está habilitada la opción "Solo mi código", en algunos casos, Visual Studio se interrumpe en la línea que produce la excepción y muestra el mensaje de error "Excepción no controlada por el código de usuario".</span><span class="sxs-lookup"><span data-stu-id="d4b4e-106">When "Just My Code" is enabled, Visual Studio in some cases will break on the line that throws the exception and display an error message that says "exception not handled by user code."</span></span> <span data-ttu-id="d4b4e-107">Este error es benigno.</span><span class="sxs-lookup"><span data-stu-id="d4b4e-107">This error is benign.</span></span> <span data-ttu-id="d4b4e-108">Puede presionar <kbd>F5</kbd> para continuar y ver el comportamiento de control de excepciones que se muestra en estos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="d4b4e-108">You can press <kbd>F5</kbd> to continue from it, and see the exception-handling behavior that is demonstrated in the examples below.</span></span> <span data-ttu-id="d4b4e-109">Para evitar que Visual Studio se interrumpa con el primer error, desactive la casilla "Solo mi código" en **Herramientas, Opciones, Depurar, General**.</span><span class="sxs-lookup"><span data-stu-id="d4b4e-109">To prevent Visual Studio from breaking on the first error, just uncheck the "Just My Code" checkbox under **Tools, Options, Debugging, General**.</span></span>

## <a name="example"></a><span data-ttu-id="d4b4e-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d4b4e-110">Example</span></span>

<span data-ttu-id="d4b4e-111">En el ejemplo siguiente, el método <xref:System.Net.WebClient.CancelAsync%2A> se registra como el método que se invocará cuando se solicite la cancelación mediante el token de cancelación.</span><span class="sxs-lookup"><span data-stu-id="d4b4e-111">In the following example, the <xref:System.Net.WebClient.CancelAsync%2A> method is registered as the method to be invoked when cancellation is requested through the cancellation token.</span></span>

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.cancellation.callback/cs/howtoexample1.cs":::
:::code language="vb" source="../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.cancellation.callback/vb/howtoexample1.vb":::

<span data-ttu-id="d4b4e-112">Si ya ha solicitado la cancelación al registrar la devolución de llamada, aún se garantiza que se llamará a la devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="d4b4e-112">If cancellation has already been requested when the callback is registered, the callback is still guaranteed to be called.</span></span> <span data-ttu-id="d4b4e-113">En este caso, el método <xref:System.Net.WebClient.CancelAsync%2A> no hará nada si no hay ninguna operación asincrónica en curso, por lo que siempre es seguro llamar al método.</span><span class="sxs-lookup"><span data-stu-id="d4b4e-113">In this particular case, the <xref:System.Net.WebClient.CancelAsync%2A> method will do nothing if no asynchronous operation is in progress, so it is always safe to call the method.</span></span>

## <a name="see-also"></a><span data-ttu-id="d4b4e-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d4b4e-114">See also</span></span>

- [<span data-ttu-id="d4b4e-115">Cancelación de subprocesos administrados</span><span class="sxs-lookup"><span data-stu-id="d4b4e-115">Cancellation in managed threads</span></span>](cancellation-in-managed-threads.md)
- <xref:System.Net.WebClient.DownloadStringTaskAsync(System.String)?displayProperty=nameWithType>
