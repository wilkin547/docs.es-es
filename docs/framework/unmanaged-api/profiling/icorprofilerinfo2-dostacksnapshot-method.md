---
title: ICorProfilerInfo2::DoStackSnapshot (Método)
ms.date: 03/30/2017
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
ms.openlocfilehash: 10cc9dedfa34cd5235df721d7010bbd928fbc3ba
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727242"
---
# <a name="icorprofilerinfo2dostacksnapshot-method"></a><span data-ttu-id="3f5f7-102">ICorProfilerInfo2::DoStackSnapshot (Método)</span><span class="sxs-lookup"><span data-stu-id="3f5f7-102">ICorProfilerInfo2::DoStackSnapshot Method</span></span>

<span data-ttu-id="3f5f7-103">Recorre los marcos administrados de la pila para el subproceso especificado y envía información al generador de perfiles a través de una devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="3f5f7-103">Walks the managed frames on the stack for the specified thread, and sends information to the profiler through a callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f5f7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3f5f7-104">Syntax</span></span>  
  
```cpp  
HRESULT DoStackSnapshot(  
    [in] ThreadID thread,  
    [in] StackSnapshotCallback *callback,  
    [in] ULONG32 infoFlags,  
    [in] void *clientData,  
    [in, size_is(contextSize), length_is(contextSize)] BYTE context[],  
    [in] ULONG32 contextSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f5f7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3f5f7-105">Parameters</span></span>  

 `thread`  
 <span data-ttu-id="3f5f7-106">de IDENTIFICADOR del subproceso de destino.</span><span class="sxs-lookup"><span data-stu-id="3f5f7-106">[in] The ID of the target thread.</span></span>  
  
 <span data-ttu-id="3f5f7-107">Si se pasa null en, se `thread` produce una instantánea del subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="3f5f7-107">Passing null in `thread` yields a snapshot of the current thread.</span></span> <span data-ttu-id="3f5f7-108">Si `ThreadID` se pasa un de un subproceso diferente, el Common Language Runtime (CLR) suspende ese subproceso, realiza la instantánea y se reanuda.</span><span class="sxs-lookup"><span data-stu-id="3f5f7-108">If a `ThreadID` of a different thread is passed, the common language runtime (CLR) suspends that thread, performs the snapshot, and resumes.</span></span>  
  
 `callback`  
 <span data-ttu-id="3f5f7-109">de Un puntero a la implementación del método [StackSnapshotCallback](stacksnapshotcallback-function.md) , al que llama CLR para proporcionar al generador de perfiles información sobre cada marco administrado y cada ejecución de marcos no administrados.</span><span class="sxs-lookup"><span data-stu-id="3f5f7-109">[in] A pointer to the implementation of the [StackSnapshotCallback](stacksnapshotcallback-function.md) method, which is called by the CLR to provide the profiler with information on each managed frame and each run of unmanaged frames.</span></span>  
  
 <span data-ttu-id="3f5f7-110">El `StackSnapshotCallback` escritor del generador de perfiles implementa el método.</span><span class="sxs-lookup"><span data-stu-id="3f5f7-110">The `StackSnapshotCallback` method is implemented by the profiler writer.</span></span>  
  
 `infoFlags`  
 <span data-ttu-id="3f5f7-111">de Un valor de la enumeración [COR_PRF_SNAPSHOT_INFO](cor-prf-snapshot-info-enumeration.md) , que especifica la cantidad de datos que se van a devolver para cada marco `StackSnapshotCallback` .</span><span class="sxs-lookup"><span data-stu-id="3f5f7-111">[in] A value of the [COR_PRF_SNAPSHOT_INFO](cor-prf-snapshot-info-enumeration.md) enumeration, which specifies the amount of data to be passed back for each frame by `StackSnapshotCallback`.</span></span>  
  
 `clientData`  
 <span data-ttu-id="3f5f7-112">de Puntero a los datos del cliente, que se pasa directamente a la `StackSnapshotCallback` función de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="3f5f7-112">[in] A pointer to the client data, which is passed straight through to the `StackSnapshotCallback` callback function.</span></span>  
  
 `context`  
 <span data-ttu-id="3f5f7-113">de Puntero a una estructura de Win32 `CONTEXT` , que se usa para inicializar el recorrido de la pila.</span><span class="sxs-lookup"><span data-stu-id="3f5f7-113">[in] A pointer to a Win32 `CONTEXT` structure, which is used to seed the stack walk.</span></span> <span data-ttu-id="3f5f7-114">La `CONTEXT` estructura Win32 contiene los valores de los registros de CPU y representa el estado de la CPU en un momento determinado en el tiempo.</span><span class="sxs-lookup"><span data-stu-id="3f5f7-114">The Win32 `CONTEXT` structure contains values of the CPU registers and represents the state of the CPU at a particular moment in time.</span></span>  
  
 <span data-ttu-id="3f5f7-115">La inicialización ayuda a CLR a determinar dónde debe comenzar el recorrido de la pila, si la parte superior de la pila es código auxiliar no administrado. de lo contrario, se omite el inicialización.</span><span class="sxs-lookup"><span data-stu-id="3f5f7-115">The seed helps the CLR determine where to begin the stack walk, if the top of the stack is unmanaged helper code; otherwise, the seed is ignored.</span></span> <span data-ttu-id="3f5f7-116">Se debe proporcionar un parámetro de inicialización para un recorrido asincrónico.</span><span class="sxs-lookup"><span data-stu-id="3f5f7-116">A seed must be supplied for an asynchronous walk.</span></span> <span data-ttu-id="3f5f7-117">Si está realizando un recorrido sincrónico, no es necesario ningún SEED.</span><span class="sxs-lookup"><span data-stu-id="3f5f7-117">If you are doing a synchronous walk, no seed is necessary.</span></span>  
  
 <span data-ttu-id="3f5f7-118">El `context` parámetro solo es válido si la marca de COR_PRF_SNAPSHOT_CONTEXT se ha pasado en el `infoFlags` parámetro.</span><span class="sxs-lookup"><span data-stu-id="3f5f7-118">The `context` parameter is valid only if the COR_PRF_SNAPSHOT_CONTEXT flag was passed in the `infoFlags` parameter.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="3f5f7-119">de Tamaño de la `CONTEXT` estructura, al que hace referencia el `context` parámetro.</span><span class="sxs-lookup"><span data-stu-id="3f5f7-119">[in] The size of the `CONTEXT` structure, which is referenced by the `context` parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3f5f7-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3f5f7-120">Remarks</span></span>  

 <span data-ttu-id="3f5f7-121">Si se pasa null para, se `thread` produce una instantánea del subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="3f5f7-121">Passing null for `thread` yields a snapshot of the current thread.</span></span> <span data-ttu-id="3f5f7-122">Las instantáneas se pueden tomar de otros subprocesos solo si el subproceso de destino se suspende en el momento.</span><span class="sxs-lookup"><span data-stu-id="3f5f7-122">Snapshots can be taken of other threads only if the target thread is suspended at the time.</span></span>  
  
 <span data-ttu-id="3f5f7-123">Cuando el generador de perfiles desea recorrer la pila, llama a `DoStackSnapshot` .</span><span class="sxs-lookup"><span data-stu-id="3f5f7-123">When the profiler wants to walk the stack, it calls `DoStackSnapshot`.</span></span> <span data-ttu-id="3f5f7-124">Antes de que el CLR vuelva de esa llamada, llama a la `StackSnapshotCallback` varias veces, una vez por cada fotograma administrado (o la ejecución de marcos no administrados) en la pila.</span><span class="sxs-lookup"><span data-stu-id="3f5f7-124">Before the CLR returns from that call, it calls your `StackSnapshotCallback` several times, once for each managed frame (or run of unmanaged frames) on the stack.</span></span> <span data-ttu-id="3f5f7-125">Cuando se encuentren fotogramas no administrados, debe recorrerlos usted mismo.</span><span class="sxs-lookup"><span data-stu-id="3f5f7-125">When unmanaged frames are encountered, you must walk them yourself.</span></span>  
  
 <span data-ttu-id="3f5f7-126">El orden en el que se recorre la pila es el inverso de cómo se insertaron los fotogramas en la pila: primero el fotograma (última inserción), el marco principal (primero insertado).</span><span class="sxs-lookup"><span data-stu-id="3f5f7-126">The order in which the stack is walked is the reverse of how the frames were pushed onto the stack: leaf (last-pushed) frame first, main (first-pushed) frame last.</span></span>  
  
 <span data-ttu-id="3f5f7-127">Para obtener más información sobre cómo programar el generador de perfiles para guiar pilas administradas, consulte [recorrido de la pila del generador de perfiles en el .NET Framework 2,0: aspectos básicos y más allá](/previous-versions/dotnet/articles/bb264782(v=msdn.10)).</span><span class="sxs-lookup"><span data-stu-id="3f5f7-127">For more information about how to program the profiler to walk managed stacks, see [Profiler Stack Walking in the .NET Framework 2.0: Basics and Beyond](/previous-versions/dotnet/articles/bb264782(v=msdn.10)).</span></span>  
  
 <span data-ttu-id="3f5f7-128">Un recorrido de pila puede ser sincrónico o asincrónico, como se explica en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="3f5f7-128">A stack walk can be synchronous or asynchronous, as explained in the following sections.</span></span>  
  
## <a name="synchronous-stack-walk"></a><span data-ttu-id="3f5f7-129">Recorrido de pila sincrónico</span><span class="sxs-lookup"><span data-stu-id="3f5f7-129">Synchronous Stack Walk</span></span>  

 <span data-ttu-id="3f5f7-130">Un recorrido de pila sincrónico implica recorrer la pila del subproceso actual en respuesta a una devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="3f5f7-130">A synchronous stack walk involves walking the stack of the current thread in response to a callback.</span></span> <span data-ttu-id="3f5f7-131">No requiere propagación ni suspensión.</span><span class="sxs-lookup"><span data-stu-id="3f5f7-131">It does not require seeding or suspending.</span></span>  
  
 <span data-ttu-id="3f5f7-132">Realiza una llamada sincrónica cuando, en respuesta a CLR que llama a uno de los métodos [ICorProfilerCallback](icorprofilercallback-interface.md) (o [ICorProfilerCallback2](icorprofilercallback2-interface.md)) del generador de perfiles, llama `DoStackSnapshot` a para recorrer la pila del subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="3f5f7-132">You make a synchronous call when, in response to the CLR calling one of your profiler's [ICorProfilerCallback](icorprofilercallback-interface.md) (or [ICorProfilerCallback2](icorprofilercallback2-interface.md)) methods, you call `DoStackSnapshot` to walk the stack of the current thread.</span></span> <span data-ttu-id="3f5f7-133">Esto resulta útil cuando desea ver el aspecto de la pila en una notificación como [ICorProfilerCallback:: ObjectAllocated](icorprofilercallback-objectallocated-method.md).</span><span class="sxs-lookup"><span data-stu-id="3f5f7-133">This is useful when you want to see what the stack looks like at a notification such as [ICorProfilerCallback::ObjectAllocated](icorprofilercallback-objectallocated-method.md).</span></span> <span data-ttu-id="3f5f7-134">Basta con llamar a `DoStackSnapshot` desde dentro del `ICorProfilerCallback` método, pasando null en `context` los `thread` parámetros y.</span><span class="sxs-lookup"><span data-stu-id="3f5f7-134">You just call `DoStackSnapshot` from within your `ICorProfilerCallback` method, passing null in the `context` and `thread` parameters.</span></span>  
  
## <a name="asynchronous-stack-walk"></a><span data-ttu-id="3f5f7-135">Recorrido de pila asincrónico</span><span class="sxs-lookup"><span data-stu-id="3f5f7-135">Asynchronous Stack Walk</span></span>  

 <span data-ttu-id="3f5f7-136">Un recorrido de pila asincrónico conlleva el recorrido de la pila de un subproceso diferente o el recorrido de la pila del subproceso actual, no en respuesta a una devolución de llamada, pero mediante el secuestro del puntero de instrucción del subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="3f5f7-136">An asynchronous stack walk entails walking the stack of a different thread, or walking the stack of the current thread, not in response to a callback, but by hijacking the current thread's instruction pointer.</span></span> <span data-ttu-id="3f5f7-137">Un recorrido asincrónico requiere un inicialización si la parte superior de la pila es código no administrado que no forma parte de una invocación de plataforma (PInvoke) o una llamada COM, sino código auxiliar en el propio CLR.</span><span class="sxs-lookup"><span data-stu-id="3f5f7-137">An asynchronous walk requires a seed if the top of the stack is unmanaged code that is not part of a platform invoke (PInvoke) or COM call, but helper code in the CLR itself.</span></span> <span data-ttu-id="3f5f7-138">Por ejemplo, el código que realiza la compilación Just-in-Time (JIT) o la recolección de elementos no utilizados es código auxiliar.</span><span class="sxs-lookup"><span data-stu-id="3f5f7-138">For example, code that does just-in-time (JIT) compiling or garbage collection is helper code.</span></span>  
  
 <span data-ttu-id="3f5f7-139">Para obtener un SEED, se suspende directamente el subproceso de destino y se recorre su pila, hasta que encuentre el marco administrado de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="3f5f7-139">You obtain a seed by directly suspending the target thread and walking its stack yourself, until you find the topmost managed frame.</span></span> <span data-ttu-id="3f5f7-140">Una vez suspendido el subproceso de destino, obtenga el contexto de registro actual del subproceso de destino.</span><span class="sxs-lookup"><span data-stu-id="3f5f7-140">After the target thread is suspended, get the target thread's current register context.</span></span> <span data-ttu-id="3f5f7-141">A continuación, determine si el contexto de registro apunta a código no administrado llamando a [ICorProfilerInfo:: getfunctionfromip (](icorprofilerinfo-getfunctionfromip-method.md) ; si devuelve un `FunctionID` valor igual a cero, el marco es código no administrado.</span><span class="sxs-lookup"><span data-stu-id="3f5f7-141">Next, determine whether the register context points to unmanaged code by calling [ICorProfilerInfo::GetFunctionFromIP](icorprofilerinfo-getfunctionfromip-method.md) — if it returns a `FunctionID` equal to zero, the frame is unmanaged code.</span></span> <span data-ttu-id="3f5f7-142">Ahora, recorra la pila hasta llegar al primer marco administrado y, a continuación, calcule el contexto de inicialización basándose en el contexto de registro para ese marco.</span><span class="sxs-lookup"><span data-stu-id="3f5f7-142">Now, walk the stack until you reach the first managed frame, and then calculate the seed context based on the register context for that frame.</span></span>  
  
 <span data-ttu-id="3f5f7-143">Llame a `DoStackSnapshot` con el contexto de inicialización para iniciar el recorrido de pila asincrónico.</span><span class="sxs-lookup"><span data-stu-id="3f5f7-143">Call `DoStackSnapshot` with your seed context to begin the asynchronous stack walk.</span></span> <span data-ttu-id="3f5f7-144">Si no proporciona una inicialización, `DoStackSnapshot` puede omitir los marcos administrados en la parte superior de la pila y, por consiguiente, le proporcionará un recorrido de pila incompleto.</span><span class="sxs-lookup"><span data-stu-id="3f5f7-144">If you do not supply a seed, `DoStackSnapshot` might skip managed frames at the top of the stack and, consequently, will give you an incomplete stack walk.</span></span> <span data-ttu-id="3f5f7-145">Si proporciona una inicialización, debe apuntar a código generado por JIT o por el generador de imágenes nativas (Ngen.exe); de lo contrario, `DoStackSnapshot` devuelve el código de error CORPROF_E_STACKSNAPSHOT_UNMANAGED_CTX.</span><span class="sxs-lookup"><span data-stu-id="3f5f7-145">If you do supply a seed, it must point to JIT-compiled or Native Image Generator (Ngen.exe)-generated code; otherwise, `DoStackSnapshot` returns the failure code, CORPROF_E_STACKSNAPSHOT_UNMANAGED_CTX.</span></span>  
  
 <span data-ttu-id="3f5f7-146">Los recorridos de pila asincrónicos pueden causar fácilmente interbloqueos o infracciones de acceso, a menos que siga estas directrices:</span><span class="sxs-lookup"><span data-stu-id="3f5f7-146">Asynchronous stack walks can easily cause deadlocks or access violations, unless you follow these guidelines:</span></span>  
  
- <span data-ttu-id="3f5f7-147">Cuando suspenda directamente los subprocesos, recuerde que solo un subproceso que nunca ha ejecutado código administrado puede suspender otro subproceso.</span><span class="sxs-lookup"><span data-stu-id="3f5f7-147">When you directly suspend threads, remember that only a thread that has never run managed code can suspend another thread.</span></span>  
  
- <span data-ttu-id="3f5f7-148">Bloquee siempre en la devolución de llamada [ICorProfilerCallback:: ThreadDestroyed (](icorprofilercallback-threaddestroyed-method.md) hasta que se complete el recorrido de la pila del subproceso.</span><span class="sxs-lookup"><span data-stu-id="3f5f7-148">Always block in your [ICorProfilerCallback::ThreadDestroyed](icorprofilercallback-threaddestroyed-method.md) callback until that thread's stack walk is complete.</span></span>  
  
- <span data-ttu-id="3f5f7-149">No mantenga un bloqueo mientras el generador de perfiles llama a una función CLR que puede desencadenar una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="3f5f7-149">Do not hold a lock while your profiler calls into a CLR function that can trigger a garbage collection.</span></span> <span data-ttu-id="3f5f7-150">Es decir, no debe mantener un bloqueo si el subproceso propietario puede realizar una llamada que desencadene una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="3f5f7-150">That is, do not hold a lock if the owning thread might make a call that triggers a garbage collection.</span></span>  
  
 <span data-ttu-id="3f5f7-151">También hay un riesgo de interbloqueo si se llama a `DoStackSnapshot` desde un subproceso creado por el generador de perfiles para que pueda recorrer la pila de un subproceso de destino independiente.</span><span class="sxs-lookup"><span data-stu-id="3f5f7-151">There is also a risk of deadlock if you call `DoStackSnapshot` from a thread that your profiler has created so that you can walk the stack of a separate target thread.</span></span> <span data-ttu-id="3f5f7-152">La primera vez que el subproceso creado entra `ICorProfilerInfo*` en determinados métodos (incluido `DoStackSnapshot` ), CLR realizará la inicialización específica de CLR por subproceso en ese subproceso.</span><span class="sxs-lookup"><span data-stu-id="3f5f7-152">The first time the thread you created enters certain `ICorProfilerInfo*` methods (including `DoStackSnapshot`), the CLR will perform per-thread, CLR-specific initialization on that thread.</span></span> <span data-ttu-id="3f5f7-153">Si el generador de perfiles ha suspendido el subproceso de destino cuya pila está intentando recorrer y el subproceso de destino ha tenido que poseer un bloqueo necesario para realizar esta inicialización por subproceso, se producirá un interbloqueo.</span><span class="sxs-lookup"><span data-stu-id="3f5f7-153">If your profiler has suspended the target thread whose stack you are trying to walk, and if that target thread happened to own a lock necessary for performing this per-thread initialization, a deadlock will occur.</span></span> <span data-ttu-id="3f5f7-154">Para evitar este interbloqueo, realice una llamada inicial a `DoStackSnapshot` desde el subproceso creado por el generador de perfiles para recorrer un subproceso de destino independiente, pero no suspenda el subproceso de destino en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="3f5f7-154">To avoid this deadlock, make an initial call into `DoStackSnapshot` from your profiler-created thread to walk a separate target thread, but do not suspend the target thread first.</span></span> <span data-ttu-id="3f5f7-155">Esta llamada inicial garantiza que la inicialización por subproceso se puede completar sin interbloqueo.</span><span class="sxs-lookup"><span data-stu-id="3f5f7-155">This initial call ensures that the per-thread initialization can complete without deadlock.</span></span> <span data-ttu-id="3f5f7-156">Si se `DoStackSnapshot` realiza correctamente y notifica al menos un fotograma, después de ese punto, será seguro que el subproceso creado por el generador de perfiles suspenda cualquier subproceso de destino y llame `DoStackSnapshot` a para recorrer la pila de ese subproceso de destino.</span><span class="sxs-lookup"><span data-stu-id="3f5f7-156">If `DoStackSnapshot` succeeds and reports at least one frame, after that point, it will be safe for that profiler-created thread to suspend any target thread and call `DoStackSnapshot` to walk the stack of that target thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f5f7-157">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3f5f7-157">Requirements</span></span>  

 <span data-ttu-id="3f5f7-158">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f5f7-158">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f5f7-159">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3f5f7-159">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3f5f7-160">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f5f7-160">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f5f7-161">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f5f7-161">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f5f7-162">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3f5f7-162">See also</span></span>

- [<span data-ttu-id="3f5f7-163">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3f5f7-163">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="3f5f7-164">ICorProfilerInfo2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3f5f7-164">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
