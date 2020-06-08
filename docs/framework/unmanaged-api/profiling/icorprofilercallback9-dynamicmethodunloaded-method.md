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
ms.openlocfilehash: 2391ad854b17ec117940a3d3568c40d6cf7f4725
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84498978"
---
# <a name="icorprofilercallback9dynamicmethodunloaded-method"></a><span data-ttu-id="b87a0-102">ICorProfilerCallback9::D método ynamicMethodUnloaded</span><span class="sxs-lookup"><span data-stu-id="b87a0-102">ICorProfilerCallback9::DynamicMethodUnloaded Method</span></span>
<span data-ttu-id="b87a0-103">[Se admite en el .NET Framework 4.7.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="b87a0-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  
  
<span data-ttu-id="b87a0-104">Notifica al generador de perfiles cada vez que un método dinámico se recolecta como elemento no utilizado y, posteriormente, se descarga.</span><span class="sxs-lookup"><span data-stu-id="b87a0-104">Notifies the profiler whenever a dynamic method is garbage collected and subsequently unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b87a0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b87a0-105">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodUnloaded(  
     [in]  FunctionID  functionId
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b87a0-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b87a0-106">Parameters</span></span>  
<span data-ttu-id="b87a0-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="b87a0-107">[in] `functionId`</span></span>  
<span data-ttu-id="b87a0-108">El identificador de la función en memoria que se ha recolectado y descargado.</span><span class="sxs-lookup"><span data-stu-id="b87a0-108">The identifier of the in-memory function that has been garbage collected and unloaded.</span></span>

## <a name="requirements"></a><span data-ttu-id="b87a0-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b87a0-109">Requirements</span></span>  
 <span data-ttu-id="b87a0-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b87a0-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b87a0-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b87a0-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b87a0-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b87a0-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b87a0-113">**.NET Framework versiones:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b87a0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b87a0-114">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="b87a0-114">See also</span></span>

- [<span data-ttu-id="b87a0-115">ICorProfilerCallback8. DynamicMethodJITCompilationStarted, método</span><span class="sxs-lookup"><span data-stu-id="b87a0-115">ICorProfilerCallback8.DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="b87a0-116">ICorProfilerCallback8. DynamicMethodJITCompilationFinished, método</span><span class="sxs-lookup"><span data-stu-id="b87a0-116">ICorProfilerCallback8.DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="b87a0-117">Interfaz ICorProfilerCallback9</span><span class="sxs-lookup"><span data-stu-id="b87a0-117">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
- [<span data-ttu-id="b87a0-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span><span class="sxs-lookup"><span data-stu-id="b87a0-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span></span>](cor-prf-high-monitor-enumeration.md)
