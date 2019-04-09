---
title: FunctionIDMapper2 (Función)
ms.date: 03/30/2017
api_name:
- FunctionIDMapper2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionIDMapper2
helpviewer_keywords:
- FunctionIDMapper2 function [.NET Framework profiling]
ms.assetid: 466ad51b-8f0c-41d9-81f7-371aac3374cb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1a236dcae29d00afe3b72dce8f81d657fb4fac28
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59082508"
---
# <a name="functionidmapper2-function"></a><span data-ttu-id="acd3e-102">FunctionIDMapper2 (Función)</span><span class="sxs-lookup"><span data-stu-id="acd3e-102">FunctionIDMapper2 Function</span></span>
<span data-ttu-id="acd3e-103">Notifica al generador de perfiles que el identificador especificado de una función puede reasignarse a otro identificador que se usará en el [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), y [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md), o[FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), y [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) devoluciones de llamada para esa función.</span><span class="sxs-lookup"><span data-stu-id="acd3e-103">Notifies the profiler that the given identifier of a function may be remapped to an alternative ID to be used in the [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), and [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md), or[FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) callbacks for that function.</span></span> `FunctionIDMapper2` <span data-ttu-id="acd3e-104">También permite al generador de perfiles indicar si desea recibir devoluciones de llamada para esa función.</span><span class="sxs-lookup"><span data-stu-id="acd3e-104">also enables the profiler to indicate whether it wants to receive callbacks for that function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acd3e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="acd3e-105">Syntax</span></span>  
  
```  
UINT_PTR __stdcall FunctionIDMapper2 (  
    [in]  FunctionID  funcId,  
    [in]  void * clientData,  
    [out] BOOL       *pbHookFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="acd3e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="acd3e-106">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="acd3e-107">[in] Identificador de la función que se va a reasignar.</span><span class="sxs-lookup"><span data-stu-id="acd3e-107">[in] The function identifier to be remapped.</span></span>  
  
 `clientData`  
 <span data-ttu-id="acd3e-108">[in] Puntero a datos que se usa para eliminar la ambigüedad entre los runtime.</span><span class="sxs-lookup"><span data-stu-id="acd3e-108">[in] A pointer to data that is used to disambiguate among runtimes.</span></span>  
  
 `pbHookFunction`  
 <span data-ttu-id="acd3e-109">[out] Puntero a un valor que el generador de perfiles establece en `true` si desea recibir devoluciones de llamada `FunctionEnter3`, `FunctionLeave3` y `FunctionTailcall3` o `FunctionEnter3WithInfo`, `FunctionLeave3WithInfo` y `FunctionTailcall3WithInfo`. De lo contrario, establece este valor en `false`.</span><span class="sxs-lookup"><span data-stu-id="acd3e-109">[out] A pointer to a value that the profiler sets to `true` if it wants to receive `FunctionEnter3`, `FunctionLeave3`, and `FunctionTailcall3`, or `FunctionEnter3WithInfo`, `FunctionLeave3WithInfo`, and `FunctionTailcall3WithInfo` callbacks; otherwise, it sets this value to `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="acd3e-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="acd3e-110">Return Value</span></span>  
 <span data-ttu-id="acd3e-111">El generador de perfiles devuelve un valor que el motor de ejecución utiliza como identificador de función alternativo.</span><span class="sxs-lookup"><span data-stu-id="acd3e-111">The profiler returns a value that the execution engine uses as an alternative function identifier.</span></span> <span data-ttu-id="acd3e-112">El valor devuelto no puede ser null a menos que se devuelva `false` en `pbHookFunction`.</span><span class="sxs-lookup"><span data-stu-id="acd3e-112">The return value cannot be null unless `false` is returned in `pbHookFunction`.</span></span> <span data-ttu-id="acd3e-113">De lo contrario, la devolución de un valor nulo genera resultados imprevisibles, que posiblemente incluyan la detención del proceso.</span><span class="sxs-lookup"><span data-stu-id="acd3e-113">Otherwise, a null return value produces unpredictable results, including possibly halting the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="acd3e-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="acd3e-114">Remarks</span></span>  
 <span data-ttu-id="acd3e-115">Este método extiende la [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) función con un parámetro adicional que se usa para pasar datos del cliente.</span><span class="sxs-lookup"><span data-stu-id="acd3e-115">This method extends the [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) function with an additional parameter that is used to pass client data.</span></span> <span data-ttu-id="acd3e-116">Los datos del cliente se usan para eliminar la ambigüedad entre los runtime.</span><span class="sxs-lookup"><span data-stu-id="acd3e-116">The client data is used to disambiguate among runtimes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="acd3e-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="acd3e-117">Requirements</span></span>  
 <span data-ttu-id="acd3e-118">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="acd3e-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="acd3e-119">**Encabezado**: CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="acd3e-119">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="acd3e-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="acd3e-120">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="acd3e-121">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="acd3e-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="acd3e-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="acd3e-122">See also</span></span>

- [<span data-ttu-id="acd3e-123">ICorProfilerInfo::SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="acd3e-123">ICorProfilerInfo::SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="acd3e-124">ICorProfilerInfo3::SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="acd3e-124">ICorProfilerInfo3::SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="acd3e-125">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="acd3e-125">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [<span data-ttu-id="acd3e-126">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="acd3e-126">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)
- [<span data-ttu-id="acd3e-127">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="acd3e-127">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="acd3e-128">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="acd3e-128">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [<span data-ttu-id="acd3e-129">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="acd3e-129">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="acd3e-130">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="acd3e-130">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="acd3e-131">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="acd3e-131">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
