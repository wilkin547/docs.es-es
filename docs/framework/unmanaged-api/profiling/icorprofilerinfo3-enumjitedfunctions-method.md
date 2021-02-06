---
description: 'Más información sobre: ICorProfilerInfo3:: EnumJITedFunctions ((método)'
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
ms.openlocfilehash: 2f5f8358e7f01c20fc6edee60869bad01b0936c1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99646938"
---
# <a name="icorprofilerinfo3enumjitedfunctions-method"></a><span data-ttu-id="40868-103">ICorProfilerInfo3::EnumJITedFunctions (Método)</span><span class="sxs-lookup"><span data-stu-id="40868-103">ICorProfilerInfo3::EnumJITedFunctions Method</span></span>

<span data-ttu-id="40868-104">Devuelve un enumerador para todas las funciones que se compilaron previamente con JIT.</span><span class="sxs-lookup"><span data-stu-id="40868-104">Returns an enumerator for all functions that were previously JIT-compiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40868-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="40868-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumJITedFunctions([out] ICorProfilerFunctionEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="40868-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="40868-106">Parameters</span></span>  

 `ppEnum`  
 <span data-ttu-id="40868-107">enuncia Puntero al enumerador [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="40868-107">[out] A pointer to the [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) enumerator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="40868-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="40868-108">Remarks</span></span>  

 <span data-ttu-id="40868-109">Este método se puede superponer con `JITCompilation` devoluciones de llamada como el método [ICorProfilerCallback:: JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) .</span><span class="sxs-lookup"><span data-stu-id="40868-109">This method may overlap with `JITCompilation` callbacks such as the [ICorProfilerCallback::JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) method.</span></span> <span data-ttu-id="40868-110">El enumerador devuelto por este método no incluye las funciones que se cargan desde imágenes nativas generadas con Ngen.exe.</span><span class="sxs-lookup"><span data-stu-id="40868-110">The enumerator returned by this method does not include functions that are loaded from native images generated with Ngen.exe.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="40868-111">La enumeración devuelta solo incluye "0" para el valor del `COR_PRF_FUNCTION::reJitId` campo.</span><span class="sxs-lookup"><span data-stu-id="40868-111">The returned enumeration includes only "0" for the value of the `COR_PRF_FUNCTION::reJitId` field.</span></span>  <span data-ttu-id="40868-112">Si necesita valores válidos `COR_PRF_FUNCTION::reJitId` , use el método [ICorProfilerInfo4:: enumjitedfunctions2 (](icorprofilerinfo4-enumjitedfunctions2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="40868-112">If you require valid `COR_PRF_FUNCTION::reJitId` values, use the [ICorProfilerInfo4::EnumJITedFunctions2](icorprofilerinfo4-enumjitedfunctions2-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40868-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="40868-113">Requirements</span></span>  

 <span data-ttu-id="40868-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40868-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40868-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="40868-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="40868-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="40868-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="40868-117">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40868-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40868-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="40868-118">See also</span></span>

- [<span data-ttu-id="40868-119">ICorProfilerInfo3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="40868-119">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="40868-120">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="40868-120">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="40868-121">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="40868-121">Profiling</span></span>](index.md)
