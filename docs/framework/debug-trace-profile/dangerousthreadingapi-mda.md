---
title: MDA de dangerousThreadingAPI
ms.date: 03/30/2017
helpviewer_keywords:
- suspending threads
- DangerousThreadingAPI MDA
- managed debugging assistants (MDAs), dangerous threading operations
- threading [.NET Framework], suspending
- MDAs (managed debugging assistants), dangerous threading operations
- Suspend method
- threading [.NET Framework], managed debugging assistants
ms.assetid: 3e5efbc5-92e4-4229-b31f-ce368a1adb96
ms.openlocfilehash: 4e7e858dfb85eeccbadb23da60d081d1407e89d8
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216668"
---
# <a name="dangerousthreadingapi-mda"></a><span data-ttu-id="e7c84-102">MDA de dangerousThreadingAPI</span><span class="sxs-lookup"><span data-stu-id="e7c84-102">dangerousThreadingAPI MDA</span></span>
<span data-ttu-id="e7c84-103">El Asistente para la depuración administrada (MDA) de `dangerousThreadingAPI` se activa cuando se llama al método <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> en un subproceso diferente al subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="e7c84-103">The `dangerousThreadingAPI` managed debugging assistant (MDA) is activated when the <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> method is called on a thread other than the current thread.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="e7c84-104">Síntomas</span><span class="sxs-lookup"><span data-stu-id="e7c84-104">Symptoms</span></span>  
 <span data-ttu-id="e7c84-105">Una aplicación no responde o se bloquea continuamente.</span><span class="sxs-lookup"><span data-stu-id="e7c84-105">An application is unresponsive or hangs indefinitely.</span></span> <span data-ttu-id="e7c84-106">Los datos de la aplicación o el sistema pueden permanecer en un estado imprevisible temporalmente o incluso después de que una aplicación se haya cerrado.</span><span class="sxs-lookup"><span data-stu-id="e7c84-106">System or application data might be left in an unpredictable state temporarily or even after an application has been shut down.</span></span> <span data-ttu-id="e7c84-107">Algunas operaciones no se completan según lo esperado.</span><span class="sxs-lookup"><span data-stu-id="e7c84-107">Some operations are not completing as expected.</span></span>  
  
 <span data-ttu-id="e7c84-108">Los síntomas pueden variar enormemente debido a la aleatoriedad inherente al problema.</span><span class="sxs-lookup"><span data-stu-id="e7c84-108">Symptoms can vary widely due to the randomness inherent to the problem.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="e7c84-109">Causa</span><span class="sxs-lookup"><span data-stu-id="e7c84-109">Cause</span></span>  
 <span data-ttu-id="e7c84-110">Un subproceso está suspendido de manera asincrónica mediante otro subproceso que usa el método <xref:System.Threading.Thread.Suspend%2A>.</span><span class="sxs-lookup"><span data-stu-id="e7c84-110">A thread is asynchronously suspended by another thread using the <xref:System.Threading.Thread.Suspend%2A> method.</span></span> <span data-ttu-id="e7c84-111">No existe ninguna manera de determinar cuándo es seguro suspender otro subproceso que puede encontrarse en el proceso de una operación.</span><span class="sxs-lookup"><span data-stu-id="e7c84-111">There is no way to determine when it is safe to suspend another thread which might be in the middle of an operation.</span></span> <span data-ttu-id="e7c84-112">La suspensión del subproceso puede provocar daños en los datos o la interrupción de invariantes.</span><span class="sxs-lookup"><span data-stu-id="e7c84-112">Suspending the thread can result in the corruption of data or the breaking of invariants.</span></span> <span data-ttu-id="e7c84-113">Si un subproceso se coloca en un estado suspendido y nunca se reanuda con el método <xref:System.Threading.Thread.Resume%2A>, la aplicación puede bloquearse de manera indefinida y posiblemente dañe los datos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e7c84-113">Should a thread be placed into a suspended state and never resumed using the <xref:System.Threading.Thread.Resume%2A> method, the application can hang indefinitely and possibly damage application data.</span></span> <span data-ttu-id="e7c84-114">Estos métodos se han marcado como obsoletos.</span><span class="sxs-lookup"><span data-stu-id="e7c84-114">These methods have been marked as obsolete.</span></span>  
  
 <span data-ttu-id="e7c84-115">Si los tipos primitivos de sincronización se incluyen en el subproceso de destino, permanecen así durante la suspensión.</span><span class="sxs-lookup"><span data-stu-id="e7c84-115">If synchronization primitives are held by the target thread, they remain held during suspension.</span></span> <span data-ttu-id="e7c84-116">Esto puede provocar interbloqueos si otro subproceso, por ejemplo el subproceso que realiza <xref:System.Threading.Thread.Suspend%2A>, intenta adquirir un bloqueo en el tipo primitivo.</span><span class="sxs-lookup"><span data-stu-id="e7c84-116">This can lead to deadlocks should another thread, for example the thread performing the <xref:System.Threading.Thread.Suspend%2A>, attempt to acquire a lock on the primitive.</span></span> <span data-ttu-id="e7c84-117">En esta situación, el problema se manifiesta como un interbloqueo.</span><span class="sxs-lookup"><span data-stu-id="e7c84-117">In this situation, the problem manifests itself as a deadlock.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="e7c84-118">Solución</span><span class="sxs-lookup"><span data-stu-id="e7c84-118">Resolution</span></span>  
 <span data-ttu-id="e7c84-119">Evite diseños que necesiten el uso de <xref:System.Threading.Thread.Suspend%2A> y <xref:System.Threading.Thread.Resume%2A>.</span><span class="sxs-lookup"><span data-stu-id="e7c84-119">Avoid designs that require the use of <xref:System.Threading.Thread.Suspend%2A> and <xref:System.Threading.Thread.Resume%2A>.</span></span> <span data-ttu-id="e7c84-120">Para obtener una cooperación entre subprocesos, use los tipos primitivos de sincronización como <xref:System.Threading.Monitor>, <xref:System.Threading.ReaderWriterLock>, <xref:System.Threading.Mutex> o la instrucción `lock` de C#.</span><span class="sxs-lookup"><span data-stu-id="e7c84-120">For cooperation between threads, use synchronization primitives such as <xref:System.Threading.Monitor>, <xref:System.Threading.ReaderWriterLock>, <xref:System.Threading.Mutex>, or the C# `lock` statement.</span></span> <span data-ttu-id="e7c84-121">Si debe usar estos métodos, reduzca el período de tiempo y minimice la cantidad de código que ejecuta mientras el subproceso está en un estado suspendido.</span><span class="sxs-lookup"><span data-stu-id="e7c84-121">If you must use these methods, reduce the window of time and minimize the amount of code that executes while the thread is in a suspended state.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="e7c84-122">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="e7c84-122">Effect on the Runtime</span></span>  
 <span data-ttu-id="e7c84-123">Este MDA no tiene ningún efecto en el CLR.</span><span class="sxs-lookup"><span data-stu-id="e7c84-123">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="e7c84-124">Solo notifica datos sobre operaciones de subproceso peligrosas.</span><span class="sxs-lookup"><span data-stu-id="e7c84-124">It only reports data about dangerous threading operations.</span></span>  
  
## <a name="output"></a><span data-ttu-id="e7c84-125">Output</span><span class="sxs-lookup"><span data-stu-id="e7c84-125">Output</span></span>  
 <span data-ttu-id="e7c84-126">El MDA identifica el método de subproceso peligroso que ha provocado que se active.</span><span class="sxs-lookup"><span data-stu-id="e7c84-126">The MDA identifies the dangerous threading method that caused it to be activated.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="e7c84-127">Configuración</span><span class="sxs-lookup"><span data-stu-id="e7c84-127">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <dangerousThreadingAPI />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="e7c84-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e7c84-128">Example</span></span>  
 <span data-ttu-id="e7c84-129">En el ejemplo de código siguiente se muestra una llamada al método <xref:System.Threading.Thread.Suspend%2A> que provoca la activación de `dangerousThreadingAPI`.</span><span class="sxs-lookup"><span data-stu-id="e7c84-129">The following code example demonstrates a call to the <xref:System.Threading.Thread.Suspend%2A> method that causes the activation of the `dangerousThreadingAPI`.</span></span>  
  
```csharp
using System.Threading;  
void FireMda()  
{  
Thread t = new Thread(delegate() { Thread.Sleep(1000); });  
    t.Start();  
    // The following line activates the MDA.  
    t.Suspend();   
    t.Resume();  
    t.Join();  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="e7c84-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e7c84-130">See also</span></span>

- <xref:System.Threading.Thread>
- [<span data-ttu-id="e7c84-131">Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)</span><span class="sxs-lookup"><span data-stu-id="e7c84-131">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="e7c84-132">lock (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e7c84-132">lock Statement</span></span>](../../csharp/language-reference/keywords/lock-statement.md)
