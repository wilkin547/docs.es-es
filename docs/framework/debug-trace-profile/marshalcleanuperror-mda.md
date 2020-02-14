---
title: MDA de marshalCleanupError
ms.date: 03/30/2017
helpviewer_keywords:
- cleanup operations
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
- marshaling cleanup error
- MarshalCleanupError MDA
- memory, cleanup errors
ms.assetid: 2f5d9e7c-ae51-4155-a435-54347aa1f091
ms.openlocfilehash: 1a14c548ce960d53f47934595171189db28edfbb
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216152"
---
# <a name="marshalcleanuperror-mda"></a><span data-ttu-id="7ea2d-102">MDA de marshalCleanupError</span><span class="sxs-lookup"><span data-stu-id="7ea2d-102">marshalCleanupError MDA</span></span>
<span data-ttu-id="7ea2d-103">El asistente para la depuración administrada (MDA, por sus siglas en inglés) `marshalCleanupError` se activa cuando Common Language Runtime (CLR) detecta un error al intentar limpiar la memoria y las estructuras temporales que se usan para serializar tipos de datos entre los límites del código nativo y administrado.</span><span class="sxs-lookup"><span data-stu-id="7ea2d-103">The `marshalCleanupError` managed debugging assistant (MDA) is activated when the common language runtime (CLR) encounters an error while attempting to clean up temporary structures and memory used for marshaling data types between native and managed code boundaries.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="7ea2d-104">Síntomas</span><span class="sxs-lookup"><span data-stu-id="7ea2d-104">Symptoms</span></span>  
 <span data-ttu-id="7ea2d-105">Se produce una fuga de memoria al realizar transiciones de código nativo y administrado, cuando no se restaura un estado de runtime (por ejemplo, una referencia cultural de subproceso) o si la limpieza de <xref:System.Runtime.InteropServices.SafeHandle> tiene errores.</span><span class="sxs-lookup"><span data-stu-id="7ea2d-105">A memory leak occurs when making native and managed code transitions, runtime state such as thread culture is not restored, or errors occur in <xref:System.Runtime.InteropServices.SafeHandle> cleanup.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="7ea2d-106">Causa</span><span class="sxs-lookup"><span data-stu-id="7ea2d-106">Cause</span></span>  
 <span data-ttu-id="7ea2d-107">Se produjo un error inesperado al limpiar las estructuras temporales.</span><span class="sxs-lookup"><span data-stu-id="7ea2d-107">An unexpected error occurred while cleaning up temporary structures.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="7ea2d-108">Solución</span><span class="sxs-lookup"><span data-stu-id="7ea2d-108">Resolution</span></span>  
 <span data-ttu-id="7ea2d-109">Revise todas las implementaciones de destructor, finalizador y cálculo de referencias de <xref:System.Runtime.InteropServices.SafeHandle> para comprobar si hay errores.</span><span class="sxs-lookup"><span data-stu-id="7ea2d-109">Review all <xref:System.Runtime.InteropServices.SafeHandle> destructor, finalizer, and custom marshaler implementations for errors.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="7ea2d-110">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="7ea2d-110">Effect on the Runtime</span></span>  
 <span data-ttu-id="7ea2d-111">Este MDA no tiene ningún efecto en el CLR.</span><span class="sxs-lookup"><span data-stu-id="7ea2d-111">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="7ea2d-112">Output</span><span class="sxs-lookup"><span data-stu-id="7ea2d-112">Output</span></span>  
 <span data-ttu-id="7ea2d-113">Un mensaje que indica que se produjo un error en la operación durante la limpieza.</span><span class="sxs-lookup"><span data-stu-id="7ea2d-113">A message reporting the operation that failed during cleanup.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="7ea2d-114">Configuración</span><span class="sxs-lookup"><span data-stu-id="7ea2d-114">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <marshalCleanupError />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7ea2d-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7ea2d-115">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="7ea2d-116">Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)</span><span class="sxs-lookup"><span data-stu-id="7ea2d-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="7ea2d-117">Serialización para interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="7ea2d-117">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
