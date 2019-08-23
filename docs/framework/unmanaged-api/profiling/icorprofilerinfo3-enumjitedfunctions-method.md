---
title: ICorProfilerInfo3::EnumJITedFunctions (Método)
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5ceb1d22500f73a29ffdfa6f16907478628358c3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69969387"
---
# <a name="icorprofilerinfo3enumjitedfunctions-method"></a><span data-ttu-id="7aea2-102">ICorProfilerInfo3::EnumJITedFunctions (Método)</span><span class="sxs-lookup"><span data-stu-id="7aea2-102">ICorProfilerInfo3::EnumJITedFunctions Method</span></span>
<span data-ttu-id="7aea2-103">Devuelve un enumerador para todas las funciones que se compilaron previamente con JIT.</span><span class="sxs-lookup"><span data-stu-id="7aea2-103">Returns an enumerator for all functions that were previously JIT-compiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7aea2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7aea2-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumJITedFunctions([out] ICorProfilerFunctionEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7aea2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7aea2-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="7aea2-106">enuncia Puntero al enumerador [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="7aea2-106">[out] A pointer to the [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) enumerator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7aea2-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7aea2-107">Remarks</span></span>  
 <span data-ttu-id="7aea2-108">Este método se puede superponer con devoluciones de `JITCompilation` llamada como el método [ICorProfilerCallback:: JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) .</span><span class="sxs-lookup"><span data-stu-id="7aea2-108">This method may overlap with `JITCompilation` callbacks such as the [ICorProfilerCallback::JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) method.</span></span> <span data-ttu-id="7aea2-109">El enumerador devuelto por este método no incluye las funciones que se cargan desde imágenes nativas generadas con Ngen. exe.</span><span class="sxs-lookup"><span data-stu-id="7aea2-109">The enumerator returned by this method does not include functions that are loaded from native images generated with Ngen.exe.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7aea2-110">La enumeración devuelta solo incluye "0" para el valor `COR_PRF_FUNCTION::reJitId` del campo.</span><span class="sxs-lookup"><span data-stu-id="7aea2-110">The returned enumeration includes only "0" for the value of the `COR_PRF_FUNCTION::reJitId` field.</span></span>  <span data-ttu-id="7aea2-111">Si necesita valores válidos `COR_PRF_FUNCTION::reJitId` , use el método [ICorProfilerInfo4:: enumjitedfunctions2 (](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="7aea2-111">If you require valid `COR_PRF_FUNCTION::reJitId` values, use the [ICorProfilerInfo4::EnumJITedFunctions2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7aea2-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7aea2-112">Requirements</span></span>  
 <span data-ttu-id="7aea2-113">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7aea2-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7aea2-114">**Encabezado**: Corprof. idl, Corprof. h</span><span class="sxs-lookup"><span data-stu-id="7aea2-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7aea2-115">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7aea2-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7aea2-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7aea2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7aea2-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="7aea2-117">See also</span></span>

- [<span data-ttu-id="7aea2-118">ICorProfilerInfo3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7aea2-118">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="7aea2-119">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="7aea2-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="7aea2-120">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="7aea2-120">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
