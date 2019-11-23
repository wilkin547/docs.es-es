---
title: ICorProfilerCallback::ObjectsAllocatedByClass (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ObjectsAllocatedByClass
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ObjectsAllocatedByClass
helpviewer_keywords:
- ObjectsAllocatedByClass method [.NET Framework profiling]
- ICorProfilerCallback::ObjectsAllocatedByClass method [.NET Framework profiling]
ms.assetid: 91d688f3-a80e-419d-9755-ff94bc04188a
topic_type:
- apiref
ms.openlocfilehash: 9ba021ec223d00e57081567b76f70f59768e6b9a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445856"
---
# <a name="icorprofilercallbackobjectsallocatedbyclass-method"></a><span data-ttu-id="f9e2b-102">ICorProfilerCallback::ObjectsAllocatedByClass (Método)</span><span class="sxs-lookup"><span data-stu-id="f9e2b-102">ICorProfilerCallback::ObjectsAllocatedByClass Method</span></span>
<span data-ttu-id="f9e2b-103">Notifies the profiler about the number of instances of each specified class that have been created since the most recent garbage collection.</span><span class="sxs-lookup"><span data-stu-id="f9e2b-103">Notifies the profiler about the number of instances of each specified class that have been created since the most recent garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9e2b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f9e2b-104">Syntax</span></span>  
  
```cpp  
HRESULT ObjectsAllocatedByClass(  
    [in] ULONG   cClassCount,  
    [in, size_is(cClassCount)] ClassID classIds[] ,  
    [in, size_is(cClassCount)] ULONG   cObjects[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="f9e2b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f9e2b-105">Parameters</span></span>  
 `cClassCount`  
 <span data-ttu-id="f9e2b-106">[in] The size of the `classIds` and `cObjects` arrays.</span><span class="sxs-lookup"><span data-stu-id="f9e2b-106">[in] The size of the `classIds` and `cObjects` arrays.</span></span>  
  
 `classIds`  
 <span data-ttu-id="f9e2b-107">[in] An array of class IDs, where each ID specifies a class with one or more instances.</span><span class="sxs-lookup"><span data-stu-id="f9e2b-107">[in] An array of class IDs, where each ID specifies a class with one or more instances.</span></span>  
  
 `cObjects`  
 <span data-ttu-id="f9e2b-108">[in] An array of integers, where each integer specifies the number of instances for the corresponding class in the `classIds` array.</span><span class="sxs-lookup"><span data-stu-id="f9e2b-108">[in] An array of integers, where each integer specifies the number of instances for the corresponding class in the `classIds` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f9e2b-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f9e2b-109">Remarks</span></span>  
 <span data-ttu-id="f9e2b-110">The `classIds` and `cObjects` arrays are parallel arrays.</span><span class="sxs-lookup"><span data-stu-id="f9e2b-110">The `classIds` and `cObjects` arrays are parallel arrays.</span></span> <span data-ttu-id="f9e2b-111">For example, `classIds[i]` and `cObjects[i]` reference the same class.</span><span class="sxs-lookup"><span data-stu-id="f9e2b-111">For example, `classIds[i]` and `cObjects[i]` reference the same class.</span></span> <span data-ttu-id="f9e2b-112">If no instance of a class has been created since the previous garbage collection, the class is omitted.</span><span class="sxs-lookup"><span data-stu-id="f9e2b-112">If no instance of a class has been created since the previous garbage collection, the class is omitted.</span></span> <span data-ttu-id="f9e2b-113">The `ObjectsAllocatedByClass` callback will not report objects allocated in the large object heap.</span><span class="sxs-lookup"><span data-stu-id="f9e2b-113">The `ObjectsAllocatedByClass` callback will not report objects allocated in the large object heap.</span></span>  
  
 <span data-ttu-id="f9e2b-114">The numbers reported by `ObjectsAllocatedByClass` are only estimates.</span><span class="sxs-lookup"><span data-stu-id="f9e2b-114">The numbers reported by `ObjectsAllocatedByClass` are only estimates.</span></span> <span data-ttu-id="f9e2b-115">For exact counts, use [ICorProfilerCallback::ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md).</span><span class="sxs-lookup"><span data-stu-id="f9e2b-115">For exact counts, use [ICorProfilerCallback::ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md).</span></span>  
  
 <span data-ttu-id="f9e2b-116">The `classIds` array may contain one or more null entries if the corresponding `cObjects` array has types that are unloading.</span><span class="sxs-lookup"><span data-stu-id="f9e2b-116">The `classIds` array may contain one or more null entries if the corresponding `cObjects` array has types that are unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9e2b-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f9e2b-117">Requirements</span></span>  
 <span data-ttu-id="f9e2b-118">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9e2b-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9e2b-119">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f9e2b-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f9e2b-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f9e2b-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f9e2b-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9e2b-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9e2b-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="f9e2b-122">See also</span></span>

- [<span data-ttu-id="f9e2b-123">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f9e2b-123">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
