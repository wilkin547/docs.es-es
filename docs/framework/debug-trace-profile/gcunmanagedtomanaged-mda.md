---
title: MDA de gcUnmanagedToManaged
description: Revise el Asistente para la depuración administrada de gcManagedToUnmanaged en .NET. Este MDA puede activarse debido a daños en el montón de elementos no utilizados durante la transición al código administrado.
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
ms.openlocfilehash: 61fbdbf0d3941aa3e876748ae4d76cd7ad0c0977
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96244228"
---
# <a name="gcunmanagedtomanaged-mda"></a><span data-ttu-id="0ad15-104">MDA de gcUnmanagedToManaged</span><span class="sxs-lookup"><span data-stu-id="0ad15-104">gcUnmanagedToManaged MDA</span></span>

<span data-ttu-id="0ad15-105">El asistente para la depuración administrada (MDA) `gcUnmanagedToManaged` produce una recolección de elementos no utilizados siempre que un subproceso realice la transición de código no administrado a administrado.</span><span class="sxs-lookup"><span data-stu-id="0ad15-105">The `gcUnmanagedToManaged` managed debugging assistant (MDA) causes a garbage collection whenever a thread transitions from unmanaged to managed code.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="0ad15-106">Síntomas</span><span class="sxs-lookup"><span data-stu-id="0ad15-106">Symptoms</span></span>  

 <span data-ttu-id="0ad15-107">Una aplicación que ejecute componentes de usuario no administrados con la invocación de plataforma y COM genera una infracción de acceso no determinista en CLR.</span><span class="sxs-lookup"><span data-stu-id="0ad15-107">An application running unmanaged user components using COM and platform invoke is causing a nondeterministic access violation in the CLR.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="0ad15-108">Causa</span><span class="sxs-lookup"><span data-stu-id="0ad15-108">Cause</span></span>  

 <span data-ttu-id="0ad15-109">Si una aplicación está ejecutando componentes de usuario no administrados, dichos componentes podrían haber dañado el montón de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="0ad15-109">If an application is running unmanaged user components, then those components might have corrupted the garbage-collected heap.</span></span> <span data-ttu-id="0ad15-110">Esto provoca una infracción de acceso en CLR cuando el recolector de elementos no utilizados intenta desplazarse por el gráfico de objetos.</span><span class="sxs-lookup"><span data-stu-id="0ad15-110">This causes an access violation in the CLR when the garbage collector tries to walk the object graph.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="0ad15-111">Solución</span><span class="sxs-lookup"><span data-stu-id="0ad15-111">Resolution</span></span>  

 <span data-ttu-id="0ad15-112">Al habilitar este asistente, se reduce el tiempo entre el momento en que el componente no administrado daña la pila de recolección de elementos no utilizados y el momento en que se produce la infracción de acceso al forzar que tenga lugar una recolección antes de cada transición administrada.</span><span class="sxs-lookup"><span data-stu-id="0ad15-112">Enabling this assistant reduces the time between when the unmanaged component corrupts the garbage-collected heap and when the access violation happens by forcing a garbage collection to occur before every managed transition.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="0ad15-113">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="0ad15-113">Effect on the Runtime</span></span>  

 <span data-ttu-id="0ad15-114">Produce una recolección de elementos no utilizados siempre que un subproceso realice la transición de código no administrado a administrado.</span><span class="sxs-lookup"><span data-stu-id="0ad15-114">Causes a garbage collection whenever a thread transitions from unmanaged to managed code.</span></span>  
  
## <a name="output"></a><span data-ttu-id="0ad15-115">Resultados</span><span class="sxs-lookup"><span data-stu-id="0ad15-115">Output</span></span>  

 <span data-ttu-id="0ad15-116">Este MDA no produce ninguna salida.</span><span class="sxs-lookup"><span data-stu-id="0ad15-116">This MDA produces no output.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="0ad15-117">Configuración</span><span class="sxs-lookup"><span data-stu-id="0ad15-117">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <gcUnmanagedToManaged/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0ad15-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="0ad15-118">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="0ad15-119">Diagnóstico de errores con asistentes de depuraciones administradas</span><span class="sxs-lookup"><span data-stu-id="0ad15-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="0ad15-120">gcManagedToUnmanaged</span><span class="sxs-lookup"><span data-stu-id="0ad15-120">gcManagedToUnmanaged</span></span>](gcmanagedtounmanaged-mda.md)
- [<span data-ttu-id="0ad15-121">Serialización de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="0ad15-121">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
