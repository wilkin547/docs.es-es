---
title: MDA de invalidOverlappedToPinvoke
ms.date: 03/30/2017
helpviewer_keywords:
- overlapped pointers
- managed debugging assistants (MDAs), overlapped pointers
- invalid overlapped pointer to platform invoke
- InvalidOverlappedToPinvoke MDA
- MDAs (managed debugging assistants), overlapped pointers
- pointers, overlapped
ms.assetid: 28876047-58bd-4fed-9452-c7da346d67c0
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7e9c7e1038591e5e8ea6f62b37ff4d02b2b6a9c5
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71052557"
---
# <a name="invalidoverlappedtopinvoke-mda"></a><span data-ttu-id="41799-102">MDA de invalidOverlappedToPinvoke</span><span class="sxs-lookup"><span data-stu-id="41799-102">invalidOverlappedToPinvoke MDA</span></span>
<span data-ttu-id="41799-103">El asistente para la depuración administrada (MDA) `invalidOverlappedToPinvoke` se activa cuando un puntero superpuesto que no se ha creado en el montón de recolección de elementos no utilizados se pasa a funciones de Win32 específicas.</span><span class="sxs-lookup"><span data-stu-id="41799-103">The `invalidOverlappedToPinvoke` managed debugging assistant (MDA) is activated when an overlapped pointer that was not created on the garbage collection heap is passed to specific Win32 functions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="41799-104">De forma predeterminada, este MDA solo se activa si se define la llamada de invocación de plataforma en el código y el depurador informa del estado de JustMyCode de cada método.</span><span class="sxs-lookup"><span data-stu-id="41799-104">By default, this MDA is activated only if the platform invoke call is defined in your code and the debugger reports the JustMyCode status of each method.</span></span> <span data-ttu-id="41799-105">Un depurador que no entienda JustMyCode (como MDbg.exe sin extensiones) no activará este MDA,</span><span class="sxs-lookup"><span data-stu-id="41799-105">A debugger that does not understand JustMyCode (such as MDbg.exe with no extensions) will not activate this MDA.</span></span> <span data-ttu-id="41799-106">Este MDA se puede habilitar en este tipo de depuradores utilizando un archivo de configuración y estableciendo explícitamente `justMyCode="false"` en el archivo .mda.config (`(<invalidOverlappedToPinvoke enable="true" justMyCode="false"/>`).</span><span class="sxs-lookup"><span data-stu-id="41799-106">This MDA can be enabled for those debuggers by using a configuration file and explicitly settting `justMyCode="false"` in the .mda.config file `(<invalidOverlappedToPinvoke enable="true" justMyCode="false"/>`).</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="41799-107">Síntomas</span><span class="sxs-lookup"><span data-stu-id="41799-107">Symptoms</span></span>  
 <span data-ttu-id="41799-108">Bloqueos o daños inexplicables del montón.</span><span class="sxs-lookup"><span data-stu-id="41799-108">Crashes or unexplainable heap corruptions.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="41799-109">Causa</span><span class="sxs-lookup"><span data-stu-id="41799-109">Cause</span></span>  
 <span data-ttu-id="41799-110">Se pasa un puntero superpuesto que no se ha creado en el montón de recolección de elementos no utilizados a funciones de sistema operativo concretas.</span><span class="sxs-lookup"><span data-stu-id="41799-110">An overlapped pointer that was not created on the garbage collection heap is passed to specific operating system functions.</span></span>  
  
 <span data-ttu-id="41799-111">En la tabla siguiente se muestran las funciones de las que realiza el seguimiento este MDA.</span><span class="sxs-lookup"><span data-stu-id="41799-111">The following table shows the functions that this MDA tracks.</span></span>  
  
|<span data-ttu-id="41799-112">Module</span><span class="sxs-lookup"><span data-stu-id="41799-112">Module</span></span>|<span data-ttu-id="41799-113">Función</span><span class="sxs-lookup"><span data-stu-id="41799-113">Function</span></span>|  
|------------|--------------|  
|<span data-ttu-id="41799-114">HttpApi.dll</span><span class="sxs-lookup"><span data-stu-id="41799-114">HttpApi.dll</span></span>|`HttpReceiveHttpRequest`|  
|<span data-ttu-id="41799-115">IpHlpApi.dll</span><span class="sxs-lookup"><span data-stu-id="41799-115">IpHlpApi.dll</span></span>|`NotifyAddrChange`|  
|<span data-ttu-id="41799-116">kernel32.dll</span><span class="sxs-lookup"><span data-stu-id="41799-116">kernel32.dll</span></span>|`ReadFile`|  
|<span data-ttu-id="41799-117">kernel32.dll</span><span class="sxs-lookup"><span data-stu-id="41799-117">kernel32.dll</span></span>|`ReadFileEx`|  
|<span data-ttu-id="41799-118">kernel32.dll</span><span class="sxs-lookup"><span data-stu-id="41799-118">kernel32.dll</span></span>|`WriteFile`|  
|<span data-ttu-id="41799-119">kernel32.dll</span><span class="sxs-lookup"><span data-stu-id="41799-119">kernel32.dll</span></span>|`WriteFileEx`|  
|<span data-ttu-id="41799-120">kernel32.dll</span><span class="sxs-lookup"><span data-stu-id="41799-120">kernel32.dll</span></span>|`ReadDirectoryChangesW`|  
|<span data-ttu-id="41799-121">kernel32.dll</span><span class="sxs-lookup"><span data-stu-id="41799-121">kernel32.dll</span></span>|`PostQueuedCompletionStatus`|  
|<span data-ttu-id="41799-122">MSWSock.dll</span><span class="sxs-lookup"><span data-stu-id="41799-122">MSWSock.dll</span></span>|`ConnectEx`|  
|<span data-ttu-id="41799-123">WS2_32.dll</span><span class="sxs-lookup"><span data-stu-id="41799-123">WS2_32.dll</span></span>|`WSASend`|  
|<span data-ttu-id="41799-124">WS2_32.dll</span><span class="sxs-lookup"><span data-stu-id="41799-124">WS2_32.dll</span></span>|`WSASendTo`|  
|<span data-ttu-id="41799-125">WS2_32.dll</span><span class="sxs-lookup"><span data-stu-id="41799-125">WS2_32.dll</span></span>|`WSARecv`|  
|<span data-ttu-id="41799-126">WS2_32.dll</span><span class="sxs-lookup"><span data-stu-id="41799-126">WS2_32.dll</span></span>|`WSARecvFrom`|  
|<span data-ttu-id="41799-127">MQRT.dll</span><span class="sxs-lookup"><span data-stu-id="41799-127">MQRT.dll</span></span>|`MQReceiveMessage`|  
  
 <span data-ttu-id="41799-128">La probabilidad de daños en el montón es alta para esta condición porque se podría descargar el <xref:System.AppDomain> que hace la llamada.</span><span class="sxs-lookup"><span data-stu-id="41799-128">The potential for heap corruption is high for this condition because the <xref:System.AppDomain> making the call might unload.</span></span> <span data-ttu-id="41799-129">Si se descarga el <xref:System.AppDomain>, el código de la aplicación liberará la memoria del puntero superpuesto, provocando daños cuando termine la operación, o producirá la pérdida de memoria, lo que más adelante causará dificultades.</span><span class="sxs-lookup"><span data-stu-id="41799-129">If the <xref:System.AppDomain> unloads, the application code will either free the memory for the overlapped pointer, causing corruption when the operation finishes, or the code will leak the memory, causing difficulties later.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="41799-130">Resolución</span><span class="sxs-lookup"><span data-stu-id="41799-130">Resolution</span></span>  
 <span data-ttu-id="41799-131">Use un objeto <xref:System.Threading.Overlapped>, llamando al método <xref:System.Threading.Overlapped.Pack%2A> para obtener una estructura <xref:System.Threading.NativeOverlapped> que se puede pasar a la función.</span><span class="sxs-lookup"><span data-stu-id="41799-131">Use an <xref:System.Threading.Overlapped> object, calling the <xref:System.Threading.Overlapped.Pack%2A> method to get a <xref:System.Threading.NativeOverlapped> structure that can be passed to the function.</span></span> <span data-ttu-id="41799-132">Si se descarga el <xref:System.AppDomain>, CLR espera hasta que la operación asincrónica finalice antes de liberar el puntero.</span><span class="sxs-lookup"><span data-stu-id="41799-132">If the <xref:System.AppDomain> unloads, the CLR waits until the asynchronous operation completes before freeing the pointer.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="41799-133">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="41799-133">Effect on the Runtime</span></span>  
 <span data-ttu-id="41799-134">Este MDA no tiene ningún efecto en el CLR.</span><span class="sxs-lookup"><span data-stu-id="41799-134">This MDA had no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="41799-135">Resultados</span><span class="sxs-lookup"><span data-stu-id="41799-135">Output</span></span>  
 <span data-ttu-id="41799-136">A continuación se muestra un ejemplo de resultado de este MDA.</span><span class="sxs-lookup"><span data-stu-id="41799-136">The following is an example of output from this MDA.</span></span>  
  
 `An overlapped pointer (0x00ea3430) that was not allocated on the GC heap was passed via Pinvoke to the Win32 function 'WriteFile' in module 'KERNEL32.DLL'. If the AppDomain is shut down, this can cause heap corruption when the async I/O completes. The best solution is to pass a NativeOverlapped structure retrieved from a call to System.Threading.Overlapped.Pack(). If the AppDomain exits, the CLR will keep this structure alive and pinned until the I/O completes.`  
  
## <a name="configuration"></a><span data-ttu-id="41799-137">Configuración</span><span class="sxs-lookup"><span data-stu-id="41799-137">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidOverlappedToPinvoke/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="41799-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="41799-138">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="41799-139">Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)</span><span class="sxs-lookup"><span data-stu-id="41799-139">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="41799-140">Serialización de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="41799-140">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
