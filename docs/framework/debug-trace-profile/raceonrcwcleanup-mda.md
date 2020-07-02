---
title: MDA de raceOnRCWCleanup
description: Revise el Asistente para la depuración administrada (MDA) de raceOnRCWCleanup, que se activa si el contenedor RCW está en uso en otro subproceso o en la pila de subprocesos de liberación en .NET.
ms.date: 03/30/2017
helpviewer_keywords:
- RCW
- managed debugging assistants (MDAs), RCWs
- race on RCW cleanup
- MDAs (managed debugging assistants), RCWs
- RaceOnRCWCleanup MDA
- runtime callable wrappers
ms.assetid: bee1e9b1-50a8-4c89-9cd9-7dd6b2458187
ms.openlocfilehash: e86ef96bebb648c7927ae5fec8b68fc4429b268b
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803656"
---
# <a name="raceonrcwcleanup-mda"></a><span data-ttu-id="4f80c-103">MDA de raceOnRCWCleanup</span><span class="sxs-lookup"><span data-stu-id="4f80c-103">raceOnRCWCleanup MDA</span></span>
<span data-ttu-id="4f80c-104">El asistente para la depuración administrada (MDA) de `raceOnRCWCleanup` se activa cuando Common Language Runtime (CLR) detecta que un [contenedor RCW](../../standard/native-interop/runtime-callable-wrapper.md) está en uso al realizar una llamada para liberarlo mediante un comando como el método <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4f80c-104">The `raceOnRCWCleanup` managed debugging assistant (MDA) is activated when the common language runtime (CLR) detects that a [Runtime Callable Wrapper](../../standard/native-interop/runtime-callable-wrapper.md) (RCW) is in use when a call to release it is made using a command such as the <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="4f80c-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="4f80c-105">Symptoms</span></span>  
 <span data-ttu-id="4f80c-106">Infracciones de acceso o daños en la memoria durante o después de la liberalización de RCW utilizando <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> o un método similar.</span><span class="sxs-lookup"><span data-stu-id="4f80c-106">Access violations or memory corruption during or after freeing an RCW using <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> or a similar method.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="4f80c-107">Causa</span><span class="sxs-lookup"><span data-stu-id="4f80c-107">Cause</span></span>  
 <span data-ttu-id="4f80c-108">RCW está en otro subproceso o en la pila de subprocesos de liberación.</span><span class="sxs-lookup"><span data-stu-id="4f80c-108">The RCW is in use on another thread or on the freeing thread stack.</span></span>  <span data-ttu-id="4f80c-109">No se puede liberar un RCW que esté en uso.</span><span class="sxs-lookup"><span data-stu-id="4f80c-109">An RCW that is in use cannot be released.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="4f80c-110">Resolución</span><span class="sxs-lookup"><span data-stu-id="4f80c-110">Resolution</span></span>  
 <span data-ttu-id="4f80c-111">No libere ningún RCW que pudiera estar en uso en este o en otros subprocesos.</span><span class="sxs-lookup"><span data-stu-id="4f80c-111">Do not free an RCW that could be in use either in the current or in other threads.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="4f80c-112">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="4f80c-112">Effect on the Runtime</span></span>  
 <span data-ttu-id="4f80c-113">Este MDA no tiene ningún efecto en el CLR.</span><span class="sxs-lookup"><span data-stu-id="4f80c-113">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="4f80c-114">Output</span><span class="sxs-lookup"><span data-stu-id="4f80c-114">Output</span></span>  
 <span data-ttu-id="4f80c-115">Un mensaje que describe el error.</span><span class="sxs-lookup"><span data-stu-id="4f80c-115">A message describing the error.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="4f80c-116">Configuración</span><span class="sxs-lookup"><span data-stu-id="4f80c-116">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <raceOnRCWCleanup/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4f80c-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="4f80c-117">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="4f80c-118">Diagnóstico de errores con asistentes de depuraciones administradas</span><span class="sxs-lookup"><span data-stu-id="4f80c-118">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="4f80c-119">Serialización de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="4f80c-119">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
