---
description: 'Más información sobre: ICorProfilerFunctionControl:: Setcodegenflags ((método)'
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
ms.openlocfilehash: 61fa8be0993a06a3b2d352af408ac47b7b30e385
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781628"
---
# <a name="icorprofilerfunctioncontrolsetcodegenflags-method"></a><span data-ttu-id="b04c8-103">ICorProfilerFunctionControl::SetCodegenFlags (Método)</span><span class="sxs-lookup"><span data-stu-id="b04c8-103">ICorProfilerFunctionControl::SetCodegenFlags Method</span></span>

<span data-ttu-id="b04c8-104">Establece una o varias marcas de la enumeración [COR_PRF_CODEGEN_FLAGS](cor-prf-codegen-flags-enumeration.md) para controlar la generación de código para una función recompilada Just-in-Time (JIT).</span><span class="sxs-lookup"><span data-stu-id="b04c8-104">Sets one or more flags from the [COR_PRF_CODEGEN_FLAGS](cor-prf-codegen-flags-enumeration.md) enumeration to control code generation for a just-in-time (JIT) recompiled function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b04c8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b04c8-105">Syntax</span></span>  
  
```cpp  
HRESULT SetCodegenFlags(  
    [in] DWORD flags);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b04c8-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b04c8-106">Parameters</span></span>  

 `flags`  
 <span data-ttu-id="b04c8-107">de Una o varias marcas de la enumeración [COR_PRF_CODEGEN_FLAGS](cor-prf-codegen-flags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="b04c8-107">[in] One or more flags from the [COR_PRF_CODEGEN_FLAGS](cor-prf-codegen-flags-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b04c8-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b04c8-108">Remarks</span></span>  

 <span data-ttu-id="b04c8-109">El generador de perfiles obtiene una instancia de esta interfaz a través de la devolución de llamada [ICorProfilerCallback4:: getrejitparameters (](icorprofilercallback4-getrejitparameters-method.md) .</span><span class="sxs-lookup"><span data-stu-id="b04c8-109">The profiler obtains an instance of this interface through the [ICorProfilerCallback4::GetReJITParameters](icorprofilercallback4-getrejitparameters-method.md) callback.</span></span> <span data-ttu-id="b04c8-110">`SetCodegenFlags` permite al generador de perfiles controlar la generación de código para la función recompilada.</span><span class="sxs-lookup"><span data-stu-id="b04c8-110">`SetCodegenFlags` allows the profiler to control the code generation for the recompiled function.</span></span> <span data-ttu-id="b04c8-111">Como con todos los demás parámetros de recompilación JIT, las marcas de generación de código se aplican a todas las instancias de la función.</span><span class="sxs-lookup"><span data-stu-id="b04c8-111">As with all other JIT recompilation parameters, the code generation flags apply to all instances of the function.</span></span>  
  
 <span data-ttu-id="b04c8-112">El compilador JIT tiene en cuenta estas marcas de compilación, junto con otras marcas especificadas por otros orígenes, al compilar una función.</span><span class="sxs-lookup"><span data-stu-id="b04c8-112">The JIT compiler considers these compilation flags, along with other flags specified by other sources, when compiling a function.</span></span>  <span data-ttu-id="b04c8-113">Los demás orígenes incluyen el depurador, las marcas globales establecidas por el generador de perfiles al iniciarse mediante el método [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) (con los valores `COR_PRF_DISABLE_INLINING` y `COR_PRF_DISABLE_OPTIMIZATIONS` ) y la devolución de llamada [ICorProfilerCallback:: jitinlining (](icorprofilercallback-jitinlining-method.md) del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="b04c8-113">The other sources include the debugger, global flags set by the profiler on startup by using the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method (with the values `COR_PRF_DISABLE_INLINING` and `COR_PRF_DISABLE_OPTIMIZATIONS`), and the profiler’s [ICorProfilerCallback::JITInlining](icorprofilercallback-jitinlining-method.md) callback.</span></span>  <span data-ttu-id="b04c8-114">El compilador JIT da prioridad a un origen que solicita la menor cantidad de optimización.</span><span class="sxs-lookup"><span data-stu-id="b04c8-114">The JIT compiler gives precedence to a source that requests the least amount of optimizing.</span></span>  <span data-ttu-id="b04c8-115">Por ejemplo, si el generador de perfiles especifica `COR_PRF_DISABLE_INLINING` en el inicio, pero no especifica `COR_PRF_CODEGEN_DISABLE_INLINING` en la devolución de llamada [ICorProfilerFunctionControl:: setcodegenflags (](icorprofilerfunctioncontrol-setcodegenflags-method.md) , la inclusión está todavía deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="b04c8-115">For example, if the profiler specifies `COR_PRF_DISABLE_INLINING` on startup, but does not specify `COR_PRF_CODEGEN_DISABLE_INLINING` in the [ICorProfilerFunctionControl::SetCodegenFlags](icorprofilerfunctioncontrol-setcodegenflags-method.md) callback, inlining is still disabled.</span></span>  <span data-ttu-id="b04c8-116">Del mismo modo, si el generador de perfiles no especifica `COR_PRF_CODEGEN_DISABLE_INLINING` en `SetCodegenFlags` , pero, a continuación, deshabilita la inserción mediante la devolución de llamada [ICorProfilerCallback:: jitinlining (](icorprofilercallback-jitinlining-method.md) , la inserción se deshabilita.</span><span class="sxs-lookup"><span data-stu-id="b04c8-116">Similarly, if the profiler does not specify `COR_PRF_CODEGEN_DISABLE_INLINING` in `SetCodegenFlags`, but then disables inlining by using the [ICorProfilerCallback::JITInlining](icorprofilercallback-jitinlining-method.md) callback, inlining is disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b04c8-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b04c8-117">Requirements</span></span>  

 <span data-ttu-id="b04c8-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b04c8-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b04c8-119">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b04c8-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b04c8-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b04c8-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b04c8-121">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b04c8-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b04c8-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="b04c8-122">See also</span></span>

- [<span data-ttu-id="b04c8-123">ICorProfilerFunctionControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b04c8-123">ICorProfilerFunctionControl Interface</span></span>](icorprofilerfunctioncontrol-interface.md)
