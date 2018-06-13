---
title: MDA de invalidFunctionPointerInDelegate
ms.date: 03/30/2017
helpviewer_keywords:
- invalidFunctionPointerInDelegate MDA
- managed debugging assistants (MDAs), invalid function pointer to delegates
- MDAs (managed debugging assistants), invalid function pointer to delegates
- function pointers, invalid
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
- invalid function pointers
ms.assetid: 99ae44f1-783e-49a9-9009-24f54bbd0f09
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 847ec4d861136b46383ce7d3801764f3d962049e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33390879"
---
# <a name="invalidfunctionpointerindelegate-mda"></a><span data-ttu-id="470ef-102">MDA de invalidFunctionPointerInDelegate</span><span class="sxs-lookup"><span data-stu-id="470ef-102">invalidFunctionPointerInDelegate MDA</span></span>
<span data-ttu-id="470ef-103">El asistente para la depuración administrada (MDA, por sus siglas en inglés) `invalidFunctionPointerInDelegate` se activa cuando un puntero de función no válido se pasa para construir un delegado sobre un puntero de función nativo.</span><span class="sxs-lookup"><span data-stu-id="470ef-103">The `invalidFunctionPointerInDelegate` managed debugging assistant (MDA) is activated when an invalid function pointer is passed in to construct a delegate over a native function pointer.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="470ef-104">Síntomas</span><span class="sxs-lookup"><span data-stu-id="470ef-104">Symptoms</span></span>  
 <span data-ttu-id="470ef-105">Infracciones de acceso o deterioro inesperado de la memoria al usar un delegado sobre un puntero de función.</span><span class="sxs-lookup"><span data-stu-id="470ef-105">Access violations or unexpected memory corruption when using a delegate over a function pointer.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="470ef-106">Motivo</span><span class="sxs-lookup"><span data-stu-id="470ef-106">Cause</span></span>  
 <span data-ttu-id="470ef-107">El puntero de función que se especificó no es válido.</span><span class="sxs-lookup"><span data-stu-id="470ef-107">An invalid function pointer was specified.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="470ef-108">Solución</span><span class="sxs-lookup"><span data-stu-id="470ef-108">Resolution</span></span>  
 <span data-ttu-id="470ef-109">Especifique un puntero de función válido.</span><span class="sxs-lookup"><span data-stu-id="470ef-109">Specify a valid function pointer</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="470ef-110">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="470ef-110">Effect on the Runtime</span></span>  
 <span data-ttu-id="470ef-111">Este MDA no tiene ningún efecto en el CLR.</span><span class="sxs-lookup"><span data-stu-id="470ef-111">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="470ef-112">Salida</span><span class="sxs-lookup"><span data-stu-id="470ef-112">Output</span></span>  
 <span data-ttu-id="470ef-113">El puntero de función no válido.</span><span class="sxs-lookup"><span data-stu-id="470ef-113">The invalid function pointer.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="470ef-114">Configuración</span><span class="sxs-lookup"><span data-stu-id="470ef-114">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidFunctionPointerInDelegate />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="470ef-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="470ef-115">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="470ef-116">Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)</span><span class="sxs-lookup"><span data-stu-id="470ef-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="470ef-117">Serialización de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="470ef-117">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
