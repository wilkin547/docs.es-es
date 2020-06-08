---
title: ICorProfilerCallback::JITCachedFunctionSearchStarted (Método)
ms.date: 03/30/2017
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
ms.openlocfilehash: d8f4a04abea0bd5eb9bf38629a8fcaf76479bcc9
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500068"
---
# <a name="icorprofilercallbackjitcachedfunctionsearchstarted-method"></a><span data-ttu-id="286b3-102">ICorProfilerCallback::JITCachedFunctionSearchStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="286b3-102">ICorProfilerCallback::JITCachedFunctionSearchStarted Method</span></span>
<span data-ttu-id="286b3-103">Notifica al generador de perfiles que se ha iniciado una búsqueda para una función que se compiló previamente mediante el generador de imágenes nativas (NGen. exe).</span><span class="sxs-lookup"><span data-stu-id="286b3-103">Notifies the profiler that a search has started for a function that was compiled previously using the Native Image Generator (NGen.exe).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="286b3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="286b3-104">Syntax</span></span>  
  
```cpp  
HRESULT JITCachedFunctionSearchStarted(  
    [in]  FunctionID functionId,  
    [out] BOOL *pbUseCachedFunction);  
```  
  
## <a name="parameters"></a><span data-ttu-id="286b3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="286b3-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="286b3-106">\[in] identificador de la función para la que se realiza la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="286b3-106">\[in] The ID of the function for which the search is being performed.</span></span>

- `pbUseCachedFunction`

  <span data-ttu-id="286b3-107">\[out] `true` si el motor de ejecución debe utilizar la versión almacenada en caché de una función (si está disponible); en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="286b3-107">\[out] `true` if the execution engine should use the cached version of a function (if available); otherwise `false`.</span></span> <span data-ttu-id="286b3-108">Si el valor es `false` , el motor de ejecución compila la función JIT en lugar de usar una versión que no está compilada JIT.</span><span class="sxs-lookup"><span data-stu-id="286b3-108">If the value is `false`, the execution engine JIT-compiles the function instead of using a version that is not JIT-compiled.</span></span>

## <a name="remarks"></a><span data-ttu-id="286b3-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="286b3-109">Remarks</span></span>  
 <span data-ttu-id="286b3-110">En la versión .NET Framework 2,0, `JITCachedFunctionSearchStarted` no se realizarán las devoluciones de llamada de [método y ICorProfilerCallback:: JITCachedFunctionSearchFinished (](icorprofilercallback-jitcachedfunctionsearchfinished-method.md) para todas las funciones de las imágenes Ngen normales.</span><span class="sxs-lookup"><span data-stu-id="286b3-110">In the .NET Framework version 2.0, the `JITCachedFunctionSearchStarted` and [ICorProfilerCallback::JITCachedFunctionSearchFinished Method](icorprofilercallback-jitcachedfunctionsearchfinished-method.md) callbacks will not be made for all functions in regular NGen images.</span></span> <span data-ttu-id="286b3-111">Solo las imágenes de NGen optimizadas para un perfil generarán devoluciones de llamada para todas las funciones de la imagen.</span><span class="sxs-lookup"><span data-stu-id="286b3-111">Only NGen images optimized for a profile will generate callbacks for all functions in the image.</span></span> <span data-ttu-id="286b3-112">Sin embargo, debido a la sobrecarga adicional, un generador de perfiles debe solicitar imágenes NGen optimizadas para el generador de perfiles solo si pretende utilizar estas devoluciones de llamada para forzar que una función se compile Just-in-Time (JIT).</span><span class="sxs-lookup"><span data-stu-id="286b3-112">However, due to the additional overhead, a profiler should request profiler-optimized NGen images only if it intends to use these callbacks to force a function to be compiled just-in-time (JIT).</span></span> <span data-ttu-id="286b3-113">De lo contrario, el generador de perfiles debe usar una estrategia diferida para recopilar información de la función.</span><span class="sxs-lookup"><span data-stu-id="286b3-113">Otherwise, the profiler should use a lazy strategy for gathering function information.</span></span>  
  
 <span data-ttu-id="286b3-114">Los perfiles deben admitir casos en los que varios subprocesos de una aplicación de la que se ha performado estén llamando al mismo método simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="286b3-114">Profilers must support cases where multiple threads of a profiled application are calling the same method simultaneously.</span></span> <span data-ttu-id="286b3-115">Por ejemplo, el subproceso A llama a `JITCachedFunctionSearchStarted` y el generador de perfiles responde estableciendo *PBUSECACHEDFUNCTION*en false para forzar la compilación JIT.</span><span class="sxs-lookup"><span data-stu-id="286b3-115">For example, thread A calls `JITCachedFunctionSearchStarted` and the profiler responds by setting *pbUseCachedFunction*to FALSE to force JIT compilation.</span></span> <span data-ttu-id="286b3-116">Después, el subproceso a llama a [ICorProfilerCallback:: JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) e [ICorProfilerCallback:: JITCompilationFinished (](icorprofilercallback-jitcompilationfinished-method.md).</span><span class="sxs-lookup"><span data-stu-id="286b3-116">Thread A then calls [ICorProfilerCallback::JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) and [ICorProfilerCallback::JITCompilationFinished](icorprofilercallback-jitcompilationfinished-method.md).</span></span>  
  
 <span data-ttu-id="286b3-117">Ahora el subproceso B llama a `JITCachedFunctionSearchStarted` para la misma función.</span><span class="sxs-lookup"><span data-stu-id="286b3-117">Now thread B calls `JITCachedFunctionSearchStarted` for the same function.</span></span> <span data-ttu-id="286b3-118">Aunque el generador de perfiles ha indicado su intención de compilar la función JIT, el generador de perfiles recibe la segunda devolución de llamada porque el subproceso B envía la devolución de llamada antes de que el generador de perfiles haya respondido a la llamada de subproceso a `JITCachedFunctionSearchStarted` .</span><span class="sxs-lookup"><span data-stu-id="286b3-118">Even though the profiler has stated its intention to JIT-compile the function, the profiler receives the second callback because thread B sends the callback before the profiler has responded to thread A's call to `JITCachedFunctionSearchStarted`.</span></span> <span data-ttu-id="286b3-119">El orden en que los subprocesos realizan llamadas depende de cómo estén programados los subprocesos.</span><span class="sxs-lookup"><span data-stu-id="286b3-119">The order in which the threads make calls depends on how the threads are scheduled.</span></span>  
  
 <span data-ttu-id="286b3-120">Cuando el generador de perfiles recibe devoluciones de llamada duplicadas, debe establecer el valor al que hace referencia `pbUseCachedFunction` en el mismo valor para todas las devoluciones de llamada duplicadas.</span><span class="sxs-lookup"><span data-stu-id="286b3-120">When the profiler receives duplicate callbacks, it must set the value referenced by `pbUseCachedFunction` to the same value for all the duplicate callbacks.</span></span> <span data-ttu-id="286b3-121">Es decir, cuando `JITCachedFunctionSearchStarted` se llama varias veces con el mismo `functionId` valor, el generador de perfiles debe responder cada vez.</span><span class="sxs-lookup"><span data-stu-id="286b3-121">That is, when `JITCachedFunctionSearchStarted` is called multiple times with the same `functionId` value, the profiler must respond the same each time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="286b3-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="286b3-122">Requirements</span></span>  
 <span data-ttu-id="286b3-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="286b3-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="286b3-124">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="286b3-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="286b3-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="286b3-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="286b3-126">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="286b3-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="286b3-127">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="286b3-127">See also</span></span>

- [<span data-ttu-id="286b3-128">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="286b3-128">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
