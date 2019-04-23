---
title: Método ICorProfilerCallback9::DynamicMethodUnloaded
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback9.DynamicMethodUnloaded
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 96cdfb79c1573648173305d6ee789aa8db030ff8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59211015"
---
# <a name="icorprofilercallback9dynamicmethodunloaded-method"></a><span data-ttu-id="8a6b1-102">Método ICorProfilerCallback9::DynamicMethodUnloaded</span><span class="sxs-lookup"><span data-stu-id="8a6b1-102">ICorProfilerCallback9::DynamicMethodUnloaded Method</span></span>
<span data-ttu-id="8a6b1-103">[Compatible con .NET Framework 4.7.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="8a6b1-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  
  
<span data-ttu-id="8a6b1-104">Notifica al generador de perfiles cada vez que un método dinámico es recolectado y posteriormente descargan.</span><span class="sxs-lookup"><span data-stu-id="8a6b1-104">Notifies the profiler whenever a dynamic method is garbage collected and subsequently unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a6b1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8a6b1-105">Syntax</span></span>  
  
```  
HRESULT DynamicMethodUnloaded(  
     [in]  FunctionID  functionId
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a6b1-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8a6b1-106">Parameters</span></span>  
<span data-ttu-id="8a6b1-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="8a6b1-107">[in] `functionId`</span></span>  
<span data-ttu-id="8a6b1-108">El identificador de la función en memoria que se ha recolectado y descarga.</span><span class="sxs-lookup"><span data-stu-id="8a6b1-108">The identifier of the in-memory function that has been garbage collected and unloaded.</span></span>   

## <a name="requirements"></a><span data-ttu-id="8a6b1-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8a6b1-109">Requirements</span></span>  
 <span data-ttu-id="8a6b1-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a6b1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a6b1-111">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8a6b1-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8a6b1-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a6b1-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a6b1-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="8a6b1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a6b1-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="8a6b1-114">See also</span></span>

- [<span data-ttu-id="8a6b1-115">Método ICorProfilerCallback8.DynamicMethodJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="8a6b1-115">ICorProfilerCallback8.DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="8a6b1-116">Método ICorProfilerCallback8.DynamicMethodJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="8a6b1-116">ICorProfilerCallback8.DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="8a6b1-117">ICorProfilerCallback9 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8a6b1-117">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
- [<span data-ttu-id="8a6b1-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span><span class="sxs-lookup"><span data-stu-id="8a6b1-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span></span>](cor-prf-high-monitor-enumeration.md)
