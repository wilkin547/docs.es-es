---
title: ICorProfilerCallback::JITCachedFunctionSearchFinished (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCachedFunctionSearchFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCachedFunctionSearchFinished
helpviewer_keywords:
- JITCachedFunctionSearchFinished method [.NET Framework profiling]
- ICorProfilerCallback::JITCachedFunctionSearchFinished method [.NET Framework profiling]
ms.assetid: 3c325c82-cddd-4b00-b3da-e450c36abf62
topic_type:
- apiref
ms.openlocfilehash: fe07270989df897c3dbf689305784f9f0af65742
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684049"
---
# <a name="icorprofilercallbackjitcachedfunctionsearchfinished-method"></a><span data-ttu-id="484db-102">ICorProfilerCallback::JITCachedFunctionSearchFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="484db-102">ICorProfilerCallback::JITCachedFunctionSearchFinished Method</span></span>

<span data-ttu-id="484db-103">Notifica al generador de perfiles que ha finalizado una búsqueda para una función que se compiló previamente mediante el generador de imágenes nativas (NGen.exe).</span><span class="sxs-lookup"><span data-stu-id="484db-103">Notifies the profiler that a search has finished for a function that was compiled previously using the Native Image Generator (NGen.exe).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="484db-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="484db-104">Syntax</span></span>  
  
```cpp  
HRESULT JITCachedFunctionSearchFinished(  
    [in] FunctionID        functionId,  
    [in] COR_PRF_JIT_CACHE result);  
```  
  
## <a name="parameters"></a><span data-ttu-id="484db-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="484db-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="484db-106">\[in] identificador de la función para la que se realizó la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="484db-106">\[in] The ID of the function for which the search was performed.</span></span>

- `result`

  <span data-ttu-id="484db-107">\[in] un valor de la enumeración [COR_PRF_JIT_CACHE](cor-prf-jit-cache-enumeration.md) que indica el resultado de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="484db-107">\[in] A value of the [COR_PRF_JIT_CACHE](cor-prf-jit-cache-enumeration.md) enumeration that indicates the result of the search.</span></span>

## <a name="remarks"></a><span data-ttu-id="484db-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="484db-108">Remarks</span></span>  

 <span data-ttu-id="484db-109">En la versión .NET Framework 2,0, no se realizarán las devoluciones de llamada [ICorProfilerCallback:: jitcachedfunctionsearchstarted (](icorprofilercallback-jitcachedfunctionsearchstarted-method.md) y `JITCachedFunctionSearchFinished` para todas las funciones de las imágenes Ngen normales.</span><span class="sxs-lookup"><span data-stu-id="484db-109">In the .NET Framework version 2.0, the [ICorProfilerCallback::JITCachedFunctionSearchStarted](icorprofilercallback-jitcachedfunctionsearchstarted-method.md) and `JITCachedFunctionSearchFinished` callbacks will not be made for all functions in regular NGen images.</span></span> <span data-ttu-id="484db-110">Solo las imágenes de NGen optimizadas para un generador de perfiles generarán devoluciones de llamada para todas las funciones de la imagen.</span><span class="sxs-lookup"><span data-stu-id="484db-110">Only NGen images optimized for a profiler will generate callbacks for all functions in the image.</span></span> <span data-ttu-id="484db-111">Sin embargo, debido a la sobrecarga adicional, un generador de perfiles debe solicitar imágenes NGen optimizadas para el generador de perfiles solo si pretende utilizar estas devoluciones de llamada para forzar que una función se compile Just-in-Time (JIT).</span><span class="sxs-lookup"><span data-stu-id="484db-111">However, due to the additional overhead, a profiler should request profiler-optimized NGen images only if it intends to use these callbacks to force a function to be compiled just-in-time (JIT).</span></span> <span data-ttu-id="484db-112">De lo contrario, el generador de perfiles debe usar una estrategia diferida para recopilar información de la función.</span><span class="sxs-lookup"><span data-stu-id="484db-112">Otherwise, the profiler should use a lazy strategy for gathering function information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="484db-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="484db-113">Requirements</span></span>  

 <span data-ttu-id="484db-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="484db-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="484db-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="484db-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="484db-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="484db-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="484db-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="484db-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="484db-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="484db-118">See also</span></span>

- [<span data-ttu-id="484db-119">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="484db-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
