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
ms.openlocfilehash: 3fd58ae8f73fd932df641ea96a44ff618dd139e2
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71052808"
---
# <a name="fatalexecutionengineerror-mda"></a><span data-ttu-id="8115f-102">MDA de fatalExecutionError</span><span class="sxs-lookup"><span data-stu-id="8115f-102">fatalExecutionEngineError MDA</span></span>
<span data-ttu-id="8115f-103">El Ayudante para la depuración administrada (MDA) de `fatalExecutionEngineError` se activa cuando se detecta un error grave en Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="8115f-103">The `fatalExecutionEngineError` managed debugging assistant (MDA) is activated when a fatal error in the common language runtime (CLR) has been detected.</span></span> <span data-ttu-id="8115f-104">Esto finaliza el proceso.</span><span class="sxs-lookup"><span data-stu-id="8115f-104">The process will be terminated.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="8115f-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="8115f-105">Symptoms</span></span>  
 <span data-ttu-id="8115f-106">Finalización de proceso inesperada.</span><span class="sxs-lookup"><span data-stu-id="8115f-106">Unexpected process termination.</span></span> <span data-ttu-id="8115f-107">No se pueden determinar otros síntomas porque los errores de CLR pueden ser debidos a distintos motivos.</span><span class="sxs-lookup"><span data-stu-id="8115f-107">Other symptoms cannot be determined because a CLR failure can occur for a variety of reasons.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="8115f-108">Causa</span><span class="sxs-lookup"><span data-stu-id="8115f-108">Cause</span></span>  
 <span data-ttu-id="8115f-109">CLR ha sufrido un daño grave.</span><span class="sxs-lookup"><span data-stu-id="8115f-109">The CLR has been fatally corrupted.</span></span> <span data-ttu-id="8115f-110">En la mayoría de los casos, esto se debe a los daños en los datos, lo que puede deberse a distintos problemas como, por ejemplo, llamar a funciones de invocación de plataforma incorrectas o pasar datos no válidos a CLR.</span><span class="sxs-lookup"><span data-stu-id="8115f-110">This is most often caused by data corruption, which can be caused by a number of problems, such as calls to malformed platform invoke functions and passing invalid data to the CLR.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="8115f-111">Resolución</span><span class="sxs-lookup"><span data-stu-id="8115f-111">Resolution</span></span>  
 <span data-ttu-id="8115f-112">Si se habilitan Ayudantes para la depuración administrada adicionales, se podría ayudar a identificar el problema.</span><span class="sxs-lookup"><span data-stu-id="8115f-112">Enabling additional MDAs might help identify the problem.</span></span> <span data-ttu-id="8115f-113">Los siguientes Ayudantes para la depuración administrada pueden resultar especialmente útiles a la hora de diagnosticar el problema:</span><span class="sxs-lookup"><span data-stu-id="8115f-113">The following MDAs can be particularly helpful in diagnosing the issue:</span></span>  
  
- [<span data-ttu-id="8115f-114">invalidOverlappedToPinvoke</span><span class="sxs-lookup"><span data-stu-id="8115f-114">invalidOverlappedToPinvoke</span></span>](invalidoverlappedtopinvoke-mda.md)  
  
- [<span data-ttu-id="8115f-115">overlappedFreeError</span><span class="sxs-lookup"><span data-stu-id="8115f-115">overlappedFreeError</span></span>](overlappedfreeerror-mda.md)  
  
- [<span data-ttu-id="8115f-116">pInvokeStackImbalance</span><span class="sxs-lookup"><span data-stu-id="8115f-116">pInvokeStackImbalance</span></span>](pinvokestackimbalance-mda.md)  
  
- [<span data-ttu-id="8115f-117">gcUnmanagedToManaged</span><span class="sxs-lookup"><span data-stu-id="8115f-117">gcUnmanagedToManaged</span></span>](gcunmanagedtomanaged-mda.md)  
  
- [<span data-ttu-id="8115f-118">gcManagedToUnmanaged</span><span class="sxs-lookup"><span data-stu-id="8115f-118">gcManagedToUnmanaged</span></span>](gcmanagedtounmanaged-mda.md)  
  
- [<span data-ttu-id="8115f-119">callbackOnCollectedDelegate</span><span class="sxs-lookup"><span data-stu-id="8115f-119">callbackOnCollectedDelegate</span></span>](callbackoncollecteddelegate-mda.md)  
  
- [<span data-ttu-id="8115f-120">reportAvOnComRelease</span><span class="sxs-lookup"><span data-stu-id="8115f-120">reportAvOnComRelease</span></span>](reportavoncomrelease-mda.md)  
  
- [<span data-ttu-id="8115f-121">invalidVariant</span><span class="sxs-lookup"><span data-stu-id="8115f-121">invalidVariant</span></span>](invalidvariant-mda.md)  
  
- [<span data-ttu-id="8115f-122">invalidIUnknown</span><span class="sxs-lookup"><span data-stu-id="8115f-122">invalidIUnknown</span></span>](invalidiunknown-mda.md)  
  
- [<span data-ttu-id="8115f-123">raceOnRCWCleanup</span><span class="sxs-lookup"><span data-stu-id="8115f-123">raceOnRCWCleanup</span></span>](raceonrcwcleanup-mda.md)  
  
- [<span data-ttu-id="8115f-124">invalidFunctionPointerInDelegate</span><span class="sxs-lookup"><span data-stu-id="8115f-124">invalidFunctionPointerInDelegate</span></span>](invalidfunctionpointerindelegate-mda.md)  
  
- [<span data-ttu-id="8115f-125">invalidGCHandleCookie</span><span class="sxs-lookup"><span data-stu-id="8115f-125">invalidGCHandleCookie</span></span>](invalidgchandlecookie-mda.md)  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="8115f-126">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="8115f-126">Effect on the Runtime</span></span>  
 <span data-ttu-id="8115f-127">Este MDA no tiene ningún efecto en el comportamiento del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="8115f-127">This MDA has no effect on the runtime's behavior.</span></span>  
  
## <a name="output"></a><span data-ttu-id="8115f-128">Resultados</span><span class="sxs-lookup"><span data-stu-id="8115f-128">Output</span></span>  
 <span data-ttu-id="8115f-129">La dirección de la función de CLR que ha producido el error grave, el identificador del subproceso donde se ha producido el error y el código de error.</span><span class="sxs-lookup"><span data-stu-id="8115f-129">The address of the CLR function that caused the fatal error, the ID of the thread where the error occurred, and the error code.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="8115f-130">Configuración</span><span class="sxs-lookup"><span data-stu-id="8115f-130">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <fatalExecutionEngineError />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8115f-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="8115f-131">See also</span></span>

- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>
- <xref:System.Runtime.ConstrainedExecution.Cer>
- [<span data-ttu-id="8115f-132">Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)</span><span class="sxs-lookup"><span data-stu-id="8115f-132">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
