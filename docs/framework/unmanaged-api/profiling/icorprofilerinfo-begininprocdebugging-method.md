---
title: ICorProfilerInfo::BeginInprocDebugging (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.BeginInprocDebugging
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::BeginInprocDebugging
helpviewer_keywords:
- BeginInprocDebugging method [.NET Framework profiling]
- ICorProfilerInfo::BeginInprocDebugging method [.NET Framework profiling]
ms.assetid: c5c82c69-99f8-4447-aee0-42cca0a5eb5c
topic_type:
- apiref
ms.openlocfilehash: fffc028c7706c86e8384483cc92ebad90b292861
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447747"
---
# <a name="icorprofilerinfobegininprocdebugging-method"></a><span data-ttu-id="7afd2-102">ICorProfilerInfo::BeginInprocDebugging (Método)</span><span class="sxs-lookup"><span data-stu-id="7afd2-102">ICorProfilerInfo::BeginInprocDebugging Method</span></span>
<span data-ttu-id="7afd2-103">Initializes in-process debugging support.</span><span class="sxs-lookup"><span data-stu-id="7afd2-103">Initializes in-process debugging support.</span></span> <span data-ttu-id="7afd2-104">This method is obsolete in the .NET Framework version 2.0.</span><span class="sxs-lookup"><span data-stu-id="7afd2-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7afd2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7afd2-105">Syntax</span></span>  
  
```cpp  
HRESULT BeginInprocDebugging(  
    [in]  BOOL   fThisThreadOnly,  
    [out] DWORD *pdwProfilerContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7afd2-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7afd2-106">Parameters</span></span>  
 `fThisThreadOnly`  
 <span data-ttu-id="7afd2-107">[in] Set this value to `true` to initialize debugging support for only the current thread; set it to `false` to initialize debugging support for all threads.</span><span class="sxs-lookup"><span data-stu-id="7afd2-107">[in] Set this value to `true` to initialize debugging support for only the current thread; set it to `false` to initialize debugging support for all threads.</span></span>  
  
 `pdwProfilerContext`  
 <span data-ttu-id="7afd2-108">[out] The pointer to a returned value that identifies the debugging session.</span><span class="sxs-lookup"><span data-stu-id="7afd2-108">[out] The pointer to a returned value that identifies the debugging session.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7afd2-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7afd2-109">Remarks</span></span>  
 <span data-ttu-id="7afd2-110">The CLR debugging services supported limited in-process debugging in the .NET Framework versions 1.0 and 1.1.</span><span class="sxs-lookup"><span data-stu-id="7afd2-110">The CLR debugging services supported limited in-process debugging in the .NET Framework versions 1.0 and 1.1.</span></span> <span data-ttu-id="7afd2-111">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span><span class="sxs-lookup"><span data-stu-id="7afd2-111">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="7afd2-112">However, due to customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span><span class="sxs-lookup"><span data-stu-id="7afd2-112">However, due to customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7afd2-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7afd2-113">Requirements</span></span>  
 <span data-ttu-id="7afd2-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7afd2-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7afd2-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7afd2-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7afd2-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7afd2-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7afd2-117">**.NET Framework Version:** 1.0</span><span class="sxs-lookup"><span data-stu-id="7afd2-117">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7afd2-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="7afd2-118">See also</span></span>

- [<span data-ttu-id="7afd2-119">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7afd2-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
