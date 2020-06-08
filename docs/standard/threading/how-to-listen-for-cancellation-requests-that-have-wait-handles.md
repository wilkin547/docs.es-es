---
title: 'Cómo: Realizar escuchas de solicitudes de cancelación cuando tienen controladores de espera'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cancellation, waiting with wait handles
ms.assetid: 6e2aa49b-fc84-4bcf-962b-17db98b7edcb
ms.openlocfilehash: e44b10b88bef61edcf3f547f56b4020740530e26
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84279548"
---
# <a name="how-to-listen-for-cancellation-requests-that-have-wait-handles"></a><span data-ttu-id="2ff0f-102">Cómo: Realizar escuchas de solicitudes de cancelación cuando tienen controladores de espera</span><span class="sxs-lookup"><span data-stu-id="2ff0f-102">How to: Listen for Cancellation Requests That Have Wait Handles</span></span>
<span data-ttu-id="2ff0f-103">Si un método se bloquea mientras está en espera para que se señalice un evento, no se puede comprobar el valor del token de cancelación ni responder de manera oportuna.</span><span class="sxs-lookup"><span data-stu-id="2ff0f-103">If a method is blocked while it is waiting for an event to be signaled, it cannot check the value of the cancellation token and respond in a timely manner.</span></span> <span data-ttu-id="2ff0f-104">El primer ejemplo muestra cómo resolver este problema cuando se trabaja con eventos como <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> que no admiten de forma nativa el marco de cancelación unificada.</span><span class="sxs-lookup"><span data-stu-id="2ff0f-104">The first example shows how to solve this problem when you are working with events such as <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> that do not natively support the unified cancellation framework.</span></span> <span data-ttu-id="2ff0f-105">El segundo ejemplo muestra un enfoque más sencillo que utiliza <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>, que es compatible con la cancelación unificada.</span><span class="sxs-lookup"><span data-stu-id="2ff0f-105">The second example shows a more streamlined approach that uses <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>, which does support unified cancellation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2ff0f-106">Cuando está habilitada la opción "Solo mi código", en algunos casos, Visual Studio se interrumpe en la línea que produce la excepción y muestra el mensaje de error "Excepción no controlada por el código de usuario".</span><span class="sxs-lookup"><span data-stu-id="2ff0f-106">When "Just My Code" is enabled, Visual Studio in some cases will break on the line that throws the exception and display an error message that says "exception not handled by user code."</span></span> <span data-ttu-id="2ff0f-107">Este error es benigno.</span><span class="sxs-lookup"><span data-stu-id="2ff0f-107">This error is benign.</span></span> <span data-ttu-id="2ff0f-108">Puede presionar F5 para continuar y ver el comportamiento de control de excepciones que se muestra en estos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="2ff0f-108">You can press F5 to continue from it, and see the exception-handling behavior that is demonstrated in the examples below.</span></span> <span data-ttu-id="2ff0f-109">Para evitar que Visual Studio se interrumpa con el primer error, desactive la casilla "Solo mi código" en **Herramientas, Opciones, Depurar, General**.</span><span class="sxs-lookup"><span data-stu-id="2ff0f-109">To prevent Visual Studio from breaking on the first error, just uncheck the "Just My Code" checkbox under **Tools, Options, Debugging, General**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ff0f-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2ff0f-110">Example</span></span>  
 <span data-ttu-id="2ff0f-111">En el ejemplo siguiente se usa <xref:System.Threading.ManualResetEvent> para mostrar cómo desbloquear identificadores de espera que no admiten la cancelación unificada.</span><span class="sxs-lookup"><span data-stu-id="2ff0f-111">The following example uses a <xref:System.Threading.ManualResetEvent> to demonstrate how to unblock wait handles that do not support unified cancellation.</span></span>  
  
 [!code-csharp[Cancellation#9](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex9.cs#9)]
 [!code-vb[Cancellation#9](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex9.vb#9)]  
  
## <a name="example"></a><span data-ttu-id="2ff0f-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2ff0f-112">Example</span></span>  
 <span data-ttu-id="2ff0f-113">En el ejemplo siguiente se usa <xref:System.Threading.ManualResetEventSlim> para mostrar cómo desbloquear primitivos de coordinación que no admiten la cancelación unificada.</span><span class="sxs-lookup"><span data-stu-id="2ff0f-113">The following example uses a <xref:System.Threading.ManualResetEventSlim> to demonstrate how to unblock coordination primitives that do support unified cancellation.</span></span> <span data-ttu-id="2ff0f-114">Puede utilizarse el mismo enfoque con otros primitivos de coordinación ligeros, como <xref:System.Threading.Semaphore>`Slim` y <xref:System.Threading.CountdownEvent>.</span><span class="sxs-lookup"><span data-stu-id="2ff0f-114">The same approach can be used with other lightweight coordination primitives, such as <xref:System.Threading.Semaphore>`Slim` and <xref:System.Threading.CountdownEvent>.</span></span>  
  
 [!code-csharp[Cancellation#10](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex10.cs#10)]
 [!code-vb[Cancellation#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex10.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="2ff0f-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="2ff0f-115">See also</span></span>

- [<span data-ttu-id="2ff0f-116">Cancelación en subprocesos administrados</span><span class="sxs-lookup"><span data-stu-id="2ff0f-116">Cancellation in Managed Threads</span></span>](cancellation-in-managed-threads.md)
