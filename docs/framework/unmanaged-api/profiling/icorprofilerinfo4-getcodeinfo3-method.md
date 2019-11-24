---
title: ICorProfilerInfo4::GetCodeInfo3 (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetCodeInfo3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetCodeInfo3
helpviewer_keywords:
- GetCodeInfo3 method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetCodeInfo3 method [.NET Framework profiling]
ms.assetid: bb8c105e-4d9a-4684-8c05-ed6909cc1b8c
topic_type:
- apiref
ms.openlocfilehash: d29145a9c224a064cf9210c56c8617d99f7690ba
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443067"
---
# <a name="icorprofilerinfo4getcodeinfo3-method"></a><span data-ttu-id="ad4b3-102">ICorProfilerInfo4::GetCodeInfo3 (Método)</span><span class="sxs-lookup"><span data-stu-id="ad4b3-102">ICorProfilerInfo4::GetCodeInfo3 Method</span></span>
<span data-ttu-id="ad4b3-103">Obtiene las extensiones de código nativo asociadas con la versión recompilada con JIT de la función especificada.</span><span class="sxs-lookup"><span data-stu-id="ad4b3-103">Gets the extents of native code associated with the JIT-recompiled version of the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad4b3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ad4b3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCodeInfo3(  
    [in]  FunctionID functionID,  
    [in]  ReJITID reJitId,  
    [in]  ULONG32 cCodeInfos,  
    [out] ULONG32 *pcCodeInfos,  
    [out, size_is(cCodeInfos), length_is(*pcCodeInfos)]  
    COR_PRF_CODE_INFO codeInfos[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad4b3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ad4b3-105">Parameters</span></span>  
 `functionID`  
 <span data-ttu-id="ad4b3-106">[in] Identificador de función con la que está asociado el código nativo.</span><span class="sxs-lookup"><span data-stu-id="ad4b3-106">[in] The ID of the function with which the native code is associated.</span></span>  
  
 `reJitId`  
 <span data-ttu-id="ad4b3-107">[in] Identidad de la función recompilada con JIT.</span><span class="sxs-lookup"><span data-stu-id="ad4b3-107">[in] The identity of the JIT-recompiled function.</span></span>  
  
 `cCodeInfos`  
 <span data-ttu-id="ad4b3-108">[in] Tamaño de la matriz `codeInfos`.</span><span class="sxs-lookup"><span data-stu-id="ad4b3-108">[in] The size of the `codeInfos` array.</span></span>  
  
 `pcCodeInfos`  
 <span data-ttu-id="ad4b3-109">[out] A pointer to the total number of [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structures available.</span><span class="sxs-lookup"><span data-stu-id="ad4b3-109">[out] A pointer to the total number of [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structures available.</span></span>  
  
 `codeInfos`  
 <span data-ttu-id="ad4b3-110">[out] Búfer proporcionado por el llamador.</span><span class="sxs-lookup"><span data-stu-id="ad4b3-110">[out] A caller-provided buffer.</span></span> <span data-ttu-id="ad4b3-111">Después de que el método vuelva, contiene una matriz de estructuras `COR_PRF_CODE_INFO`, cada una de las cuales describe un bloque de código nativo.</span><span class="sxs-lookup"><span data-stu-id="ad4b3-111">After the method returns, it contains an array of `COR_PRF_CODE_INFO` structures, each of which describes a block of native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ad4b3-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ad4b3-112">Remarks</span></span>  
 <span data-ttu-id="ad4b3-113">The `GetCodeInfo3` method is similar to [GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md), except that it will get the JIT-recompiled ID of the function that contains the specified IP address.</span><span class="sxs-lookup"><span data-stu-id="ad4b3-113">The `GetCodeInfo3` method is similar to [GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md), except that it will get the JIT-recompiled ID of the function that contains the specified IP address.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ad4b3-114">`GetCodeInfo3` can trigger a garbage collection, whereas [GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md) will not.</span><span class="sxs-lookup"><span data-stu-id="ad4b3-114">`GetCodeInfo3` can trigger a garbage collection, whereas [GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md) will not.</span></span> <span data-ttu-id="ad4b3-115">For more information, see the [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md) HRESULT.</span><span class="sxs-lookup"><span data-stu-id="ad4b3-115">For more information, see the [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md) HRESULT.</span></span>  
  
 <span data-ttu-id="ad4b3-116">Las extensiones se clasifican en orden creciente de desplazamiento de Common Intermediate Language (CIL).</span><span class="sxs-lookup"><span data-stu-id="ad4b3-116">The extents are sorted in order of increasing Common Intermediate Language (CIL) offset.</span></span>  
  
 <span data-ttu-id="ad4b3-117">After `GetCodeInfo3` returns, you must verify that the `codeInfos` buffer was large enough to contain all the [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structures.</span><span class="sxs-lookup"><span data-stu-id="ad4b3-117">After `GetCodeInfo3` returns, you must verify that the `codeInfos` buffer was large enough to contain all the [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structures.</span></span> <span data-ttu-id="ad4b3-118">Para ello, compare el valor de `cCodeInfos` con el valor del parámetro `cchName`.</span><span class="sxs-lookup"><span data-stu-id="ad4b3-118">To do this, compare the value of `cCodeInfos` with the value of the `cchName` parameter.</span></span> <span data-ttu-id="ad4b3-119">If `cCodeInfos` divided by the size of a [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structure is smaller than `pcCodeInfos`, allocate a larger `codeInfos` buffer, update `cCodeInfos` with the new, larger size, and call `GetCodeInfo3` again.</span><span class="sxs-lookup"><span data-stu-id="ad4b3-119">If `cCodeInfos` divided by the size of a [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structure is smaller than `pcCodeInfos`, allocate a larger `codeInfos` buffer, update `cCodeInfos` with the new, larger size, and call `GetCodeInfo3` again.</span></span>  
  
 <span data-ttu-id="ad4b3-120">También tiene la opción de llamar primero a `GetCodeInfo3` con un búfer `codeInfos` de longitud de cero para obtener el tamaño de búfer correcto.</span><span class="sxs-lookup"><span data-stu-id="ad4b3-120">Alternatively, you can first call `GetCodeInfo3` with a zero-length `codeInfos` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="ad4b3-121">You can then set the `codeInfos` buffer size to the value returned in `pcCodeInfos`, multiplied by the size of a [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structure, and call `GetCodeInfo3` again.</span><span class="sxs-lookup"><span data-stu-id="ad4b3-121">You can then set the `codeInfos` buffer size to the value returned in `pcCodeInfos`, multiplied by the size of a [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structure, and call `GetCodeInfo3` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad4b3-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ad4b3-122">Requirements</span></span>  
 <span data-ttu-id="ad4b3-123">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad4b3-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad4b3-124">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ad4b3-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ad4b3-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ad4b3-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ad4b3-126">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad4b3-126">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad4b3-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="ad4b3-127">See also</span></span>

- [<span data-ttu-id="ad4b3-128">GetCodeInfo2 (método)</span><span class="sxs-lookup"><span data-stu-id="ad4b3-128">GetCodeInfo2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md)
- [<span data-ttu-id="ad4b3-129">ICorProfilerInfo4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad4b3-129">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [<span data-ttu-id="ad4b3-130">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="ad4b3-130">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="ad4b3-131">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="ad4b3-131">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
