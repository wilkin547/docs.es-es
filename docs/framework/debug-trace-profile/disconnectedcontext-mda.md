---
title: MDA de disconnectedContext
ms.date: 03/30/2017
helpviewer_keywords:
- DisconnectedContext MDA
- MDAs (managed debugging assistants), disconnected context
- dead context
- transitioning disconnected apartment or context
- context disconnections
- managed debugging assistants (MDAs), disconnected context
ms.assetid: 1887d31d-7006-4491-93b3-68fd5b05f71d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1819fffaf2eccb6a26578eaf993100b8eca7c76e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966434"
---
# <a name="disconnectedcontext-mda"></a><span data-ttu-id="aee44-102">MDA de disconnectedContext</span><span class="sxs-lookup"><span data-stu-id="aee44-102">disconnectedContext MDA</span></span>
<span data-ttu-id="aee44-103">El asistente para la depuración administrada (MDA, por sus siglas en inglés) `disconnectedContext` se activa cuando el CLR intenta realizar una transición a un contexto o apartamento desconectado mientras atiende una solicitud relativa a un objeto COM.</span><span class="sxs-lookup"><span data-stu-id="aee44-103">The `disconnectedContext` managed debugging assistant (MDA) is activated when the CLR attempts to transition into a disconnected apartment or context while servicing a request concerning a COM object.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="aee44-104">Síntomas</span><span class="sxs-lookup"><span data-stu-id="aee44-104">Symptoms</span></span>  
 <span data-ttu-id="aee44-105">Las llamadas realizadas en un [contenedor RCW](../../standard/native-interop/runtime-callable-wrapper.md) (RCW) se entregan al componente COM subyacente en el contexto o apartamento actual, en vez de entregarse en el que existen.</span><span class="sxs-lookup"><span data-stu-id="aee44-105">Calls made on a [Runtime Callable Wrapper](../../standard/native-interop/runtime-callable-wrapper.md) (RCW) are delivered to the underlying COM component in the current apartment or context instead of the one in which they exist.</span></span> <span data-ttu-id="aee44-106">Esto puede causar daños o pérdida de datos si el componente COM no es multiproceso, como en el caso de componentes de contenedor uniproceso (STA, por sus siglas en inglés).</span><span class="sxs-lookup"><span data-stu-id="aee44-106">This can cause corruption and or data loss if the COM component is not multithreaded, as in the case of single-threaded apartment (STA) components.</span></span> <span data-ttu-id="aee44-107">O bien, si el RCW es un proxy, la llamada puede producir una <xref:System.Runtime.InteropServices.COMException> con un HRESULT de RPC_E_WRONG_THREAD.</span><span class="sxs-lookup"><span data-stu-id="aee44-107">Alternatively, if the RCW is itself a proxy, the call might result in the throwing of a <xref:System.Runtime.InteropServices.COMException> with an HRESULT of RPC_E_WRONG_THREAD.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="aee44-108">Causa</span><span class="sxs-lookup"><span data-stu-id="aee44-108">Cause</span></span>  
 <span data-ttu-id="aee44-109">El apartamento o contexto OLE se cierra cuando el CLR intenta realizar una transición hacia él.</span><span class="sxs-lookup"><span data-stu-id="aee44-109">The OLE apartment or context has been shut down when the CLR attempts to transition into it.</span></span> <span data-ttu-id="aee44-110">Con frecuencia, la causa es que los contenedores STA se cierran antes de que todos los componentes COM propiedad del apartamento se liberen completamente. Esto puede deberse a una llamada explícita del código de usuario en un RCW o mientras el CLR manipula el componente COM, por ejemplo, cuando el CLR libera el componente COM si el RCW asociado se ha recolectado por no utilizarse.</span><span class="sxs-lookup"><span data-stu-id="aee44-110">This is most commonly caused by STA apartments being shut down before all the COM components owned by the apartment were completely released This can occur as a result of an explicit call from user code on an RCW or while the CLR itself is manipulating the COM component, for example when the CLR is releasing the COM component when the associated RCW has been garbage collected.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="aee44-111">Resolución</span><span class="sxs-lookup"><span data-stu-id="aee44-111">Resolution</span></span>  
 <span data-ttu-id="aee44-112">Para evitar este problema, asegúrese de que el subproceso que posee el STA no termina antes de que la aplicación haya finalizado con todos los objetos que habitan en el apartamento.</span><span class="sxs-lookup"><span data-stu-id="aee44-112">To avoid this problem, ensure the thread that owns the STA does not terminate before the application has finished with all the objects that live in the apartment.</span></span> <span data-ttu-id="aee44-113">Lo mismo es aplicable a los contextos; asegúrese de que estos no se cierran antes de que la aplicación finalice completamente con todos los componentes COM que habitan en el contexto.</span><span class="sxs-lookup"><span data-stu-id="aee44-113">The same applies to contexts; ensure contexts are not shut down before the application is completely finished with any COM components that live inside the context.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="aee44-114">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="aee44-114">Effect on the Runtime</span></span>  
 <span data-ttu-id="aee44-115">Este MDA no tiene ningún efecto en el CLR.</span><span class="sxs-lookup"><span data-stu-id="aee44-115">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="aee44-116">Solo recoge datos sobre el contexto desconectado.</span><span class="sxs-lookup"><span data-stu-id="aee44-116">It only reports data about the disconnected context.</span></span>  
  
## <a name="output"></a><span data-ttu-id="aee44-117">Salida</span><span class="sxs-lookup"><span data-stu-id="aee44-117">Output</span></span>  
 <span data-ttu-id="aee44-118">Recoge la cookie de contexto del apartamento o contexto desconectado.</span><span class="sxs-lookup"><span data-stu-id="aee44-118">Reports the context cookie of the disconnected apartment or context.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="aee44-119">Configuración</span><span class="sxs-lookup"><span data-stu-id="aee44-119">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <disconnectedContext />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="aee44-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="aee44-120">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="aee44-121">Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)</span><span class="sxs-lookup"><span data-stu-id="aee44-121">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="aee44-122">Serialización de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="aee44-122">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
