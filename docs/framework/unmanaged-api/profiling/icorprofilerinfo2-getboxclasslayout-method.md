---
title: ICorProfilerInfo2::GetBoxClassLayout (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetBoxClassLayout
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetBoxClassLayout
helpviewer_keywords:
- GetBoxClassLayout method [.NET Framework profiling]
- ICorProfilerInfo2::GetBoxClassLayout method [.NET Framework profiling]
ms.assetid: 624672b5-1189-488a-85d2-3e12b49617c1
topic_type:
- apiref
ms.openlocfilehash: 5f98c35f77fdb200be2e96364c9ac06c386faa62
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436023"
---
# <a name="icorprofilerinfo2getboxclasslayout-method"></a><span data-ttu-id="1ad5a-102">ICorProfilerInfo2::GetBoxClassLayout (Método)</span><span class="sxs-lookup"><span data-stu-id="1ad5a-102">ICorProfilerInfo2::GetBoxClassLayout Method</span></span>
<span data-ttu-id="1ad5a-103">Gets information about where the specified value type is located when it is boxed.</span><span class="sxs-lookup"><span data-stu-id="1ad5a-103">Gets information about where the specified value type is located when it is boxed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ad5a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1ad5a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBoxClassLayout(  
    [in] ClassID classId,  
    [out] ULONG32 *pBufferOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1ad5a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1ad5a-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="1ad5a-106">[in] The ID of the class that describes the value type that is boxed.</span><span class="sxs-lookup"><span data-stu-id="1ad5a-106">[in] The ID of the class that describes the value type that is boxed.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="1ad5a-107">[out] An integer that is the offset, relative to the boxed object ID pointer, of the value type.</span><span class="sxs-lookup"><span data-stu-id="1ad5a-107">[out] An integer that is the offset, relative to the boxed object ID pointer, of the value type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1ad5a-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1ad5a-108">Remarks</span></span>  
 <span data-ttu-id="1ad5a-109">The `pBufferOffset` value is the location of the value type within a box.</span><span class="sxs-lookup"><span data-stu-id="1ad5a-109">The `pBufferOffset` value is the location of the value type within a box.</span></span> <span data-ttu-id="1ad5a-110">After `pBufferOffset` is applied to a boxed object, the value type's class layout can be used to interpret the object's value.</span><span class="sxs-lookup"><span data-stu-id="1ad5a-110">After `pBufferOffset` is applied to a boxed object, the value type's class layout can be used to interpret the object's value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ad5a-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1ad5a-111">Requirements</span></span>  
 <span data-ttu-id="1ad5a-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1ad5a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ad5a-113">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1ad5a-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1ad5a-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1ad5a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1ad5a-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ad5a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ad5a-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="1ad5a-116">See also</span></span>

- [<span data-ttu-id="1ad5a-117">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1ad5a-117">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="1ad5a-118">ICorProfilerInfo2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1ad5a-118">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
