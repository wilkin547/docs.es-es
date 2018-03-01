---
title: "ICorProfilerInfo3::EnumJITedFunctions (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerInfo3.EnumJITedFunctions Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::EnumJITedFunctions
helpviewer_keywords:
- ICorProfilerInfo3::EnumJITedFunctions method [.NET Framework profiling]
- EnumJITedFunctions method [.NET Framework profiling]
ms.assetid: e2847a36-f460-45e2-9b6c-b33b008f40d9
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 11a6b34be4f9bf046749941ac12895bf7040e331
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo3enumjitedfunctions-method"></a><span data-ttu-id="bef20-102">ICorProfilerInfo3::EnumJITedFunctions (Método)</span><span class="sxs-lookup"><span data-stu-id="bef20-102">ICorProfilerInfo3::EnumJITedFunctions Method</span></span>
<span data-ttu-id="bef20-103">Devuelve un enumerador para todas las funciones que estaban previamente compiladas con JIT.</span><span class="sxs-lookup"><span data-stu-id="bef20-103">Returns an enumerator for all functions that were previously JIT-compiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bef20-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bef20-104">Syntax</span></span>  
  
```  
HRESULT EnumJITedFunctions([out] ICorProfilerFunctionEnum** ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bef20-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bef20-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="bef20-106">[out] Un puntero a la [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) enumerador.</span><span class="sxs-lookup"><span data-stu-id="bef20-106">[out] A pointer to the [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) enumerator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bef20-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bef20-107">Remarks</span></span>  
 <span data-ttu-id="bef20-108">Este método se puede superponer con `JITCompilation` las devoluciones de llamada, como el [ICorProfilerCallback:: JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="bef20-108">This method may overlap with `JITCompilation` callbacks such as the [ICorProfilerCallback::JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) method.</span></span> <span data-ttu-id="bef20-109">El enumerador devuelto por este método no incluye funciones que se cargan desde imágenes nativas generadas con Ngen.exe.</span><span class="sxs-lookup"><span data-stu-id="bef20-109">The enumerator returned by this method does not include functions that are loaded from native images generated with Ngen.exe.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bef20-110">La enumeración devuelta incluye solo "0" para el valor de la `COR_PRF_FUNCTION::reJitId` campo.</span><span class="sxs-lookup"><span data-stu-id="bef20-110">The returned enumeration includes only "0" for the value of the `COR_PRF_FUNCTION::reJitId` field.</span></span>  <span data-ttu-id="bef20-111">Si necesitas válido `COR_PRF_FUNCTION::reJitId` valores, utilice la [icorprofilerinfo4:: Enumjitedfunctions2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="bef20-111">If you require valid `COR_PRF_FUNCTION::reJitId` values, use the [ICorProfilerInfo4::EnumJITedFunctions2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bef20-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bef20-112">Requirements</span></span>  
 <span data-ttu-id="bef20-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bef20-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bef20-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bef20-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bef20-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bef20-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bef20-116">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bef20-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bef20-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="bef20-117">See Also</span></span>  
 [<span data-ttu-id="bef20-118">ICorProfilerInfo3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bef20-118">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="bef20-119">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="bef20-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="bef20-120">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="bef20-120">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
