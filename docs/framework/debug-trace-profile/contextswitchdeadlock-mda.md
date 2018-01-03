---
title: MDA de contextSwitchDeadlock
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deadlocks [.NET Framework]
- pumping messages
- STA message pumping
- single-threaded COM components
- MDAs (managed debugging assistants), context switching deadlocks
- managed debugging assistants (MDAs), context switching deadlocks
- ContextSwitchDeadlock MDA
- message pumping
- context switching deadlocks
ms.assetid: 26dfaa15-9ddb-4b0a-b6da-999bba664fa6
caps.latest.revision: "22"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 816afbae0cca18de24c11152541a509b54c119b8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="contextswitchdeadlock-mda"></a><span data-ttu-id="9d778-102">MDA de contextSwitchDeadlock</span><span class="sxs-lookup"><span data-stu-id="9d778-102">contextSwitchDeadlock MDA</span></span>
<span data-ttu-id="9d778-103">El asistente para la depuración administrada (MDA, por sus siglas en inglés) `contextSwitchDeadlock` se activa cuando se detecta un interbloqueo durante un intento de transición de contexto COM.</span><span class="sxs-lookup"><span data-stu-id="9d778-103">The `contextSwitchDeadlock` managed debugging assistant (MDA) is activated when a deadlock is detected during an attempted COM context transition.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="9d778-104">Síntomas</span><span class="sxs-lookup"><span data-stu-id="9d778-104">Symptoms</span></span>  
 <span data-ttu-id="9d778-105">El síntoma más común es que no se devuelve una llamada en un componente COM sin administrar de código administrado.</span><span class="sxs-lookup"><span data-stu-id="9d778-105">The most common symptom is that a call on an unmanaged COM component from managed code does not return.</span></span>  <span data-ttu-id="9d778-106">Otro síntoma es el aumento de uso de memoria con el tiempo.</span><span class="sxs-lookup"><span data-stu-id="9d778-106">Another symptom is memory usage increasing over time.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="9d778-107">Motivo</span><span class="sxs-lookup"><span data-stu-id="9d778-107">Cause</span></span>  
 <span data-ttu-id="9d778-108">La causa más probable es que haya un subproceso de contenedor uniproceso (STA, por sus siglas en inglés) que no esté suministrando mensajes.</span><span class="sxs-lookup"><span data-stu-id="9d778-108">The most probable cause is that a single-threaded apartment (STA) thread is not pumping messages.</span></span> <span data-ttu-id="9d778-109">El subproceso de STA está en espera sin suministrar mensajes o está realizando operaciones extensas y no permite que la cola de mensajes se suministre.</span><span class="sxs-lookup"><span data-stu-id="9d778-109">The STA thread is either waiting without pumping messages or is performing lengthy operations and is not allowing the message queue to pump.</span></span>  
  
 <span data-ttu-id="9d778-110">El incremento en el uso de memoria con el tiempo está causado por el subproceso de finalizador que intenta llamar a `Release` en un componente COM sin administrar y que ese componente no devuelve.</span><span class="sxs-lookup"><span data-stu-id="9d778-110">Memory usage increasing over time is caused by the finalizer thread attempting to call `Release` on an unmanaged COM component and that component is not returning.</span></span>  <span data-ttu-id="9d778-111">Esto impide que el finalizador pueda recuperar otros objetos.</span><span class="sxs-lookup"><span data-stu-id="9d778-111">This prevents the finalizer from reclaiming other objects.</span></span>  
  
 <span data-ttu-id="9d778-112">De forma predeterminada, STA es el modelo de subprocesos del subproceso principal de aplicaciones de consola de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="9d778-112">By default, the threading model for the main thread of Visual Basic console applications is STA.</span></span> <span data-ttu-id="9d778-113">Este MDA se activa si un subproceso de STA usa la interoperabilidad de COM directa o indirectamente mediante Common Language Runtime o un control de terceros.</span><span class="sxs-lookup"><span data-stu-id="9d778-113">This MDA is activated if an STA thread uses COM interoperability either directly or indirectly through the common language runtime or a third-party control.</span></span>  <span data-ttu-id="9d778-114">Para evitar la activación de este MDA en una aplicación de consola de Visual Basic, aplique el atributo <xref:System.MTAThreadAttribute> al método principal o modifique la aplicación para que suministre mensajes.</span><span class="sxs-lookup"><span data-stu-id="9d778-114">To avoid activating this MDA in a Visual Basic console application, apply the <xref:System.MTAThreadAttribute> attribute to the main method or modify the application to pump messages.</span></span>  
  
 <span data-ttu-id="9d778-115">Es posible que el MDA se active equivocadamente si se cumplen todas las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="9d778-115">It is possible for this MDA to be falsely activated when all of the following conditions are met:</span></span>  
  
-   <span data-ttu-id="9d778-116">Una aplicación crea componentes COM a partir de subprocesos de STA directa o indirectamente a través de bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="9d778-116">An application creates COM components from STA threads either directly or indirectly through libraries.</span></span>  
  
-   <span data-ttu-id="9d778-117">La aplicación se detuvo en el depurador y el usuario continuó con la aplicación o realizó una operación de paso.</span><span class="sxs-lookup"><span data-stu-id="9d778-117">The application was stopped in the debugger and the user either continued the application or performed a step operation.</span></span>  
  
-   <span data-ttu-id="9d778-118">La depuración sin administrar no está habilitada.</span><span class="sxs-lookup"><span data-stu-id="9d778-118">Unmanaged debugging is not enabled.</span></span>  
  
 <span data-ttu-id="9d778-119">Para determinar si el MDA se activa equivocadamente, deshabilite todos los puntos de interrupción, reinicie la aplicación y deje que se ejecute sin detenerla.</span><span class="sxs-lookup"><span data-stu-id="9d778-119">To determine if the MDA is being falsely activated, disable all breakpoints, restart the application, and allow it to run without stopping.</span></span> <span data-ttu-id="9d778-120">Si el MDA no se activa, es probable que la activación inicial fuese falsa.</span><span class="sxs-lookup"><span data-stu-id="9d778-120">If the MDA is not activated, it is likely the initial activation was false.</span></span> <span data-ttu-id="9d778-121">En este caso, deshabilite el MDA para evitar interferencias con la sesión de depuración.</span><span class="sxs-lookup"><span data-stu-id="9d778-121">In this case, disable the MDA to avoid interference with the debugging session.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9d778-122">Este MDA está incluido de forma predeterminada en [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] y en versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="9d778-122">This MDA is in the default set for [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] and later versions.</span></span> <span data-ttu-id="9d778-123">Cuando el proceso de hospedaje está habilitado en [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], no se pueden deshabilitar los MDA que vienen incluidos de serie.</span><span class="sxs-lookup"><span data-stu-id="9d778-123">When the hosting process is enabled in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], you cannot disable MDAs that are in the default set.</span></span> <span data-ttu-id="9d778-124">De forma predeterminada, el proceso de hospedaje está habilitado, por lo que debe deshabilitarse explícitamente.</span><span class="sxs-lookup"><span data-stu-id="9d778-124">The hosting process is enabled by default, so it must be explicitly disabled.</span></span> <span data-ttu-id="9d778-125">Para más información sobre cómo deshabilitar MDA, vea "Enabling and Disabling MDAs (Habilitar y deshabilitar MDA)" en [Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span><span class="sxs-lookup"><span data-stu-id="9d778-125">For information about how to disable MDAs, see "Enabling and Disabling MDAs" in [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="9d778-126">Resolución</span><span class="sxs-lookup"><span data-stu-id="9d778-126">Resolution</span></span>  
 <span data-ttu-id="9d778-127">Siga las reglas COM respecto al suministro de mensajes de STA.</span><span class="sxs-lookup"><span data-stu-id="9d778-127">Follow COM rules regarding STA message pumping.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="9d778-128">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="9d778-128">Effect on the Runtime</span></span>  
 <span data-ttu-id="9d778-129">Este MDA no tiene ningún efecto en el CLR.</span><span class="sxs-lookup"><span data-stu-id="9d778-129">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="9d778-130">Solo recoge datos sobre contextos COM.</span><span class="sxs-lookup"><span data-stu-id="9d778-130">It only reports data about COM contexts.</span></span>  
  
## <a name="output"></a><span data-ttu-id="9d778-131">Salida</span><span class="sxs-lookup"><span data-stu-id="9d778-131">Output</span></span>  
 <span data-ttu-id="9d778-132">Mensaje que describe el contexto actual y el de destino.</span><span class="sxs-lookup"><span data-stu-id="9d778-132">A message describing the current context and the target context.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="9d778-133">Configuración</span><span class="sxs-lookup"><span data-stu-id="9d778-133">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <contextSwitchDeadlock />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9d778-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="9d778-134">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="9d778-135">Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)</span><span class="sxs-lookup"><span data-stu-id="9d778-135">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="9d778-136">Serialización de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="9d778-136">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
