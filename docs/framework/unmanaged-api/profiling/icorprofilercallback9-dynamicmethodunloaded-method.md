---
title: ICorProfilerCallback9::D método ynamicMethodUnloaded
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback9.DynamicMethodUnloaded
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 05a788179ff40a6889ed613b5f8659dd3f8e066f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73196318"
---
# <a name="icorprofilercallback9dynamicmethodunloaded-method"></a><span data-ttu-id="107ec-102">ICorProfilerCallback9::D método ynamicMethodUnloaded</span><span class="sxs-lookup"><span data-stu-id="107ec-102">ICorProfilerCallback9::DynamicMethodUnloaded Method</span></span>
<span data-ttu-id="107ec-103">[Se admite en el .NET Framework 4.7.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="107ec-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  
  
<span data-ttu-id="107ec-104">Notifica al generador de perfiles cada vez que un método dinámico se recolecta como elemento no utilizado y, posteriormente, se descarga.</span><span class="sxs-lookup"><span data-stu-id="107ec-104">Notifies the profiler whenever a dynamic method is garbage collected and subsequently unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="107ec-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="107ec-105">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodUnloaded(  
     [in]  FunctionID  functionId
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="107ec-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="107ec-106">Parameters</span></span>  
<span data-ttu-id="107ec-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="107ec-107">[in] `functionId`</span></span>  
<span data-ttu-id="107ec-108">El identificador de la función en memoria que se ha recolectado y descargado.</span><span class="sxs-lookup"><span data-stu-id="107ec-108">The identifier of the in-memory function that has been garbage collected and unloaded.</span></span>   

## <a name="requirements"></a><span data-ttu-id="107ec-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="107ec-109">Requirements</span></span>  
 <span data-ttu-id="107ec-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="107ec-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="107ec-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="107ec-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="107ec-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="107ec-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="107ec-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="107ec-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="107ec-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="107ec-114">See also</span></span>

- [<span data-ttu-id="107ec-115">ICorProfilerCallback8. DynamicMethodJITCompilationStarted, método</span><span class="sxs-lookup"><span data-stu-id="107ec-115">ICorProfilerCallback8.DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="107ec-116">ICorProfilerCallback8. DynamicMethodJITCompilationFinished, método</span><span class="sxs-lookup"><span data-stu-id="107ec-116">ICorProfilerCallback8.DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="107ec-117">ICorProfilerCallback9 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="107ec-117">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
- [<span data-ttu-id="107ec-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span><span class="sxs-lookup"><span data-stu-id="107ec-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span></span>](cor-prf-high-monitor-enumeration.md)
