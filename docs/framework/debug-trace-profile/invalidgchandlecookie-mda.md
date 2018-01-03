---
title: MDA de invalidGCHandleCookie
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid cookies
- cookies, invalid
- managed debugging assistants (MDAs), invalid cookies
- InvalidGCHandleCookie MDA
- invalid cookies
ms.assetid: 613ad742-3c11-401d-a6b3-893ceb8de4f8
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4f4cb7655d8d70cf46926cf193d6594523316e81
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="invalidgchandlecookie-mda"></a><span data-ttu-id="96a91-102">MDA de invalidGCHandleCookie</span><span class="sxs-lookup"><span data-stu-id="96a91-102">invalidGCHandleCookie MDA</span></span>
<span data-ttu-id="96a91-103">El Asistente para la depuración administrada (MDA) `invalidGCHandleCookie` se activa cuando se intenta realizar la conversión de una cookie <xref:System.IntPtr> no válida a un <xref:System.Runtime.InteropServices.GCHandle>.</span><span class="sxs-lookup"><span data-stu-id="96a91-103">The `invalidGCHandleCookie` managed debugging assistant (MDA) is activated when a conversion from an invalid <xref:System.IntPtr> cookie to a <xref:System.Runtime.InteropServices.GCHandle> is attempted.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="96a91-104">Síntomas</span><span class="sxs-lookup"><span data-stu-id="96a91-104">Symptoms</span></span>  
 <span data-ttu-id="96a91-105">Comportamiento indefinido, como infracciones de acceso y daños en la memoria, al intentar usar o recuperar <xref:System.Runtime.InteropServices.GCHandle> desde <xref:System.IntPtr>.</span><span class="sxs-lookup"><span data-stu-id="96a91-105">Undefined behavior such as access violations and memory corruption while attempting to use or retrieve a <xref:System.Runtime.InteropServices.GCHandle> from an <xref:System.IntPtr>.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="96a91-106">Motivo</span><span class="sxs-lookup"><span data-stu-id="96a91-106">Cause</span></span>  
 <span data-ttu-id="96a91-107">La cookie probablemente no es válida porque no se creó originalmente desde un <xref:System.Runtime.InteropServices.GCHandle>, representa un <xref:System.Runtime.InteropServices.GCHandle> que ya se ha liberado, es una cookie de un <xref:System.Runtime.InteropServices.GCHandle> en un dominio de aplicación diferente, o bien se serializó en código nativo como un <xref:System.Runtime.InteropServices.GCHandle> pero se volvió a pasar al CLR como un <xref:System.IntPtr>, donde se intentó una conversión.</span><span class="sxs-lookup"><span data-stu-id="96a91-107">The cookie is probably invalid because it was not originally created from a <xref:System.Runtime.InteropServices.GCHandle>, represents a <xref:System.Runtime.InteropServices.GCHandle> that has already been freed, is a cookie to a <xref:System.Runtime.InteropServices.GCHandle> in a different application domain, or was marshaled to native code as a <xref:System.Runtime.InteropServices.GCHandle> but passed back into the CLR as an <xref:System.IntPtr>, where a cast was attempted.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="96a91-108">Resolución</span><span class="sxs-lookup"><span data-stu-id="96a91-108">Resolution</span></span>  
 <span data-ttu-id="96a91-109">Especifique una cookie de <xref:System.IntPtr> válida para el <xref:System.Runtime.InteropServices.GCHandle>.</span><span class="sxs-lookup"><span data-stu-id="96a91-109">Specify a valid <xref:System.IntPtr> cookie for the <xref:System.Runtime.InteropServices.GCHandle>.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="96a91-110">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="96a91-110">Effect on the Runtime</span></span>  
 <span data-ttu-id="96a91-111">Cuando se habilita este MDA, el depurador ya no es capaz de realizar un seguimiento de las raíces hasta sus objetos porque los valores de cookie que se pasan son diferentes a los que se devuelven cuando el MDA no está habilitado.</span><span class="sxs-lookup"><span data-stu-id="96a91-111">When this MDA is enabled, the debugger is no longer able to trace the roots back to their objects because the cookie values passed back are different from the ones returned when the MDA is not enabled.</span></span>  
  
## <a name="output"></a><span data-ttu-id="96a91-112">Salida</span><span class="sxs-lookup"><span data-stu-id="96a91-112">Output</span></span>  
 <span data-ttu-id="96a91-113">Se notifica el valor de la cookie de <xref:System.IntPtr> no válida.</span><span class="sxs-lookup"><span data-stu-id="96a91-113">The invalid <xref:System.IntPtr> cookie value is reported.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="96a91-114">Configuración</span><span class="sxs-lookup"><span data-stu-id="96a91-114">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidGCHandleCookie />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="96a91-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="96a91-115">See Also</span></span>  
 <xref:System.Runtime.InteropServices.GCHandle.FromIntPtr%2A>  
 <xref:System.Runtime.InteropServices.GCHandle>  
 [<span data-ttu-id="96a91-116">Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)</span><span class="sxs-lookup"><span data-stu-id="96a91-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
