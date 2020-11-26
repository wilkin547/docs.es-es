---
title: MDA de fatalExecutionError
description: Revise el Asistente para la depuración administrada (MDA) de Fatalexecutionerror en .NET, que puede activarse debido a una terminación inesperada del proceso.
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
ms.openlocfilehash: a9347338d53755b74b3ff291f75cb6b221134130
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96244280"
---
# <a name="fatalexecutionengineerror-mda"></a><span data-ttu-id="63a63-103">MDA de fatalExecutionError</span><span class="sxs-lookup"><span data-stu-id="63a63-103">fatalExecutionEngineError MDA</span></span>

<span data-ttu-id="63a63-104">El Ayudante para la depuración administrada (MDA) de `fatalExecutionEngineError` se activa cuando se detecta un error grave en Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="63a63-104">The `fatalExecutionEngineError` managed debugging assistant (MDA) is activated when a fatal error in the common language runtime (CLR) has been detected.</span></span> <span data-ttu-id="63a63-105">Esto finaliza el proceso.</span><span class="sxs-lookup"><span data-stu-id="63a63-105">The process will be terminated.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="63a63-106">Síntomas</span><span class="sxs-lookup"><span data-stu-id="63a63-106">Symptoms</span></span>  

 <span data-ttu-id="63a63-107">Finalización de proceso inesperada.</span><span class="sxs-lookup"><span data-stu-id="63a63-107">Unexpected process termination.</span></span> <span data-ttu-id="63a63-108">No se pueden determinar otros síntomas porque los errores de CLR pueden ser debidos a distintos motivos.</span><span class="sxs-lookup"><span data-stu-id="63a63-108">Other symptoms cannot be determined because a CLR failure can occur for a variety of reasons.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="63a63-109">Causa</span><span class="sxs-lookup"><span data-stu-id="63a63-109">Cause</span></span>  

 <span data-ttu-id="63a63-110">CLR ha sufrido un daño grave.</span><span class="sxs-lookup"><span data-stu-id="63a63-110">The CLR has been fatally corrupted.</span></span> <span data-ttu-id="63a63-111">En la mayoría de los casos, esto se debe a los daños en los datos, lo que puede deberse a distintos problemas como, por ejemplo, llamar a funciones de invocación de plataforma incorrectas o pasar datos no válidos a CLR.</span><span class="sxs-lookup"><span data-stu-id="63a63-111">This is most often caused by data corruption, which can be caused by a number of problems, such as calls to malformed platform invoke functions and passing invalid data to the CLR.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="63a63-112">Solución</span><span class="sxs-lookup"><span data-stu-id="63a63-112">Resolution</span></span>  

 <span data-ttu-id="63a63-113">Si se habilitan Ayudantes para la depuración administrada adicionales, se podría ayudar a identificar el problema.</span><span class="sxs-lookup"><span data-stu-id="63a63-113">Enabling additional MDAs might help identify the problem.</span></span> <span data-ttu-id="63a63-114">Los siguientes Ayudantes para la depuración administrada pueden resultar especialmente útiles a la hora de diagnosticar el problema:</span><span class="sxs-lookup"><span data-stu-id="63a63-114">The following MDAs can be particularly helpful in diagnosing the issue:</span></span>  
  
- [<span data-ttu-id="63a63-115">invalidOverlappedToPinvoke</span><span class="sxs-lookup"><span data-stu-id="63a63-115">invalidOverlappedToPinvoke</span></span>](invalidoverlappedtopinvoke-mda.md)  
  
- [<span data-ttu-id="63a63-116">overlappedFreeError</span><span class="sxs-lookup"><span data-stu-id="63a63-116">overlappedFreeError</span></span>](overlappedfreeerror-mda.md)  
  
- [<span data-ttu-id="63a63-117">pInvokeStackImbalance</span><span class="sxs-lookup"><span data-stu-id="63a63-117">pInvokeStackImbalance</span></span>](pinvokestackimbalance-mda.md)  
  
- [<span data-ttu-id="63a63-118">gcUnmanagedToManaged</span><span class="sxs-lookup"><span data-stu-id="63a63-118">gcUnmanagedToManaged</span></span>](gcunmanagedtomanaged-mda.md)  
  
- [<span data-ttu-id="63a63-119">gcManagedToUnmanaged</span><span class="sxs-lookup"><span data-stu-id="63a63-119">gcManagedToUnmanaged</span></span>](gcmanagedtounmanaged-mda.md)  
  
- [<span data-ttu-id="63a63-120">callbackOnCollectedDelegate</span><span class="sxs-lookup"><span data-stu-id="63a63-120">callbackOnCollectedDelegate</span></span>](callbackoncollecteddelegate-mda.md)  
  
- [<span data-ttu-id="63a63-121">reportAvOnComRelease</span><span class="sxs-lookup"><span data-stu-id="63a63-121">reportAvOnComRelease</span></span>](reportavoncomrelease-mda.md)  
  
- [<span data-ttu-id="63a63-122">invalidVariant</span><span class="sxs-lookup"><span data-stu-id="63a63-122">invalidVariant</span></span>](invalidvariant-mda.md)  
  
- [<span data-ttu-id="63a63-123">invalidIUnknown</span><span class="sxs-lookup"><span data-stu-id="63a63-123">invalidIUnknown</span></span>](invalidiunknown-mda.md)  
  
- [<span data-ttu-id="63a63-124">raceOnRCWCleanup</span><span class="sxs-lookup"><span data-stu-id="63a63-124">raceOnRCWCleanup</span></span>](raceonrcwcleanup-mda.md)  
  
- [<span data-ttu-id="63a63-125">invalidFunctionPointerInDelegate</span><span class="sxs-lookup"><span data-stu-id="63a63-125">invalidFunctionPointerInDelegate</span></span>](invalidfunctionpointerindelegate-mda.md)  
  
- [<span data-ttu-id="63a63-126">invalidGCHandleCookie</span><span class="sxs-lookup"><span data-stu-id="63a63-126">invalidGCHandleCookie</span></span>](invalidgchandlecookie-mda.md)  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="63a63-127">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="63a63-127">Effect on the Runtime</span></span>  

 <span data-ttu-id="63a63-128">Este MDA no tiene ningún efecto en el comportamiento del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="63a63-128">This MDA has no effect on the runtime's behavior.</span></span>  
  
## <a name="output"></a><span data-ttu-id="63a63-129">Resultados</span><span class="sxs-lookup"><span data-stu-id="63a63-129">Output</span></span>  

 <span data-ttu-id="63a63-130">La dirección de la función de CLR que ha producido el error grave, el identificador del subproceso donde se ha producido el error y el código de error.</span><span class="sxs-lookup"><span data-stu-id="63a63-130">The address of the CLR function that caused the fatal error, the ID of the thread where the error occurred, and the error code.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="63a63-131">Configuración</span><span class="sxs-lookup"><span data-stu-id="63a63-131">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <fatalExecutionEngineError />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="63a63-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="63a63-132">See also</span></span>

- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>
- <xref:System.Runtime.ConstrainedExecution.Cer>
- [<span data-ttu-id="63a63-133">Diagnóstico de errores con asistentes de depuraciones administradas</span><span class="sxs-lookup"><span data-stu-id="63a63-133">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
