---
title: COR_PRF_MONITOR (Enumeración)
ms.date: 03/30/2017
api_name:
- COR_PRF_MONITOR
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_MONITOR
helpviewer_keywords:
- COR_PRF_MONITOR enumeration [.NET Framework profiling]
ms.assetid: 9294d702-b4e5-441c-a930-e63d27b86bfd
topic_type:
- apiref
ms.openlocfilehash: e5e850e2464c310697c1cd1797d2207958591907
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696874"
---
# <a name="cor_prf_monitor-enumeration"></a><span data-ttu-id="eacfa-102">COR_PRF_MONITOR (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="eacfa-102">COR_PRF_MONITOR Enumeration</span></span>

<span data-ttu-id="eacfa-103">Contiene valores que se usan para especificar el comportamiento, las funcionalidades o los eventos a los que el generador de perfiles quiere suscribirse.</span><span class="sxs-lookup"><span data-stu-id="eacfa-103">Contains values that are used to specify behavior, capabilities, or events to which the profiler wishes to subscribe.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eacfa-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eacfa-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_MONITOR_NONE                = 0x00000000,  
    COR_PRF_MONITOR_FUNCTION_UNLOADS    = 0x00000001,  
    COR_PRF_MONITOR_CLASS_LOADS         = 0x00000002,  
    COR_PRF_MONITOR_MODULE_LOADS        = 0x00000004,  
    COR_PRF_MONITOR_ASSEMBLY_LOADS      = 0x00000008,  
    COR_PRF_MONITOR_APPDOMAIN_LOADS     = 0x00000010,  
    COR_PRF_MONITOR_JIT_COMPILATION     = 0x00000020,  
    COR_PRF_MONITOR_EXCEPTIONS          = 0x00000040,  
    COR_PRF_MONITOR_GC                  = 0x00000080,  
    COR_PRF_MONITOR_OBJECT_ALLOCATED    = 0x00000100,  
    COR_PRF_MONITOR_THREADS             = 0x00000200,  
    COR_PRF_MONITOR_REMOTING            = 0x00000400,  
    COR_PRF_MONITOR_CODE_TRANSITIONS    = 0x00000800,  
    COR_PRF_MONITOR_ENTERLEAVE          = 0x00001000,  
    COR_PRF_MONITOR_CCW                 = 0x00002000,  
    COR_PRF_MONITOR_REMOTING_COOKIE     = 0x00004000 |
                                          COR_PRF_MONITOR_REMOTING,  
    COR_PRF_MONITOR_REMOTING_ASYNC      = 0x00008000 |
                                          COR_PRF_MONITOR_REMOTING,  
    COR_PRF_MONITOR_SUSPENDS            = 0x00010000,  
    COR_PRF_MONITOR_CACHE_SEARCHES      = 0x00020000,  
    COR_PRF_ENABLE_REJIT                = 0x00040000,  
    COR_PRF_ENABLE_INPROC_DEBUGGING     = 0x00080000,  
    COR_PRF_ENABLE_JIT_MAPS             = 0x00100000,  
    COR_PRF_DISABLE_INLINING            = 0x00200000,  
    COR_PRF_DISABLE_OPTIMIZATIONS       = 0x00400000,  
    COR_PRF_ENABLE_OBJECT_ALLOCATED     = 0x00800000,  
    COR_PRF_MONITOR_CLR_EXCEPTIONS      = 0x01000000,  
    COR_PRF_MONITOR_ALL                 = 0x0107FFFF,  
    COR_PRF_ENABLE_FUNCTION_ARGS        = 0X02000000,  
    COR_PRF_ENABLE_FUNCTION_RETVAL      = 0X04000000,  
    COR_PRF_ENABLE_FRAME_INFO           = 0X08000000,  
    COR_PRF_ENABLE_STACK_SNAPSHOT       = 0X10000000,  
    COR_PRF_USE_PROFILE_IMAGES          = 0x20000000,  
    COR_PRF_DISABLE_TRANSPARENCY_CHECKS_UNDER_FULL_TRUST  
                                        = 0x40000000,  
    COR_PRF_DISABLE_ALL_NGEN_IMAGES     = 0x80000000,  
    COR_PRF_ALL                         = 0x8FFFFFFF,  
    COR_PRF_REQUIRE_PROFILE_IMAGE       = COR_PRF_USE_PROFILE_IMAGES |
                                          COR_PRF_MONITOR_CODE_TRANSITIONS |
                                          COR_PRF_MONITOR_ENTERLEAVE,  
    COR_PRF_ALLOWABLE_AFTER_ATTACH      = COR_PRF_MONITOR_THREADS |  
                                          COR_PRF_MONITOR_MODULE_LOADS |  
                                          COR_PRF_MONITOR_ASSEMBLY_LOADS |  
                                          COR_PRF_MONITOR_APPDOMAIN_LOADS |  
                                          COR_PRF_ENABLE_STACK_SNAPSHOT |  
                                          COR_PRF_MONITOR_GC |  
                                          COR_PRF_MONITOR_SUSPENDS |  
                                          COR_PRF_MONITOR_CLASS_LOADS |  
                                          COR_PRF_MONITOR_JIT_COMPILATION,  
    COR_PRF_MONITOR_IMMUTABLE           = COR_PRF_MONITOR_CODE_TRANSITIONS |  
                                          COR_PRF_MONITOR_REMOTING |  
                                          COR_PRF_MONITOR_REMOTING_COOKIE |  
                                          COR_PRF_MONITOR_REMOTING_ASYNC |  
                                          COR_PRF_ENABLE_REJIT |  
                                          COR_PRF_ENABLE_INPROC_DEBUGGING |  
                                          COR_PRF_ENABLE_JIT_MAPS |  
                                          COR_PRF_DISABLE_OPTIMIZATIONS |  
                                          COR_PRF_DISABLE_INLINING |  
                                          COR_PRF_ENABLE_OBJECT_ALLOCATED |  
                                          COR_PRF_ENABLE_FUNCTION_ARGS |  
                                          COR_PRF_ENABLE_FUNCTION_RETVAL |  
                                          COR_PRF_ENABLE_FRAME_INFO |  
                                          COR_PRF_USE_PROFILE_IMAGES |  
                     COR_PRF_DISABLE_TRANSPARENCY_CHECKS_UNDER_FULL_TRUST |  
                                          COR_PRF_DISABLE_ALL_NGEN_IMAGES  
} COR_PRF_MONITOR;  
```  
  
## <a name="members"></a><span data-ttu-id="eacfa-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="eacfa-105">Members</span></span>  

 <span data-ttu-id="eacfa-106">En las secciones siguientes se enumeran `COR_PRF_MONITOR` los miembros de enumeración por categoría.</span><span class="sxs-lookup"><span data-stu-id="eacfa-106">The following sections list `COR_PRF_MONITOR` enumeration members by category.</span></span> <span data-ttu-id="eacfa-107">Las categorías son:</span><span class="sxs-lookup"><span data-stu-id="eacfa-107">The categories are:</span></span>  
  
- [<span data-ttu-id="eacfa-108">No se ha establecido ninguna marca</span><span class="sxs-lookup"><span data-stu-id="eacfa-108">No flags set</span></span>](#None)  
  
- [<span data-ttu-id="eacfa-109">Marcas de devolución de llamada</span><span class="sxs-lookup"><span data-stu-id="eacfa-109">Callback flags</span></span>](#Callback)  
  
- [<span data-ttu-id="eacfa-110">Marcas para habilitar características</span><span class="sxs-lookup"><span data-stu-id="eacfa-110">Feature-enabling flags</span></span>](#Feature)  
  
- [<span data-ttu-id="eacfa-111">Marcas de configuración</span><span class="sxs-lookup"><span data-stu-id="eacfa-111">Configuration flags</span></span>](#Config)  
  
- [<span data-ttu-id="eacfa-112">Marcas compuestas</span><span class="sxs-lookup"><span data-stu-id="eacfa-112">Composite flags</span></span>](#Composite)  
  
<a name="None"></a>

### <a name="no-flags-set"></a><span data-ttu-id="eacfa-113">No se ha establecido ninguna marca</span><span class="sxs-lookup"><span data-stu-id="eacfa-113">No flags set</span></span>  
  
|<span data-ttu-id="eacfa-114">Miembro</span><span class="sxs-lookup"><span data-stu-id="eacfa-114">Member</span></span>|<span data-ttu-id="eacfa-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="eacfa-115">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_MONITOR_NONE`|<span data-ttu-id="eacfa-116">No se establecen marcas.</span><span class="sxs-lookup"><span data-stu-id="eacfa-116">No flags are set.</span></span>|  
  
<a name="Callback"></a>

### <a name="callback-flags"></a><span data-ttu-id="eacfa-117">Marcas de devolución de llamada</span><span class="sxs-lookup"><span data-stu-id="eacfa-117">Callback flags</span></span>  
  
|<span data-ttu-id="eacfa-118">Miembro</span><span class="sxs-lookup"><span data-stu-id="eacfa-118">Member</span></span>|<span data-ttu-id="eacfa-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="eacfa-119">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_MONITOR_ALL`|<span data-ttu-id="eacfa-120">Habilita todos los eventos de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="eacfa-120">Enables all callback events.</span></span>|  
|`COR_PRF_MONITOR_APPDOMAIN_LOADS`|<span data-ttu-id="eacfa-121">Controla las `AppDomainCreation*` `AppDomainShutdown*` devoluciones de llamada y en la interfaz [ICorProfilerCallback](icorprofilercallback-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="eacfa-121">Controls the `AppDomainCreation*` and `AppDomainShutdown*` callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_ASSEMBLY_LOADS`|<span data-ttu-id="eacfa-122">Controla las `AssemblyLoad*` `AssemblyUnload*` devoluciones de llamada y en la interfaz [ICorProfilerCallback](icorprofilercallback-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="eacfa-122">Controls the `AssemblyLoad*` and `AssemblyUnload*` callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_CACHE_SEARCHES`|<span data-ttu-id="eacfa-123">Controla las `JITCachedFunctionSearch*` devoluciones de llamada en la interfaz [ICorProfilerCallback](icorprofilercallback-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="eacfa-123">Controls the `JITCachedFunctionSearch*` callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span><br /><br /> <span data-ttu-id="eacfa-124">El comportamiento de esta marca se cambió en .NET Framework versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="eacfa-124">The behavior of this flag is changed in the .NET Framework version 2.0.</span></span>|  
|`COR_PRF_MONITOR_CCW`|<span data-ttu-id="eacfa-125">Controla las `COMClassicVTable*` devoluciones de llamada en la interfaz [ICorProfilerCallback](icorprofilercallback-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="eacfa-125">Controls the `COMClassicVTable*` callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_CLASS_LOADS`|<span data-ttu-id="eacfa-126">Controla las `ClassLoad*` `ClassUnload*` devoluciones de llamada y en la interfaz [ICorProfilerCallback](icorprofilercallback-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="eacfa-126">Controls the `ClassLoad*` and `ClassUnload*` callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_CLR_EXCEPTIONS`|<span data-ttu-id="eacfa-127">Controla las `ExceptionCLRCatcher*` devoluciones de llamada en la interfaz [ICorProfilerCallback](icorprofilercallback-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="eacfa-127">Controls the `ExceptionCLRCatcher*` callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_CODE_TRANSITIONS`|<span data-ttu-id="eacfa-128">Controla las devoluciones de llamada [UnmanagedToManagedTransition (](icorprofilercallback-unmanagedtomanagedtransition-method.md) y [ManagedToUnmanagedTransition (](icorprofilercallback-managedtounmanagedtransition-method.md) en la interfaz [ICorProfilerCallback](icorprofilercallback-interface.md)</span><span class="sxs-lookup"><span data-stu-id="eacfa-128">Controls the [UnmanagedToManagedTransition](icorprofilercallback-unmanagedtomanagedtransition-method.md) and [ManagedToUnmanagedTransition](icorprofilercallback-managedtounmanagedtransition-method.md) callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface</span></span>|  
|`COR_PRF_MONITOR_ENTERLEAVE`|<span data-ttu-id="eacfa-129">Controla las `FunctionEnter*` `FunctionLeave*` `FunctionTailCall*` [funciones estáticas globales de generación de perfiles](profiling-global-static-functions.md), y.</span><span class="sxs-lookup"><span data-stu-id="eacfa-129">Controls the `FunctionEnter*`,  `FunctionLeave*`, and `FunctionTailCall*`[profiling global static functions](profiling-global-static-functions.md).</span></span>|  
|`COR_PRF_MONITOR_EXCEPTIONS`|<span data-ttu-id="eacfa-130">Controla la devolución de llamada de [exceptionthrown (](icorprofilercallback-exceptionthrown-method.md) y las `ExceptionSearch*` `ExceptionOSHandler*` `ExceptionUnwind*` `ExceptionCatcher*` devoluciones de llamada,, y en la interfaz [ICorProfilerCallback](icorprofilercallback-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="eacfa-130">Controls the [ExceptionThrown](icorprofilercallback-exceptionthrown-method.md) callback and the `ExceptionSearch*`, `ExceptionOSHandler*`, `ExceptionUnwind*`, and `ExceptionCatcher*` callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_FUNCTION_UNLOADS`|<span data-ttu-id="eacfa-131">Controla la devolución de llamada [functionunloadstarted (](icorprofilercallback-functionunloadstarted-method.md) en la interfaz [ICorProfilerCallback](icorprofilercallback-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="eacfa-131">Controls the [FunctionUnloadStarted](icorprofilercallback-functionunloadstarted-method.md) callback in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_GC`|<span data-ttu-id="eacfa-132">Controla las devoluciones de llamada [garbagecollectionstarted (](icorprofilercallback2-garbagecollectionstarted-method.md),   [garbagecollectionfinished (](icorprofilercallback2-garbagecollectionfinished-method.md),  [MovedReferences](icorprofilercallback-movedreferences-method.md), [movedreferences2 (](icorprofilercallback4-movedreferences2-method.md),    [SurvivingReferences (](icorprofilercallback2-survivingreferences-method.md),  [survivingreferences2 (](icorprofilercallback4-survivingreferences2-method.md), [ObjectReferences](icorprofilercallback-objectreferences-method.md),   [ObjectsAllocatedByClass (](icorprofilercallback-objectsallocatedbyclass-method.md),  [RootReferences](icorprofilercallback-rootreferences-method.md), [RootReferences2 (](icorprofilercallback2-rootreferences2-method.md), [HandleCreated](icorprofilercallback2-handlecreated-method.md),  [handledestroyed (](icorprofilercallback2-handledestroyed-method.md)y [finalizeableobjectqueued (](icorprofilercallback2-finalizeableobjectqueued-method.md) en las `ICorProfilerCallback*` interfaces.</span><span class="sxs-lookup"><span data-stu-id="eacfa-132">Controls the [GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md),   [GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md),  [MovedReferences](icorprofilercallback-movedreferences-method.md), [MovedReferences2](icorprofilercallback4-movedreferences2-method.md),    [SurvivingReferences](icorprofilercallback2-survivingreferences-method.md),  [SurvivingReferences2](icorprofilercallback4-survivingreferences2-method.md), [ObjectReferences](icorprofilercallback-objectreferences-method.md),   [ObjectsAllocatedByClass](icorprofilercallback-objectsallocatedbyclass-method.md),  [RootReferences](icorprofilercallback-rootreferences-method.md), [RootReferences2](icorprofilercallback2-rootreferences2-method.md), [HandleCreated](icorprofilercallback2-handlecreated-method.md),  [HandleDestroyed](icorprofilercallback2-handledestroyed-method.md), and [FinalizeableObjectQueued](icorprofilercallback2-finalizeableobjectqueued-method.md) callbacks in the `ICorProfilerCallback*` interfaces.</span></span> <span data-ttu-id="eacfa-133">Cuando `COR_PRF_MONITOR_GC` se asigna, se desactiva la recolección de elementos no utilizados simultánea.</span><span class="sxs-lookup"><span data-stu-id="eacfa-133">When `COR_PRF_MONITOR_GC` is allocated, concurrent garbage collection is turned off.</span></span>|  
|`COR_PRF_MONITOR_JIT_COMPILATION`|<span data-ttu-id="eacfa-134">Controla las `JITCompilation*` devoluciones de llamada, [Jitfunctionpitched (](icorprofilercallback-jitfunctionpitched-method.md)y [Jitinlining (](icorprofilercallback-jitinlining-method.md) en la interfaz [ICorProfilerCallback](icorprofilercallback-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="eacfa-134">Controls the `JITCompilation*`, [JITFunctionPitched](icorprofilercallback-jitfunctionpitched-method.md), and [JITInlining](icorprofilercallback-jitinlining-method.md) callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_MODULE_LOADS`|<span data-ttu-id="eacfa-135">Controla las `ModuleLoad*`  `ModuleUnload*` devoluciones de llamada, y [moduleattachedtoassembly (](icorprofilercallback-moduleattachedtoassembly-method.md) en la interfaz [ICorProfilerCallback](icorprofilercallback-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="eacfa-135">Controls the `ModuleLoad*`,  `ModuleUnload*`, and [ModuleAttachedToAssembly](icorprofilercallback-moduleattachedtoassembly-method.md) callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_OBJECT_ALLOCATED`|<span data-ttu-id="eacfa-136">Controla la devolución de llamada [ObjectAllocated](icorprofilercallback-objectallocated-method.md) en la interfaz [ICorProfilerCallback](icorprofilercallback-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="eacfa-136">Controls the [ObjectAllocated](icorprofilercallback-objectallocated-method.md) callback in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_REMOTING`|<span data-ttu-id="eacfa-137">Controla las `Remoting*` devoluciones de llamada en la interfaz [ICorProfilerCallback](icorprofilercallback-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="eacfa-137">Controls the `Remoting*` callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_REMOTING_ASYNC`|<span data-ttu-id="eacfa-138">Controla si las devoluciones de llamada `Remoting*` supervisarán eventos asincrónicos.</span><span class="sxs-lookup"><span data-stu-id="eacfa-138">Controls whether the `Remoting*` callbacks will monitor asynchronous events.</span></span>|  
|`COR_PRF_MONITOR_REMOTING_COOKIE`|<span data-ttu-id="eacfa-139">Controla si se pasa una cookie a las devoluciones de llamada `Remoting*`.</span><span class="sxs-lookup"><span data-stu-id="eacfa-139">Controls whether a cookie is passed to the `Remoting*` callbacks.</span></span>|  
|`COR_PRF_MONITOR_SUSPENDS`|<span data-ttu-id="eacfa-140">Controla las `RuntimeSuspend*` `RuntimeResume*` devoluciones de llamada,, [RuntimeThreadSuspended (](icorprofilercallback-runtimethreadsuspended-method.md)y [RuntimeThreadResumed (](icorprofilercallback-runtimethreadresumed-method.md) en la interfaz [ICorProfilerCallback](icorprofilercallback-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="eacfa-140">Controls the `RuntimeSuspend*`, `RuntimeResume*`, [RuntimeThreadSuspended](icorprofilercallback-runtimethreadsuspended-method.md), and [RuntimeThreadResumed](icorprofilercallback-runtimethreadresumed-method.md) callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_THREADS`|<span data-ttu-id="eacfa-141">Controla las devoluciones de llamada [ThreadCreated (](icorprofilercallback-threadcreated-method.md),  [ThreadDestroyed (](icorprofilercallback-threaddestroyed-method.md),  [threadassignedtoosthread (](icorprofilercallback-threadassignedtoosthread-method.md)y [threadnamechanged (](icorprofilercallback2-threadnamechanged-method.md) en las interfaces [ICorProfilerCallback](icorprofilercallback-interface.md) e [ICorProfilerCallback2](icorprofilercallback2-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="eacfa-141">Controls the [ThreadCreated](icorprofilercallback-threadcreated-method.md),  [ThreadDestroyed](icorprofilercallback-threaddestroyed-method.md),  [ThreadAssignedToOSThread](icorprofilercallback-threadassignedtoosthread-method.md), and [ThreadNameChanged](icorprofilercallback2-threadnamechanged-method.md) callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) and [ICorProfilerCallback2](icorprofilercallback2-interface.md) interfaces.</span></span>|  
  
<a name="Feature"></a>

### <a name="feature-enabling-flags"></a><span data-ttu-id="eacfa-142">Marcas para habilitar características</span><span class="sxs-lookup"><span data-stu-id="eacfa-142">Feature-enabling flags</span></span>  
  
|<span data-ttu-id="eacfa-143">Miembro</span><span class="sxs-lookup"><span data-stu-id="eacfa-143">Member</span></span>|<span data-ttu-id="eacfa-144">Descripción</span><span class="sxs-lookup"><span data-stu-id="eacfa-144">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_ENABLE_FRAME_INFO`|<span data-ttu-id="eacfa-145">Habilita la recuperación de un exacto `ClassID` para una función genérica llamando al método [getfunctioninfo2 (](icorprofilerinfo2-getfunctioninfo2-method.md) con un `COR_PRF_FRAME_INFO` valor devuelto por la devolución de llamada [FunctionEnter2](functionenter2-function.md) .</span><span class="sxs-lookup"><span data-stu-id="eacfa-145">Enables the retrieval of an exact `ClassID` for a generic function by calling the [GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) method with a `COR_PRF_FRAME_INFO` value returned by the [FunctionEnter2](functionenter2-function.md) callback.</span></span>|  
|`COR_PRF_ENABLE_FUNCTION_ARGS`|<span data-ttu-id="eacfa-146">Habilita el seguimiento de argumentos mediante la devolución de llamada [FunctionEnter2](functionenter2-function.md) o la devolución de llamada [FunctionEnter3WithInfo](functionenter3withinfo-function.md) y el método [GetFunctionEnter3Info (](icorprofilerinfo3-getfunctionenter3info-method.md) .</span><span class="sxs-lookup"><span data-stu-id="eacfa-146">Enables argument tracing using the [FunctionEnter2](functionenter2-function.md) callback or the [FunctionEnter3WithInfo](functionenter3withinfo-function.md) callback and the [GetFunctionEnter3Info](icorprofilerinfo3-getfunctionenter3info-method.md) method.</span></span>|  
|`COR_PRF_ENABLE_FUNCTION_RETVAL`|<span data-ttu-id="eacfa-147">Habilita el seguimiento de valores devueltos mediante la devolución de llamada [FunctionLeave2](functionleave2-function.md) o la devolución de llamada [FunctionLeave3WithInfo](functionleave3withinfo-function.md) y el método [GetFunctionLeave3Info (](icorprofilerinfo3-getfunctionleave3info-method.md) .</span><span class="sxs-lookup"><span data-stu-id="eacfa-147">Enables tracing of return values by using the [FunctionLeave2](functionleave2-function.md) callback or the [FunctionLeave3WithInfo](functionleave3withinfo-function.md) callback and [GetFunctionLeave3Info](icorprofilerinfo3-getfunctionleave3info-method.md) method.</span></span>|  
|`COR_PRF_ENABLE_INPROC_DEBUGGING`|<span data-ttu-id="eacfa-148">Desusado.</span><span class="sxs-lookup"><span data-stu-id="eacfa-148">Deprecated.</span></span><br /><br /> <span data-ttu-id="eacfa-149">No se admite la depuración en proceso.</span><span class="sxs-lookup"><span data-stu-id="eacfa-149">In process debugging is not supported.</span></span> <span data-ttu-id="eacfa-150">Esta marca no tiene efecto.</span><span class="sxs-lookup"><span data-stu-id="eacfa-150">This flag has no effect.</span></span>|  
|`COR_PRF_ENABLE_JIT_MAPS`|<span data-ttu-id="eacfa-151">Desusado.</span><span class="sxs-lookup"><span data-stu-id="eacfa-151">Deprecated.</span></span><br /><br /> <span data-ttu-id="eacfa-152">Permite al generador de perfiles obtener asignaciones de IL a nativo mediante [GetILToNativeMapping](icorprofilerinfo-getiltonativemapping-method.md).</span><span class="sxs-lookup"><span data-stu-id="eacfa-152">Allows the profiler to obtain IL-to-native maps by using [GetILToNativeMapping](icorprofilerinfo-getiltonativemapping-method.md).</span></span> <span data-ttu-id="eacfa-153">A partir de .NET Framework 2.0, el tiempo de ejecución siempre realiza el seguimiento de las asignaciones de IL a nativo; por lo tanto, se considera que esta marca está siempre establecida.</span><span class="sxs-lookup"><span data-stu-id="eacfa-153">Starting with the .NET Framework 2.0, the runtime always tracks IL-to-native maps; therefore, this flag is always considered to be set.</span></span>|  
|`COR_PRF_ENABLE_OBJECT_ALLOCATED`|<span data-ttu-id="eacfa-154">Informa al tiempo de ejecución que puede que el generador de perfiles quiera notificaciones de asignación de objetos.</span><span class="sxs-lookup"><span data-stu-id="eacfa-154">Informs the runtime that the profiler may want object allocation notifications.</span></span> <span data-ttu-id="eacfa-155">Esta marca se debe establecer durante la inicialización.</span><span class="sxs-lookup"><span data-stu-id="eacfa-155">This flag must be set during initialization.</span></span> <span data-ttu-id="eacfa-156">Permite al generador de perfiles utilizar posteriormente la `COR_PRF_MONITOR_OBJECT_ALLOCATED` marca para recibir devoluciones de llamada de [ObjectAllocated](icorprofilercallback-objectallocated-method.md) .</span><span class="sxs-lookup"><span data-stu-id="eacfa-156">It allows the profiler to subsequently use the `COR_PRF_MONITOR_OBJECT_ALLOCATED` flag to receive [ObjectAllocated](icorprofilercallback-objectallocated-method.md) callbacks.</span></span>|  
|`COR_PRF_ENABLE_REJIT`|<span data-ttu-id="eacfa-157">Habilita las llamadas a los métodos [requestrejit (](icorprofilerinfo4-requestrejit-method.md) y [requestrevert (](icorprofilerinfo4-requestrevert-method.md) .</span><span class="sxs-lookup"><span data-stu-id="eacfa-157">Enables calls to the [RequestReJIT](icorprofilerinfo4-requestrejit-method.md) and [RequestRevert](icorprofilerinfo4-requestrevert-method.md) methods.</span></span> <span data-ttu-id="eacfa-158">El generador de perfiles debe establecer esta marca en el inicio.</span><span class="sxs-lookup"><span data-stu-id="eacfa-158">The profiler must set this flag on startup.</span></span>  <span data-ttu-id="eacfa-159">Si el generador de perfiles especifica esta marca, también debe especificar `COR_PRF_DISABLE_ALL_NGEN_IMAGES`.</span><span class="sxs-lookup"><span data-stu-id="eacfa-159">If the profiler specifies this flag, it must also specify `COR_PRF_DISABLE_ALL_NGEN_IMAGES`.</span></span>|  
|`COR_PRF_ENABLE_STACK_SNAPSHOT`|<span data-ttu-id="eacfa-160">Habilita las llamadas al método [DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) .</span><span class="sxs-lookup"><span data-stu-id="eacfa-160">Enables calls to the [DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>|  
  
<a name="Config"></a>

### <a name="configuration-flags"></a><span data-ttu-id="eacfa-161">Marcas de configuración</span><span class="sxs-lookup"><span data-stu-id="eacfa-161">Configuration flags</span></span>  
  
|<span data-ttu-id="eacfa-162">Miembro</span><span class="sxs-lookup"><span data-stu-id="eacfa-162">Member</span></span>|<span data-ttu-id="eacfa-163">Descripción</span><span class="sxs-lookup"><span data-stu-id="eacfa-163">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_DISABLE_ALL_NGEN_IMAGES`|<span data-ttu-id="eacfa-164">Impide que se carguen todas las imágenes nativas (incluidas imágenes mejoradas por el generador de perfiles).</span><span class="sxs-lookup"><span data-stu-id="eacfa-164">Prevents all native images (including profiler-enhanced images) from loading.</span></span>  <span data-ttu-id="eacfa-165">Si se especifican esta marca y la marca `COR_PRF_USE_PROFILE_IMAGES`, se usa `COR_PRF_DISABLE_ALL_NGEN_IMAGES`.</span><span class="sxs-lookup"><span data-stu-id="eacfa-165">If this flag and the `COR_PRF_USE_PROFILE_IMAGES` flag are both specified, `COR_PRF_DISABLE_ALL_NGEN_IMAGES` is used.</span></span>|  
|`COR_PRF_DISABLE_INLINING`|<span data-ttu-id="eacfa-166">Deshabilita todas las inserciones.</span><span class="sxs-lookup"><span data-stu-id="eacfa-166">Disables all inlining.</span></span>|  
|`COR_PRF_DISABLE_OPTIMIZATIONS`|<span data-ttu-id="eacfa-167">Deshabilita todas las optimizaciones de código.</span><span class="sxs-lookup"><span data-stu-id="eacfa-167">Disables all code optimizations.</span></span>|  
|`COR_PRF_DISABLE_TRANSPARENCY_CHECKS_UNDER_FULL_TRUST`|<span data-ttu-id="eacfa-168">Deshabilita las comprobaciones de transparencia de seguridad que normalmente se realizan durante la compilación Just-In-Time (JIT) y la carga de las clases para ensamblados de confianza total.</span><span class="sxs-lookup"><span data-stu-id="eacfa-168">Disables security transparency checks that are normally done during just-in-time (JIT) compilation and class loading for full-trust assemblies.</span></span> <span data-ttu-id="eacfa-169">Esto puede hacer que la instrumentación sea más fácil de realizar.</span><span class="sxs-lookup"><span data-stu-id="eacfa-169">This can make some instrumentation easier to perform.</span></span>|  
|`COR_PRF_USE_PROFILE_IMAGES`|<span data-ttu-id="eacfa-170">Hace que la búsqueda de imágenes nativas busque imágenes mejoradas por el generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="eacfa-170">Causes the native image search to look for profiler-enhanced images.</span></span> <span data-ttu-id="eacfa-171">Si no se encuentra ninguna imagen mejorada por el generador de perfiles para un ensamblado determinado, Common Language Runtime vuelve a JIT para ese ensamblado.</span><span class="sxs-lookup"><span data-stu-id="eacfa-171">If no profiler-enhanced image is found for a given assembly, the common language runtime falls back to JIT for that assembly.</span></span> <span data-ttu-id="eacfa-172">Si se especifican esta marca y la marca `COR_PRF_DISABLE_ALL_NGEN_IMAGES`, se usa `COR_PRF_DISABLE_ALL_NGEN_IMAGES`.</span><span class="sxs-lookup"><span data-stu-id="eacfa-172">If this flag and the `COR_PRF_DISABLE_ALL_NGEN_IMAGES` flag are both specified, `COR_PRF_DISABLE_ALL_NGEN_IMAGES` is used.</span></span>|  
  
<a name="Composite"></a>

### <a name="composite-flags"></a><span data-ttu-id="eacfa-173">Marcas compuestas</span><span class="sxs-lookup"><span data-stu-id="eacfa-173">Composite flags</span></span>  
  
|<span data-ttu-id="eacfa-174">Miembro</span><span class="sxs-lookup"><span data-stu-id="eacfa-174">Member</span></span>|<span data-ttu-id="eacfa-175">Descripción</span><span class="sxs-lookup"><span data-stu-id="eacfa-175">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_ALL`|<span data-ttu-id="eacfa-176">Representa todos los valores de la marca `COR_PRF_MONITOR`.</span><span class="sxs-lookup"><span data-stu-id="eacfa-176">Represents all `COR_PRF_MONITOR` flag values.</span></span>|  
|`COR_PRF_ALLOWABLE_AFTER_ATTACH`|<span data-ttu-id="eacfa-177">Representa todas las marcas `COR_PRF_MONITOR` que se pueden establecer después de que el generador de perfiles se asocie a una aplicación en ejecución.</span><span class="sxs-lookup"><span data-stu-id="eacfa-177">Represents all `COR_PRF_MONITOR` flags that can be set after the profiler is attached to a running app.</span></span> <span data-ttu-id="eacfa-178">En la sección sobre la sintaxis se indica cada una de las marcas presentes en esta máscara de bits.</span><span class="sxs-lookup"><span data-stu-id="eacfa-178">The syntax section indicates the individual flags that are present in this bitmask.</span></span>|  
|`COR_PRF_MONITOR_ALL`|<span data-ttu-id="eacfa-179">Habilita todos los eventos de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="eacfa-179">Enables all callback events.</span></span>|  
|`COR_PRF_MONITOR_IMMUTABLE`|<span data-ttu-id="eacfa-180">Representa todas las marcas `COR_PRF_MONITOR` que se pueden establecer solo durante la inicialización.</span><span class="sxs-lookup"><span data-stu-id="eacfa-180">Represents all `COR_PRF_MONITOR` flags that can be set only during initialization.</span></span> <span data-ttu-id="eacfa-181">Al intentar cambiar cualquiera de estas marcas después de la inicialización se genera un valor `HRESULT` que indica error.</span><span class="sxs-lookup"><span data-stu-id="eacfa-181">Trying to change any of these flags after initialization returns an `HRESULT` value that indicates failure.</span></span>|  
|`COR_PRF_REQUIRE_PROFILE_IMAGE`|<span data-ttu-id="eacfa-182">Representa todas las marcas `COR_PRF_MONITOR` que requieren imágenes mejoradas para el perfil.</span><span class="sxs-lookup"><span data-stu-id="eacfa-182">Represents all `COR_PRF_MONITOR` flags that require profile-enhanced images.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eacfa-183">Comentarios</span><span class="sxs-lookup"><span data-stu-id="eacfa-183">Remarks</span></span>  

 <span data-ttu-id="eacfa-184">`COR_PRF_MONITOR`Se usa un valor con los métodos [ICorProfilerInfo:: GetEventMask (](icorprofilerinfo-geteventmask-method.md) y [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) para definir las notificaciones de eventos que el Common Language Runtime realiza al generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="eacfa-184">A `COR_PRF_MONITOR` value is used with the [ICorProfilerInfo::GetEventMask](icorprofilerinfo-geteventmask-method.md) and [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) methods to define the event notifications that the common language runtime makes to the profiler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eacfa-185">Requisitos</span><span class="sxs-lookup"><span data-stu-id="eacfa-185">Requirements</span></span>  

 <span data-ttu-id="eacfa-186">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eacfa-186">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eacfa-187">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="eacfa-187">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="eacfa-188">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eacfa-188">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eacfa-189">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eacfa-189">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eacfa-190">Consulte también</span><span class="sxs-lookup"><span data-stu-id="eacfa-190">See also</span></span>

- [<span data-ttu-id="eacfa-191">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="eacfa-191">Profiling Enumerations</span></span>](profiling-enumerations.md)
- [<span data-ttu-id="eacfa-192">Método GetEventMask</span><span class="sxs-lookup"><span data-stu-id="eacfa-192">GetEventMask Method</span></span>](icorprofilerinfo-geteventmask-method.md)
- [<span data-ttu-id="eacfa-193">Método SetEventMask</span><span class="sxs-lookup"><span data-stu-id="eacfa-193">SetEventMask Method</span></span>](icorprofilerinfo-seteventmask-method.md)
