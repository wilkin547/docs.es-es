---
title: MDA de invalidGCHandleCookie
description: Revise el Asistente para la depuración administrada (MDA) invalidGCHandleCookie, que se activa cuando se intenta realizar una conversión de una cookie IntPtr no válida a GCHandle.
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid cookies
- cookies, invalid
- managed debugging assistants (MDAs), invalid cookies
- InvalidGCHandleCookie MDA
- invalid cookies
ms.assetid: 613ad742-3c11-401d-a6b3-893ceb8de4f8
ms.openlocfilehash: 1063b7be902d3063717b6639564d819ef3292c0e
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051303"
---
# <a name="invalidgchandlecookie-mda"></a><span data-ttu-id="d80d6-103">MDA de invalidGCHandleCookie</span><span class="sxs-lookup"><span data-stu-id="d80d6-103">invalidGCHandleCookie MDA</span></span>
<span data-ttu-id="d80d6-104">El Asistente para la depuración administrada (MDA) `invalidGCHandleCookie` se activa cuando se intenta realizar la conversión de una cookie <xref:System.IntPtr> no válida a un <xref:System.Runtime.InteropServices.GCHandle>.</span><span class="sxs-lookup"><span data-stu-id="d80d6-104">The `invalidGCHandleCookie` managed debugging assistant (MDA) is activated when a conversion from an invalid <xref:System.IntPtr> cookie to a <xref:System.Runtime.InteropServices.GCHandle> is attempted.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="d80d6-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="d80d6-105">Symptoms</span></span>  
 <span data-ttu-id="d80d6-106">Comportamiento indefinido, como infracciones de acceso y daños en la memoria, al intentar usar o recuperar <xref:System.Runtime.InteropServices.GCHandle> desde <xref:System.IntPtr>.</span><span class="sxs-lookup"><span data-stu-id="d80d6-106">Undefined behavior such as access violations and memory corruption while attempting to use or retrieve a <xref:System.Runtime.InteropServices.GCHandle> from an <xref:System.IntPtr>.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="d80d6-107">Causa</span><span class="sxs-lookup"><span data-stu-id="d80d6-107">Cause</span></span>  
 <span data-ttu-id="d80d6-108">La cookie probablemente no es válida porque no se creó originalmente desde un <xref:System.Runtime.InteropServices.GCHandle>, representa un <xref:System.Runtime.InteropServices.GCHandle> que ya se ha liberado, es una cookie de un <xref:System.Runtime.InteropServices.GCHandle> en un dominio de aplicación diferente, o bien se serializó en código nativo como un <xref:System.Runtime.InteropServices.GCHandle> pero se volvió a pasar al CLR como un <xref:System.IntPtr>, donde se intentó una conversión.</span><span class="sxs-lookup"><span data-stu-id="d80d6-108">The cookie is probably invalid because it was not originally created from a <xref:System.Runtime.InteropServices.GCHandle>, represents a <xref:System.Runtime.InteropServices.GCHandle> that has already been freed, is a cookie to a <xref:System.Runtime.InteropServices.GCHandle> in a different application domain, or was marshaled to native code as a <xref:System.Runtime.InteropServices.GCHandle> but passed back into the CLR as an <xref:System.IntPtr>, where a cast was attempted.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="d80d6-109">Resolución</span><span class="sxs-lookup"><span data-stu-id="d80d6-109">Resolution</span></span>  
 <span data-ttu-id="d80d6-110">Especifique una cookie de <xref:System.IntPtr> válida para el <xref:System.Runtime.InteropServices.GCHandle>.</span><span class="sxs-lookup"><span data-stu-id="d80d6-110">Specify a valid <xref:System.IntPtr> cookie for the <xref:System.Runtime.InteropServices.GCHandle>.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="d80d6-111">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="d80d6-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="d80d6-112">Cuando se habilita este MDA, el depurador ya no es capaz de realizar un seguimiento de las raíces hasta sus objetos porque los valores de cookie que se pasan son diferentes a los que se devuelven cuando el MDA no está habilitado.</span><span class="sxs-lookup"><span data-stu-id="d80d6-112">When this MDA is enabled, the debugger is no longer able to trace the roots back to their objects because the cookie values passed back are different from the ones returned when the MDA is not enabled.</span></span>  
  
## <a name="output"></a><span data-ttu-id="d80d6-113">Output</span><span class="sxs-lookup"><span data-stu-id="d80d6-113">Output</span></span>  
 <span data-ttu-id="d80d6-114">Se notifica el valor de la cookie de <xref:System.IntPtr> no válida.</span><span class="sxs-lookup"><span data-stu-id="d80d6-114">The invalid <xref:System.IntPtr> cookie value is reported.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="d80d6-115">Configuración</span><span class="sxs-lookup"><span data-stu-id="d80d6-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidGCHandleCookie />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d80d6-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="d80d6-116">See also</span></span>

- <xref:System.Runtime.InteropServices.GCHandle.FromIntPtr%2A>
- <xref:System.Runtime.InteropServices.GCHandle>
- [<span data-ttu-id="d80d6-117">Diagnóstico de errores con asistentes de depuraciones administradas</span><span class="sxs-lookup"><span data-stu-id="d80d6-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
