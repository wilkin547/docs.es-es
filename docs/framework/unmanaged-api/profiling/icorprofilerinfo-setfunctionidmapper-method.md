---
title: ICorProfilerInfo::SetFunctionIDMapper (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetFunctionIDMapper
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetFunctionIDMapper
helpviewer_keywords:
- ICorProfilerInfo::SetFunctionIDMapper method [.NET Framework profiling]
- SetFunctionIDMapper method [.NET Framework profiling]
ms.assetid: 1a6e5dae-d366-4497-9c02-7b5b1f43f9ec
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 52e8bc29ce03c54fd81ddc0d041cff6b9c35bb2d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57475611"
---
# <a name="icorprofilerinfosetfunctionidmapper-method"></a><span data-ttu-id="3bd28-102">ICorProfilerInfo::SetFunctionIDMapper (Método)</span><span class="sxs-lookup"><span data-stu-id="3bd28-102">ICorProfilerInfo::SetFunctionIDMapper Method</span></span>
<span data-ttu-id="3bd28-103">Especifica la función implementada por el generador de perfiles a la que se llamará para asignar los valores `FunctionID` a valores alternativos, que se pasan los enlaces de entrada y salida de función del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="3bd28-103">Specifies the profiler-implemented function that will be called to map `FunctionID` values to alternative values, which are passed to the profiler's function entry/exit hooks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3bd28-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3bd28-104">Syntax</span></span>  
  
```  
HRESULT SetFunctionIDMapper (  
    [in] FunctionIDMapper *pFunc);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3bd28-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3bd28-105">Parameters</span></span>  
 `pFunc`  
 <span data-ttu-id="3bd28-106">[in] Un puntero a la [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) implementación que se llamará para asignar el `FunctionID` valores a sus valores alternativos.</span><span class="sxs-lookup"><span data-stu-id="3bd28-106">[in] A pointer to the [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) implementation that will be called to map the `FunctionID` values to their alternative values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3bd28-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3bd28-107">Remarks</span></span>  
 <span data-ttu-id="3bd28-108">Las alternativas para la `FunctionID` se pasarán a enlaces de entrada y salida de función del generador de perfiles ([FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md), [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md), y [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)) que se especifican mediante el [ICorProfilerInfo2:: Setenterleavefunctionhooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="3bd28-108">The alternatives for the `FunctionID` values will be passed to the profiler's function entry/exit hooks ([FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md), [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md), and [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)) that are specified by the [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md) method.</span></span>  
  
 <span data-ttu-id="3bd28-109">El `FunctionIDMapper` puede establecerse una sola vez y se recomienda establecerlo el [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="3bd28-109">The `FunctionIDMapper` can be set only once and it is recommended that you set it in the [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3bd28-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3bd28-110">Requirements</span></span>  
 <span data-ttu-id="3bd28-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3bd28-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3bd28-112">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3bd28-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3bd28-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3bd28-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3bd28-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3bd28-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bd28-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="3bd28-115">See also</span></span>
- [<span data-ttu-id="3bd28-116">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3bd28-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
