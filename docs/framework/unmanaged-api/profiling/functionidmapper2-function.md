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
ms.openlocfilehash: 7aa90b92d129f1269d901f1cbb5c6a0750de9a90
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728542"
---
# <a name="functionidmapper2-function"></a><span data-ttu-id="e2ee7-102">FunctionIDMapper2 (Función)</span><span class="sxs-lookup"><span data-stu-id="e2ee7-102">FunctionIDMapper2 Function</span></span>

<span data-ttu-id="e2ee7-103">Notifica al generador de perfiles que el identificador especificado de una función puede reasignarse a un identificador alternativo que se va a usar en las devoluciones de llamada [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md), [FunctionTailcall3](functiontailcall3-function.md)o[FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md)y [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) de esa función.</span><span class="sxs-lookup"><span data-stu-id="e2ee7-103">Notifies the profiler that the given identifier of a function may be remapped to an alternative ID to be used in the [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md), and [FunctionTailcall3](functiontailcall3-function.md), or[FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) callbacks for that function.</span></span> <span data-ttu-id="e2ee7-104">Además, `FunctionIDMapper2` permite al generador de perfiles indicar si desea recibir devoluciones de llamada de esa función.</span><span class="sxs-lookup"><span data-stu-id="e2ee7-104">`FunctionIDMapper2` also enables the profiler to indicate whether it wants to receive callbacks for that function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2ee7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e2ee7-105">Syntax</span></span>  
  
```cpp  
UINT_PTR __stdcall FunctionIDMapper2 (  
    [in]  FunctionID  funcId,  
    [in]  void * clientData,  
    [out] BOOL       *pbHookFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2ee7-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e2ee7-106">Parameters</span></span>

- `funcId`

  <span data-ttu-id="e2ee7-107">\[en] el identificador de función que se va a reasignar.</span><span class="sxs-lookup"><span data-stu-id="e2ee7-107">\[in] The function identifier to be remapped.</span></span>

- `clientData`

  <span data-ttu-id="e2ee7-108">\[in] un puntero a datos que se usa para eliminar la ambigüedad entre los tiempos de ejecución.</span><span class="sxs-lookup"><span data-stu-id="e2ee7-108">\[in] A pointer to data that is used to disambiguate among runtimes.</span></span>

- `pbHookFunction`

  <span data-ttu-id="e2ee7-109">\[out] un puntero a un valor que el generador de perfiles establece en `true` si desea recibir `FunctionEnter3` `FunctionLeave3` `FunctionTailcall3` devoluciones de llamada, y, o `FunctionEnter3WithInfo` , `FunctionLeave3WithInfo` y `FunctionTailcall3WithInfo` ; de lo contrario, establece este valor en `false` .</span><span class="sxs-lookup"><span data-stu-id="e2ee7-109">\[out] A pointer to a value that the profiler sets to `true` if it wants to receive `FunctionEnter3`, `FunctionLeave3`, and `FunctionTailcall3`, or `FunctionEnter3WithInfo`, `FunctionLeave3WithInfo`, and `FunctionTailcall3WithInfo` callbacks; otherwise, it sets this value to `false`.</span></span>

## <a name="return-value"></a><span data-ttu-id="e2ee7-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e2ee7-110">Return Value</span></span>  

 <span data-ttu-id="e2ee7-111">El generador de perfiles devuelve un valor que el motor de ejecución utiliza como identificador de función alternativo.</span><span class="sxs-lookup"><span data-stu-id="e2ee7-111">The profiler returns a value that the execution engine uses as an alternative function identifier.</span></span> <span data-ttu-id="e2ee7-112">El valor devuelto no puede ser null a menos que se devuelva `false` en `pbHookFunction`.</span><span class="sxs-lookup"><span data-stu-id="e2ee7-112">The return value cannot be null unless `false` is returned in `pbHookFunction`.</span></span> <span data-ttu-id="e2ee7-113">De lo contrario, la devolución de un valor nulo genera resultados imprevisibles, que posiblemente incluyan la detención del proceso.</span><span class="sxs-lookup"><span data-stu-id="e2ee7-113">Otherwise, a null return value produces unpredictable results, including possibly halting the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2ee7-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e2ee7-114">Remarks</span></span>  

 <span data-ttu-id="e2ee7-115">Este método extiende la función [FunctionIDMapper](functionidmapper-function.md) con un parámetro adicional que se usa para pasar los datos del cliente.</span><span class="sxs-lookup"><span data-stu-id="e2ee7-115">This method extends the [FunctionIDMapper](functionidmapper-function.md) function with an additional parameter that is used to pass client data.</span></span> <span data-ttu-id="e2ee7-116">Los datos del cliente se usan para eliminar la ambigüedad entre los runtime.</span><span class="sxs-lookup"><span data-stu-id="e2ee7-116">The client data is used to disambiguate among runtimes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2ee7-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e2ee7-117">Requirements</span></span>  

 <span data-ttu-id="e2ee7-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2ee7-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2ee7-119">**Encabezado:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="e2ee7-119">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="e2ee7-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e2ee7-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e2ee7-121">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2ee7-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2ee7-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e2ee7-122">See also</span></span>

- [<span data-ttu-id="e2ee7-123">ICorProfilerInfo::SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="e2ee7-123">ICorProfilerInfo::SetFunctionIDMapper</span></span>](icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="e2ee7-124">ICorProfilerInfo3::SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="e2ee7-124">ICorProfilerInfo3::SetFunctionIDMapper2</span></span>](icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="e2ee7-125">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="e2ee7-125">FunctionEnter3</span></span>](functionenter3-function.md)
- [<span data-ttu-id="e2ee7-126">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="e2ee7-126">FunctionLeave3</span></span>](functionleave3-function.md)
- [<span data-ttu-id="e2ee7-127">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="e2ee7-127">FunctionTailcall3</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="e2ee7-128">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="e2ee7-128">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="e2ee7-129">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="e2ee7-129">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="e2ee7-130">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="e2ee7-130">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="e2ee7-131">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="e2ee7-131">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
