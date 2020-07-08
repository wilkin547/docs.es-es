---
title: MDA de marshalCleanupError
description: Revise el Asistente para la depuración administrada (MDA) marshalCleanupError, que se invoca porque se produjo un error inesperado al limpiar las estructuras temporales.
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
ms.openlocfilehash: 3c7498d6f51484de3a2e84d611a2634f53724ab6
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051617"
---
# <a name="marshalcleanuperror-mda"></a><span data-ttu-id="c7b3f-103">MDA de marshalCleanupError</span><span class="sxs-lookup"><span data-stu-id="c7b3f-103">marshalCleanupError MDA</span></span>
<span data-ttu-id="c7b3f-104">El asistente para la depuración administrada (MDA, por sus siglas en inglés) `marshalCleanupError` se activa cuando Common Language Runtime (CLR) detecta un error al intentar limpiar la memoria y las estructuras temporales que se usan para serializar tipos de datos entre los límites del código nativo y administrado.</span><span class="sxs-lookup"><span data-stu-id="c7b3f-104">The `marshalCleanupError` managed debugging assistant (MDA) is activated when the common language runtime (CLR) encounters an error while attempting to clean up temporary structures and memory used for marshaling data types between native and managed code boundaries.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="c7b3f-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="c7b3f-105">Symptoms</span></span>  
 <span data-ttu-id="c7b3f-106">Se produce una fuga de memoria al realizar transiciones de código nativo y administrado, cuando no se restaura un estado de runtime (por ejemplo, una referencia cultural de subproceso) o si la limpieza de <xref:System.Runtime.InteropServices.SafeHandle> tiene errores.</span><span class="sxs-lookup"><span data-stu-id="c7b3f-106">A memory leak occurs when making native and managed code transitions, runtime state such as thread culture is not restored, or errors occur in <xref:System.Runtime.InteropServices.SafeHandle> cleanup.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="c7b3f-107">Causa</span><span class="sxs-lookup"><span data-stu-id="c7b3f-107">Cause</span></span>  
 <span data-ttu-id="c7b3f-108">Se produjo un error inesperado al limpiar las estructuras temporales.</span><span class="sxs-lookup"><span data-stu-id="c7b3f-108">An unexpected error occurred while cleaning up temporary structures.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="c7b3f-109">Resolución</span><span class="sxs-lookup"><span data-stu-id="c7b3f-109">Resolution</span></span>  
 <span data-ttu-id="c7b3f-110">Revise todas las implementaciones de destructor, finalizador y cálculo de referencias de <xref:System.Runtime.InteropServices.SafeHandle> para comprobar si hay errores.</span><span class="sxs-lookup"><span data-stu-id="c7b3f-110">Review all <xref:System.Runtime.InteropServices.SafeHandle> destructor, finalizer, and custom marshaler implementations for errors.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="c7b3f-111">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="c7b3f-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="c7b3f-112">Este MDA no tiene ningún efecto en el CLR.</span><span class="sxs-lookup"><span data-stu-id="c7b3f-112">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="c7b3f-113">Output</span><span class="sxs-lookup"><span data-stu-id="c7b3f-113">Output</span></span>  
 <span data-ttu-id="c7b3f-114">Un mensaje que indica que se produjo un error en la operación durante la limpieza.</span><span class="sxs-lookup"><span data-stu-id="c7b3f-114">A message reporting the operation that failed during cleanup.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="c7b3f-115">Configuración</span><span class="sxs-lookup"><span data-stu-id="c7b3f-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <marshalCleanupError />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c7b3f-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="c7b3f-116">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="c7b3f-117">Diagnóstico de errores con asistentes de depuraciones administradas</span><span class="sxs-lookup"><span data-stu-id="c7b3f-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="c7b3f-118">Serialización de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="c7b3f-118">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
