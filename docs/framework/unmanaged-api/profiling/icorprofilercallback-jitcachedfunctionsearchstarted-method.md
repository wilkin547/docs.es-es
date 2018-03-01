---
title: "ICorProfilerCallback::JITCachedFunctionSearchStarted (Método)"
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
- ICorProfilerCallback.JITCachedFunctionSearchStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCachedFunctionSearchStarted
helpviewer_keywords:
- JITCachedFunctionSearchStarted method [.NET Framework profiling]
- ICorProfilerCallback::JITCachedFunctionSearchStarted method [.NET Framework profiling]
ms.assetid: 5cba642c-0d80-48ee-889d-198c5044d821
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d2208a1a1637b3bb8dd7d7963ab806aeae7921dd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackjitcachedfunctionsearchstarted-method"></a><span data-ttu-id="6c47e-102">ICorProfilerCallback::JITCachedFunctionSearchStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="6c47e-102">ICorProfilerCallback::JITCachedFunctionSearchStarted Method</span></span>
<span data-ttu-id="6c47e-103">Notifica al generador de perfiles que se ha iniciado una búsqueda para una función que se compiló anteriormente con el generador de imágenes nativas (NGen.exe).</span><span class="sxs-lookup"><span data-stu-id="6c47e-103">Notifies the profiler that a search has started for a function that was compiled previously using the Native Image Generator (NGen.exe).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c47e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6c47e-104">Syntax</span></span>  
  
```  
HRESULT JITCachedFunctionSearchStarted(  
    [in]  FunctionID functionId,  
    [out] BOOL *pbUseCachedFunction);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6c47e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6c47e-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="6c47e-106">[in] El identificador de la función para la que se realiza la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="6c47e-106">[in] The ID of the function for which the search is being performed.</span></span>  
  
 `pbUseCachedFunction`  
 <span data-ttu-id="6c47e-107">[out] `true` si el motor de ejecución debe usar la versión en caché de una función (si está disponible); en caso contrario `false`.</span><span class="sxs-lookup"><span data-stu-id="6c47e-107">[out] `true` if the execution engine should use the cached version of a function (if available); otherwise `false`.</span></span> <span data-ttu-id="6c47e-108">Si el valor es `false`, el motor de ejecución del compilador JIT compila la función en lugar de usar una versión que no está compilado JIT.</span><span class="sxs-lookup"><span data-stu-id="6c47e-108">If the value is `false`, the execution engine JIT-compiles the function instead of using a version that is not JIT-compiled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6c47e-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6c47e-109">Remarks</span></span>  
 <span data-ttu-id="6c47e-110">En .NET Framework versión 2.0, el `JITCachedFunctionSearchStarted` y [ICorProfilerCallback:: JITCachedFunctionSearchFinished (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchfinished-method.md) no se realizarán las devoluciones de llamada para todas las funciones en imágenes NGen normales.</span><span class="sxs-lookup"><span data-stu-id="6c47e-110">In the .NET Framework version 2.0, the `JITCachedFunctionSearchStarted` and [ICorProfilerCallback::JITCachedFunctionSearchFinished Method](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchfinished-method.md) callbacks will not be made for all functions in regular NGen images.</span></span> <span data-ttu-id="6c47e-111">Sólo las imágenes NGen optimizadas para un perfil generará las devoluciones de llamada para todas las funciones en la imagen.</span><span class="sxs-lookup"><span data-stu-id="6c47e-111">Only NGen images optimized for a profile will generate callbacks for all functions in the image.</span></span> <span data-ttu-id="6c47e-112">Sin embargo, debido a la sobrecarga adicional, un generador de perfiles debe solicitar imágenes NGen optimizadas de generador de perfiles solo si tiene intención de utilizar estas devoluciones de llamada para forzar una función para ser compilado just-in-time (JIT).</span><span class="sxs-lookup"><span data-stu-id="6c47e-112">However, due to the additional overhead, a profiler should request profiler-optimized NGen images only if it intends to use these callbacks to force a function to be compiled just-in-time (JIT).</span></span> <span data-ttu-id="6c47e-113">En caso contrario, el generador de perfiles debe utilizar una estrategia lenta para recopilar información de la función.</span><span class="sxs-lookup"><span data-stu-id="6c47e-113">Otherwise, the profiler should use a lazy strategy for gathering function information.</span></span>  
  
 <span data-ttu-id="6c47e-114">Los generadores de perfiles deben admitir casos en los que varios subprocesos de una aplicación de perfiles llamen al mismo método simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="6c47e-114">Profilers must support cases where multiple threads of a profiled application are calling the same method simultaneously.</span></span> <span data-ttu-id="6c47e-115">Por ejemplo, un subproceso llama a `JITCachedFunctionSearchStarted` y el generador de perfiles responde estableciendo *pbUseCachedFunction*en FALSE para forzar una compilación JIT.</span><span class="sxs-lookup"><span data-stu-id="6c47e-115">For example, thread A calls `JITCachedFunctionSearchStarted` and the profiler responds by setting *pbUseCachedFunction*to FALSE to force JIT compilation.</span></span> <span data-ttu-id="6c47e-116">Subproceso llama a un then [ICorProfilerCallback:: JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) y [ICorProfilerCallback:: JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md).</span><span class="sxs-lookup"><span data-stu-id="6c47e-116">Thread A then calls [ICorProfilerCallback::JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) and [ICorProfilerCallback::JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md).</span></span>  
  
 <span data-ttu-id="6c47e-117">Ahora subproceso B llama `JITCachedFunctionSearchStarted` para la misma función.</span><span class="sxs-lookup"><span data-stu-id="6c47e-117">Now thread B calls `JITCachedFunctionSearchStarted` for the same function.</span></span> <span data-ttu-id="6c47e-118">Aunque el generador de perfiles se ha indicado su intención de la función de compilación JIT, el generador de perfiles recibe la segunda llamada porque el subproceso B envía la devolución de llamada antes de que el generador de perfiles ha respondido a la llamada del subproceso a `JITCachedFunctionSearchStarted`.</span><span class="sxs-lookup"><span data-stu-id="6c47e-118">Even though the profiler has stated its intention to JIT-compile the function, the profiler receives the second callback because thread B sends the callback before the profiler has responded to thread A's call to `JITCachedFunctionSearchStarted`.</span></span> <span data-ttu-id="6c47e-119">El orden en la que los subprocesos realizan llamadas depende de cómo se programan los subprocesos.</span><span class="sxs-lookup"><span data-stu-id="6c47e-119">The order in which the threads make calls depends on how the threads are scheduled.</span></span>  
  
 <span data-ttu-id="6c47e-120">Cuando el generador de perfiles recibe las devoluciones de llamada duplicados, debe establecer el valor al que hace referencia `pbUseCachedFunction` en el mismo valor para todas las devoluciones de llamada duplicados.</span><span class="sxs-lookup"><span data-stu-id="6c47e-120">When the profiler receives duplicate callbacks, it must set the value referenced by `pbUseCachedFunction` to the same value for all the duplicate callbacks.</span></span> <span data-ttu-id="6c47e-121">Es decir, cuando `JITCachedFunctionSearchStarted` se llama varias veces con el mismo `functionId` valor, el generador de perfiles debe responder lo mismo cada vez.</span><span class="sxs-lookup"><span data-stu-id="6c47e-121">That is, when `JITCachedFunctionSearchStarted` is called multiple times with the same `functionId` value, the profiler must respond the same each time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c47e-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6c47e-122">Requirements</span></span>  
 <span data-ttu-id="6c47e-123">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c47e-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c47e-124">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6c47e-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6c47e-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6c47e-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6c47e-126">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c47e-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c47e-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="6c47e-127">See Also</span></span>  
 [<span data-ttu-id="6c47e-128">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c47e-128">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
