---
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
ms.openlocfilehash: add89fe81fccbd5e6f5ad5d27f0ab3ace489963e
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868530"
---
# <a name="icorprofilerinfo3getfunctiontailcall3info-method"></a><span data-ttu-id="31101-102">ICorProfilerInfo3::GetFunctionTailcall3Info (Método)</span><span class="sxs-lookup"><span data-stu-id="31101-102">ICorProfilerInfo3::GetFunctionTailcall3Info Method</span></span>
<span data-ttu-id="31101-103">Proporciona el marco de pila de la función que la función [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) está informando al generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="31101-103">Provides the stack frame of the function that is being reported to the profiler by the [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) function.</span></span> <span data-ttu-id="31101-104">Solo se puede llamar a este método durante la devolución de llamada `FunctionTailcall3WithInfo`.</span><span class="sxs-lookup"><span data-stu-id="31101-104">This method can be called only during the `FunctionTailcall3WithInfo` callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31101-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="31101-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionTailcall3Info(   
            [in]  FunctionID functionId,   
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="31101-106">Parameters</span><span class="sxs-lookup"><span data-stu-id="31101-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="31101-107">de `FunctionID` de la función que se devuelve.</span><span class="sxs-lookup"><span data-stu-id="31101-107">[in] The `FunctionID` of the function that is returning.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="31101-108">[in] Controlador opaco que representa información sobre un marco de pila determinado.</span><span class="sxs-lookup"><span data-stu-id="31101-108">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="31101-109">El generador de perfiles debe proporcionar el mismo `eltInfo` que se proporcionó al generador de perfiles mediante la función `FunctionTailcall3WithInfo`.</span><span class="sxs-lookup"><span data-stu-id="31101-109">The profiler should provide the same `eltInfo` that was given to the profiler by the `FunctionTailcall3WithInfo` function.</span></span>  
  
 `pFrameInfo`  
 <span data-ttu-id="31101-110">[out] Controlador opaco que representa información genérica sobre un marco de pila determinado.</span><span class="sxs-lookup"><span data-stu-id="31101-110">[out] An opaque handle that represents generics information about a given stack frame.</span></span> <span data-ttu-id="31101-111">Este identificador es válido solo durante la devolución de llamada `FunctionTailcall3WithInfo` en la que el generador de perfiles llamó al método `GetFunctionTailcall3Info`.</span><span class="sxs-lookup"><span data-stu-id="31101-111">This handle is valid only during the `FunctionTailcall3WithInfo` callback in which the profiler called the `GetFunctionTailcall3Info` method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="31101-112">Notas</span><span class="sxs-lookup"><span data-stu-id="31101-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31101-113">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="31101-113">Requirements</span></span>  
 <span data-ttu-id="31101-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31101-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31101-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="31101-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="31101-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="31101-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="31101-117">**.NET Framework versiones:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31101-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31101-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="31101-118">See also</span></span>

- [<span data-ttu-id="31101-119">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="31101-119">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="31101-120">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="31101-120">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="31101-121">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="31101-121">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="31101-122">ICorProfilerInfo3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="31101-122">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="31101-123">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="31101-123">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="31101-124">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="31101-124">Profiling</span></span>](index.md)
