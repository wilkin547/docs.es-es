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
ms.openlocfilehash: cbb33d2cddab22ad2072354ba543d2cd6a60a668
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61754575"
---
# <a name="invalidfunctionpointerindelegate-mda"></a><span data-ttu-id="8c14c-102">MDA de invalidFunctionPointerInDelegate</span><span class="sxs-lookup"><span data-stu-id="8c14c-102">invalidFunctionPointerInDelegate MDA</span></span>
<span data-ttu-id="8c14c-103">El asistente para la depuración administrada (MDA, por sus siglas en inglés) `invalidFunctionPointerInDelegate` se activa cuando un puntero de función no válido se pasa para construir un delegado sobre un puntero de función nativo.</span><span class="sxs-lookup"><span data-stu-id="8c14c-103">The `invalidFunctionPointerInDelegate` managed debugging assistant (MDA) is activated when an invalid function pointer is passed in to construct a delegate over a native function pointer.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="8c14c-104">Síntomas</span><span class="sxs-lookup"><span data-stu-id="8c14c-104">Symptoms</span></span>  
 <span data-ttu-id="8c14c-105">Infracciones de acceso o deterioro inesperado de la memoria al usar un delegado sobre un puntero de función.</span><span class="sxs-lookup"><span data-stu-id="8c14c-105">Access violations or unexpected memory corruption when using a delegate over a function pointer.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="8c14c-106">Motivo</span><span class="sxs-lookup"><span data-stu-id="8c14c-106">Cause</span></span>  
 <span data-ttu-id="8c14c-107">El puntero de función que se especificó no es válido.</span><span class="sxs-lookup"><span data-stu-id="8c14c-107">An invalid function pointer was specified.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="8c14c-108">Resolución</span><span class="sxs-lookup"><span data-stu-id="8c14c-108">Resolution</span></span>  
 <span data-ttu-id="8c14c-109">Especifique un puntero de función válido.</span><span class="sxs-lookup"><span data-stu-id="8c14c-109">Specify a valid function pointer</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="8c14c-110">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="8c14c-110">Effect on the Runtime</span></span>  
 <span data-ttu-id="8c14c-111">Este MDA no tiene ningún efecto en el CLR.</span><span class="sxs-lookup"><span data-stu-id="8c14c-111">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="8c14c-112">Salida</span><span class="sxs-lookup"><span data-stu-id="8c14c-112">Output</span></span>  
 <span data-ttu-id="8c14c-113">El puntero de función no válido.</span><span class="sxs-lookup"><span data-stu-id="8c14c-113">The invalid function pointer.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="8c14c-114">Configuración</span><span class="sxs-lookup"><span data-stu-id="8c14c-114">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidFunctionPointerInDelegate />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8c14c-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="8c14c-115">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="8c14c-116">Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)</span><span class="sxs-lookup"><span data-stu-id="8c14c-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="8c14c-117">Serialización de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="8c14c-117">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
