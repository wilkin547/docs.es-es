---
title: MDA de gcManagedToUnmanaged
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1aa528eb2acc872b1956edef3af3724bb3b54d67
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="gcmanagedtounmanaged-mda"></a><span data-ttu-id="e8481-102">MDA de gcManagedToUnmanaged</span><span class="sxs-lookup"><span data-stu-id="e8481-102">gcManagedToUnmanaged MDA</span></span>
<span data-ttu-id="e8481-103">El asistente para la depuración administrada (MDA) `gcManagedToUnmanaged` produce una recolección de elementos no utilizados siempre que un subproceso realiza la transición de código administrado a no administrado.</span><span class="sxs-lookup"><span data-stu-id="e8481-103">The `gcManagedToUnmanaged` managed debugging assistant (MDA) causes a garbage collection whenever a thread transitions from managed to unmanaged code.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="e8481-104">Síntomas</span><span class="sxs-lookup"><span data-stu-id="e8481-104">Symptoms</span></span>  
 <span data-ttu-id="e8481-105">Un componente de usuario no administrado produce una infracción de acceso al intentar usar un objeto administrado que se había expuesto a COM.</span><span class="sxs-lookup"><span data-stu-id="e8481-105">An unmanaged user component throws an access violation when trying to use a managed object that had been exposed to COM.</span></span> <span data-ttu-id="e8481-106">El objeto COM aparece como liberado.</span><span class="sxs-lookup"><span data-stu-id="e8481-106">The COM object appears to have been released.</span></span> <span data-ttu-id="e8481-107">La infracción de acceso es no determinista.</span><span class="sxs-lookup"><span data-stu-id="e8481-107">The access violation is nondeterministic.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="e8481-108">Motivo</span><span class="sxs-lookup"><span data-stu-id="e8481-108">Cause</span></span>  
 <span data-ttu-id="e8481-109">Si un componente no administrado no cuenta correctamente las referencias de un objeto COM administrado, CLR podría recopilar un objeto administrado expuesto a COM cuando el componente no administrado todavía contiene una referencia al objeto.</span><span class="sxs-lookup"><span data-stu-id="e8481-109">If an unmanaged component is not reference counting a managed COM object correctly, then the runtime could collect a managed object exposed to COM when the unmanaged component still holds a reference to the object.</span></span> <span data-ttu-id="e8481-110">Como CLR llama a <xref:System.Runtime.InteropServices.Marshal.Release%2A> durante las recolecciones de elementos no utilizados, si el componente de usuario utiliza el objeto antes de que se produzca la recolección de elementos no utilizados, aún no se habrá recolectado.</span><span class="sxs-lookup"><span data-stu-id="e8481-110">The runtime calls <xref:System.Runtime.InteropServices.Marshal.Release%2A> during garbage collections, so if the user component uses the object before the garbage collection occurs, then it will not yet have been collected.</span></span> <span data-ttu-id="e8481-111">Este es el origen del no determinismo.</span><span class="sxs-lookup"><span data-stu-id="e8481-111">This is the source of the nondeterminism.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="e8481-112">Resolución</span><span class="sxs-lookup"><span data-stu-id="e8481-112">Resolution</span></span>  
 <span data-ttu-id="e8481-113">Habilitar este asistente reduce el tiempo entre el momento en que el objeto es apto para la recolección y el momento en que se llama a <xref:System.Runtime.InteropServices.Marshal.Release%2A>, lo que ayuda a realizar un seguimiento de qué componente no administrado intenta acceder primero al objeto recolectado.</span><span class="sxs-lookup"><span data-stu-id="e8481-113">Enabling this assistant reduces the time between when the object is eligible for collection and <xref:System.Runtime.InteropServices.Marshal.Release%2A> is called, helping to track down which unmanaged component first tries to access the collected object.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="e8481-114">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="e8481-114">Effect on the Runtime</span></span>  
 <span data-ttu-id="e8481-115">Produce una recolección de elementos no utilizados siempre que un subproceso realice la transición de código administrado a no administrado.</span><span class="sxs-lookup"><span data-stu-id="e8481-115">Causes a garbage collection whenever a thread transitions from managed to unmanaged code.</span></span>  
  
## <a name="output"></a><span data-ttu-id="e8481-116">Salida</span><span class="sxs-lookup"><span data-stu-id="e8481-116">Output</span></span>  
 <span data-ttu-id="e8481-117">Este MDA no produce ninguna salida.</span><span class="sxs-lookup"><span data-stu-id="e8481-117">This MDA produces no output.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="e8481-118">Configuración</span><span class="sxs-lookup"><span data-stu-id="e8481-118">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <gcManagedToUnmanaged/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e8481-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="e8481-119">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="e8481-120">Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)</span><span class="sxs-lookup"><span data-stu-id="e8481-120">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="e8481-121">Serialización para interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="e8481-121">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)  
 [<span data-ttu-id="e8481-122">gcUnmanagedToManaged</span><span class="sxs-lookup"><span data-stu-id="e8481-122">gcUnmanagedToManaged</span></span>](../../../docs/framework/debug-trace-profile/gcunmanagedtomanaged-mda.md)
