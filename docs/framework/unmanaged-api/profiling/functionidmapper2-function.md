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
ms.openlocfilehash: af0ef412395394bb660ae6ed64fb154caef41655
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866923"
---
# <a name="functionidmapper2-function"></a><span data-ttu-id="13df1-102">FunctionIDMapper2 (Función)</span><span class="sxs-lookup"><span data-stu-id="13df1-102">FunctionIDMapper2 Function</span></span>
<span data-ttu-id="13df1-103">Notifica al generador de perfiles que el identificador especificado de una función puede reasignarse a un identificador alternativo que se va a usar en las devoluciones de llamada [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md), [FunctionTailcall3](functiontailcall3-function.md)o[FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md)y [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) de esa función.</span><span class="sxs-lookup"><span data-stu-id="13df1-103">Notifies the profiler that the given identifier of a function may be remapped to an alternative ID to be used in the [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md), and [FunctionTailcall3](functiontailcall3-function.md), or[FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) callbacks for that function.</span></span> <span data-ttu-id="13df1-104">Además, `FunctionIDMapper2` permite al generador de perfiles indicar si desea recibir devoluciones de llamada de esa función.</span><span class="sxs-lookup"><span data-stu-id="13df1-104">`FunctionIDMapper2` also enables the profiler to indicate whether it wants to receive callbacks for that function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13df1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="13df1-105">Syntax</span></span>  
  
```cpp  
UINT_PTR __stdcall FunctionIDMapper2 (  
    [in]  FunctionID  funcId,  
    [in]  void * clientData,  
    [out] BOOL       *pbHookFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="13df1-106">Parameters</span><span class="sxs-lookup"><span data-stu-id="13df1-106">Parameters</span></span>

- `funcId`

  <span data-ttu-id="13df1-107">\[en] el identificador de función que se va a reasignar.</span><span class="sxs-lookup"><span data-stu-id="13df1-107">\[in] The function identifier to be remapped.</span></span>

- `clientData`

  <span data-ttu-id="13df1-108">\[in] un puntero a datos que se usa para eliminar la ambigüedad entre los tiempos de ejecución.</span><span class="sxs-lookup"><span data-stu-id="13df1-108">\[in] A pointer to data that is used to disambiguate among runtimes.</span></span>

- `pbHookFunction`

  <span data-ttu-id="13df1-109">\[out] puntero a un valor que el generador de perfiles establece en `true` si desea recibir `FunctionEnter3`, `FunctionLeave3`y `FunctionTailcall3`, o `FunctionEnter3WithInfo`, `FunctionLeave3WithInfo`y `FunctionTailcall3WithInfo` devoluciones de llamada; de lo contrario, establece este valor en `false`.</span><span class="sxs-lookup"><span data-stu-id="13df1-109">\[out] A pointer to a value that the profiler sets to `true` if it wants to receive `FunctionEnter3`, `FunctionLeave3`, and `FunctionTailcall3`, or `FunctionEnter3WithInfo`, `FunctionLeave3WithInfo`, and `FunctionTailcall3WithInfo` callbacks; otherwise, it sets this value to `false`.</span></span>

## <a name="return-value"></a><span data-ttu-id="13df1-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="13df1-110">Return Value</span></span>  
 <span data-ttu-id="13df1-111">El generador de perfiles devuelve un valor que el motor de ejecución utiliza como identificador de función alternativo.</span><span class="sxs-lookup"><span data-stu-id="13df1-111">The profiler returns a value that the execution engine uses as an alternative function identifier.</span></span> <span data-ttu-id="13df1-112">El valor devuelto no puede ser null a menos que se devuelva `false` en `pbHookFunction`.</span><span class="sxs-lookup"><span data-stu-id="13df1-112">The return value cannot be null unless `false` is returned in `pbHookFunction`.</span></span> <span data-ttu-id="13df1-113">De lo contrario, la devolución de un valor nulo genera resultados imprevisibles, que posiblemente incluyan la detención del proceso.</span><span class="sxs-lookup"><span data-stu-id="13df1-113">Otherwise, a null return value produces unpredictable results, including possibly halting the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="13df1-114">Notas</span><span class="sxs-lookup"><span data-stu-id="13df1-114">Remarks</span></span>  
 <span data-ttu-id="13df1-115">Este método extiende la función [FunctionIDMapper](functionidmapper-function.md) con un parámetro adicional que se usa para pasar los datos del cliente.</span><span class="sxs-lookup"><span data-stu-id="13df1-115">This method extends the [FunctionIDMapper](functionidmapper-function.md) function with an additional parameter that is used to pass client data.</span></span> <span data-ttu-id="13df1-116">Los datos del cliente se usan para eliminar la ambigüedad entre los runtime.</span><span class="sxs-lookup"><span data-stu-id="13df1-116">The client data is used to disambiguate among runtimes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13df1-117">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="13df1-117">Requirements</span></span>  
 <span data-ttu-id="13df1-118">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13df1-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13df1-119">**Encabezado:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="13df1-119">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="13df1-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="13df1-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="13df1-121">**.NET Framework versiones:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13df1-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13df1-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="13df1-122">See also</span></span>

- [<span data-ttu-id="13df1-123">ICorProfilerInfo::SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="13df1-123">ICorProfilerInfo::SetFunctionIDMapper</span></span>](icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="13df1-124">ICorProfilerInfo3::SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="13df1-124">ICorProfilerInfo3::SetFunctionIDMapper2</span></span>](icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="13df1-125">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="13df1-125">FunctionEnter3</span></span>](functionenter3-function.md)
- [<span data-ttu-id="13df1-126">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="13df1-126">FunctionLeave3</span></span>](functionleave3-function.md)
- [<span data-ttu-id="13df1-127">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="13df1-127">FunctionTailcall3</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="13df1-128">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="13df1-128">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="13df1-129">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="13df1-129">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="13df1-130">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="13df1-130">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="13df1-131">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="13df1-131">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
