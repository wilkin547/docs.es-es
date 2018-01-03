---
title: MDA de invalidVariant
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid variant
- VARIANT type errors
- InvalidVariant MDA
- invalid VARIANT types
- managed debugging assistants (MDAs), invalid variant
ms.assetid: d273e070-d1b1-4a53-a9c7-7af837b04a3d
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f97fb7f9bdb144f2b586c387f33211734f664eb0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="invalidvariant-mda"></a><span data-ttu-id="5eacc-102">MDA de invalidVariant</span><span class="sxs-lookup"><span data-stu-id="5eacc-102">invalidVariant MDA</span></span>
<span data-ttu-id="5eacc-103">El asistente para la depuración administrada (MDA) de `invalidVariant` se activa cuando se encuentra una estructura `VARIANT` no válida durante una llamada de código nativo o no administrado a un código administrado.</span><span class="sxs-lookup"><span data-stu-id="5eacc-103">The `invalidVariant` managed debugging assistant (MDA) is activated when an invalid `VARIANT` structure is encountered during a call from native or unmanaged code to managed code.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="5eacc-104">Síntomas</span><span class="sxs-lookup"><span data-stu-id="5eacc-104">Symptoms</span></span>  
 <span data-ttu-id="5eacc-105">Comportamiento inesperado durante una transición entre código nativo y administrado que implica el cálculo de referencias de `VARIANT` a un objeto.</span><span class="sxs-lookup"><span data-stu-id="5eacc-105">Unexpected behavior during a transition between native and managed code involving the marshaling of a `VARIANT` to an object.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="5eacc-106">Motivo</span><span class="sxs-lookup"><span data-stu-id="5eacc-106">Cause</span></span>  
 <span data-ttu-id="5eacc-107">El código nativo está pasando una estructura `VARIANT` incorrecta al código administrado.</span><span class="sxs-lookup"><span data-stu-id="5eacc-107">Native code is passing a malformed `VARIANT` structure to managed code.</span></span>  <span data-ttu-id="5eacc-108">El motor en tiempo de ejecución intenta calcular las referencias de `VARIANT` a un objeto y activa el MDA si `VARIANT` no es válido.</span><span class="sxs-lookup"><span data-stu-id="5eacc-108">The runtime attempts to marshal this `VARIANT` to an object and activates the MDA if the `VARIANT` is not valid.</span></span> <span data-ttu-id="5eacc-109">Los ejemplos de `VARIANT` no válidas incluyen `VARIANT` con `VARTYPE` VT_EMPTY &#124; VT_BYREF o `VARIANT` con `VARTYPE` VT_VARIANT.</span><span class="sxs-lookup"><span data-stu-id="5eacc-109">Examples of invalid `VARIANT`S include a `VARIANT` with `VARTYPE` VT_EMPTY &#124; VT_BYREF or a `VARIANT` with `VARTYPE` VT_VARIANT.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="5eacc-110">Resolución</span><span class="sxs-lookup"><span data-stu-id="5eacc-110">Resolution</span></span>  
 <span data-ttu-id="5eacc-111">El paso de `VARIANT` por parte del código nativo o no administrado debe garantizar que `VARIANT` se forme e inicialice correctamente.</span><span class="sxs-lookup"><span data-stu-id="5eacc-111">The native or unmanaged code passing the `VARIANT` must ensure that the `VARIANT` is correctly formed and initialized.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="5eacc-112">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="5eacc-112">Effect on the Runtime</span></span>  
 <span data-ttu-id="5eacc-113">Este MDA no tiene ningún efecto en el comportamiento del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5eacc-113">The MDA has no effect on the runtime's behavior.</span></span>  
  
## <a name="output"></a><span data-ttu-id="5eacc-114">Resultado</span><span class="sxs-lookup"><span data-stu-id="5eacc-114">Output</span></span>  
 <span data-ttu-id="5eacc-115">Un mensaje de MDA que indica que el motor en tiempo de ejecución detectó una `VARIANT` no válida pasada a código administrado mediante un módulo no administrado.</span><span class="sxs-lookup"><span data-stu-id="5eacc-115">An MDA message indicating that the runtime detected an invalid `VARIANT` passed to managed code by an unmanaged module.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="5eacc-116">Configuración</span><span class="sxs-lookup"><span data-stu-id="5eacc-116">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidVariant />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5eacc-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="5eacc-117">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="5eacc-118">Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)</span><span class="sxs-lookup"><span data-stu-id="5eacc-118">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="5eacc-119">Serialización de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="5eacc-119">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
