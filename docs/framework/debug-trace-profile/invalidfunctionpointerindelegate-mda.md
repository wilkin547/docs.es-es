---
title: MDA de invalidFunctionPointerInDelegate
description: Revise el Asistente para la depuración administrada (MDA) de invalidFunctionPointerInDelegate, que se invoca si se pasa un puntero de función no válido para crear un delegado.
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
ms.openlocfilehash: a17427d117c62ba782af3c9549c84623a3013b06
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051745"
---
# <a name="invalidfunctionpointerindelegate-mda"></a><span data-ttu-id="fd3cd-103">MDA de invalidFunctionPointerInDelegate</span><span class="sxs-lookup"><span data-stu-id="fd3cd-103">invalidFunctionPointerInDelegate MDA</span></span>
<span data-ttu-id="fd3cd-104">El asistente para la depuración administrada (MDA, por sus siglas en inglés) `invalidFunctionPointerInDelegate` se activa cuando un puntero de función no válido se pasa para construir un delegado sobre un puntero de función nativo.</span><span class="sxs-lookup"><span data-stu-id="fd3cd-104">The `invalidFunctionPointerInDelegate` managed debugging assistant (MDA) is activated when an invalid function pointer is passed in to construct a delegate over a native function pointer.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="fd3cd-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="fd3cd-105">Symptoms</span></span>  
 <span data-ttu-id="fd3cd-106">Infracciones de acceso o deterioro inesperado de la memoria al usar un delegado sobre un puntero de función.</span><span class="sxs-lookup"><span data-stu-id="fd3cd-106">Access violations or unexpected memory corruption when using a delegate over a function pointer.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="fd3cd-107">Causa</span><span class="sxs-lookup"><span data-stu-id="fd3cd-107">Cause</span></span>  
 <span data-ttu-id="fd3cd-108">El puntero de función que se especificó no es válido.</span><span class="sxs-lookup"><span data-stu-id="fd3cd-108">An invalid function pointer was specified.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="fd3cd-109">Resolución</span><span class="sxs-lookup"><span data-stu-id="fd3cd-109">Resolution</span></span>  
 <span data-ttu-id="fd3cd-110">Especifique un puntero de función válido.</span><span class="sxs-lookup"><span data-stu-id="fd3cd-110">Specify a valid function pointer</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="fd3cd-111">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="fd3cd-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="fd3cd-112">Este MDA no tiene ningún efecto en el CLR.</span><span class="sxs-lookup"><span data-stu-id="fd3cd-112">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="fd3cd-113">Output</span><span class="sxs-lookup"><span data-stu-id="fd3cd-113">Output</span></span>  
 <span data-ttu-id="fd3cd-114">El puntero de función no válido.</span><span class="sxs-lookup"><span data-stu-id="fd3cd-114">The invalid function pointer.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="fd3cd-115">Configuración</span><span class="sxs-lookup"><span data-stu-id="fd3cd-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidFunctionPointerInDelegate />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fd3cd-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="fd3cd-116">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="fd3cd-117">Diagnóstico de errores con asistentes de depuraciones administradas</span><span class="sxs-lookup"><span data-stu-id="fd3cd-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="fd3cd-118">Serialización de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="fd3cd-118">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
