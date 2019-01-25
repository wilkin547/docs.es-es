---
title: MDA de overlappedFreeError
ms.date: 03/30/2017
helpviewer_keywords:
- OverlappedFreeError MDA
- overlapped free method call error
- managed debugging assistants (MDAs), overlapped structures
- overlapped structures
- MDAs (managed debugging assistants), overlapped structures
- freeing overlapped structures
ms.assetid: b6ab2d48-6eee-4bab-97a3-046b3b0a5470
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 675e2e4d5022f0260450f9f0b2025f215b3ead7e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54708292"
---
# <a name="overlappedfreeerror-mda"></a><span data-ttu-id="54b93-102">MDA de overlappedFreeError</span><span class="sxs-lookup"><span data-stu-id="54b93-102">overlappedFreeError MDA</span></span>
<span data-ttu-id="54b93-103">El Asistente para la depuración administrada (MDA) `overlappedFreeError` se activa cuando se llama al método <xref:System.Threading.Overlapped.Free%28System.Threading.NativeOverlapped%2A%29?displayProperty=nameWithType> antes de que se haya completado la operación superpuesta.</span><span class="sxs-lookup"><span data-stu-id="54b93-103">The `overlappedFreeError` managed debugging assistant (MDA) is activated when the <xref:System.Threading.Overlapped.Free%28System.Threading.NativeOverlapped%2A%29?displayProperty=nameWithType> method is called before the overlapped operation has completed.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="54b93-104">Síntomas</span><span class="sxs-lookup"><span data-stu-id="54b93-104">Symptoms</span></span>  
 <span data-ttu-id="54b93-105">Infracciones de acceso o daños en el montón de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="54b93-105">Access violations or corruption of the garbage-collected heap.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="54b93-106">Motivo</span><span class="sxs-lookup"><span data-stu-id="54b93-106">Cause</span></span>  
 <span data-ttu-id="54b93-107">Una estructura superpuesta se liberó antes de finalizar la operación.</span><span class="sxs-lookup"><span data-stu-id="54b93-107">An overlapped structure was freed before the operation completed.</span></span> <span data-ttu-id="54b93-108">Es posible que la función que está usando el puntero superpuesto escriba en la estructura más adelante, después de que se haya liberado.</span><span class="sxs-lookup"><span data-stu-id="54b93-108">The function that is using the overlapped pointer might write to the structure later, after it has been freed.</span></span> <span data-ttu-id="54b93-109">Esto puede provocar daños en el montón porque es posible que ahora otro objeto ocupe esa región.</span><span class="sxs-lookup"><span data-stu-id="54b93-109">That can cause heap corruption because another object might now occupy that region.</span></span>  
  
 <span data-ttu-id="54b93-110">Es posible que este MDA no represente un error si la operación superpuesta no se inició correctamente.</span><span class="sxs-lookup"><span data-stu-id="54b93-110">This MDA might not represent an error if the overlapped operation did not start successfully.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="54b93-111">Resolución</span><span class="sxs-lookup"><span data-stu-id="54b93-111">Resolution</span></span>  
 <span data-ttu-id="54b93-112">Asegúrese de que se complete la operación de E/S que usa la estructura superpuesta antes de llamar al método <xref:System.Threading.Overlapped.Free%28System.Threading.NativeOverlapped%2A%29>.</span><span class="sxs-lookup"><span data-stu-id="54b93-112">Ensure that the I/O operation using the overlapped structure has completed before calling the <xref:System.Threading.Overlapped.Free%28System.Threading.NativeOverlapped%2A%29> method.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="54b93-113">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="54b93-113">Effect on the Runtime</span></span>  
 <span data-ttu-id="54b93-114">Este MDA no tiene ningún efecto en el CLR.</span><span class="sxs-lookup"><span data-stu-id="54b93-114">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="54b93-115">Salida</span><span class="sxs-lookup"><span data-stu-id="54b93-115">Output</span></span>  
 <span data-ttu-id="54b93-116">A continuación puede ver un resultado de ejemplo para este MDA.</span><span class="sxs-lookup"><span data-stu-id="54b93-116">The following is sample output for this MDA.</span></span>  
  
 `An overlapped pointer (0x00ea3430) that was not allocated on the GC heap was passed via Pinvoke to the win32 function 'WriteFile' in module 'KERNEL32.DLL'. If the AppDomain is shut down, this can cause heap corruption when the async I/O completes. The best solution is to pass a NativeOverlappedStructure retrieved from a call to System.Threading.Overlapped.Pack(). If the AppDomain exits, the CLR will keep this structure alive and pinned until the I/O completes.`  
  
## <a name="configuration"></a><span data-ttu-id="54b93-117">Configuración</span><span class="sxs-lookup"><span data-stu-id="54b93-117">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <overlappedFreeError/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="54b93-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="54b93-118">See also</span></span>
- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="54b93-119">Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)</span><span class="sxs-lookup"><span data-stu-id="54b93-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="54b93-120">Serialización de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="54b93-120">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
