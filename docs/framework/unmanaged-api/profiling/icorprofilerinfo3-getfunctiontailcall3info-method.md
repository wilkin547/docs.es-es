---
description: 'Más información sobre: ICorProfilerInfo3:: Getfunctiontailcall3info ((método)'
title: ICorProfilerInfo3::GetFunctionTailcall3Info (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetFunctionTailcall3Info Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetFunctionTailcall3Info
helpviewer_keywords:
- ICorProfilerInfo3::GetFunctionTailcall3Info method [.NET Framework profiling]
- GetFunctionTailcall3Info method [.NET Framework profiling]
ms.assetid: afdb5ac9-5bf5-4b91-b7cb-f81db23d7da3
topic_type:
- apiref
ms.openlocfilehash: a8976a11cf7a2c556afa62a559e3a294d81b9a1d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99646808"
---
# <a name="icorprofilerinfo3getfunctiontailcall3info-method"></a><span data-ttu-id="a7ac1-103">ICorProfilerInfo3::GetFunctionTailcall3Info (Método)</span><span class="sxs-lookup"><span data-stu-id="a7ac1-103">ICorProfilerInfo3::GetFunctionTailcall3Info Method</span></span>

<span data-ttu-id="a7ac1-104">Proporciona el marco de pila de la función que la función [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) está informando al generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="a7ac1-104">Provides the stack frame of the function that is being reported to the profiler by the [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) function.</span></span> <span data-ttu-id="a7ac1-105">Solo se puede llamar a este método durante la devolución de llamada `FunctionTailcall3WithInfo`.</span><span class="sxs-lookup"><span data-stu-id="a7ac1-105">This method can be called only during the `FunctionTailcall3WithInfo` callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7ac1-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a7ac1-106">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionTailcall3Info(
            [in]  FunctionID functionId,
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7ac1-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a7ac1-107">Parameters</span></span>  

 `functionId`  
 <span data-ttu-id="a7ac1-108">de `FunctionID` De la función que devuelve.</span><span class="sxs-lookup"><span data-stu-id="a7ac1-108">[in] The `FunctionID` of the function that is returning.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="a7ac1-109">[in] Controlador opaco que representa información sobre un marco de pila determinado.</span><span class="sxs-lookup"><span data-stu-id="a7ac1-109">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="a7ac1-110">El generador de perfiles debe proporcionar la misma que proporcionó el `eltInfo` generador de perfiles mediante la `FunctionTailcall3WithInfo` función.</span><span class="sxs-lookup"><span data-stu-id="a7ac1-110">The profiler should provide the same `eltInfo` that was given to the profiler by the `FunctionTailcall3WithInfo` function.</span></span>  
  
 `pFrameInfo`  
 <span data-ttu-id="a7ac1-111">[out] Controlador opaco que representa información genérica sobre un marco de pila determinado.</span><span class="sxs-lookup"><span data-stu-id="a7ac1-111">[out] An opaque handle that represents generics information about a given stack frame.</span></span> <span data-ttu-id="a7ac1-112">Este identificador es válido solo durante la devolución de llamada `FunctionTailcall3WithInfo` en la que el generador de perfiles llamó al método `GetFunctionTailcall3Info`.</span><span class="sxs-lookup"><span data-stu-id="a7ac1-112">This handle is valid only during the `FunctionTailcall3WithInfo` callback in which the profiler called the `GetFunctionTailcall3Info` method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7ac1-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a7ac1-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7ac1-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a7ac1-114">Requirements</span></span>  

 <span data-ttu-id="a7ac1-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7ac1-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7ac1-116">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a7ac1-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a7ac1-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a7ac1-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a7ac1-118">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7ac1-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7ac1-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="a7ac1-119">See also</span></span>

- [<span data-ttu-id="a7ac1-120">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="a7ac1-120">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="a7ac1-121">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="a7ac1-121">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="a7ac1-122">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="a7ac1-122">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="a7ac1-123">ICorProfilerInfo3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a7ac1-123">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="a7ac1-124">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="a7ac1-124">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="a7ac1-125">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="a7ac1-125">Profiling</span></span>](index.md)
