---
title: MDA de gcManagedToUnmanaged
description: Revise el Asistente para la depuración administrada gcManagedToUnmanaged. Este MDA puede activarse debido a la recolección de elementos no utilizados prematura durante la transición a código no administrado.
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
ms.openlocfilehash: 76c621a1f2bb780d38228f2a84d4c77441774770
ms.sourcegitcommit: a2c8b19e813a52b91facbb5d7e3c062c7188b457
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415919"
---
# <a name="gcmanagedtounmanaged-mda"></a><span data-ttu-id="14288-104">MDA de gcManagedToUnmanaged</span><span class="sxs-lookup"><span data-stu-id="14288-104">gcManagedToUnmanaged MDA</span></span>
<span data-ttu-id="14288-105">El asistente para la depuración administrada (MDA) `gcManagedToUnmanaged` produce una recolección de elementos no utilizados siempre que un subproceso realiza la transición de código administrado a no administrado.</span><span class="sxs-lookup"><span data-stu-id="14288-105">The `gcManagedToUnmanaged` managed debugging assistant (MDA) causes a garbage collection whenever a thread transitions from managed to unmanaged code.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="14288-106">Síntomas</span><span class="sxs-lookup"><span data-stu-id="14288-106">Symptoms</span></span>  
 <span data-ttu-id="14288-107">Un componente de usuario no administrado produce una infracción de acceso al intentar usar un objeto administrado que se había expuesto a COM.</span><span class="sxs-lookup"><span data-stu-id="14288-107">An unmanaged user component throws an access violation when trying to use a managed object that had been exposed to COM.</span></span> <span data-ttu-id="14288-108">El objeto COM aparece como liberado.</span><span class="sxs-lookup"><span data-stu-id="14288-108">The COM object appears to have been released.</span></span> <span data-ttu-id="14288-109">La infracción de acceso es no determinista.</span><span class="sxs-lookup"><span data-stu-id="14288-109">The access violation is nondeterministic.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="14288-110">Causa</span><span class="sxs-lookup"><span data-stu-id="14288-110">Cause</span></span>  
 <span data-ttu-id="14288-111">Si un componente no administrado no cuenta correctamente las referencias de un objeto COM administrado, CLR podría recopilar un objeto administrado expuesto a COM cuando el componente no administrado todavía contiene una referencia al objeto.</span><span class="sxs-lookup"><span data-stu-id="14288-111">If an unmanaged component is not reference counting a managed COM object correctly, then the runtime could collect a managed object exposed to COM when the unmanaged component still holds a reference to the object.</span></span> <span data-ttu-id="14288-112">Como CLR llama a <xref:System.Runtime.InteropServices.Marshal.Release%2A> durante las recolecciones de elementos no utilizados, si el componente de usuario utiliza el objeto antes de que se produzca la recolección de elementos no utilizados, aún no se habrá recolectado.</span><span class="sxs-lookup"><span data-stu-id="14288-112">The runtime calls <xref:System.Runtime.InteropServices.Marshal.Release%2A> during garbage collections, so if the user component uses the object before the garbage collection occurs, then it will not yet have been collected.</span></span> <span data-ttu-id="14288-113">Este es el origen del no determinismo.</span><span class="sxs-lookup"><span data-stu-id="14288-113">This is the source of the nondeterminism.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="14288-114">Solución</span><span class="sxs-lookup"><span data-stu-id="14288-114">Resolution</span></span>  
 <span data-ttu-id="14288-115">Habilitar este asistente reduce el tiempo entre el momento en que el objeto es apto para la recolección y el momento en que se llama a <xref:System.Runtime.InteropServices.Marshal.Release%2A>, lo que ayuda a realizar un seguimiento de qué componente no administrado intenta acceder primero al objeto recolectado.</span><span class="sxs-lookup"><span data-stu-id="14288-115">Enabling this assistant reduces the time between when the object is eligible for collection and <xref:System.Runtime.InteropServices.Marshal.Release%2A> is called, helping to track down which unmanaged component first tries to access the collected object.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="14288-116">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="14288-116">Effect on the Runtime</span></span>  
 <span data-ttu-id="14288-117">Produce una recolección de elementos no utilizados siempre que un subproceso realice la transición de código administrado a no administrado.</span><span class="sxs-lookup"><span data-stu-id="14288-117">Causes a garbage collection whenever a thread transitions from managed to unmanaged code.</span></span>  
  
## <a name="output"></a><span data-ttu-id="14288-118">Output</span><span class="sxs-lookup"><span data-stu-id="14288-118">Output</span></span>  
 <span data-ttu-id="14288-119">Este MDA no produce ninguna salida.</span><span class="sxs-lookup"><span data-stu-id="14288-119">This MDA produces no output.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="14288-120">Configuración</span><span class="sxs-lookup"><span data-stu-id="14288-120">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <gcManagedToUnmanaged/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="14288-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="14288-121">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="14288-122">Diagnóstico de errores con asistentes de depuraciones administradas</span><span class="sxs-lookup"><span data-stu-id="14288-122">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="14288-123">Serialización de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="14288-123">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
- [<span data-ttu-id="14288-124">gcUnmanagedToManaged</span><span class="sxs-lookup"><span data-stu-id="14288-124">gcUnmanagedToManaged</span></span>](gcunmanagedtomanaged-mda.md)
