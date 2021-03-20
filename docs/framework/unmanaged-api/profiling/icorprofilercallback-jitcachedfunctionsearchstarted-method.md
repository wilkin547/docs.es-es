---
description: 'Más información sobre: ICorProfilerCallback:: Jitcachedfunctionsearchstarted ((método)'
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
ms.openlocfilehash: 3f384c1a02da1747b28701d2eba994b56a85c18f
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2021
ms.locfileid: "104759965"
---
# <a name="icorprofilercallbackjitcachedfunctionsearchstarted-method"></a><span data-ttu-id="15045-103">ICorProfilerCallback::JITCachedFunctionSearchStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="15045-103">ICorProfilerCallback::JITCachedFunctionSearchStarted Method</span></span>

<span data-ttu-id="15045-104">Notifica al generador de perfiles que se ha iniciado una búsqueda para una función que se compiló previamente mediante el generador de imágenes nativas (NGen.exe).</span><span class="sxs-lookup"><span data-stu-id="15045-104">Notifies the profiler that a search has started for a function that was compiled previously using the Native Image Generator (NGen.exe).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15045-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="15045-105">Syntax</span></span>  
  
```cpp  
HRESULT JITCachedFunctionSearchStarted(  
    [in]  FunctionID functionId,  
    [out] BOOL *pbUseCachedFunction);  
```  
  
## <a name="parameters"></a><span data-ttu-id="15045-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="15045-106">Parameters</span></span>

<span data-ttu-id="15045-107">`functionId` de IDENTIFICADOR de la función para la que se realiza la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="15045-107">`functionId` [in] The ID of the function for which the search is being performed.</span></span>

<span data-ttu-id="15045-108">`pbUseCachedFunction` [out] `true` Si el motor de ejecución debe utilizar la versión almacenada en caché de una función (si está disponible); en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="15045-108">`pbUseCachedFunction` [out] `true` if the execution engine should use the cached version of a function (if available); otherwise `false`.</span></span> <span data-ttu-id="15045-109">Si el valor es `false` , el motor de ejecución compila la función JIT en lugar de usar una versión que no está compilada JIT.</span><span class="sxs-lookup"><span data-stu-id="15045-109">If the value is `false`, the execution engine JIT-compiles the function instead of using a version that is not JIT-compiled.</span></span>

## <a name="remarks"></a><span data-ttu-id="15045-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="15045-110">Remarks</span></span>  

 <span data-ttu-id="15045-111">En la versión .NET Framework 2,0, `JITCachedFunctionSearchStarted` no se realizarán las devoluciones de llamada de [método y ICorProfilerCallback:: JITCachedFunctionSearchFinished (](icorprofilercallback-jitcachedfunctionsearchfinished-method.md) para todas las funciones de las imágenes Ngen normales.</span><span class="sxs-lookup"><span data-stu-id="15045-111">In the .NET Framework version 2.0, the `JITCachedFunctionSearchStarted` and [ICorProfilerCallback::JITCachedFunctionSearchFinished Method](icorprofilercallback-jitcachedfunctionsearchfinished-method.md) callbacks will not be made for all functions in regular NGen images.</span></span> <span data-ttu-id="15045-112">Solo las imágenes de NGen optimizadas para un perfil generarán devoluciones de llamada para todas las funciones de la imagen.</span><span class="sxs-lookup"><span data-stu-id="15045-112">Only NGen images optimized for a profile will generate callbacks for all functions in the image.</span></span> <span data-ttu-id="15045-113">Sin embargo, debido a la sobrecarga adicional, un generador de perfiles debe solicitar imágenes NGen optimizadas para el generador de perfiles solo si pretende utilizar estas devoluciones de llamada para forzar que una función se compile Just-in-Time (JIT).</span><span class="sxs-lookup"><span data-stu-id="15045-113">However, due to the additional overhead, a profiler should request profiler-optimized NGen images only if it intends to use these callbacks to force a function to be compiled just-in-time (JIT).</span></span> <span data-ttu-id="15045-114">De lo contrario, el generador de perfiles debe usar una estrategia diferida para recopilar información de la función.</span><span class="sxs-lookup"><span data-stu-id="15045-114">Otherwise, the profiler should use a lazy strategy for gathering function information.</span></span>  
  
 <span data-ttu-id="15045-115">Los perfiles deben admitir casos en los que varios subprocesos de una aplicación de la que se ha performado estén llamando al mismo método simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="15045-115">Profilers must support cases where multiple threads of a profiled application are calling the same method simultaneously.</span></span> <span data-ttu-id="15045-116">Por ejemplo, el subproceso A llama a `JITCachedFunctionSearchStarted` y el generador de perfiles responde estableciendo *PBUSECACHEDFUNCTION* en false para forzar la compilación JIT.</span><span class="sxs-lookup"><span data-stu-id="15045-116">For example, thread A calls `JITCachedFunctionSearchStarted` and the profiler responds by setting *pbUseCachedFunction* to FALSE to force JIT compilation.</span></span> <span data-ttu-id="15045-117">Después, el subproceso a llama a [ICorProfilerCallback:: JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) e [ICorProfilerCallback:: JITCompilationFinished (](icorprofilercallback-jitcompilationfinished-method.md).</span><span class="sxs-lookup"><span data-stu-id="15045-117">Thread A then calls [ICorProfilerCallback::JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) and [ICorProfilerCallback::JITCompilationFinished](icorprofilercallback-jitcompilationfinished-method.md).</span></span>  
  
 <span data-ttu-id="15045-118">Ahora el subproceso B llama a `JITCachedFunctionSearchStarted` para la misma función.</span><span class="sxs-lookup"><span data-stu-id="15045-118">Now thread B calls `JITCachedFunctionSearchStarted` for the same function.</span></span> <span data-ttu-id="15045-119">Aunque el generador de perfiles ha indicado su intención de compilar la función JIT, el generador de perfiles recibe la segunda devolución de llamada porque el subproceso B envía la devolución de llamada antes de que el generador de perfiles haya respondido a la llamada de subproceso a `JITCachedFunctionSearchStarted` .</span><span class="sxs-lookup"><span data-stu-id="15045-119">Even though the profiler has stated its intention to JIT-compile the function, the profiler receives the second callback because thread B sends the callback before the profiler has responded to thread A's call to `JITCachedFunctionSearchStarted`.</span></span> <span data-ttu-id="15045-120">El orden en que los subprocesos realizan llamadas depende de cómo estén programados los subprocesos.</span><span class="sxs-lookup"><span data-stu-id="15045-120">The order in which the threads make calls depends on how the threads are scheduled.</span></span>  
  
 <span data-ttu-id="15045-121">Cuando el generador de perfiles recibe devoluciones de llamada duplicadas, debe establecer el valor al que hace referencia `pbUseCachedFunction` en el mismo valor para todas las devoluciones de llamada duplicadas.</span><span class="sxs-lookup"><span data-stu-id="15045-121">When the profiler receives duplicate callbacks, it must set the value referenced by `pbUseCachedFunction` to the same value for all the duplicate callbacks.</span></span> <span data-ttu-id="15045-122">Es decir, cuando `JITCachedFunctionSearchStarted` se llama varias veces con el mismo `functionId` valor, el generador de perfiles debe responder cada vez.</span><span class="sxs-lookup"><span data-stu-id="15045-122">That is, when `JITCachedFunctionSearchStarted` is called multiple times with the same `functionId` value, the profiler must respond the same each time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15045-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="15045-123">Requirements</span></span>  

 <span data-ttu-id="15045-124">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15045-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15045-125">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="15045-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="15045-126">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="15045-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="15045-127">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15045-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15045-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="15045-128">See also</span></span>

- [<span data-ttu-id="15045-129">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="15045-129">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
