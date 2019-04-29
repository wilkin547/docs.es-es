---
title: MDA de raceOnRCWCleanup
ms.date: 03/30/2017
helpviewer_keywords:
- RCW
- managed debugging assistants (MDAs), RCWs
- race on RCW cleanup
- MDAs (managed debugging assistants), RCWs
- RaceOnRCWCleanup MDA
- runtime callable wrappers
ms.assetid: bee1e9b1-50a8-4c89-9cd9-7dd6b2458187
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 628790bb8229dc519589c122235f07a38ba57c1c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791580"
---
# <a name="raceonrcwcleanup-mda"></a><span data-ttu-id="167ec-102">MDA de raceOnRCWCleanup</span><span class="sxs-lookup"><span data-stu-id="167ec-102">raceOnRCWCleanup MDA</span></span>
<span data-ttu-id="167ec-103">El asistente para la depuración administrada (MDA) de `raceOnRCWCleanup` se activa cuando Common Language Runtime (CLR) detecta que un [contenedor RCW](../../../docs/framework/interop/runtime-callable-wrapper.md) está en uso al realizar una llamada para liberarlo mediante un comando como el método <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="167ec-103">The `raceOnRCWCleanup` managed debugging assistant (MDA) is activated when the common language runtime (CLR) detects that a [Runtime Callable Wrapper](../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW) is in use when a call to release it is made using a command such as the <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="167ec-104">Síntomas</span><span class="sxs-lookup"><span data-stu-id="167ec-104">Symptoms</span></span>  
 <span data-ttu-id="167ec-105">Infracciones de acceso o daños en la memoria durante o después de la liberalización de RCW utilizando <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> o un método similar.</span><span class="sxs-lookup"><span data-stu-id="167ec-105">Access violations or memory corruption during or after freeing an RCW using <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> or a similar method.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="167ec-106">Motivo</span><span class="sxs-lookup"><span data-stu-id="167ec-106">Cause</span></span>  
 <span data-ttu-id="167ec-107">RCW está en otro subproceso o en la pila de subprocesos de liberación.</span><span class="sxs-lookup"><span data-stu-id="167ec-107">The RCW is in use on another thread or on the freeing thread stack.</span></span>  <span data-ttu-id="167ec-108">No se puede liberar un RCW que esté en uso.</span><span class="sxs-lookup"><span data-stu-id="167ec-108">An RCW that is in use cannot be released.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="167ec-109">Resolución</span><span class="sxs-lookup"><span data-stu-id="167ec-109">Resolution</span></span>  
 <span data-ttu-id="167ec-110">No libere ningún RCW que pudiera estar en uso en este o en otros subprocesos.</span><span class="sxs-lookup"><span data-stu-id="167ec-110">Do not free an RCW that could be in use either in the current or in other threads.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="167ec-111">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="167ec-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="167ec-112">Este MDA no tiene ningún efecto en el CLR.</span><span class="sxs-lookup"><span data-stu-id="167ec-112">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="167ec-113">Salida</span><span class="sxs-lookup"><span data-stu-id="167ec-113">Output</span></span>  
 <span data-ttu-id="167ec-114">Un mensaje que describe el error.</span><span class="sxs-lookup"><span data-stu-id="167ec-114">A message describing the error.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="167ec-115">Configuración</span><span class="sxs-lookup"><span data-stu-id="167ec-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <raceOnRCWCleanup/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="167ec-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="167ec-116">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="167ec-117">Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)</span><span class="sxs-lookup"><span data-stu-id="167ec-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="167ec-118">Serialización de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="167ec-118">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
