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
ms.openlocfilehash: 680bd351a64632e67432ee03352ee7caa8f4b2d0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780386"
---
# <a name="icorprofilercallback9dynamicmethodunloaded-method"></a><span data-ttu-id="33236-102">Método ICorProfilerCallback9::DynamicMethodUnloaded</span><span class="sxs-lookup"><span data-stu-id="33236-102">ICorProfilerCallback9::DynamicMethodUnloaded Method</span></span>
<span data-ttu-id="33236-103">[Compatible con .NET Framework 4.7.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="33236-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  
  
<span data-ttu-id="33236-104">Notifica al generador de perfiles cada vez que un método dinámico es recolectado y posteriormente descargan.</span><span class="sxs-lookup"><span data-stu-id="33236-104">Notifies the profiler whenever a dynamic method is garbage collected and subsequently unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33236-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="33236-105">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodUnloaded(  
     [in]  FunctionID  functionId
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="33236-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="33236-106">Parameters</span></span>  
<span data-ttu-id="33236-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="33236-107">[in] `functionId`</span></span>  
<span data-ttu-id="33236-108">El identificador de la función en memoria que se ha recolectado y descarga.</span><span class="sxs-lookup"><span data-stu-id="33236-108">The identifier of the in-memory function that has been garbage collected and unloaded.</span></span>   

## <a name="requirements"></a><span data-ttu-id="33236-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="33236-109">Requirements</span></span>  
 <span data-ttu-id="33236-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33236-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33236-111">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="33236-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="33236-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="33236-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="33236-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="33236-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33236-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="33236-114">See also</span></span>

- [<span data-ttu-id="33236-115">Método ICorProfilerCallback8.DynamicMethodJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="33236-115">ICorProfilerCallback8.DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="33236-116">Método ICorProfilerCallback8.DynamicMethodJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="33236-116">ICorProfilerCallback8.DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="33236-117">ICorProfilerCallback9 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="33236-117">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
- [<span data-ttu-id="33236-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span><span class="sxs-lookup"><span data-stu-id="33236-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span></span>](cor-prf-high-monitor-enumeration.md)
