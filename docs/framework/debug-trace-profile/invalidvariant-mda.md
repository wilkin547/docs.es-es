---
title: MDA de invalidVariant
description: Revise el Asistente para la depuración administrada invalidVariant, que se invoca si se encuentra una variante no válida en una llamada desde código nativo/no administrado a código administrado.
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid variant
- VARIANT type errors
- InvalidVariant MDA
- invalid VARIANT types
- managed debugging assistants (MDAs), invalid variant
ms.assetid: d273e070-d1b1-4a53-a9c7-7af837b04a3d
ms.openlocfilehash: ab1233d9faa86ef1508fa8fe2b5af46cb37bd523
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051641"
---
# <a name="invalidvariant-mda"></a><span data-ttu-id="88f9d-103">MDA de invalidVariant</span><span class="sxs-lookup"><span data-stu-id="88f9d-103">invalidVariant MDA</span></span>
<span data-ttu-id="88f9d-104">El asistente para la depuración administrada (MDA) de `invalidVariant` se activa cuando se encuentra una estructura `VARIANT` no válida durante una llamada de código nativo o no administrado a un código administrado.</span><span class="sxs-lookup"><span data-stu-id="88f9d-104">The `invalidVariant` managed debugging assistant (MDA) is activated when an invalid `VARIANT` structure is encountered during a call from native or unmanaged code to managed code.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="88f9d-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="88f9d-105">Symptoms</span></span>  
 <span data-ttu-id="88f9d-106">Comportamiento inesperado durante una transición entre código nativo y administrado que implica la serialización de `VARIANT` a un objeto.</span><span class="sxs-lookup"><span data-stu-id="88f9d-106">Unexpected behavior during a transition between native and managed code involving the marshaling of a `VARIANT` to an object.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="88f9d-107">Causa</span><span class="sxs-lookup"><span data-stu-id="88f9d-107">Cause</span></span>  
 <span data-ttu-id="88f9d-108">El código nativo está pasando una estructura `VARIANT` incorrecta al código administrado.</span><span class="sxs-lookup"><span data-stu-id="88f9d-108">Native code is passing a malformed `VARIANT` structure to managed code.</span></span>  <span data-ttu-id="88f9d-109"> El motor en tiempo de ejecución intenta calcular las referencias de `VARIANT` a un objeto y activa el MDA si `VARIANT` no es válido.</span><span class="sxs-lookup"><span data-stu-id="88f9d-109">The runtime attempts to marshal this `VARIANT` to an object and activates the MDA if the `VARIANT` is not valid.</span></span> <span data-ttu-id="88f9d-110">Los ejemplos de `VARIANT` no válidas incluyen `VARIANT` con `VARTYPE` VT_EMPTY &#124; VT_BYREF o `VARIANT` con `VARTYPE` VT_VARIANT.</span><span class="sxs-lookup"><span data-stu-id="88f9d-110">Examples of invalid `VARIANT`S include a `VARIANT` with `VARTYPE` VT_EMPTY &#124; VT_BYREF or a `VARIANT` with `VARTYPE` VT_VARIANT.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="88f9d-111">Resolución</span><span class="sxs-lookup"><span data-stu-id="88f9d-111">Resolution</span></span>  
 <span data-ttu-id="88f9d-112">El paso de `VARIANT` por parte del código nativo o no administrado debe garantizar que `VARIANT` se forme e inicialice correctamente.</span><span class="sxs-lookup"><span data-stu-id="88f9d-112">The native or unmanaged code passing the `VARIANT` must ensure that the `VARIANT` is correctly formed and initialized.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="88f9d-113">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="88f9d-113">Effect on the Runtime</span></span>  
 <span data-ttu-id="88f9d-114">Este MDA no tiene ningún efecto en el comportamiento del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="88f9d-114">The MDA has no effect on the runtime's behavior.</span></span>  
  
## <a name="output"></a><span data-ttu-id="88f9d-115">Output</span><span class="sxs-lookup"><span data-stu-id="88f9d-115">Output</span></span>  
 <span data-ttu-id="88f9d-116">Un mensaje de MDA que indica que el motor en tiempo de ejecución detectó una `VARIANT` no válida pasada a código administrado mediante un módulo no administrado.</span><span class="sxs-lookup"><span data-stu-id="88f9d-116">An MDA message indicating that the runtime detected an invalid `VARIANT` passed to managed code by an unmanaged module.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="88f9d-117">Configuración</span><span class="sxs-lookup"><span data-stu-id="88f9d-117">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidVariant />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="88f9d-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="88f9d-118">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="88f9d-119">Diagnóstico de errores con asistentes de depuraciones administradas</span><span class="sxs-lookup"><span data-stu-id="88f9d-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="88f9d-120">Serialización de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="88f9d-120">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
