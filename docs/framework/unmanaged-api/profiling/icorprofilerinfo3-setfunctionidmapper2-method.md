---
title: ICorProfilerInfo3::SetFunctionIDMapper2 (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.SetFunctionIDMapper2 Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::SetFunctionIDMapper2
helpviewer_keywords:
- SetFunctionIDMapper2 method [.NET Framework profiling]
- ICorProfilerInfo3::SetFunctionIDMapper2 method [.NET Framework profiling]
ms.assetid: 8cdb1188-952a-4ba8-9f05-bfebc18cdd29
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ee520ba95a8eefcc3322af0d0dd6e03c70d35cd4
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468707"
---
# <a name="icorprofilerinfo3setfunctionidmapper2-method"></a><span data-ttu-id="60235-102">ICorProfilerInfo3::SetFunctionIDMapper2 (Método)</span><span class="sxs-lookup"><span data-stu-id="60235-102">ICorProfilerInfo3::SetFunctionIDMapper2 Method</span></span>
<span data-ttu-id="60235-103">Especifica la función implementada por el generador de perfiles a la que se llamará para asignar los valores `FunctionID` a valores alternativos, que se pasan los enlaces de entrada y salida de función del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="60235-103">Specifies the profiler-implemented function that will be called to map `FunctionID` values to alternative values, which are passed to the profiler's function entry/exit hooks.</span></span> <span data-ttu-id="60235-104">Este método extiende la [SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md) método con un parámetro de datos adicionales, que pueden usar los generadores de perfiles para eliminar la ambigüedad entre los Runtime.</span><span class="sxs-lookup"><span data-stu-id="60235-104">This method extends the [ICorProfilerInfo::SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md) method with an additional data parameter, which profilers may use to disambiguate among runtimes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60235-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="60235-105">Syntax</span></span>  
  
```  
HRESULT SetFunctionIDMapper2(  
       [in] FunctionIDMapper2 *pFunc,  
       [in] void *clientData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="60235-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="60235-106">Parameters</span></span>  
 `pFunc`  
 <span data-ttu-id="60235-107">[in] Un puntero a un [FunctionIDMapper2](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md) implementación que se llamará para asignar el `FunctionID` valores a sus valores alternativos.</span><span class="sxs-lookup"><span data-stu-id="60235-107">[in] A pointer to a [FunctionIDMapper2](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md) implementation that will be called to map the `FunctionID` values to their alternative values.</span></span>  
  
 `clientData`  
 <span data-ttu-id="60235-108">[in] Un puntero que se pasa a cada [FunctionIDMapper2](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md) función llamada realizada por el tiempo de ejecución actual.</span><span class="sxs-lookup"><span data-stu-id="60235-108">[in] A pointer that is passed to every [FunctionIDMapper2](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md) function call made by the current runtime.</span></span> <span data-ttu-id="60235-109">El generador de perfiles puede utilizar esta información para eliminar la ambigüedad entre los Runtime.</span><span class="sxs-lookup"><span data-stu-id="60235-109">The profiler can use this information to disambiguate among runtimes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="60235-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="60235-110">Return Value</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="60235-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="60235-111">Remarks</span></span>  
 <span data-ttu-id="60235-112">Las alternativas para los valores de FunctionID se pasarán a enlaces de entrada y salida de función del generador de perfiles ([FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), y [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md) ; o [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), y [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)) que se especifican mediante el [ SetEnterLeaveFunctionHooks3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) o [SetEnterLeaveFunctionHooks3WithInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="60235-112">The alternatives for the FunctionID values will be passed to the profiler's function entry/exit hooks ([FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), and [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md); or [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)) that are specified by the [SetEnterLeaveFunctionHooks3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) or [SetEnterLeaveFunctionHooks3WithInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) method.</span></span>  
  
 <span data-ttu-id="60235-113">El `FunctionIDMapper2` método se puede establecer una sola vez; se recomienda establecerlo el [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="60235-113">The `FunctionIDMapper2` method can be set only once; we recommend that you set it in the [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60235-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="60235-114">Requirements</span></span>  
 <span data-ttu-id="60235-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="60235-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60235-116">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="60235-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="60235-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="60235-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="60235-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60235-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60235-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="60235-119">See also</span></span>
- [<span data-ttu-id="60235-120">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="60235-120">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="60235-121">ICorProfilerInfo3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="60235-121">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="60235-122">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="60235-122">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="60235-123">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="60235-123">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
