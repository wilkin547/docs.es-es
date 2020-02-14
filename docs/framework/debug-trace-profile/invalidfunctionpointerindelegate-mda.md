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
ms.openlocfilehash: 723f51e14c314bde40c34d629ba7fc4f6276c633
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217380"
---
# <a name="invalidfunctionpointerindelegate-mda"></a><span data-ttu-id="6be63-102">MDA de invalidFunctionPointerInDelegate</span><span class="sxs-lookup"><span data-stu-id="6be63-102">invalidFunctionPointerInDelegate MDA</span></span>
<span data-ttu-id="6be63-103">El asistente para la depuración administrada (MDA, por sus siglas en inglés) `invalidFunctionPointerInDelegate` se activa cuando un puntero de función no válido se pasa para construir un delegado sobre un puntero de función nativo.</span><span class="sxs-lookup"><span data-stu-id="6be63-103">The `invalidFunctionPointerInDelegate` managed debugging assistant (MDA) is activated when an invalid function pointer is passed in to construct a delegate over a native function pointer.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="6be63-104">Síntomas</span><span class="sxs-lookup"><span data-stu-id="6be63-104">Symptoms</span></span>  
 <span data-ttu-id="6be63-105">Infracciones de acceso o deterioro inesperado de la memoria al usar un delegado sobre un puntero de función.</span><span class="sxs-lookup"><span data-stu-id="6be63-105">Access violations or unexpected memory corruption when using a delegate over a function pointer.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="6be63-106">Causa</span><span class="sxs-lookup"><span data-stu-id="6be63-106">Cause</span></span>  
 <span data-ttu-id="6be63-107">El puntero de función que se especificó no es válido.</span><span class="sxs-lookup"><span data-stu-id="6be63-107">An invalid function pointer was specified.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="6be63-108">Solución</span><span class="sxs-lookup"><span data-stu-id="6be63-108">Resolution</span></span>  
 <span data-ttu-id="6be63-109">Especifique un puntero de función válido.</span><span class="sxs-lookup"><span data-stu-id="6be63-109">Specify a valid function pointer</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="6be63-110">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="6be63-110">Effect on the Runtime</span></span>  
 <span data-ttu-id="6be63-111">Este MDA no tiene ningún efecto en el CLR.</span><span class="sxs-lookup"><span data-stu-id="6be63-111">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="6be63-112">Output</span><span class="sxs-lookup"><span data-stu-id="6be63-112">Output</span></span>  
 <span data-ttu-id="6be63-113">El puntero de función no válido.</span><span class="sxs-lookup"><span data-stu-id="6be63-113">The invalid function pointer.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="6be63-114">Configuración</span><span class="sxs-lookup"><span data-stu-id="6be63-114">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidFunctionPointerInDelegate />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6be63-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6be63-115">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="6be63-116">Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)</span><span class="sxs-lookup"><span data-stu-id="6be63-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="6be63-117">Serialización para interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="6be63-117">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
