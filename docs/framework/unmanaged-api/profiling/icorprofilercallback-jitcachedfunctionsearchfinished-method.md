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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 89c7b0fe0f3ade3f57aa50b100bc9b4ecc904a17
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452002"
---
# <a name="icorprofilercallbackjitcachedfunctionsearchfinished-method"></a><span data-ttu-id="a66c1-102">ICorProfilerCallback::JITCachedFunctionSearchFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="a66c1-102">ICorProfilerCallback::JITCachedFunctionSearchFinished Method</span></span>
<span data-ttu-id="a66c1-103">Notifica al generador de perfiles que ha finalizado la búsqueda para una función que se compiló anteriormente con el generador de imágenes nativas (NGen.exe).</span><span class="sxs-lookup"><span data-stu-id="a66c1-103">Notifies the profiler that a search has finished for a function that was compiled previously using the Native Image Generator (NGen.exe).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a66c1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a66c1-104">Syntax</span></span>  
  
```  
HRESULT JITCachedFunctionSearchFinished(  
    [in] FunctionID        functionId,  
    [in] COR_PRF_JIT_CACHE result);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a66c1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a66c1-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="a66c1-106">[in] El identificador de la función para el que se realiza la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="a66c1-106">[in] The ID of the function for which the search was performed.</span></span>  
  
 `result`  
 <span data-ttu-id="a66c1-107">[in] Un valor de la [COR_PRF_JIT_CACHE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-jit-cache-enumeration.md) enumeración que indica el resultado de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="a66c1-107">[in] A value of the [COR_PRF_JIT_CACHE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-jit-cache-enumeration.md) enumeration that indicates the result of the search.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a66c1-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a66c1-108">Remarks</span></span>  
 <span data-ttu-id="a66c1-109">En .NET Framework versión 2.0, el [ICorProfilerCallback:: JITCachedFunctionSearchStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchstarted-method.md) y `JITCachedFunctionSearchFinished` no se realizarán las devoluciones de llamada para todas las funciones en imágenes NGen normales.</span><span class="sxs-lookup"><span data-stu-id="a66c1-109">In the .NET Framework version 2.0, the [ICorProfilerCallback::JITCachedFunctionSearchStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchstarted-method.md) and `JITCachedFunctionSearchFinished` callbacks will not be made for all functions in regular NGen images.</span></span> <span data-ttu-id="a66c1-110">Sólo las imágenes NGen optimizadas para un generador de perfiles generará las devoluciones de llamada para todas las funciones en la imagen.</span><span class="sxs-lookup"><span data-stu-id="a66c1-110">Only NGen images optimized for a profiler will generate callbacks for all functions in the image.</span></span> <span data-ttu-id="a66c1-111">Sin embargo, debido a la sobrecarga adicional, un generador de perfiles debe solicitar imágenes NGen optimizadas de generador de perfiles solo si tiene intención de utilizar estas devoluciones de llamada para forzar una función para ser compilado just-in-time (JIT).</span><span class="sxs-lookup"><span data-stu-id="a66c1-111">However, due to the additional overhead, a profiler should request profiler-optimized NGen images only if it intends to use these callbacks to force a function to be compiled just-in-time (JIT).</span></span> <span data-ttu-id="a66c1-112">En caso contrario, el generador de perfiles debe utilizar una estrategia lenta para recopilar información de la función.</span><span class="sxs-lookup"><span data-stu-id="a66c1-112">Otherwise, the profiler should use a lazy strategy for gathering function information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a66c1-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a66c1-113">Requirements</span></span>  
 <span data-ttu-id="a66c1-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a66c1-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a66c1-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a66c1-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a66c1-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a66c1-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a66c1-117">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a66c1-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a66c1-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="a66c1-118">See Also</span></span>  
 [<span data-ttu-id="a66c1-119">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a66c1-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
