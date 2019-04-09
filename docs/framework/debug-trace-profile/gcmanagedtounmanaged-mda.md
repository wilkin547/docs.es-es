---
title: MDA de gcManagedToUnmanaged
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), garbage collection
- GcManagedToUnmanaged MDA
- GC managed to unmanaged
- transitioning threads managed to unmanaged code
- threading [.NET Framework], garbage collection
- managed to unmanaged garbage collection
- managed debugging assistants (MDAs), garbage collection
- threading [.NET Framework], managed debugging assistants
- garbage collection, run-time errors
ms.assetid: 7417f837-805e-4fed-a430-ca919c8421dc
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7bb4779e300df71a5d075a322bcac8398ce42f34
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59204281"
---
# <a name="gcmanagedtounmanaged-mda"></a><span data-ttu-id="9a467-102">MDA de gcManagedToUnmanaged</span><span class="sxs-lookup"><span data-stu-id="9a467-102">gcManagedToUnmanaged MDA</span></span>
<span data-ttu-id="9a467-103">El asistente para la depuración administrada (MDA) `gcManagedToUnmanaged` produce una recolección de elementos no utilizados siempre que un subproceso realiza la transición de código administrado a no administrado.</span><span class="sxs-lookup"><span data-stu-id="9a467-103">The `gcManagedToUnmanaged` managed debugging assistant (MDA) causes a garbage collection whenever a thread transitions from managed to unmanaged code.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="9a467-104">Síntomas</span><span class="sxs-lookup"><span data-stu-id="9a467-104">Symptoms</span></span>  
 <span data-ttu-id="9a467-105">Un componente de usuario no administrado produce una infracción de acceso al intentar usar un objeto administrado que se había expuesto a COM.</span><span class="sxs-lookup"><span data-stu-id="9a467-105">An unmanaged user component throws an access violation when trying to use a managed object that had been exposed to COM.</span></span> <span data-ttu-id="9a467-106">El objeto COM aparece como liberado.</span><span class="sxs-lookup"><span data-stu-id="9a467-106">The COM object appears to have been released.</span></span> <span data-ttu-id="9a467-107">La infracción de acceso es no determinista.</span><span class="sxs-lookup"><span data-stu-id="9a467-107">The access violation is nondeterministic.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="9a467-108">Motivo</span><span class="sxs-lookup"><span data-stu-id="9a467-108">Cause</span></span>  
 <span data-ttu-id="9a467-109">Si un componente no administrado no cuenta correctamente las referencias de un objeto COM administrado, CLR podría recopilar un objeto administrado expuesto a COM cuando el componente no administrado todavía contiene una referencia al objeto.</span><span class="sxs-lookup"><span data-stu-id="9a467-109">If an unmanaged component is not reference counting a managed COM object correctly, then the runtime could collect a managed object exposed to COM when the unmanaged component still holds a reference to the object.</span></span> <span data-ttu-id="9a467-110">Como CLR llama a <xref:System.Runtime.InteropServices.Marshal.Release%2A> durante las recolecciones de elementos no utilizados, si el componente de usuario utiliza el objeto antes de que se produzca la recolección de elementos no utilizados, aún no se habrá recolectado.</span><span class="sxs-lookup"><span data-stu-id="9a467-110">The runtime calls <xref:System.Runtime.InteropServices.Marshal.Release%2A> during garbage collections, so if the user component uses the object before the garbage collection occurs, then it will not yet have been collected.</span></span> <span data-ttu-id="9a467-111">Este es el origen del no determinismo.</span><span class="sxs-lookup"><span data-stu-id="9a467-111">This is the source of the nondeterminism.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="9a467-112">Resolución</span><span class="sxs-lookup"><span data-stu-id="9a467-112">Resolution</span></span>  
 <span data-ttu-id="9a467-113">Habilitar este asistente reduce el tiempo entre el momento en que el objeto es apto para la recolección y el momento en que se llama a <xref:System.Runtime.InteropServices.Marshal.Release%2A>, lo que ayuda a realizar un seguimiento de qué componente no administrado intenta acceder primero al objeto recolectado.</span><span class="sxs-lookup"><span data-stu-id="9a467-113">Enabling this assistant reduces the time between when the object is eligible for collection and <xref:System.Runtime.InteropServices.Marshal.Release%2A> is called, helping to track down which unmanaged component first tries to access the collected object.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="9a467-114">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="9a467-114">Effect on the Runtime</span></span>  
 <span data-ttu-id="9a467-115">Produce una recolección de elementos no utilizados siempre que un subproceso realice la transición de código administrado a no administrado.</span><span class="sxs-lookup"><span data-stu-id="9a467-115">Causes a garbage collection whenever a thread transitions from managed to unmanaged code.</span></span>  
  
## <a name="output"></a><span data-ttu-id="9a467-116">Salida</span><span class="sxs-lookup"><span data-stu-id="9a467-116">Output</span></span>  
 <span data-ttu-id="9a467-117">Este MDA no produce ninguna salida.</span><span class="sxs-lookup"><span data-stu-id="9a467-117">This MDA produces no output.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="9a467-118">Configuración</span><span class="sxs-lookup"><span data-stu-id="9a467-118">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <gcManagedToUnmanaged/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9a467-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="9a467-119">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="9a467-120">Diagnóstico de errores con asistentes de depuraciones administradas</span><span class="sxs-lookup"><span data-stu-id="9a467-120">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="9a467-121">Serialización de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="9a467-121">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
- [<span data-ttu-id="9a467-122">gcUnmanagedToManaged</span><span class="sxs-lookup"><span data-stu-id="9a467-122">gcUnmanagedToManaged</span></span>](../../../docs/framework/debug-trace-profile/gcunmanagedtomanaged-mda.md)
