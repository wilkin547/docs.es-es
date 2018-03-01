---
title: "ICorProfilerInfo2::DoStackSnapshot (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerInfo2.DoStackSnapshot
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::DoStackSnapshot
helpviewer_keywords:
- ICorProfilerInfo2::DoStackSnapshot method [.NET Framework profiling]
- DoStackSnapshot method [.NET Framework profiling]
ms.assetid: 287b11e9-7c52-4a13-ba97-751203fa97f4
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5548254eb160547643a874fd2e31a085ec6f3ecb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo2dostacksnapshot-method"></a><span data-ttu-id="e4794-102">ICorProfilerInfo2::DoStackSnapshot (Método)</span><span class="sxs-lookup"><span data-stu-id="e4794-102">ICorProfilerInfo2::DoStackSnapshot Method</span></span>
<span data-ttu-id="e4794-103">Recorre los marcos administrados en la pila para el subproceso especificado y envía información al generador de perfiles mediante una devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="e4794-103">Walks the managed frames on the stack for the specified thread, and sends information to the profiler through a callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4794-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e4794-104">Syntax</span></span>  
  
```  
HRESULT DoStackSnapshot(  
    [in] ThreadID thread,  
    [in] StackSnapshotCallback *callback,  
    [in] ULONG32 infoFlags,  
    [in] void *clientData,  
    [in, size_is(contextSize), length_is(contextSize)] BYTE context[],  
    [in] ULONG32 contextSize);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e4794-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e4794-105">Parameters</span></span>  
 `thread`  
 <span data-ttu-id="e4794-106">[in] El identificador del subproceso de destino.</span><span class="sxs-lookup"><span data-stu-id="e4794-106">[in] The ID of the target thread.</span></span>  
  
 <span data-ttu-id="e4794-107">Si se pasa null en `thread` , se genera una instantánea del subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="e4794-107">Passing null in `thread` yields a snapshot of the current thread.</span></span> <span data-ttu-id="e4794-108">Si un `ThreadID` de se pasa un subproceso diferente, common language runtime (CLR) suspende ese subproceso, realiza la instantánea y se reanuda.</span><span class="sxs-lookup"><span data-stu-id="e4794-108">If a `ThreadID` of a different thread is passed, the common language runtime (CLR) suspends that thread, performs the snapshot, and resumes.</span></span>  
  
 `callback`  
 <span data-ttu-id="e4794-109">[in] Un puntero a la implementación de la [StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md) método, que es llamado por el CLR para proporcionar el generador de perfiles con información sobre cada marco administrado y cada ejecución de marcos no administrados.</span><span class="sxs-lookup"><span data-stu-id="e4794-109">[in] A pointer to the implementation of the [StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md) method, which is called by the CLR to provide the profiler with information on each managed frame and each run of unmanaged frames.</span></span>  
  
 <span data-ttu-id="e4794-110">El `StackSnapshotCallback` método lo implementa el escritor del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="e4794-110">The `StackSnapshotCallback` method is implemented by the profiler writer.</span></span>  
  
 `infoFlags`  
 <span data-ttu-id="e4794-111">[in] Un valor de la [COR_PRF_SNAPSHOT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-snapshot-info-enumeration.md) enumeración, que especifica la cantidad de datos que se pasarán nuevo para cada fotograma por `StackSnapshotCallback`.</span><span class="sxs-lookup"><span data-stu-id="e4794-111">[in] A value of the [COR_PRF_SNAPSHOT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-snapshot-info-enumeration.md) enumeration, which specifies the amount of data to be passed back for each frame by `StackSnapshotCallback`.</span></span>  
  
 `clientData`  
 <span data-ttu-id="e4794-112">[in] Un puntero a los datos de cliente, que se pasan directamente a la `StackSnapshotCallback` función de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="e4794-112">[in] A pointer to the client data, which is passed straight through to the `StackSnapshotCallback` callback function.</span></span>  
  
 `context`  
 <span data-ttu-id="e4794-113">[in] Un puntero a Win32 `CONTEXT` estructura, que se utiliza para inicializar el recorrido de pila.</span><span class="sxs-lookup"><span data-stu-id="e4794-113">[in] A pointer to a Win32 `CONTEXT` structure, which is used to seed the stack walk.</span></span> <span data-ttu-id="e4794-114">Win32 `CONTEXT` estructura contiene valores de los registros de la CPU y representa el estado de la CPU en un momento determinado.</span><span class="sxs-lookup"><span data-stu-id="e4794-114">The Win32 `CONTEXT` structure contains values of the CPU registers and represents the state of the CPU at a particular moment in time.</span></span>  
  
 <span data-ttu-id="e4794-115">El valor de inicialización ayuda a CLR a determinar dónde comenzar el recorrido de pila, si la parte superior de la pila es código auxiliar no administrado; en caso contrario, se omite el valor de inicialización.</span><span class="sxs-lookup"><span data-stu-id="e4794-115">The seed helps the CLR determine where to begin the stack walk, if the top of the stack is unmanaged helper code; otherwise, the seed is ignored.</span></span> <span data-ttu-id="e4794-116">Debe suministrar un valor de inicialización para los recorridos asincrónicos.</span><span class="sxs-lookup"><span data-stu-id="e4794-116">A seed must be supplied for an asynchronous walk.</span></span> <span data-ttu-id="e4794-117">Si va a realizar un recorrido sincrónico, no es necesario ningún valor de inicialización.</span><span class="sxs-lookup"><span data-stu-id="e4794-117">If you are doing a synchronous walk, no seed is necessary.</span></span>  
  
 <span data-ttu-id="e4794-118">El `context` parámetro sólo es válido si el marcador COR_PRF_SNAPSHOT_CONTEXT se pasó en el `infoFlags` parámetro.</span><span class="sxs-lookup"><span data-stu-id="e4794-118">The `context` parameter is valid only if the COR_PRF_SNAPSHOT_CONTEXT flag was passed in the `infoFlags` parameter.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="e4794-119">[in] El tamaño de la `CONTEXT` estructura, que hace referencia el `context` parámetro.</span><span class="sxs-lookup"><span data-stu-id="e4794-119">[in] The size of the `CONTEXT` structure, which is referenced by the `context` parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e4794-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e4794-120">Remarks</span></span>  
 <span data-ttu-id="e4794-121">Si se pasa null para `thread` , se genera una instantánea del subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="e4794-121">Passing null for `thread` yields a snapshot of the current thread.</span></span> <span data-ttu-id="e4794-122">Pueden tomar instantáneas de otros subprocesos sólo si se suspende el subproceso de destino en el momento.</span><span class="sxs-lookup"><span data-stu-id="e4794-122">Snapshots can be taken of other threads only if the target thread is suspended at the time.</span></span>  
  
 <span data-ttu-id="e4794-123">Cuando el generador de perfiles desea recorrer la pila, llama al método `DoStackSnapshot`.</span><span class="sxs-lookup"><span data-stu-id="e4794-123">When the profiler wants to walk the stack, it calls `DoStackSnapshot`.</span></span> <span data-ttu-id="e4794-124">Antes de que el CLR vuelva de esa llamada, llama a su `StackSnapshotCallback` varias veces, una vez para cada administran marco (o ejecución de marcos no administrados) en la pila.</span><span class="sxs-lookup"><span data-stu-id="e4794-124">Before the CLR returns from that call, it calls your `StackSnapshotCallback` several times, once for each managed frame (or run of unmanaged frames) on the stack.</span></span> <span data-ttu-id="e4794-125">Cuando se encuentran marcos no administrados, debe recorrer a usted mismo.</span><span class="sxs-lookup"><span data-stu-id="e4794-125">When unmanaged frames are encountered, you must walk them yourself.</span></span>  
  
 <span data-ttu-id="e4794-126">El orden en el que se recorre la pila es el inverso de cómo los fotogramas se insertan en la pila: hoja (Insertar última) en primer lugar, principal (insertar primero) fotogramas última.</span><span class="sxs-lookup"><span data-stu-id="e4794-126">The order in which the stack is walked is the reverse of how the frames were pushed onto the stack: leaf (last-pushed) frame first, main (first-pushed) frame last.</span></span>  
  
 <span data-ttu-id="e4794-127">Para obtener más información acerca de cómo programar el generador de perfiles para rastrear pilas administradas, vea [recorrido de pila de generador de perfiles en .NET Framework 2.0: Basics y versiones posteriores](http://go.microsoft.com/fwlink/?LinkId=73638).</span><span class="sxs-lookup"><span data-stu-id="e4794-127">For more information about how to program the profiler to walk managed stacks, see [Profiler Stack Walking in the .NET Framework 2.0: Basics and Beyond](http://go.microsoft.com/fwlink/?LinkId=73638).</span></span>  
  
 <span data-ttu-id="e4794-128">Un recorrido de pila puede ser sincrónicas o asincrónicas, como se explica en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="e4794-128">A stack walk can be synchronous or asynchronous, as explained in the following sections.</span></span>  
  
## <a name="synchronous-stack-walk"></a><span data-ttu-id="e4794-129">Recorrido de pila sincrónico</span><span class="sxs-lookup"><span data-stu-id="e4794-129">Synchronous Stack Walk</span></span>  
 <span data-ttu-id="e4794-130">Un recorrido de pila sincrónico implica recorrer la pila del subproceso actual en respuesta a una devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="e4794-130">A synchronous stack walk involves walking the stack of the current thread in response to a callback.</span></span> <span data-ttu-id="e4794-131">No se requiere inicialización ni suspensión.</span><span class="sxs-lookup"><span data-stu-id="e4794-131">It does not require seeding or suspending.</span></span>  
  
 <span data-ttu-id="e4794-132">Realice una sincrónica a llamar cuando, en respuesta a una llamada entre el generador de perfiles de CLR [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) (o [ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)) métodos, se llama a `DoStackSnapshot` para recorrer la pila de la subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="e4794-132">You make a synchronous call when, in response to the CLR calling one of your profiler's [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) (or [ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)) methods, you call `DoStackSnapshot` to walk the stack of the current thread.</span></span> <span data-ttu-id="e4794-133">Esto es útil cuando desea ver la pila de aspecto en una notificación como [ICorProfilerCallback:: ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md).</span><span class="sxs-lookup"><span data-stu-id="e4794-133">This is useful when you want to see what the stack looks like at a notification such as [ICorProfilerCallback::ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md).</span></span> <span data-ttu-id="e4794-134">Se llama a `DoStackSnapshot` desde su `ICorProfilerCallback` método, se pasa null en el `context` y `thread` parámetros.</span><span class="sxs-lookup"><span data-stu-id="e4794-134">You just call `DoStackSnapshot` from within your `ICorProfilerCallback` method, passing null in the `context` and `thread` parameters.</span></span>  
  
## <a name="asynchronous-stack-walk"></a><span data-ttu-id="e4794-135">Recorrido de pila asincrónico</span><span class="sxs-lookup"><span data-stu-id="e4794-135">Asynchronous Stack Walk</span></span>  
 <span data-ttu-id="e4794-136">Un recorrido de pila asincrónico implica el recorrido de la pila de un subproceso diferente o recorrer la pila del subproceso actual, no en respuesta a una devolución de llamada, pero por cambiando la configuración de puntero de instrucción del subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="e4794-136">An asynchronous stack walk entails walking the stack of a different thread, or walking the stack of the current thread, not in response to a callback, but by hijacking the current thread's instruction pointer.</span></span> <span data-ttu-id="e4794-137">Un recorrido asincrónico requiere un valor de inicialización si la parte superior de la pila es código no administrado que no forma parte de una plataforma de invocación (PInvoke) o llamada de COM, pero código auxiliar en el CLR.</span><span class="sxs-lookup"><span data-stu-id="e4794-137">An asynchronous walk requires a seed if the top of the stack is unmanaged code that is not part of a platform invoke (PInvoke) or COM call, but helper code in the CLR itself.</span></span> <span data-ttu-id="e4794-138">Por ejemplo, el código que realiza la recopilación de compilación o de elementos no utilizados de just-in-time (JIT) es código auxiliar.</span><span class="sxs-lookup"><span data-stu-id="e4794-138">For example, code that does just-in-time (JIT) compiling or garbage collection is helper code.</span></span>  
  
 <span data-ttu-id="e4794-139">Obtener un valor de inicialización suspendiendo directamente el subproceso de destino y recorriendo la pila usted mismo, hasta que encuentre el primer marco administrado.</span><span class="sxs-lookup"><span data-stu-id="e4794-139">You obtain a seed by directly suspending the target thread and walking its stack yourself, until you find the topmost managed frame.</span></span> <span data-ttu-id="e4794-140">Después de que se suspende el subproceso de destino, obtenga el contexto del registro actual del subproceso de destino.</span><span class="sxs-lookup"><span data-stu-id="e4794-140">After the target thread is suspended, get the target thread's current register context.</span></span> <span data-ttu-id="e4794-141">A continuación, determine si el contexto del Registro apunta a código no administrado mediante una llamada a [ICorProfilerInfo:: GetFunctionFromIP](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctionfromip-method.md) : si devuelve un `FunctionID` igual a cero, el marco es código no administrado.</span><span class="sxs-lookup"><span data-stu-id="e4794-141">Next, determine whether the register context points to unmanaged code by calling [ICorProfilerInfo::GetFunctionFromIP](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctionfromip-method.md) — if it returns a `FunctionID` equal to zero, the frame is unmanaged code.</span></span> <span data-ttu-id="e4794-142">Ahora, recorra la pila hasta que llegue al primer marco administrado y, a continuación, calcule el contexto de inicialización basado en el contexto del registro para ese marco.</span><span class="sxs-lookup"><span data-stu-id="e4794-142">Now, walk the stack until you reach the first managed frame, and then calculate the seed context based on the register context for that frame.</span></span>  
  
 <span data-ttu-id="e4794-143">Llamar a `DoStackSnapshot` con su contexto de inicialización para comenzar el recorrido de pila asincrónico.</span><span class="sxs-lookup"><span data-stu-id="e4794-143">Call `DoStackSnapshot` with your seed context to begin the asynchronous stack walk.</span></span> <span data-ttu-id="e4794-144">Si no se proporciona un valor de inicialización, `DoStackSnapshot` podría omitir los marcos administrados en la parte superior de la pila y, por lo tanto, le proporcionará un recorrido de pila incompleto.</span><span class="sxs-lookup"><span data-stu-id="e4794-144">If you do not supply a seed, `DoStackSnapshot` might skip managed frames at the top of the stack and, consequently, will give you an incomplete stack walk.</span></span> <span data-ttu-id="e4794-145">Si se proporciona un valor de inicialización, debe señalar a compilado JIT o Native Image Generator (Ngen.exe)-genera código; en caso contrario, `DoStackSnapshot` devuelve el código de error, CORPROF_E_STACKSNAPSHOT_UNMANAGED_CTX.</span><span class="sxs-lookup"><span data-stu-id="e4794-145">If you do supply a seed, it must point to JIT-compiled or Native Image Generator (Ngen.exe)-generated code; otherwise, `DoStackSnapshot` returns the failure code, CORPROF_E_STACKSNAPSHOT_UNMANAGED_CTX.</span></span>  
  
 <span data-ttu-id="e4794-146">Recorridos de pila asincrónicos fácilmente pueden causar interbloqueos o infracciones de acceso, a menos que siga estas instrucciones:</span><span class="sxs-lookup"><span data-stu-id="e4794-146">Asynchronous stack walks can easily cause deadlocks or access violations, unless you follow these guidelines:</span></span>  
  
-   <span data-ttu-id="e4794-147">Cuando suspende directamente los subprocesos, recuerde que sólo un subproceso que nunca se ha ejecutado el código administrado puede suspender otro subproceso.</span><span class="sxs-lookup"><span data-stu-id="e4794-147">When you directly suspend threads, remember that only a thread that has never run managed code can suspend another thread.</span></span>  
  
-   <span data-ttu-id="e4794-148">Bloquear siempre su [ICorProfilerCallback:: ThreadDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md) hasta que finalice el recorrido de pila del subproceso que la devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="e4794-148">Always block in your [ICorProfilerCallback::ThreadDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md) callback until that thread's stack walk is complete.</span></span>  
  
-   <span data-ttu-id="e4794-149">No mantenga un bloqueo mientras el generador de perfiles llama a una función CLR que puede desencadenar una recolección de elementos.</span><span class="sxs-lookup"><span data-stu-id="e4794-149">Do not hold a lock while your profiler calls into a CLR function that can trigger a garbage collection.</span></span> <span data-ttu-id="e4794-150">Es decir, no mantenga un bloqueo si el subproceso que posee podría realizar una llamada que desencadena una recolección.</span><span class="sxs-lookup"><span data-stu-id="e4794-150">That is, do not hold a lock if the owning thread might make a call that triggers a garbage collection.</span></span>  
  
 <span data-ttu-id="e4794-151">Hay también un riesgo de interbloqueo si se llama a `DoStackSnapshot` desde un subproceso que ha creado el generador de perfiles para que pueda recorrer la pila de un subproceso de destino diferente.</span><span class="sxs-lookup"><span data-stu-id="e4794-151">There is also a risk of deadlock if you call `DoStackSnapshot` from a thread that your profiler has created so that you can walk the stack of a separate target thread.</span></span> <span data-ttu-id="e4794-152">La primera vez que el subproceso que creó entra en ciertos `ICorProfilerInfo*` métodos (incluidos los `DoStackSnapshot`), el CLR realizará por subproceso, inicialización específica del CLR en ese subproceso.</span><span class="sxs-lookup"><span data-stu-id="e4794-152">The first time the thread you created enters certain `ICorProfilerInfo*` methods (including `DoStackSnapshot`), the CLR will perform per-thread, CLR-specific initialization on that thread.</span></span> <span data-ttu-id="e4794-153">Si el generador de perfiles ha suspendido el subproceso de destino cuyo pila intenta recorrer y si ese subproceso de destino ha ocurrido con su propio bloqueo necesario para realizar esta inicialización por subproceso, se producirá un interbloqueo.</span><span class="sxs-lookup"><span data-stu-id="e4794-153">If your profiler has suspended the target thread whose stack you are trying to walk, and if that target thread happened to own a lock necessary for performing this per-thread initialization, a deadlock will occur.</span></span> <span data-ttu-id="e4794-154">Para evitar este interbloqueo, realizar una llamada inicial a `DoStackSnapshot` desde el subproceso creado por el generador de perfiles para recorrer otro subproceso de destino, pero no suspende el subproceso de destino primero.</span><span class="sxs-lookup"><span data-stu-id="e4794-154">To avoid this deadlock, make an initial call into `DoStackSnapshot` from your profiler-created thread to walk a separate target thread, but do not suspend the target thread first.</span></span> <span data-ttu-id="e4794-155">Esta llamada inicial asegura que la inicialización por subproceso puede completarse sin interbloqueos.</span><span class="sxs-lookup"><span data-stu-id="e4794-155">This initial call ensures that the per-thread initialization can complete without deadlock.</span></span> <span data-ttu-id="e4794-156">Si `DoStackSnapshot` se realiza correctamente y notifica al menos un fotograma, después de ese punto, que son seguros para ese subproceso creado por el generador de perfiles para suspender cualquier subproceso de destino y la llamada `DoStackSnapshot` para recorrer la pila de ese subproceso de destino.</span><span class="sxs-lookup"><span data-stu-id="e4794-156">If `DoStackSnapshot` succeeds and reports at least one frame, after that point, it will be safe for that profiler-created thread to suspend any target thread and call `DoStackSnapshot` to walk the stack of that target thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4794-157">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e4794-157">Requirements</span></span>  
 <span data-ttu-id="e4794-158">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4794-158">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4794-159">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e4794-159">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e4794-160">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e4794-160">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e4794-161">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4794-161">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4794-162">Vea también</span><span class="sxs-lookup"><span data-stu-id="e4794-162">See Also</span></span>  
 [<span data-ttu-id="e4794-163">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e4794-163">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="e4794-164">ICorProfilerInfo2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e4794-164">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
