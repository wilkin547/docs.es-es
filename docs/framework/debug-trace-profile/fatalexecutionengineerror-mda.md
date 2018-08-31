---
title: MDA de fatalExecutionError
ms.date: 03/30/2017
helpviewer_keywords:
- corrupted CLR
- fatal execution error
- terminated processes
- unexpected terminations
- fatal errors
- MDAs (managed debugging assistants), fatal errors
- process termination
- FatalExecutionEngineError MDA
- managed debugging assistants (MDAs), fatal errors
ms.assetid: 8b559e44-2393-4e4e-8160-7558d37a4a89
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f12b94198b88111d559cfe372c28bdbf4b37e3fe
ms.sourcegitcommit: fe02afbc39e78afd78cc6050e4a9c12a75f579f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2018
ms.locfileid: "43257482"
---
# <a name="fatalexecutionengineerror-mda"></a><span data-ttu-id="a7311-102">MDA de fatalExecutionError</span><span class="sxs-lookup"><span data-stu-id="a7311-102">fatalExecutionEngineError MDA</span></span>
<span data-ttu-id="a7311-103">El Ayudante para la depuración administrada (MDA) de `fatalExecutionEngineError` se activa cuando se detecta un error grave en Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="a7311-103">The `fatalExecutionEngineError` managed debugging assistant (MDA) is activated when a fatal error in the common language runtime (CLR) has been detected.</span></span> <span data-ttu-id="a7311-104">Esto finaliza el proceso.</span><span class="sxs-lookup"><span data-stu-id="a7311-104">The process will be terminated.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="a7311-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="a7311-105">Symptoms</span></span>  
 <span data-ttu-id="a7311-106">Finalización de proceso inesperada.</span><span class="sxs-lookup"><span data-stu-id="a7311-106">Unexpected process termination.</span></span> <span data-ttu-id="a7311-107">No se pueden determinar otros síntomas porque los errores de CLR pueden ser debidos a distintos motivos.</span><span class="sxs-lookup"><span data-stu-id="a7311-107">Other symptoms cannot be determined because a CLR failure can occur for a variety of reasons.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="a7311-108">Motivo</span><span class="sxs-lookup"><span data-stu-id="a7311-108">Cause</span></span>  
 <span data-ttu-id="a7311-109">CLR ha sufrido un daño grave.</span><span class="sxs-lookup"><span data-stu-id="a7311-109">The CLR has been fatally corrupted.</span></span> <span data-ttu-id="a7311-110">En la mayoría de los casos, esto se debe a los daños en los datos, lo que puede deberse a distintos problemas como, por ejemplo, llamar a funciones de invocación de plataforma incorrectas o pasar datos no válidos a CLR.</span><span class="sxs-lookup"><span data-stu-id="a7311-110">This is most often caused by data corruption, which can be caused by a number of problems, such as calls to malformed platform invoke functions and passing invalid data to the CLR.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="a7311-111">Resolución</span><span class="sxs-lookup"><span data-stu-id="a7311-111">Resolution</span></span>  
 <span data-ttu-id="a7311-112">Si se habilitan Ayudantes para la depuración administrada adicionales, se podría ayudar a identificar el problema.</span><span class="sxs-lookup"><span data-stu-id="a7311-112">Enabling additional MDAs might help identify the problem.</span></span> <span data-ttu-id="a7311-113">Los siguientes Ayudantes para la depuración administrada pueden resultar especialmente útiles a la hora de diagnosticar el problema:</span><span class="sxs-lookup"><span data-stu-id="a7311-113">The following MDAs can be particularly helpful in diagnosing the issue:</span></span>  
  
-   [<span data-ttu-id="a7311-114">invalidOverlappedToPinvoke</span><span class="sxs-lookup"><span data-stu-id="a7311-114">invalidOverlappedToPinvoke</span></span>](../../../docs/framework/debug-trace-profile/invalidoverlappedtopinvoke-mda.md)  
  
-   [<span data-ttu-id="a7311-115">overlappedFreeError</span><span class="sxs-lookup"><span data-stu-id="a7311-115">overlappedFreeError</span></span>](../../../docs/framework/debug-trace-profile/overlappedfreeerror-mda.md)  
  
-   [<span data-ttu-id="a7311-116">pInvokeStackImbalance</span><span class="sxs-lookup"><span data-stu-id="a7311-116">pInvokeStackImbalance</span></span>](../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md)  
  
-   [<span data-ttu-id="a7311-117">gcUnmanagedToManaged</span><span class="sxs-lookup"><span data-stu-id="a7311-117">gcUnmanagedToManaged</span></span>](../../../docs/framework/debug-trace-profile/gcunmanagedtomanaged-mda.md)  
  
-   [<span data-ttu-id="a7311-118">gcManagedToUnmanaged</span><span class="sxs-lookup"><span data-stu-id="a7311-118">gcManagedToUnmanaged</span></span>](../../../docs/framework/debug-trace-profile/gcmanagedtounmanaged-mda.md)  
  
-   [<span data-ttu-id="a7311-119">callbackOnCollectedDelegate</span><span class="sxs-lookup"><span data-stu-id="a7311-119">callbackOnCollectedDelegate</span></span>](../../../docs/framework/debug-trace-profile/callbackoncollecteddelegate-mda.md)  
  
-   [<span data-ttu-id="a7311-120">reportAvOnComRelease</span><span class="sxs-lookup"><span data-stu-id="a7311-120">reportAvOnComRelease</span></span>](../../../docs/framework/debug-trace-profile/reportavoncomrelease-mda.md)  
  
-   [<span data-ttu-id="a7311-121">invalidVariant</span><span class="sxs-lookup"><span data-stu-id="a7311-121">invalidVariant</span></span>](../../../docs/framework/debug-trace-profile/invalidvariant-mda.md)  
  
-   [<span data-ttu-id="a7311-122">invalidIUnknown</span><span class="sxs-lookup"><span data-stu-id="a7311-122">invalidIUnknown</span></span>](../../../docs/framework/debug-trace-profile/invalidiunknown-mda.md)  
  
-   [<span data-ttu-id="a7311-123">raceOnRCWCleanup</span><span class="sxs-lookup"><span data-stu-id="a7311-123">raceOnRCWCleanup</span></span>](../../../docs/framework/debug-trace-profile/raceonrcwcleanup-mda.md)  
  
-   [<span data-ttu-id="a7311-124">invalidFunctionPointerInDelegate</span><span class="sxs-lookup"><span data-stu-id="a7311-124">invalidFunctionPointerInDelegate</span></span>](../../../docs/framework/debug-trace-profile/invalidfunctionpointerindelegate-mda.md)  
  
-   [<span data-ttu-id="a7311-125">invalidGCHandleCookie</span><span class="sxs-lookup"><span data-stu-id="a7311-125">invalidGCHandleCookie</span></span>](../../../docs/framework/debug-trace-profile/invalidgchandlecookie-mda.md)  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="a7311-126">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="a7311-126">Effect on the Runtime</span></span>  
 <span data-ttu-id="a7311-127">Este MDA no tiene ningún efecto en el comportamiento del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a7311-127">This MDA has no effect on the runtime's behavior.</span></span>  
  
## <a name="output"></a><span data-ttu-id="a7311-128">Salida</span><span class="sxs-lookup"><span data-stu-id="a7311-128">Output</span></span>  
 <span data-ttu-id="a7311-129">La dirección de la función de CLR que ha producido el error grave, el identificador del subproceso donde se ha producido el error y el código de error.</span><span class="sxs-lookup"><span data-stu-id="a7311-129">The address of the CLR function that caused the fatal error, the ID of the thread where the error occurred, and the error code.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="a7311-130">Configuración</span><span class="sxs-lookup"><span data-stu-id="a7311-130">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <fatalExecutionEngineError />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a7311-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="a7311-131">See Also</span></span>  
 <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>  
 <xref:System.Runtime.ConstrainedExecution.Cer>  
 [<span data-ttu-id="a7311-132">Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)</span><span class="sxs-lookup"><span data-stu-id="a7311-132">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
