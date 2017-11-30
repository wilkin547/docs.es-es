---
title: Destruir subprocesos
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
- destroying threads
- threading [.NET Framework], destroying threads
ms.assetid: df54e648-c5d1-47c9-bd29-8e4438c1db6d
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4a41dce5db707d0be49c283256de665d316e1a1f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="destroying-threads"></a><span data-ttu-id="795fa-102">Destruir subprocesos</span><span class="sxs-lookup"><span data-stu-id="795fa-102">Destroying Threads</span></span>
<span data-ttu-id="795fa-103">El <xref:System.Threading.Thread.Abort%2A> método se utiliza para detener un subproceso administrado de forma permanente.</span><span class="sxs-lookup"><span data-stu-id="795fa-103">The <xref:System.Threading.Thread.Abort%2A> method is used to stop a managed thread permanently.</span></span> <span data-ttu-id="795fa-104">Cuando se llama a <xref:System.Threading.Thread.Abort%2A>, common language runtime produce una <xref:System.Threading.ThreadAbortException> en el subproceso de destino, que puede detectar el subproceso de destino.</span><span class="sxs-lookup"><span data-stu-id="795fa-104">When you call <xref:System.Threading.Thread.Abort%2A>, the common language runtime throws a <xref:System.Threading.ThreadAbortException> in the target thread, which the target thread can catch.</span></span> <span data-ttu-id="795fa-105">Para obtener más información, consulta <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="795fa-105">For more information, see <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="795fa-106">Si se está ejecutando un subproceso no administrado código, cuando su <xref:System.Threading.Thread.Abort%2A> se llama al método, el tiempo de ejecución lo marca <xref:System.Threading.ThreadState.AbortRequested?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="795fa-106">If a thread is executing unmanaged code when its <xref:System.Threading.Thread.Abort%2A> method is called, the runtime marks it <xref:System.Threading.ThreadState.AbortRequested?displayProperty=nameWithType>.</span></span> <span data-ttu-id="795fa-107">La excepción se produce cuando el subproceso vuelve al código administrado.</span><span class="sxs-lookup"><span data-stu-id="795fa-107">The exception is thrown when the thread returns to managed code.</span></span>  
  
 <span data-ttu-id="795fa-108">Una vez que se anula un subproceso, no se puede reiniciar.</span><span class="sxs-lookup"><span data-stu-id="795fa-108">Once a thread is aborted, it cannot be restarted.</span></span>  
  
 <span data-ttu-id="795fa-109">El <xref:System.Threading.Thread.Abort%2A> método no hace que el subproceso se anule inmediatamente, porque el subproceso de destino puede detectar la <xref:System.Threading.ThreadAbortException> y ejecutar cantidades arbitrarias de código en un `finally` bloque.</span><span class="sxs-lookup"><span data-stu-id="795fa-109">The <xref:System.Threading.Thread.Abort%2A> method does not cause the thread to abort immediately, because the target thread can catch the <xref:System.Threading.ThreadAbortException> and execute arbitrary amounts of code in a `finally` block.</span></span> <span data-ttu-id="795fa-110">Puede llamar a <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> si tiene que esperar hasta que haya finalizado el subproceso.</span><span class="sxs-lookup"><span data-stu-id="795fa-110">You can call <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> if you need to wait until the thread has ended.</span></span> <span data-ttu-id="795fa-111"><xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType>es una llamada de bloqueo que no vuelve hasta que el subproceso se ha detenido realmente o ha transcurrido un intervalo de tiempo de espera opcional.</span><span class="sxs-lookup"><span data-stu-id="795fa-111"><xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> is a blocking call that does not return until the thread has actually stopped executing or an optional timeout interval has elapsed.</span></span> <span data-ttu-id="795fa-112">El subproceso anulado podría llamar a la <xref:System.Threading.Thread.ResetAbort%2A> método o llevar a cabo el procesamiento sin enlazar en una `finally` bloquear, por lo que si no especifica un tiempo de espera, no se garantiza que la espera para finalizar.</span><span class="sxs-lookup"><span data-stu-id="795fa-112">The aborted thread could call the <xref:System.Threading.Thread.ResetAbort%2A> method or perform unbounded processing in a `finally` block, so if you do not specify a timeout, the wait is not guaranteed to end.</span></span>  
  
 <span data-ttu-id="795fa-113">Subprocesos que están esperando en una llamada a la <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> método puede interrumpirse por otros subprocesos que llaman a <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="795fa-113">Threads that are waiting on a call to the <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> method can be interrupted by other threads that call <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType>.</span></span>  
  
## <a name="handling-threadabortexception"></a><span data-ttu-id="795fa-114">Controlar ThreadAbortException</span><span class="sxs-lookup"><span data-stu-id="795fa-114">Handling ThreadAbortException</span></span>  
 <span data-ttu-id="795fa-115">Si espera que el subproceso anulado, ya sea como resultado de llamar al método <xref:System.Threading.Thread.Abort%2A> desde su propio código o como resultado de descargar un dominio de aplicación en el que está ejecutando el subproceso (<xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> utiliza <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> para finalizar subprocesos), debe controlar el subproceso el <xref:System.Threading.ThreadAbortException> y realizar cualquier procesamiento final en un `finally` cláusula, tal como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="795fa-115">If you expect your thread to be aborted, either as a result of calling <xref:System.Threading.Thread.Abort%2A> from your own code or as a result of unloading an application domain in which the thread is running (<xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> uses <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> to terminate threads), your thread must handle the <xref:System.Threading.ThreadAbortException> and perform any final processing in a `finally` clause, as shown in the following code.</span></span>  
  
```vb  
Try  
    ' Code that is executing when the thread is aborted.  
Catch ex As ThreadAbortException  
    ' Clean-up code can go here.  
    ' If there is no Finally clause, ThreadAbortException is  
    ' re-thrown by the system at the end of the Catch clause.   
Finally  
    ' Clean-up code can go here.  
End Try  
' Do not put clean-up code here, because the exception   
' is rethrown at the end of the Finally clause.  
```  
  
```csharp  
try   
{  
    // Code that is executing when the thread is aborted.  
}   
catch (ThreadAbortException ex)   
{  
    // Clean-up code can go here.  
    // If there is no Finally clause, ThreadAbortException is  
    // re-thrown by the system at the end of the Catch clause.   
}  
// Do not put clean-up code here, because the exception   
// is rethrown at the end of the Finally clause.  
```  
  
 <span data-ttu-id="795fa-116">El código de limpieza debe estar en el `catch` cláusula o la `finally` cláusula, porque un <xref:System.Threading.ThreadAbortException> se vuelve a iniciar el sistema al final de la `finally` cláusula, o al final de la `catch` cláusula si no hay ningún `finally` cláusula.</span><span class="sxs-lookup"><span data-stu-id="795fa-116">Your clean-up code must be in the `catch` clause or the `finally` clause, because a <xref:System.Threading.ThreadAbortException> is rethrown by the system at the end of the `finally` clause, or at the end of the `catch` clause if there is no `finally` clause.</span></span>  
  
 <span data-ttu-id="795fa-117">Puede impedir que el sistema de vuelva a iniciar la excepción mediante una llamada a la <xref:System.Threading.Thread.ResetAbort%2A?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="795fa-117">You can prevent the system from rethrowing the exception by calling the <xref:System.Threading.Thread.ResetAbort%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="795fa-118">Sin embargo, debe hacerlo los solo si su propio código que provocó la <xref:System.Threading.ThreadAbortException>.</span><span class="sxs-lookup"><span data-stu-id="795fa-118">However, you should do this only if your own code caused the <xref:System.Threading.ThreadAbortException>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="795fa-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="795fa-119">See Also</span></span>  
 <xref:System.Threading.ThreadAbortException>  
 <xref:System.Threading.Thread>  
 [<span data-ttu-id="795fa-120">Usar subprocesos y subprocesamiento</span><span class="sxs-lookup"><span data-stu-id="795fa-120">Using Threads and Threading</span></span>](../../../docs/standard/threading/using-threads-and-threading.md)
