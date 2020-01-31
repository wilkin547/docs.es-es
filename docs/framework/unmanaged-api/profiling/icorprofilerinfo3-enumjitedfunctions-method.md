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
ms.openlocfilehash: a22a0de9a20f32ce1c9818bbcf29222a4b331420
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862430"
---
# <a name="icorprofilerinfo3enumjitedfunctions-method"></a><span data-ttu-id="3f3a7-102">ICorProfilerInfo3::EnumJITedFunctions (Método)</span><span class="sxs-lookup"><span data-stu-id="3f3a7-102">ICorProfilerInfo3::EnumJITedFunctions Method</span></span>
<span data-ttu-id="3f3a7-103">Devuelve un enumerador para todas las funciones que se compilaron previamente con JIT.</span><span class="sxs-lookup"><span data-stu-id="3f3a7-103">Returns an enumerator for all functions that were previously JIT-compiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f3a7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3f3a7-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumJITedFunctions([out] ICorProfilerFunctionEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f3a7-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="3f3a7-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="3f3a7-106">enuncia Puntero al enumerador [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="3f3a7-106">[out] A pointer to the [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) enumerator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3f3a7-107">Notas</span><span class="sxs-lookup"><span data-stu-id="3f3a7-107">Remarks</span></span>  
 <span data-ttu-id="3f3a7-108">Este método se puede superponer con `JITCompilation` devoluciones de llamada como el método [ICorProfilerCallback:: JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) .</span><span class="sxs-lookup"><span data-stu-id="3f3a7-108">This method may overlap with `JITCompilation` callbacks such as the [ICorProfilerCallback::JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) method.</span></span> <span data-ttu-id="3f3a7-109">El enumerador devuelto por este método no incluye las funciones que se cargan desde imágenes nativas generadas con Ngen. exe.</span><span class="sxs-lookup"><span data-stu-id="3f3a7-109">The enumerator returned by this method does not include functions that are loaded from native images generated with Ngen.exe.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3f3a7-110">La enumeración devuelta solo incluye "0" para el valor del campo `COR_PRF_FUNCTION::reJitId`.</span><span class="sxs-lookup"><span data-stu-id="3f3a7-110">The returned enumeration includes only "0" for the value of the `COR_PRF_FUNCTION::reJitId` field.</span></span>  <span data-ttu-id="3f3a7-111">Si necesita valores de `COR_PRF_FUNCTION::reJitId` válidos, use el método [ICorProfilerInfo4:: enumjitedfunctions2 (](icorprofilerinfo4-enumjitedfunctions2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="3f3a7-111">If you require valid `COR_PRF_FUNCTION::reJitId` values, use the [ICorProfilerInfo4::EnumJITedFunctions2](icorprofilerinfo4-enumjitedfunctions2-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f3a7-112">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="3f3a7-112">Requirements</span></span>  
 <span data-ttu-id="3f3a7-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f3a7-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f3a7-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3f3a7-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3f3a7-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f3a7-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f3a7-116">**.NET Framework versiones:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f3a7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f3a7-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="3f3a7-117">See also</span></span>

- [<span data-ttu-id="3f3a7-118">ICorProfilerInfo3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3f3a7-118">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="3f3a7-119">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="3f3a7-119">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="3f3a7-120">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="3f3a7-120">Profiling</span></span>](index.md)
