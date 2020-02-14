---
title: MDA de gcUnmanagedToManaged
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), garbage collection
- GC unmanaged to managed
- transitioning threads unmanaged to managed code
- GcUnmanagedToManaged MDA
- threading [.NET Framework], garbage collection
- managed debugging assistants (MDAs), garbage collection
- threading [.NET Framework], managed debugging assistants
- garbage collection, run-time errors
- unmanaged to managed garbage collection
ms.assetid: 103eb3a3-1cf0-4406-8a9a-a7798fdc22d1
ms.openlocfilehash: dd4080870ae88da8d4e2055369cd36f3981f2eac
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216457"
---
# <a name="gcunmanagedtomanaged-mda"></a><span data-ttu-id="bb668-102">MDA de gcUnmanagedToManaged</span><span class="sxs-lookup"><span data-stu-id="bb668-102">gcUnmanagedToManaged MDA</span></span>
<span data-ttu-id="bb668-103">El asistente para la depuración administrada (MDA) `gcUnmanagedToManaged` produce una recolección de elementos no utilizados siempre que un subproceso realice la transición de código no administrado a administrado.</span><span class="sxs-lookup"><span data-stu-id="bb668-103">The `gcUnmanagedToManaged` managed debugging assistant (MDA) causes a garbage collection whenever a thread transitions from unmanaged to managed code.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="bb668-104">Síntomas</span><span class="sxs-lookup"><span data-stu-id="bb668-104">Symptoms</span></span>  
 <span data-ttu-id="bb668-105">Una aplicación que ejecute componentes de usuario no administrados con la invocación de plataforma y COM genera una infracción de acceso no determinista en CLR.</span><span class="sxs-lookup"><span data-stu-id="bb668-105">An application running unmanaged user components using COM and platform invoke is causing a nondeterministic access violation in the CLR.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="bb668-106">Causa</span><span class="sxs-lookup"><span data-stu-id="bb668-106">Cause</span></span>  
 <span data-ttu-id="bb668-107">Si una aplicación está ejecutando componentes de usuario no administrados, dichos componentes podrían haber dañado el montón de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="bb668-107">If an application is running unmanaged user components, then those components might have corrupted the garbage-collected heap.</span></span> <span data-ttu-id="bb668-108">Esto provoca una infracción de acceso en CLR cuando el recolector de elementos no utilizados intenta desplazarse por el gráfico de objetos.</span><span class="sxs-lookup"><span data-stu-id="bb668-108">This causes an access violation in the CLR when the garbage collector tries to walk the object graph.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="bb668-109">Solución</span><span class="sxs-lookup"><span data-stu-id="bb668-109">Resolution</span></span>  
 <span data-ttu-id="bb668-110">Al habilitar este asistente, se reduce el tiempo entre el momento en que el componente no administrado daña la pila de recolección de elementos no utilizados y el momento en que se produce la infracción de acceso al forzar que tenga lugar una recolección antes de cada transición administrada.</span><span class="sxs-lookup"><span data-stu-id="bb668-110">Enabling this assistant reduces the time between when the unmanaged component corrupts the garbage-collected heap and when the access violation happens by forcing a garbage collection to occur before every managed transition.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="bb668-111">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="bb668-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="bb668-112">Produce una recolección de elementos no utilizados siempre que un subproceso realice la transición de código no administrado a administrado.</span><span class="sxs-lookup"><span data-stu-id="bb668-112">Causes a garbage collection whenever a thread transitions from unmanaged to managed code.</span></span>  
  
## <a name="output"></a><span data-ttu-id="bb668-113">Output</span><span class="sxs-lookup"><span data-stu-id="bb668-113">Output</span></span>  
 <span data-ttu-id="bb668-114">Este MDA no produce ninguna salida.</span><span class="sxs-lookup"><span data-stu-id="bb668-114">This MDA produces no output.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="bb668-115">Configuración</span><span class="sxs-lookup"><span data-stu-id="bb668-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <gcUnmanagedToManaged/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bb668-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bb668-116">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="bb668-117">Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)</span><span class="sxs-lookup"><span data-stu-id="bb668-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="bb668-118">gcManagedToUnmanaged</span><span class="sxs-lookup"><span data-stu-id="bb668-118">gcManagedToUnmanaged</span></span>](gcmanagedtounmanaged-mda.md)
- [<span data-ttu-id="bb668-119">Serialización para interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="bb668-119">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
