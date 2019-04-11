---
title: MDA de invalidVariant
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid variant
- VARIANT type errors
- InvalidVariant MDA
- invalid VARIANT types
- managed debugging assistants (MDAs), invalid variant
ms.assetid: d273e070-d1b1-4a53-a9c7-7af837b04a3d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 64f5a4425d70974bae8c4f7bec28041e687fe95f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59228489"
---
# <a name="invalidvariant-mda"></a><span data-ttu-id="6a734-102">MDA de invalidVariant</span><span class="sxs-lookup"><span data-stu-id="6a734-102">invalidVariant MDA</span></span>
<span data-ttu-id="6a734-103">El asistente para la depuración administrada (MDA) de `invalidVariant` se activa cuando se encuentra una estructura `VARIANT` no válida durante una llamada de código nativo o no administrado a un código administrado.</span><span class="sxs-lookup"><span data-stu-id="6a734-103">The `invalidVariant` managed debugging assistant (MDA) is activated when an invalid `VARIANT` structure is encountered during a call from native or unmanaged code to managed code.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="6a734-104">Síntomas</span><span class="sxs-lookup"><span data-stu-id="6a734-104">Symptoms</span></span>  
 <span data-ttu-id="6a734-105">Comportamiento inesperado durante una transición entre código nativo y administrado que implica la serialización de `VARIANT` a un objeto.</span><span class="sxs-lookup"><span data-stu-id="6a734-105">Unexpected behavior during a transition between native and managed code involving the marshaling of a `VARIANT` to an object.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="6a734-106">Motivo</span><span class="sxs-lookup"><span data-stu-id="6a734-106">Cause</span></span>  
 <span data-ttu-id="6a734-107">El código nativo está pasando una estructura `VARIANT` incorrecta al código administrado.</span><span class="sxs-lookup"><span data-stu-id="6a734-107">Native code is passing a malformed `VARIANT` structure to managed code.</span></span>  <span data-ttu-id="6a734-108"> El motor en tiempo de ejecución intenta calcular las referencias de `VARIANT` a un objeto y activa el MDA si `VARIANT` no es válido.</span><span class="sxs-lookup"><span data-stu-id="6a734-108">The runtime attempts to marshal this `VARIANT` to an object and activates the MDA if the `VARIANT` is not valid.</span></span> <span data-ttu-id="6a734-109">Los ejemplos de `VARIANT` no válidas incluyen `VARIANT` con `VARTYPE` VT_EMPTY &#124; VT_BYREF o `VARIANT` con `VARTYPE` VT_VARIANT.</span><span class="sxs-lookup"><span data-stu-id="6a734-109">Examples of invalid `VARIANT`S include a `VARIANT` with `VARTYPE` VT_EMPTY &#124; VT_BYREF or a `VARIANT` with `VARTYPE` VT_VARIANT.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="6a734-110">Resolución</span><span class="sxs-lookup"><span data-stu-id="6a734-110">Resolution</span></span>  
 <span data-ttu-id="6a734-111">El paso de `VARIANT` por parte del código nativo o no administrado debe garantizar que `VARIANT` se forme e inicialice correctamente.</span><span class="sxs-lookup"><span data-stu-id="6a734-111">The native or unmanaged code passing the `VARIANT` must ensure that the `VARIANT` is correctly formed and initialized.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="6a734-112">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="6a734-112">Effect on the Runtime</span></span>  
 <span data-ttu-id="6a734-113">Este MDA no tiene ningún efecto en el comportamiento del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="6a734-113">The MDA has no effect on the runtime's behavior.</span></span>  
  
## <a name="output"></a><span data-ttu-id="6a734-114">Salida</span><span class="sxs-lookup"><span data-stu-id="6a734-114">Output</span></span>  
 <span data-ttu-id="6a734-115">Un mensaje de MDA que indica que el motor en tiempo de ejecución detectó una `VARIANT` no válida pasada a código administrado mediante un módulo no administrado.</span><span class="sxs-lookup"><span data-stu-id="6a734-115">An MDA message indicating that the runtime detected an invalid `VARIANT` passed to managed code by an unmanaged module.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="6a734-116">Configuración</span><span class="sxs-lookup"><span data-stu-id="6a734-116">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidVariant />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6a734-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="6a734-117">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="6a734-118">Diagnóstico de errores con asistentes de depuraciones administradas</span><span class="sxs-lookup"><span data-stu-id="6a734-118">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="6a734-119">Serialización de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="6a734-119">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
