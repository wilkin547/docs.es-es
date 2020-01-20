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
ms.openlocfilehash: efd4c596f67d5eabace8ecafb48f2d350df6a18e
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2020
ms.locfileid: "75938046"
---
# <a name="destroying-threads"></a><span data-ttu-id="1a4ef-102">Destrucción de subprocesos</span><span class="sxs-lookup"><span data-stu-id="1a4ef-102">Destroying threads</span></span>

<span data-ttu-id="1a4ef-103">Para finalizar la ejecución del subproceso, normalmente se usa el [modelo de cancelación cooperativa](cancellation-in-managed-threads.md).</span><span class="sxs-lookup"><span data-stu-id="1a4ef-103">To terminate the execution of the thread, you usually use the [cooperative cancellation model](cancellation-in-managed-threads.md).</span></span> <span data-ttu-id="1a4ef-104">A veces no es posible detener un subproceso de forma cooperativa, ya que ejecuta código de terceros no diseñado para la cancelación cooperativa.</span><span class="sxs-lookup"><span data-stu-id="1a4ef-104">Sometimes it is not possible to stop a thread cooperatively, because it runs third-party code not designed for cooperative cancellation.</span></span> <span data-ttu-id="1a4ef-105">El método <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> de .NET Framework se puede utilizar para terminar un subproceso administrado forzosamente.</span><span class="sxs-lookup"><span data-stu-id="1a4ef-105">The <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> method in .NET Framework can be used to terminate a managed thread forcibly.</span></span> <span data-ttu-id="1a4ef-106">Cuando se llama a <xref:System.Threading.Thread.Abort%2A>, Common Language Runtime inicia una clase <xref:System.Threading.ThreadAbortException> en el subproceso de destino, que este último puede detectar.</span><span class="sxs-lookup"><span data-stu-id="1a4ef-106">When you call <xref:System.Threading.Thread.Abort%2A>, the Common Language Runtime throws a <xref:System.Threading.ThreadAbortException> in the target thread, which the target thread can catch.</span></span> <span data-ttu-id="1a4ef-107">Para obtener más información, vea <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1a4ef-107">For more information, see <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="1a4ef-108">El método <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> no se admite en .NET Core.</span><span class="sxs-lookup"><span data-stu-id="1a4ef-108">The <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> method is not supported in .NET Core.</span></span> <span data-ttu-id="1a4ef-109">Si necesita terminar la ejecución de código de terceros de forma forzada en .NET Core, ejecútelo en el proceso independiente y use <xref:System.Diagnostics.Process.Kill%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1a4ef-109">If you need to terminate the execution of third-party code forcibly in .NET Core, run it in the separate process and use <xref:System.Diagnostics.Process.Kill%2A?displayProperty=nameWithType>.</span></span>

> [!NOTE]
> <span data-ttu-id="1a4ef-110">Si un subproceso ejecuta código no administrado al llamar a su método <xref:System.Threading.Thread.Abort%2A>, el tiempo de ejecución lo marca como <xref:System.Threading.ThreadState.AbortRequested?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1a4ef-110">If a thread is executing unmanaged code when its <xref:System.Threading.Thread.Abort%2A> method is called, the runtime marks it <xref:System.Threading.ThreadState.AbortRequested?displayProperty=nameWithType>.</span></span> <span data-ttu-id="1a4ef-111">La excepción se produce cuando el subproceso vuelve al código administrado.</span><span class="sxs-lookup"><span data-stu-id="1a4ef-111">The exception is thrown when the thread returns to managed code.</span></span>  
  
 <span data-ttu-id="1a4ef-112">Una vez que se anula un subproceso, no se puede reiniciar.</span><span class="sxs-lookup"><span data-stu-id="1a4ef-112">Once a thread is aborted, it cannot be restarted.</span></span>  
  
 <span data-ttu-id="1a4ef-113">El método <xref:System.Threading.Thread.Abort%2A> no hace que el subproceso se anule inmediatamente, porque el subproceso de destino puede detectar <xref:System.Threading.ThreadAbortException> y ejecutar cantidades arbitrarias de código en un bloque `finally`.</span><span class="sxs-lookup"><span data-stu-id="1a4ef-113">The <xref:System.Threading.Thread.Abort%2A> method does not cause the thread to abort immediately, because the target thread can catch the <xref:System.Threading.ThreadAbortException> and execute arbitrary amounts of code in a `finally` block.</span></span> <span data-ttu-id="1a4ef-114">Puede llamar a <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> si tiene que esperar hasta que haya finalizado el subproceso.</span><span class="sxs-lookup"><span data-stu-id="1a4ef-114">You can call <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> if you need to wait until the thread has ended.</span></span> <span data-ttu-id="1a4ef-115"><xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> es una llamada de bloqueo que no realiza ninguna devolución hasta que el subproceso se haya dejado de ejecutar realmente o hasta que haya transcurrido un intervalo de tiempo de espera opcional.</span><span class="sxs-lookup"><span data-stu-id="1a4ef-115"><xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> is a blocking call that does not return until the thread has actually stopped executing or an optional timeout interval has elapsed.</span></span> <span data-ttu-id="1a4ef-116">El subproceso anulado podría llamar al método <xref:System.Threading.Thread.ResetAbort%2A> o llevar a cabo el procesamiento sin enlazar en un bloqueo `finally`, por lo que si no especifica un tiempo de espera, no se garantiza que la espera finalice.</span><span class="sxs-lookup"><span data-stu-id="1a4ef-116">The aborted thread could call the <xref:System.Threading.Thread.ResetAbort%2A> method or perform unbounded processing in a `finally` block, so if you do not specify a timeout, the wait is not guaranteed to end.</span></span>  
  
 <span data-ttu-id="1a4ef-117">Los subprocesos que esperan una llamada al método <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> pueden interrumpirse con otros subprocesos que llaman a <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1a4ef-117">Threads that are waiting on a call to the <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> method can be interrupted by other threads that call <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType>.</span></span>  
  
## <a name="handling-threadabortexception"></a><span data-ttu-id="1a4ef-118">Control de ThreadAbortException</span><span class="sxs-lookup"><span data-stu-id="1a4ef-118">Handling ThreadAbortException</span></span>  
 <span data-ttu-id="1a4ef-119">Si espera que se anule el subproceso, como resultado de una llamada a <xref:System.Threading.Thread.Abort%2A> desde su propio código o como resultado de la descarga de un dominio de aplicación en que se ejecuta el subproceso (<xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> usa <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> para terminar los subprocesos), el subproceso debe controlar <xref:System.Threading.ThreadAbortException> y realizar cualquier procesamiento final en una cláusula `finally`, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="1a4ef-119">If you expect your thread to be aborted, either as a result of calling <xref:System.Threading.Thread.Abort%2A> from your own code or as a result of unloading an application domain in which the thread is running (<xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> uses <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> to terminate threads), your thread must handle the <xref:System.Threading.ThreadAbortException> and perform any final processing in a `finally` clause, as shown in the following code.</span></span>  
  
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
  
 <span data-ttu-id="1a4ef-120">El código de limpieza debe estar en la cláusula `catch` o en la cláusula `finally`, porque el sistema vuelve a generar <xref:System.Threading.ThreadAbortException> al final de la cláusula `finally` o al final de la cláusula `catch` si no existe la cláusula `finally`.</span><span class="sxs-lookup"><span data-stu-id="1a4ef-120">Your clean-up code must be in the `catch` clause or the `finally` clause, because a <xref:System.Threading.ThreadAbortException> is rethrown by the system at the end of the `finally` clause, or at the end of the `catch` clause if there is no `finally` clause.</span></span>  
  
 <span data-ttu-id="1a4ef-121">Puede impedir que el sistema vuelva a generar la excepción mediante una llamada al método <xref:System.Threading.Thread.ResetAbort%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1a4ef-121">You can prevent the system from rethrowing the exception by calling the <xref:System.Threading.Thread.ResetAbort%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="1a4ef-122">Sin embargo, debe hacerlo solo si su propio código generó <xref:System.Threading.ThreadAbortException>.</span><span class="sxs-lookup"><span data-stu-id="1a4ef-122">However, you should do this only if your own code caused the <xref:System.Threading.ThreadAbortException>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a4ef-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="1a4ef-123">See also</span></span>

- <xref:System.Threading.ThreadAbortException>
- <xref:System.Threading.Thread>
- [<span data-ttu-id="1a4ef-124">Usar subprocesos y subprocesamiento</span><span class="sxs-lookup"><span data-stu-id="1a4ef-124">Using Threads and Threading</span></span>](../../../docs/standard/threading/using-threads-and-threading.md)
