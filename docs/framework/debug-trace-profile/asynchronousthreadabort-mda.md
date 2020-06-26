---
title: MDA de asynchronousThreadAbort
description: Revise cómo se activa el Asistente para la depuración administrada (MDA) asynchronousThreadAbort cuando un subproceso intenta colocar una anulación asincrónica en otro subproceso.
ms.date: 03/30/2017
helpviewer_keywords:
- asynchronous thread aborts
- AsynchronousThreadAbort MDA
- managed debugging assistants (MDAs), asynchronous thread aborts
- threading [.NET Framework], managed debugging assistants
- MDAs (managed debugging assistants), asynchronous thread aborts
ms.assetid: 9ebe40b2-d703-421e-8660-984acc42bfe0
ms.openlocfilehash: 469372d57d9c21198353d171fec16458691eb25d
ms.sourcegitcommit: a2c8b19e813a52b91facbb5d7e3c062c7188b457
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415672"
---
# <a name="asynchronousthreadabort-mda"></a><span data-ttu-id="1c29a-103">MDA de asynchronousThreadAbort</span><span class="sxs-lookup"><span data-stu-id="1c29a-103">asynchronousThreadAbort MDA</span></span>
<span data-ttu-id="1c29a-104">El Asistente para la depuración administrada (MDA) `asynchronousThreadAbort` se activa cuando un subproceso intenta incorporar una anulación asincrónica a otro subproceso.</span><span class="sxs-lookup"><span data-stu-id="1c29a-104">The `asynchronousThreadAbort` managed debugging assistant (MDA) is activated when a thread attempts to introduce an asynchronous abort into another thread.</span></span> <span data-ttu-id="1c29a-105">Las anulaciones de subproceso sincrónicas no activan el MDA `asynchronousThreadAbort`.</span><span class="sxs-lookup"><span data-stu-id="1c29a-105">Synchronous thread aborts do not activate the `asynchronousThreadAbort` MDA.</span></span>

## <a name="symptoms"></a><span data-ttu-id="1c29a-106">Síntomas</span><span class="sxs-lookup"><span data-stu-id="1c29a-106">Symptoms</span></span>
 <span data-ttu-id="1c29a-107">Una aplicación se bloquea con una <xref:System.Threading.ThreadAbortException> no controlada cuando se anula el subproceso de aplicación principal.</span><span class="sxs-lookup"><span data-stu-id="1c29a-107">An application crashes with an unhandled <xref:System.Threading.ThreadAbortException> when the main application thread is aborted.</span></span> <span data-ttu-id="1c29a-108">Si la aplicación siguiera ejecutándose, las consecuencias podrían ser peores que el bloqueo, posiblemente más datos dañados.</span><span class="sxs-lookup"><span data-stu-id="1c29a-108">If the application were to continue to execute, the consequences might be worse than the application crashing, possibly resulting in further data corruption.</span></span>

 <span data-ttu-id="1c29a-109">Las operaciones que debían ser atómicas es probable que se hayan interrumpido tras la finalización parcial, dejando los datos de la aplicación en un estado impredecible.</span><span class="sxs-lookup"><span data-stu-id="1c29a-109">Operations meant to be atomic have likely been interrupted after partial completion, leaving application data in an unpredictable state.</span></span> <span data-ttu-id="1c29a-110">Una <xref:System.Threading.ThreadAbortException> se puede generar desde puntos aparentemente aleatorios de la ejecución de código, a menudo en ubicaciones desde las que no se esperaba que se generara una excepción.</span><span class="sxs-lookup"><span data-stu-id="1c29a-110">A <xref:System.Threading.ThreadAbortException> can be generated from seemingly random points in the execution of code, often in places from which an exception is not expected to arise.</span></span> <span data-ttu-id="1c29a-111">El código podría no ser capaz de controlar este tipo de excepción, lo que daría lugar a un estado dañado.</span><span class="sxs-lookup"><span data-stu-id="1c29a-111">The code might not be capable of handling such an exception, resulting in a corrupt state.</span></span>

 <span data-ttu-id="1c29a-112">Los síntomas pueden variar enormemente debido a la aleatoriedad inherente al problema.</span><span class="sxs-lookup"><span data-stu-id="1c29a-112">Symptoms can vary widely due to the randomness inherent to the problem.</span></span>

## <a name="cause"></a><span data-ttu-id="1c29a-113">Causa</span><span class="sxs-lookup"><span data-stu-id="1c29a-113">Cause</span></span>
 <span data-ttu-id="1c29a-114">El código de un subproceso ha llamado al método <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> de un subproceso de destino para incorporar una anulación de subproceso asincrónica.</span><span class="sxs-lookup"><span data-stu-id="1c29a-114">Code in one thread called the <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> method on a target thread to introduce an asynchronous thread abort.</span></span> <span data-ttu-id="1c29a-115">La anulación de subproceso es asincrónica porque el código que realiza la llamada a <xref:System.Threading.Thread.Abort%2A> se ejecuta en un subproceso distinto al destino de la operación de anulación.</span><span class="sxs-lookup"><span data-stu-id="1c29a-115">The thread abort is asynchronous because the code that makes the call to <xref:System.Threading.Thread.Abort%2A> is running on a different thread than the target of the abort operation.</span></span> <span data-ttu-id="1c29a-116">Las anulaciones de subproceso sincrónicas no deberían causar problemas, ya que el subproceso que realiza la <xref:System.Threading.Thread.Abort%2A> debe haberla hecho únicamente en un punto de control seguro donde el estado de la aplicación es coherente.</span><span class="sxs-lookup"><span data-stu-id="1c29a-116">Synchronous thread aborts should not cause a problem because the thread performing the <xref:System.Threading.Thread.Abort%2A> should have done so only at a safe checkpoint where application state is consistent.</span></span>

 <span data-ttu-id="1c29a-117">Las anulaciones de subproceso asincrónicas presentan un problema, ya que se procesan en puntos impredecibles de la ejecución del subproceso de destino.</span><span class="sxs-lookup"><span data-stu-id="1c29a-117">Asynchronous thread aborts present a problem because they are processed at unpredictable points in the target thread's execution.</span></span> <span data-ttu-id="1c29a-118">Para evitar esto, el código escrito para ejecutarse en un subproceso que se pueda anular de este modo tendría que controlar una <xref:System.Threading.ThreadAbortException> prácticamente en cada línea de código, teniendo cuidado de volver a poner los datos de la aplicación en un estado coherente.</span><span class="sxs-lookup"><span data-stu-id="1c29a-118">To avoid this, code written to run on a thread that might be aborted in this manner would need to handle a <xref:System.Threading.ThreadAbortException> at almost every line of code, taking care to put application data back into a consistent state.</span></span> <span data-ttu-id="1c29a-119">No es realista esperar que el código se escriba teniendo en cuenta este problema ni escribir código protegido frente a todas las circunstancias posibles.</span><span class="sxs-lookup"><span data-stu-id="1c29a-119">It is not realistic to expect code to be written with this problem in mind or to write code that protects against all possible circumstances.</span></span>

 <span data-ttu-id="1c29a-120">Las llamadas a código no administrado y bloques `finally` no se anulan asincrónicamente, sino inmediatamente al salir de una de estas categorías.</span><span class="sxs-lookup"><span data-stu-id="1c29a-120">Calls into unmanaged code and `finally` blocks will not be aborted asynchronously but immediately upon exit from one of these categories.</span></span>

 <span data-ttu-id="1c29a-121">La causa puede ser difícil de determinar debido a la aleatoriedad inherente al problema.</span><span class="sxs-lookup"><span data-stu-id="1c29a-121">The cause might be difficult to determine due to the randomness inherent to the problem.</span></span>

## <a name="resolution"></a><span data-ttu-id="1c29a-122">Solución</span><span class="sxs-lookup"><span data-stu-id="1c29a-122">Resolution</span></span>
 <span data-ttu-id="1c29a-123">Evite el diseño de código que necesite anulaciones de subproceso asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="1c29a-123">Avoid code design that requires the use of asynchronous thread aborts.</span></span> <span data-ttu-id="1c29a-124">Existen varios enfoques más adecuados para la interrupción de un subproceso de destino que no requieren una llamada a <xref:System.Threading.Thread.Abort%2A>.</span><span class="sxs-lookup"><span data-stu-id="1c29a-124">There are several approaches more appropriate for interruption of a target thread that do not require a call to <xref:System.Threading.Thread.Abort%2A>.</span></span> <span data-ttu-id="1c29a-125">El más seguro consiste en incorporar un mecanismo, como una propiedad común, que indique al subproceso de destino que solicite una interrupción.</span><span class="sxs-lookup"><span data-stu-id="1c29a-125">The safest is to introduce a mechanism, such as a common property, that signals the target thread to request an interrupt.</span></span> <span data-ttu-id="1c29a-126">El subproceso de destino comprueba la señal en determinados puntos de control seguros.</span><span class="sxs-lookup"><span data-stu-id="1c29a-126">The target thread checks the signal at certain safe checkpoints.</span></span> <span data-ttu-id="1c29a-127">Si observa que se ha solicitado una interrupción, puede cerrar correctamente.</span><span class="sxs-lookup"><span data-stu-id="1c29a-127">If it notices that an interrupt has been requested, it can shut down gracefully.</span></span>

## <a name="effect-on-the-runtime"></a><span data-ttu-id="1c29a-128">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="1c29a-128">Effect on the Runtime</span></span>
 <span data-ttu-id="1c29a-129">Este MDA no tiene ningún efecto en el CLR.</span><span class="sxs-lookup"><span data-stu-id="1c29a-129">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="1c29a-130">Solo notifica datos sobre las anulaciones de subproceso asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="1c29a-130">It only reports data about asynchronous thread aborts.</span></span>

## <a name="output"></a><span data-ttu-id="1c29a-131">Output</span><span class="sxs-lookup"><span data-stu-id="1c29a-131">Output</span></span>
 <span data-ttu-id="1c29a-132">El MDA notifica el identificador del subproceso que realiza la anulación y el identificador del subproceso que es el destino de ella.</span><span class="sxs-lookup"><span data-stu-id="1c29a-132">The MDA reports the ID of the thread performing the abort and the ID of the thread that is the target of the abort.</span></span> <span data-ttu-id="1c29a-133">Nunca serán iguales, porque eso está limitado a las interrupciones asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="1c29a-133">These will never be the same because this is limited to asynchronous aborts.</span></span>

## <a name="configuration"></a><span data-ttu-id="1c29a-134">Configuración</span><span class="sxs-lookup"><span data-stu-id="1c29a-134">Configuration</span></span>

```xml
<mdaConfig>
  <assistants>
    <asynchronousThreadAbort />
  </assistants>
</mdaConfig>
```

## <a name="example"></a><span data-ttu-id="1c29a-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1c29a-135">Example</span></span>
 <span data-ttu-id="1c29a-136">La activación del MDA `asynchronousThreadAbort` solo exige una llamada a <xref:System.Threading.Thread.Abort%2A> en un subproceso independiente en ejecución.</span><span class="sxs-lookup"><span data-stu-id="1c29a-136">Activating the `asynchronousThreadAbort` MDA requires only a call to <xref:System.Threading.Thread.Abort%2A> on a separate running thread.</span></span> <span data-ttu-id="1c29a-137">Tenga en cuenta las consecuencias si el contenido de la función de inicio del subproceso fuera un conjunto de operaciones más complejas que la anulación pudiera interrumpir en cualquier punto arbitrario.</span><span class="sxs-lookup"><span data-stu-id="1c29a-137">Consider the consequences if the contents of the thread start function were a set of more complex operations which might be interrupted at any arbitrary point by the abort.</span></span>

```csharp
using System.Threading;
void FireMda()
{
    Thread t = new Thread(delegate() { Thread.Sleep(1000); });
    t.Start();
    // The following line activates the MDA.
    t.Abort();
    t.Join();
}
```

## <a name="see-also"></a><span data-ttu-id="1c29a-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1c29a-138">See also</span></span>

- <xref:System.Threading.Thread>
- [<span data-ttu-id="1c29a-139">Diagnóstico de errores con asistentes de depuraciones administradas</span><span class="sxs-lookup"><span data-stu-id="1c29a-139">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
