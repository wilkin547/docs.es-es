---
title: ICorProfilerInfo3::GetFunctionLeave3Info (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetFunctionLeave3Info Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetFunctionLeave3Info
helpviewer_keywords:
- GetFunctionLeave3Info method [.NET Framework profiling]
- ICorProfilerInfo3::GetFunctionLeave3Info method [.NET Framework profiling]
ms.assetid: df7083d2-fd43-44c7-9ce5-912c25cef0ff
topic_type:
- apiref
ms.openlocfilehash: bab52d9179d7454cab4a47e1a2bfe80a49b00c2a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502839"
---
# <a name="icorprofilerinfo3getfunctionleave3info-method"></a><span data-ttu-id="a95e2-102">ICorProfilerInfo3::GetFunctionLeave3Info (Método)</span><span class="sxs-lookup"><span data-stu-id="a95e2-102">ICorProfilerInfo3::GetFunctionLeave3Info Method</span></span>
<span data-ttu-id="a95e2-103">Proporciona el marco de pila y el valor devuelto de la función que se está informando al generador de perfiles mediante la función de [función FunctionLeave3WithInfo](functionleave3withinfo-function.md) .</span><span class="sxs-lookup"><span data-stu-id="a95e2-103">Provides the stack frame and return value of the function that is being reported to the profiler by the [FunctionLeave3WithInfo function](functionleave3withinfo-function.md) function.</span></span> <span data-ttu-id="a95e2-104">Solo se puede llamar a este método durante la devolución de llamada `FunctionLeave3WithInfo`.</span><span class="sxs-lookup"><span data-stu-id="a95e2-104">This method can be called only during the `FunctionLeave3WithInfo` callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a95e2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a95e2-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionLeave3Info(  
            [in]  FunctionID functionId,  
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo,  
            [out] COR_PRF_FUNCTION_ARGUMENT_RANGE *pRetvalRange);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a95e2-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a95e2-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="a95e2-107">de `FunctionID`De la función que devuelve.</span><span class="sxs-lookup"><span data-stu-id="a95e2-107">[in] The `FunctionID` of the function that is returning.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="a95e2-108">[in] Controlador opaco que representa información sobre un marco de pila determinado.</span><span class="sxs-lookup"><span data-stu-id="a95e2-108">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="a95e2-109">El generador de perfiles debe proporcionar el mismo que proporcionó el `eltInfo` generador de perfiles mediante la función [FunctionLeave3WithInfo](functionleave3withinfo-function.md) .</span><span class="sxs-lookup"><span data-stu-id="a95e2-109">The profiler should provide the same `eltInfo` that was given to the profiler by the [FunctionLeave3WithInfo](functionleave3withinfo-function.md) function.</span></span>  
  
 `pFrameInfo`  
 <span data-ttu-id="a95e2-110">[out] Controlador opaco que representa información genérica sobre un marco de pila determinado.</span><span class="sxs-lookup"><span data-stu-id="a95e2-110">[out] An opaque handle that represents generics information about a given stack frame.</span></span> <span data-ttu-id="a95e2-111">Este identificador es válido solo durante la devolución de llamada `FunctionLeave3WithInfo` en la que el generador de perfiles llamó al método `GetFunctionLeave3Info`.</span><span class="sxs-lookup"><span data-stu-id="a95e2-111">This handle is valid only during the `FunctionLeave3WithInfo` callback in which the profiler called the `GetFunctionLeave3Info` method.</span></span>  
  
 `pRetvalRange`  
 <span data-ttu-id="a95e2-112">enuncia Puntero a una estructura de [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) que contiene el valor devuelto de la función.</span><span class="sxs-lookup"><span data-stu-id="a95e2-112">[out] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) structure that contains the value that is returned from the function.</span></span> <span data-ttu-id="a95e2-113">Para tener acceso a la información del valor devuelto, `COR_PRF_ENABLE_FUNCTION_RETVAL` se debe establecer la marca.</span><span class="sxs-lookup"><span data-stu-id="a95e2-113">To access return value information, the `COR_PRF_ENABLE_FUNCTION_RETVAL` flag must be set.</span></span> <span data-ttu-id="a95e2-114">El generador de perfiles puede utilizar el [método ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) para establecer las marcas de evento.</span><span class="sxs-lookup"><span data-stu-id="a95e2-114">The profiler can use the [ICorProfilerInfo::SetEventMask method](icorprofilerinfo-seteventmask-method.md) to set the event flags.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a95e2-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a95e2-115">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a95e2-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a95e2-116">Requirements</span></span>  
 <span data-ttu-id="a95e2-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a95e2-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a95e2-118">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a95e2-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a95e2-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a95e2-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a95e2-120">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a95e2-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a95e2-121">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="a95e2-121">See also</span></span>

- [<span data-ttu-id="a95e2-122">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="a95e2-122">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="a95e2-123">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="a95e2-123">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="a95e2-124">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="a95e2-124">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="a95e2-125">ICorProfilerInfo3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a95e2-125">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="a95e2-126">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="a95e2-126">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="a95e2-127">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="a95e2-127">Profiling</span></span>](index.md)
