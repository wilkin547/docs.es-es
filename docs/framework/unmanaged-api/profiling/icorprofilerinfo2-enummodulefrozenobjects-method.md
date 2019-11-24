---
title: ICorProfilerInfo2::EnumModuleFrozenObjects (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.EnumModuleFrozenObjects
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::EnumModuleFrozenObjects
helpviewer_keywords:
- EnumModuleFrozenObjects method [.NET Framework profiling]
- ICorProfilerInfo2::EnumModuleFrozenObjects method [.NET Framework profiling]
ms.assetid: 920b6483-7064-4d64-8613-fcc38ccf9b1e
topic_type:
- apiref
ms.openlocfilehash: 51e0c5b08b8a2ac3b8eaf38cdabd682078ba70c8
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436051"
---
# <a name="icorprofilerinfo2enummodulefrozenobjects-method"></a><span data-ttu-id="70cd2-102">ICorProfilerInfo2::EnumModuleFrozenObjects (Método)</span><span class="sxs-lookup"><span data-stu-id="70cd2-102">ICorProfilerInfo2::EnumModuleFrozenObjects Method</span></span>
<span data-ttu-id="70cd2-103">Gets an enumerator that allows iteration over the frozen objects in the specified module.This method is obsolete.</span><span class="sxs-lookup"><span data-stu-id="70cd2-103">Gets an enumerator that allows iteration over the frozen objects in the specified module.This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70cd2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="70cd2-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumModuleFrozenObjects(  
    [in] ModuleID moduleID,  
    [out] ICorProfilerObjectEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="70cd2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="70cd2-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="70cd2-106">[in] The ID of the module that contains the frozen objects to be enumerated.</span><span class="sxs-lookup"><span data-stu-id="70cd2-106">[in] The ID of the module that contains the frozen objects to be enumerated.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="70cd2-107">[out] A pointer to the address of an [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) interface, which enumerates the frozen objects.</span><span class="sxs-lookup"><span data-stu-id="70cd2-107">[out] A pointer to the address of an [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) interface, which enumerates the frozen objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70cd2-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="70cd2-108">Requirements</span></span>  
 <span data-ttu-id="70cd2-109">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="70cd2-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70cd2-110">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="70cd2-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="70cd2-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="70cd2-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="70cd2-112">**.NET Framework Versions:** 3.5, 3.0 SP1, 3.0, 2.0 SP1, 2.0</span><span class="sxs-lookup"><span data-stu-id="70cd2-112">**.NET Framework Versions:** 3.5, 3.0 SP1, 3.0, 2.0 SP1, 2.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70cd2-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="70cd2-113">See also</span></span>

- [<span data-ttu-id="70cd2-114">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="70cd2-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="70cd2-115">ICorProfilerInfo2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="70cd2-115">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
