---
title: Destrucción de subprocesos
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- destroying threads
- threading [.NET Framework], destroying threads
ms.assetid: df54e648-c5d1-47c9-bd29-8e4438c1db6d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5cd6e85dca7c4c32361b964573f318b165e8d683
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43385024"
---
# <a name="destroying-threads"></a><span data-ttu-id="f19e7-102">Destrucción de subprocesos</span><span class="sxs-lookup"><span data-stu-id="f19e7-102">Destroying threads</span></span>
<span data-ttu-id="f19e7-103">El método <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> se utiliza para detener un subproceso administrado de forma permanente.</span><span class="sxs-lookup"><span data-stu-id="f19e7-103">The <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> method is used to stop a managed thread permanently.</span></span> <span data-ttu-id="f19e7-104">Cuando se llama a <xref:System.Threading.Thread.Abort%2A>, Common Language Runtime produce una clase <xref:System.Threading.ThreadAbortException> en el subproceso de destino, que este último puede detectar.</span><span class="sxs-lookup"><span data-stu-id="f19e7-104">When you call <xref:System.Threading.Thread.Abort%2A>, the common language runtime throws a <xref:System.Threading.ThreadAbortException> in the target thread, which the target thread can catch.</span></span> <span data-ttu-id="f19e7-105">Para obtener más información, vea <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f19e7-105">For more information, see <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f19e7-106">Si un subproceso ejecuta código no administrado al llamar a su método <xref:System.Threading.Thread.Abort%2A>, el tiempo de ejecución lo marca como <xref:System.Threading.ThreadState.AbortRequested?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f19e7-106">If a thread is executing unmanaged code when its <xref:System.Threading.Thread.Abort%2A> method is called, the runtime marks it <xref:System.Threading.ThreadState.AbortRequested?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f19e7-107">La excepción se produce cuando el subproceso vuelve al código administrado.</span><span class="sxs-lookup"><span data-stu-id="f19e7-107">The exception is thrown when the thread returns to managed code.</span></span>  
  
 <span data-ttu-id="f19e7-108">Una vez que se anula un subproceso, no se puede reiniciar.</span><span class="sxs-lookup"><span data-stu-id="f19e7-108">Once a thread is aborted, it cannot be restarted.</span></span>  
  
 <span data-ttu-id="f19e7-109">El método <xref:System.Threading.Thread.Abort%2A> no hace que el subproceso se anule inmediatamente, porque el subproceso de destino puede detectar <xref:System.Threading.ThreadAbortException> y ejecutar cantidades arbitrarias de código en un bloque `finally`.</span><span class="sxs-lookup"><span data-stu-id="f19e7-109">The <xref:System.Threading.Thread.Abort%2A> method does not cause the thread to abort immediately, because the target thread can catch the <xref:System.Threading.ThreadAbortException> and execute arbitrary amounts of code in a `finally` block.</span></span> <span data-ttu-id="f19e7-110">Puede llamar a <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> si tiene que esperar hasta que haya finalizado el subproceso.</span><span class="sxs-lookup"><span data-stu-id="f19e7-110">You can call <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> if you need to wait until the thread has ended.</span></span> <span data-ttu-id="f19e7-111"><xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> es una llamada de bloqueo que no realiza ninguna devolución hasta que el subproceso se haya dejado de ejecutar realmente o hasta que haya transcurrido un intervalo de tiempo de espera opcional.</span><span class="sxs-lookup"><span data-stu-id="f19e7-111"><xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> is a blocking call that does not return until the thread has actually stopped executing or an optional timeout interval has elapsed.</span></span> <span data-ttu-id="f19e7-112">El subproceso anulado podría llamar al método <xref:System.Threading.Thread.ResetAbort%2A> o llevar a cabo el procesamiento sin enlazar en un bloqueo `finally`, por lo que si no especifica un tiempo de espera, no se garantiza que la espera finalice.</span><span class="sxs-lookup"><span data-stu-id="f19e7-112">The aborted thread could call the <xref:System.Threading.Thread.ResetAbort%2A> method or perform unbounded processing in a `finally` block, so if you do not specify a timeout, the wait is not guaranteed to end.</span></span>  
  
 <span data-ttu-id="f19e7-113">Los subprocesos que esperan una llamada al método <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> pueden interrumpirse con otros subprocesos que llaman a <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f19e7-113">Threads that are waiting on a call to the <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> method can be interrupted by other threads that call <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType>.</span></span>  
  
## <a name="handling-threadabortexception"></a><span data-ttu-id="f19e7-114">Control de ThreadAbortException</span><span class="sxs-lookup"><span data-stu-id="f19e7-114">Handling ThreadAbortException</span></span>  
 <span data-ttu-id="f19e7-115">Si espera que se anule el subproceso, como resultado de una llamada a <xref:System.Threading.Thread.Abort%2A> desde su propio código o como resultado de la descarga de un dominio de aplicación en que se ejecuta el subproceso (<xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> usa <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> para terminar los subprocesos), el subproceso debe controlar <xref:System.Threading.ThreadAbortException> y realizar cualquier procesamiento final en una cláusula `finally`, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="f19e7-115">If you expect your thread to be aborted, either as a result of calling <xref:System.Threading.Thread.Abort%2A> from your own code or as a result of unloading an application domain in which the thread is running (<xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> uses <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> to terminate threads), your thread must handle the <xref:System.Threading.ThreadAbortException> and perform any final processing in a `finally` clause, as shown in the following code.</span></span>  
  
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
  
 <span data-ttu-id="f19e7-116">El código de limpieza debe estar en la cláusula `catch` o en la cláusula `finally`, porque el sistema vuelve a generar <xref:System.Threading.ThreadAbortException> al final de la cláusula `finally` o al final de la cláusula `catch` si no existe la cláusula `finally`.</span><span class="sxs-lookup"><span data-stu-id="f19e7-116">Your clean-up code must be in the `catch` clause or the `finally` clause, because a <xref:System.Threading.ThreadAbortException> is rethrown by the system at the end of the `finally` clause, or at the end of the `catch` clause if there is no `finally` clause.</span></span>  
  
 <span data-ttu-id="f19e7-117">Puede impedir que el sistema vuelva a generar la excepción mediante una llamada al método <xref:System.Threading.Thread.ResetAbort%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f19e7-117">You can prevent the system from rethrowing the exception by calling the <xref:System.Threading.Thread.ResetAbort%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="f19e7-118">Sin embargo, debe hacerlo solo si su propio código generó <xref:System.Threading.ThreadAbortException>.</span><span class="sxs-lookup"><span data-stu-id="f19e7-118">However, you should do this only if your own code caused the <xref:System.Threading.ThreadAbortException>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f19e7-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="f19e7-119">See Also</span></span>  
 <xref:System.Threading.ThreadAbortException>  
 <xref:System.Threading.Thread>  
 [<span data-ttu-id="f19e7-120">Usar subprocesos y subprocesamiento</span><span class="sxs-lookup"><span data-stu-id="f19e7-120">Using Threads and Threading</span></span>](../../../docs/standard/threading/using-threads-and-threading.md)
