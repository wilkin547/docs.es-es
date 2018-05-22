---
title: Temporizadores
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [.NET Framework], timers
- timers, about timers
ms.assetid: 7091500d-be18-499b-a942-95366ce185e5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 478484651bf839f842148f0b4164c9387db3b98a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="timers"></a><span data-ttu-id="78361-102">Temporizadores</span><span class="sxs-lookup"><span data-stu-id="78361-102">Timers</span></span>
<span data-ttu-id="78361-103">Los temporizadores son objetos pequeños que permiten especificar un delegado para llamarlo en un momento específico.</span><span class="sxs-lookup"><span data-stu-id="78361-103">Timers are lightweight objects that enable you to specify a delegate to be called at a specified time.</span></span> <span data-ttu-id="78361-104">Un subproceso del grupo realiza la operación de espera.</span><span class="sxs-lookup"><span data-stu-id="78361-104">A thread in the thread pool performs the wait operation.</span></span>  
  
 <span data-ttu-id="78361-105">El uso de la clase <xref:System.Threading.Timer?displayProperty=nameWithType> es sencillo.</span><span class="sxs-lookup"><span data-stu-id="78361-105">Using the <xref:System.Threading.Timer?displayProperty=nameWithType> class is straightforward.</span></span> <span data-ttu-id="78361-106">Para crear un **Timer**, debe pasar un delegado <xref:System.Threading.TimerCallback> al método de devolución de llamada, un objeto que representa el estado que se pasará a la devolución de llamada, la hora de compilación inicial y una cifra que representa el período entre invocaciones de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="78361-106">You create a **Timer**, passing a <xref:System.Threading.TimerCallback> delegate to the callback method, an object representing state that will be passed to the callback, an initial raise time, and a time representing the period between callback invocations.</span></span> <span data-ttu-id="78361-107">Para cancelar un temporizador pendiente, se debe llamar a la función **Timer.Dispose**.</span><span class="sxs-lookup"><span data-stu-id="78361-107">To cancel a pending timer, call the **Timer.Dispose** function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="78361-108">Hay otras dos clases de temporizador.</span><span class="sxs-lookup"><span data-stu-id="78361-108">There are two other timer classes.</span></span> <span data-ttu-id="78361-109">La clase <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> es un control que funciona con diseñadores visuales y está pensado para su uso en contextos de interfaz de usuario; provoca eventos en el subproceso de interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="78361-109">The <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> class is a control that works with visual designers and is meant to be used in user interface contexts; it raises events on the user interface thread.</span></span> <span data-ttu-id="78361-110">La clase <xref:System.Timers.Timer?displayProperty=nameWithType> deriva de <xref:System.ComponentModel.Component>, por lo que puede usarse con diseñadores visuales; también provoca eventos, pero lo hace en un subproceso <xref:System.Threading.ThreadPool>.</span><span class="sxs-lookup"><span data-stu-id="78361-110">The <xref:System.Timers.Timer?displayProperty=nameWithType> class derives from <xref:System.ComponentModel.Component>, so it can be used with visual designers; it also raises events, but it raises them on a <xref:System.Threading.ThreadPool> thread.</span></span> <span data-ttu-id="78361-111">La clase <xref:System.Threading.Timer?displayProperty=nameWithType> realiza las devoluciones de llamada en un subproceso <xref:System.Threading.ThreadPool> y no utiliza el modelo de evento para nada.</span><span class="sxs-lookup"><span data-stu-id="78361-111">The <xref:System.Threading.Timer?displayProperty=nameWithType> class makes callbacks on a <xref:System.Threading.ThreadPool> thread and does not use the event model at all.</span></span> <span data-ttu-id="78361-112">También proporciona un objeto de estado al método de devolución de llamada, lo que no hacen otros temporizadores.</span><span class="sxs-lookup"><span data-stu-id="78361-112">It also provides a state object to the callback method, which the other timers do not.</span></span> <span data-ttu-id="78361-113">Es sumamente ligero.</span><span class="sxs-lookup"><span data-stu-id="78361-113">It is extremely lightweight.</span></span>  
  
 <span data-ttu-id="78361-114">El ejemplo de código siguiente inicia un temporizador que se inicia después de un segundo (1000 milisegundos) y emite un chasquido por segundo hasta que presione la tecla **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="78361-114">The following code example starts a timer that starts after one second (1000 milliseconds) and ticks every second until you press the **Enter** key.</span></span> <span data-ttu-id="78361-115">La variable que contiene la referencia al temporizador es un campo de nivel de clase para garantizar que el temporizador no está sujeto a la recolección de elementos no utilizados mientras que todavía está en ejecución.</span><span class="sxs-lookup"><span data-stu-id="78361-115">The variable containing the reference to the timer is a class-level field, to ensure that the timer is not subject to garbage collection while it is still running.</span></span> <span data-ttu-id="78361-116">Para obtener más información acerca de la recolección de elementos no utilizados agresiva, vea <xref:System.GC.KeepAlive%2A>.</span><span class="sxs-lookup"><span data-stu-id="78361-116">For more information on aggressive garbage collection, see <xref:System.GC.KeepAlive%2A>.</span></span>  
  
 [!code-cpp[System.Threading.Timer#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.Timer/CPP/source2.cpp#2)]
 [!code-csharp[System.Threading.Timer#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.Timer/CS/source2.cs#2)]
 [!code-vb[System.Threading.Timer#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.Timer/VB/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="78361-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="78361-117">See Also</span></span>  
 <xref:System.Threading.Timer>  
 [<span data-ttu-id="78361-118">Objetos y características de subprocesos</span><span class="sxs-lookup"><span data-stu-id="78361-118">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)
