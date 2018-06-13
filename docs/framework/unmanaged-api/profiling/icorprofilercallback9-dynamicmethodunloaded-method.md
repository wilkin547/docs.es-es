---
title: ICorProfilerCallback9::DynamicMethodUnloaded (método)
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
ms.openlocfilehash: 16b3334647922f845645e6eb58db3146f4c9b936
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452408"
---
# <a name="icorprofilercallback9dynamicmethodunloaded-method"></a><span data-ttu-id="63aa4-102">ICorProfilerCallback9::DynamicMethodUnloaded (método)</span><span class="sxs-lookup"><span data-stu-id="63aa4-102">ICorProfilerCallback9::DynamicMethodUnloaded Method</span></span>
<span data-ttu-id="63aa4-103">[Compatible con .NET Framework 4.7.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="63aa4-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  
  
<span data-ttu-id="63aa4-104">Notifica al generador de perfiles siempre que un método dinámico es recolectado y posteriormente se descargan.</span><span class="sxs-lookup"><span data-stu-id="63aa4-104">Notifies the profiler whenever a dynamic method is garbage collected and subsequently unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63aa4-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="63aa4-105">Syntax</span></span>  
  
```  
HRESULT DynamicMethodUnloaded(  
     [in]  FunctionID  functionId
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="63aa4-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="63aa4-106">Parameters</span></span>  
<span data-ttu-id="63aa4-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="63aa4-107">[in] `functionId`</span></span>  
<span data-ttu-id="63aa4-108">El identificador de la función en memoria que se ha recolectado y descarga.</span><span class="sxs-lookup"><span data-stu-id="63aa4-108">The identifier of the in-memory function that has been garbage collected and unloaded.</span></span>   

## <a name="requirements"></a><span data-ttu-id="63aa4-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="63aa4-109">Requirements</span></span>  
 <span data-ttu-id="63aa4-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63aa4-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63aa4-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="63aa4-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="63aa4-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="63aa4-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="63aa4-113">**Versiones de .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="63aa4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63aa4-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="63aa4-114">See Also</span></span>  
[<span data-ttu-id="63aa4-115">ICorProfilerCallback8.DynamicMethodJITCompilationStarted (método)</span><span class="sxs-lookup"><span data-stu-id="63aa4-115">ICorProfilerCallback8.DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)  
[<span data-ttu-id="63aa4-116">ICorProfilerCallback8.DynamicMethodJITCompilationFinished (método)</span><span class="sxs-lookup"><span data-stu-id="63aa4-116">ICorProfilerCallback8.DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)  
<span data-ttu-id="63aa4-117">[Interfaz ICorProfilerCallback9](icorprofilercallback9-interface.md) </span><span class="sxs-lookup"><span data-stu-id="63aa4-117">[ICorProfilerCallback9 Interface](icorprofilercallback9-interface.md) </span></span>  
[<span data-ttu-id="63aa4-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span><span class="sxs-lookup"><span data-stu-id="63aa4-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span></span>](cor-prf-high-monitor-enumeration.md)
