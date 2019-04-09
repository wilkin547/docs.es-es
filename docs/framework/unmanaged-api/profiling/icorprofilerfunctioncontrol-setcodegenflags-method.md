---
title: ICorProfilerFunctionControl::SetCodegenFlags (Método)
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 12f91bdd264135eb0ff3a48e15611cf5a0e3c064
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59104447"
---
# <a name="icorprofilerfunctioncontrolsetcodegenflags-method"></a><span data-ttu-id="997ba-102">ICorProfilerFunctionControl::SetCodegenFlags (Método)</span><span class="sxs-lookup"><span data-stu-id="997ba-102">ICorProfilerFunctionControl::SetCodegenFlags Method</span></span>
<span data-ttu-id="997ba-103">Establece una o más marcas de la [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) enumeración a la generación de código de control para un just-in-time (JIT) vuelve a compilar la función.</span><span class="sxs-lookup"><span data-stu-id="997ba-103">Sets one or more flags from the [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) enumeration to control code generation for a just-in-time (JIT) recompiled function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="997ba-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="997ba-104">Syntax</span></span>  
  
```  
HRESULT SetCodegenFlags(  
    [in] DWORD flags);  
```  
  
## <a name="parameters"></a><span data-ttu-id="997ba-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="997ba-105">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="997ba-106">[in] Uno o más marcadores de la [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) enumeración.</span><span class="sxs-lookup"><span data-stu-id="997ba-106">[in] One or more flags from the [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="997ba-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="997ba-107">Remarks</span></span>  
 <span data-ttu-id="997ba-108">El generador de perfiles Obtiene una instancia de esta interfaz a través de la [Icorprofilercallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="997ba-108">The profiler obtains an instance of this interface through the [ICorProfilerCallback4::GetReJITParameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) callback.</span></span> `SetCodegenFlags` <span data-ttu-id="997ba-109">permite que el generador de perfiles controlar la generación de código para la función ha vuelto a compilar.</span><span class="sxs-lookup"><span data-stu-id="997ba-109">allows the profiler to control the code generation for the recompiled function.</span></span> <span data-ttu-id="997ba-110">Al igual que con todos los demás parámetros de recompilación JIT, las marcas de generación de código se aplican a todas las instancias de la función.</span><span class="sxs-lookup"><span data-stu-id="997ba-110">As with all other JIT recompilation parameters, the code generation flags apply to all instances of the function.</span></span>  
  
 <span data-ttu-id="997ba-111">El compilador JIT tiene en cuenta estos marcadores de compilación, junto con otras marcas especificadas por otros orígenes, al compilar una función.</span><span class="sxs-lookup"><span data-stu-id="997ba-111">The JIT compiler considers these compilation flags, along with other flags specified by other sources, when compiling a function.</span></span>  <span data-ttu-id="997ba-112">Los demás orígenes incluyen el depurador, indicadores globales establecen en el inicio mediante el generador de perfiles mediante el [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) método (con los valores `COR_PRF_DISABLE_INLINING` y `COR_PRF_DISABLE_OPTIMIZATIONS`) y el generador de perfiles [ JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="997ba-112">The other sources include the debugger, global flags set by the profiler on startup by using the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method (with the values `COR_PRF_DISABLE_INLINING` and `COR_PRF_DISABLE_OPTIMIZATIONS`), and the profiler’s [ICorProfilerCallback::JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) callback.</span></span>  <span data-ttu-id="997ba-113">El compilador JIT da prioridad a un origen que solicita la menor cantidad de optimización.</span><span class="sxs-lookup"><span data-stu-id="997ba-113">The JIT compiler gives precedence to a source that requests the least amount of optimizing.</span></span>  <span data-ttu-id="997ba-114">Por ejemplo, si especifica el generador de perfiles `COR_PRF_DISABLE_INLINING` durante el inicio, pero no especifica `COR_PRF_CODEGEN_DISABLE_INLINING` en el [Icorprofilerfunctioncontrol](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) todavía está deshabilitada la devolución de llamada, inclusión entre líneas.</span><span class="sxs-lookup"><span data-stu-id="997ba-114">For example, if the profiler specifies `COR_PRF_DISABLE_INLINING` on startup, but does not specify `COR_PRF_CODEGEN_DISABLE_INLINING` in the [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) callback, inlining is still disabled.</span></span>  <span data-ttu-id="997ba-115">De forma similar, si no especifica el generador de perfiles `COR_PRF_CODEGEN_DISABLE_INLINING` en `SetCodegenFlags`, pero, a continuación, deshabilita la inserción mediante el uso de la [JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) está deshabilitada la devolución de llamada, inclusión entre líneas.</span><span class="sxs-lookup"><span data-stu-id="997ba-115">Similarly, if the profiler does not specify `COR_PRF_CODEGEN_DISABLE_INLINING` in `SetCodegenFlags`, but then disables inlining by using the [ICorProfilerCallback::JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) callback, inlining is disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="997ba-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="997ba-116">Requirements</span></span>  
 <span data-ttu-id="997ba-117">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="997ba-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="997ba-118">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="997ba-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="997ba-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="997ba-119">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="997ba-120">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="997ba-120">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="997ba-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="997ba-121">See also</span></span>

- [<span data-ttu-id="997ba-122">ICorProfilerFunctionControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="997ba-122">ICorProfilerFunctionControl Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)
