---
title: MDA de contextSwitchDeadlock
ms.date: 03/30/2017
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
ms.openlocfilehash: e3fc4a2cb35cdcc713ba0ef362071083af08a27b
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217555"
---
# <a name="contextswitchdeadlock-mda"></a><span data-ttu-id="7571f-102">MDA de contextSwitchDeadlock</span><span class="sxs-lookup"><span data-stu-id="7571f-102">contextSwitchDeadlock MDA</span></span>

<span data-ttu-id="7571f-103">El asistente para la depuración administrada (MDA, por sus siglas en inglés) `contextSwitchDeadlock` se activa cuando se detecta un interbloqueo durante un intento de transición de contexto COM.</span><span class="sxs-lookup"><span data-stu-id="7571f-103">The `contextSwitchDeadlock` managed debugging assistant (MDA) is activated when a deadlock is detected during an attempted COM context transition.</span></span>

## <a name="symptoms"></a><span data-ttu-id="7571f-104">Síntomas</span><span class="sxs-lookup"><span data-stu-id="7571f-104">Symptoms</span></span>

<span data-ttu-id="7571f-105">El síntoma más común es que no se devuelve una llamada en un componente COM sin administrar de código administrado.</span><span class="sxs-lookup"><span data-stu-id="7571f-105">The most common symptom is that a call on an unmanaged COM component from managed code does not return.</span></span>  <span data-ttu-id="7571f-106">Otro síntoma es el aumento de uso de memoria con el tiempo.</span><span class="sxs-lookup"><span data-stu-id="7571f-106">Another symptom is memory usage increasing over time.</span></span>

## <a name="cause"></a><span data-ttu-id="7571f-107">Causa</span><span class="sxs-lookup"><span data-stu-id="7571f-107">Cause</span></span>

<span data-ttu-id="7571f-108">La causa más probable es que haya un subproceso de contenedor uniproceso (STA, por sus siglas en inglés) que no esté suministrando mensajes.</span><span class="sxs-lookup"><span data-stu-id="7571f-108">The most probable cause is that a single-threaded apartment (STA) thread is not pumping messages.</span></span> <span data-ttu-id="7571f-109">El subproceso de STA está en espera sin suministrar mensajes o está realizando operaciones extensas y no permite que la cola de mensajes se suministre.</span><span class="sxs-lookup"><span data-stu-id="7571f-109">The STA thread is either waiting without pumping messages or is performing lengthy operations and is not allowing the message queue to pump.</span></span>

<span data-ttu-id="7571f-110">El incremento en el uso de memoria con el tiempo está causado por el subproceso de finalizador que intenta llamar a `Release` en un componente COM sin administrar y que ese componente no devuelve.</span><span class="sxs-lookup"><span data-stu-id="7571f-110">Memory usage increasing over time is caused by the finalizer thread attempting to call `Release` on an unmanaged COM component and that component is not returning.</span></span>  <span data-ttu-id="7571f-111">Esto impide que el finalizador pueda recuperar otros objetos.</span><span class="sxs-lookup"><span data-stu-id="7571f-111">This prevents the finalizer from reclaiming other objects.</span></span>

<span data-ttu-id="7571f-112">De forma predeterminada, STA es el modelo de subprocesos del subproceso principal de aplicaciones de consola de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="7571f-112">By default, the threading model for the main thread of Visual Basic console applications is STA.</span></span> <span data-ttu-id="7571f-113">Este MDA se activa si un subproceso de STA usa la interoperabilidad de COM directa o indirectamente mediante Common Language Runtime o un control de terceros.</span><span class="sxs-lookup"><span data-stu-id="7571f-113">This MDA is activated if an STA thread uses COM interoperability either directly or indirectly through the common language runtime or a third-party control.</span></span>  <span data-ttu-id="7571f-114">Para evitar la activación de este MDA en una aplicación de consola de Visual Basic, aplique el atributo <xref:System.MTAThreadAttribute> al método principal o modifique la aplicación para que suministre mensajes.</span><span class="sxs-lookup"><span data-stu-id="7571f-114">To avoid activating this MDA in a Visual Basic console application, apply the <xref:System.MTAThreadAttribute> attribute to the main method or modify the application to pump messages.</span></span>

<span data-ttu-id="7571f-115">Es posible que el MDA se active equivocadamente si se cumplen todas las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="7571f-115">It is possible for this MDA to be falsely activated when all of the following conditions are met:</span></span>

- <span data-ttu-id="7571f-116">Una aplicación crea componentes COM a partir de subprocesos de STA directa o indirectamente a través de bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="7571f-116">An application creates COM components from STA threads either directly or indirectly through libraries.</span></span>

- <span data-ttu-id="7571f-117">La aplicación se detuvo en el depurador y el usuario continuó con la aplicación o realizó una operación de paso.</span><span class="sxs-lookup"><span data-stu-id="7571f-117">The application was stopped in the debugger and the user either continued the application or performed a step operation.</span></span>

- <span data-ttu-id="7571f-118">La depuración sin administrar no está habilitada.</span><span class="sxs-lookup"><span data-stu-id="7571f-118">Unmanaged debugging is not enabled.</span></span>

<span data-ttu-id="7571f-119">Para determinar si el MDA se activa equivocadamente, deshabilite todos los puntos de interrupción, reinicie la aplicación y deje que se ejecute sin detenerla.</span><span class="sxs-lookup"><span data-stu-id="7571f-119">To determine if the MDA is being falsely activated, disable all breakpoints, restart the application, and allow it to run without stopping.</span></span> <span data-ttu-id="7571f-120">Si el MDA no se activa, es probable que la activación inicial fuese falsa.</span><span class="sxs-lookup"><span data-stu-id="7571f-120">If the MDA is not activated, it is likely the initial activation was false.</span></span> <span data-ttu-id="7571f-121">En este caso, deshabilite el MDA para evitar interferencias con la sesión de depuración.</span><span class="sxs-lookup"><span data-stu-id="7571f-121">In this case, disable the MDA to avoid interference with the debugging session.</span></span>

> [!NOTE]
> <span data-ttu-id="7571f-122">Este MDA está en el conjunto predeterminado de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7571f-122">This MDA is in the default set for Visual Studio.</span></span> <span data-ttu-id="7571f-123">Para obtener información sobre cómo deshabilitar los MDA, vea [diagnosticar errores con asistentes para la depuración administrada](diagnosing-errors-with-managed-debugging-assistants.md#enable-and-disable-mdas).</span><span class="sxs-lookup"><span data-stu-id="7571f-123">For information about how to disable MDAs, see [Diagnosing Errors with Managed Debugging Assistants](diagnosing-errors-with-managed-debugging-assistants.md#enable-and-disable-mdas).</span></span>

## <a name="resolution"></a><span data-ttu-id="7571f-124">Solución</span><span class="sxs-lookup"><span data-stu-id="7571f-124">Resolution</span></span>

<span data-ttu-id="7571f-125">Siga las reglas COM respecto al suministro de mensajes de STA.</span><span class="sxs-lookup"><span data-stu-id="7571f-125">Follow COM rules regarding STA message pumping.</span></span>

## <a name="effect-on-the-runtime"></a><span data-ttu-id="7571f-126">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="7571f-126">Effect on the Runtime</span></span>

<span data-ttu-id="7571f-127">Este MDA no tiene ningún efecto en el CLR.</span><span class="sxs-lookup"><span data-stu-id="7571f-127">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="7571f-128">Solo recoge datos sobre contextos COM.</span><span class="sxs-lookup"><span data-stu-id="7571f-128">It only reports data about COM contexts.</span></span>

## <a name="output"></a><span data-ttu-id="7571f-129">Output</span><span class="sxs-lookup"><span data-stu-id="7571f-129">Output</span></span>

<span data-ttu-id="7571f-130">Mensaje que describe el contexto actual y el de destino.</span><span class="sxs-lookup"><span data-stu-id="7571f-130">A message describing the current context and the target context.</span></span>

## <a name="configuration"></a><span data-ttu-id="7571f-131">Configuración</span><span class="sxs-lookup"><span data-stu-id="7571f-131">Configuration</span></span>

```xml
<mdaConfig>
  <assistants>
    <contextSwitchDeadlock />
  </assistants>
</mdaConfig>
```

## <a name="see-also"></a><span data-ttu-id="7571f-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7571f-132">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="7571f-133">Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)</span><span class="sxs-lookup"><span data-stu-id="7571f-133">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="7571f-134">Serialización para interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="7571f-134">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
