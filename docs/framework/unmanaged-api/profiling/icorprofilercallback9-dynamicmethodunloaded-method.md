---
title: ICorProfilerCallback9::DynamicMethodUnloaded Método
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback9.DynamicMethodUnloaded
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 0eb38c83e9ab706c96bdef971f0bf17cc096822b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177038"
---
# <a name="icorprofilercallback9dynamicmethodunloaded-method"></a><span data-ttu-id="f8d2f-102">ICorProfilerCallback9::DynamicMethodUnloaded Método</span><span class="sxs-lookup"><span data-stu-id="f8d2f-102">ICorProfilerCallback9::DynamicMethodUnloaded Method</span></span>
<span data-ttu-id="f8d2f-103">[Soportado en .NET Framework 4.7.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="f8d2f-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  
  
<span data-ttu-id="f8d2f-104">Notifica al generador de perfiles cada vez que se recopila un método dinámico y se descarga posteriormente.</span><span class="sxs-lookup"><span data-stu-id="f8d2f-104">Notifies the profiler whenever a dynamic method is garbage collected and subsequently unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8d2f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f8d2f-105">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodUnloaded(  
     [in]  FunctionID  functionId
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f8d2f-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f8d2f-106">Parameters</span></span>  
<span data-ttu-id="f8d2f-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="f8d2f-107">[in] `functionId`</span></span>  
<span data-ttu-id="f8d2f-108">Identificador de la función en memoria que se ha recopilado y descargado.</span><span class="sxs-lookup"><span data-stu-id="f8d2f-108">The identifier of the in-memory function that has been garbage collected and unloaded.</span></span>

## <a name="requirements"></a><span data-ttu-id="f8d2f-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f8d2f-109">Requirements</span></span>  
 <span data-ttu-id="f8d2f-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8d2f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8d2f-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f8d2f-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f8d2f-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f8d2f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f8d2f-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f8d2f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8d2f-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f8d2f-114">See also</span></span>

- [<span data-ttu-id="f8d2f-115">ICorProfilerCallback8.DynamicMethodJITCompilationStarted Método</span><span class="sxs-lookup"><span data-stu-id="f8d2f-115">ICorProfilerCallback8.DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="f8d2f-116">ICorProfilerCallback8.DynamicMethodJITCompilationFinished Método</span><span class="sxs-lookup"><span data-stu-id="f8d2f-116">ICorProfilerCallback8.DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="f8d2f-117">ICorProfilerCallback9 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f8d2f-117">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
- [<span data-ttu-id="f8d2f-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span><span class="sxs-lookup"><span data-stu-id="f8d2f-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span></span>](cor-prf-high-monitor-enumeration.md)
