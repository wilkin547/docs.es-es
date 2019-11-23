---
title: ICorProfilerInfo9::GetCodeInfo4
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo9.GetCodeInfo4
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: ce29703a181106353695414e8b291b14c697fc56
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444789"
---
# <a name="icorprofilerinfo9getcodeinfo4-method"></a><span data-ttu-id="0bbfe-102">ICorProfilerInfo9::GetCodeInfo4 Method</span><span class="sxs-lookup"><span data-stu-id="0bbfe-102">ICorProfilerInfo9::GetCodeInfo4 Method</span></span>

<span data-ttu-id="0bbfe-103">Given the native code start address, returns the blocks of virtual memory that store this code.</span><span class="sxs-lookup"><span data-stu-id="0bbfe-103">Given the native code start address, returns the blocks of virtual memory that store this code.</span></span>

## <a name="syntax"></a><span data-ttu-id="0bbfe-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0bbfe-104">Syntax</span></span>

```cpp
HRESULT GetCodeInfo4( [in]  UINT_PTR pNativeCodeStartAddress,
                      [in]  ULONG32 cCodeInfos,
                      [out] ULONG32* pcCodeInfos,
                      [out] COR_PRF_CODE_INFO codeInfos[]);
```

#### <a name="parameters"></a><span data-ttu-id="0bbfe-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0bbfe-105">Parameters</span></span>

`pNativeCodeStartAddress` \
<span data-ttu-id="0bbfe-106">[in] A pointer to the start of a native function.</span><span class="sxs-lookup"><span data-stu-id="0bbfe-106">[in] A pointer to the start of a native function.</span></span>

`cCodeInfos` \
<span data-ttu-id="0bbfe-107">[in] Tamaño de la matriz `codeInfos`.</span><span class="sxs-lookup"><span data-stu-id="0bbfe-107">[in] The size of the `codeInfos` array.</span></span>

`pcCodeInfos` \
<span data-ttu-id="0bbfe-108">[out] A pointer to the total number of [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structures available.</span><span class="sxs-lookup"><span data-stu-id="0bbfe-108">[out] A pointer to the total number of [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structures available.</span></span>

`codeInfos` \
<span data-ttu-id="0bbfe-109">[out] Búfer proporcionado por el llamador.</span><span class="sxs-lookup"><span data-stu-id="0bbfe-109">[out] A caller-provided buffer.</span></span> <span data-ttu-id="0bbfe-110">Después de que el método vuelva, contiene una matriz de estructuras `COR_PRF_CODE_INFO`, cada una de las cuales describe un bloque de código nativo.</span><span class="sxs-lookup"><span data-stu-id="0bbfe-110">After the method returns, it contains an array of `COR_PRF_CODE_INFO` structures, each of which describes a block of native code.</span></span>

## <a name="remarks"></a><span data-ttu-id="0bbfe-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0bbfe-111">Remarks</span></span>

<span data-ttu-id="0bbfe-112">The `GetCodeInfo4` method is similar to [GetCodeInfo3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getcodeinfo3-method.md), except that it can look up code information for different native versions of a method.</span><span class="sxs-lookup"><span data-stu-id="0bbfe-112">The `GetCodeInfo4` method is similar to [GetCodeInfo3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getcodeinfo3-method.md), except that it can look up code information for different native versions of a method.</span></span>

> [!NOTE]
> <span data-ttu-id="0bbfe-113">`GetCodeInfo4` can trigger a garbage collection.</span><span class="sxs-lookup"><span data-stu-id="0bbfe-113">`GetCodeInfo4` can trigger a garbage collection.</span></span>

<span data-ttu-id="0bbfe-114">Las extensiones se clasifican en orden creciente de desplazamiento de Common Intermediate Language (CIL).</span><span class="sxs-lookup"><span data-stu-id="0bbfe-114">The extents are sorted in order of increasing Common Intermediate Language (CIL) offset.</span></span>

<span data-ttu-id="0bbfe-115">After `GetCodeInfo4` returns, you must verify that the `codeInfos` buffer was large enough to contain all the [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structures.</span><span class="sxs-lookup"><span data-stu-id="0bbfe-115">After `GetCodeInfo4` returns, you must verify that the `codeInfos` buffer was large enough to contain all the [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structures.</span></span> <span data-ttu-id="0bbfe-116">Para ello, compare el valor de `cCodeInfos` con el valor del parámetro `cchName`.</span><span class="sxs-lookup"><span data-stu-id="0bbfe-116">To do this, compare the value of `cCodeInfos` with the value of the `cchName` parameter.</span></span> <span data-ttu-id="0bbfe-117">If `cCodeInfos` divided by the size of a [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structure is smaller than `pcCodeInfos`, allocate a larger `codeInfos` buffer, update `cCodeInfos` with the new, larger size, and call `GetCodeInfo4` again.</span><span class="sxs-lookup"><span data-stu-id="0bbfe-117">If `cCodeInfos` divided by the size of a [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structure is smaller than `pcCodeInfos`, allocate a larger `codeInfos` buffer, update `cCodeInfos` with the new, larger size, and call `GetCodeInfo4` again.</span></span>

<span data-ttu-id="0bbfe-118">También tiene la opción de llamar primero a `GetCodeInfo4` con un búfer `codeInfos` de longitud de cero para obtener el tamaño de búfer correcto.</span><span class="sxs-lookup"><span data-stu-id="0bbfe-118">Alternatively, you can first call `GetCodeInfo4` with a zero-length `codeInfos` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="0bbfe-119">You can then set the `codeInfos` buffer size to the value returned in `pcCodeInfos`, multiplied by the size of a [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structure, and call `GetCodeInfo4` again.</span><span class="sxs-lookup"><span data-stu-id="0bbfe-119">You can then set the `codeInfos` buffer size to the value returned in `pcCodeInfos`, multiplied by the size of a [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structure, and call `GetCodeInfo4` again.</span></span>

## <a name="requirements"></a><span data-ttu-id="0bbfe-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0bbfe-120">Requirements</span></span>

<span data-ttu-id="0bbfe-121">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="0bbfe-121">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>

<span data-ttu-id="0bbfe-122">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0bbfe-122">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="0bbfe-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0bbfe-123">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="0bbfe-124">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0bbfe-124">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="0bbfe-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="0bbfe-125">See also</span></span>

- [<span data-ttu-id="0bbfe-126">ICorProfilerInfo9 Interface</span><span class="sxs-lookup"><span data-stu-id="0bbfe-126">ICorProfilerInfo9 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/ICorProfilerInfo9-interface.md)
