---
title: ICorProfilerFunctionControl::SetCodegenFlags (método)
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionControl.SetCodegenFlags
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionControl::SetCodegenFlags
helpviewer_keywords:
- ICorProfilerFunctionControl::SetCodegenFlags method [.NET Framework profiling]
- SetCodegenFlags method, ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: a2d5daa5-b990-4ae5-bf2a-c0862fe58bd7
topic_type:
- apiref
ms.openlocfilehash: 88c9f552b73af69ea4e1f64b75ed74ea762dcdfb
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74429943"
---
# <a name="icorprofilerfunctioncontrolsetcodegenflags-method"></a><span data-ttu-id="48203-102">ICorProfilerFunctionControl::SetCodegenFlags (método)</span><span class="sxs-lookup"><span data-stu-id="48203-102">ICorProfilerFunctionControl::SetCodegenFlags Method</span></span>
<span data-ttu-id="48203-103">Establece una o varias marcas de la enumeración [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) para controlar la generación de código para una función recompilada Just-in-Time (JIT).</span><span class="sxs-lookup"><span data-stu-id="48203-103">Sets one or more flags from the [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) enumeration to control code generation for a just-in-time (JIT) recompiled function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48203-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="48203-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCodegenFlags(  
    [in] DWORD flags);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48203-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="48203-105">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="48203-106">de Una o varias marcas de la enumeración [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="48203-106">[in] One or more flags from the [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="48203-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="48203-107">Remarks</span></span>  
 <span data-ttu-id="48203-108">El generador de perfiles obtiene una instancia de esta interfaz a través de la devolución de llamada [ICorProfilerCallback4:: getrejitparameters (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) .</span><span class="sxs-lookup"><span data-stu-id="48203-108">The profiler obtains an instance of this interface through the [ICorProfilerCallback4::GetReJITParameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) callback.</span></span> <span data-ttu-id="48203-109">`SetCodegenFlags` permite al generador de perfiles controlar la generación de código para la función recompilada.</span><span class="sxs-lookup"><span data-stu-id="48203-109">`SetCodegenFlags` allows the profiler to control the code generation for the recompiled function.</span></span> <span data-ttu-id="48203-110">Como con todos los demás parámetros de recompilación JIT, las marcas de generación de código se aplican a todas las instancias de la función.</span><span class="sxs-lookup"><span data-stu-id="48203-110">As with all other JIT recompilation parameters, the code generation flags apply to all instances of the function.</span></span>  
  
 <span data-ttu-id="48203-111">El compilador JIT tiene en cuenta estas marcas de compilación, junto con otras marcas especificadas por otros orígenes, al compilar una función.</span><span class="sxs-lookup"><span data-stu-id="48203-111">The JIT compiler considers these compilation flags, along with other flags specified by other sources, when compiling a function.</span></span>  <span data-ttu-id="48203-112">Los demás orígenes incluyen el depurador, las marcas globales establecidas por el generador de perfiles al iniciarse mediante el método [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) (con los valores `COR_PRF_DISABLE_INLINING` y `COR_PRF_DISABLE_OPTIMIZATIONS`) y la devolución de llamada [ICorProfilerCallback:: jitinlining (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="48203-112">The other sources include the debugger, global flags set by the profiler on startup by using the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method (with the values `COR_PRF_DISABLE_INLINING` and `COR_PRF_DISABLE_OPTIMIZATIONS`), and the profiler’s [ICorProfilerCallback::JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) callback.</span></span>  <span data-ttu-id="48203-113">El compilador JIT da prioridad a un origen que solicita la menor cantidad de optimización.</span><span class="sxs-lookup"><span data-stu-id="48203-113">The JIT compiler gives precedence to a source that requests the least amount of optimizing.</span></span>  <span data-ttu-id="48203-114">Por ejemplo, si el generador de perfiles especifica `COR_PRF_DISABLE_INLINING` en el inicio, pero no especifica `COR_PRF_CODEGEN_DISABLE_INLINING` en la devolución de llamada [ICorProfilerFunctionControl:: setcodegenflags (](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) , la inserción está todavía deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="48203-114">For example, if the profiler specifies `COR_PRF_DISABLE_INLINING` on startup, but does not specify `COR_PRF_CODEGEN_DISABLE_INLINING` in the [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) callback, inlining is still disabled.</span></span>  <span data-ttu-id="48203-115">Del mismo modo, si el generador de perfiles no especifica `COR_PRF_CODEGEN_DISABLE_INLINING` en `SetCodegenFlags`, pero deshabilita la inserción mediante la devolución de llamada [ICorProfilerCallback:: jitinlining (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) , la inserción se deshabilita.</span><span class="sxs-lookup"><span data-stu-id="48203-115">Similarly, if the profiler does not specify `COR_PRF_CODEGEN_DISABLE_INLINING` in `SetCodegenFlags`, but then disables inlining by using the [ICorProfilerCallback::JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) callback, inlining is disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48203-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="48203-116">Requirements</span></span>  
 <span data-ttu-id="48203-117">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48203-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48203-118">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="48203-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="48203-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="48203-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="48203-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48203-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48203-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="48203-121">See also</span></span>

- [<span data-ttu-id="48203-122">ICorProfilerFunctionControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="48203-122">ICorProfilerFunctionControl Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)
