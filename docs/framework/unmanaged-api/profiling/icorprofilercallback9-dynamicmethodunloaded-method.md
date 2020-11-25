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
ms.openlocfilehash: 0e6fe3430696c16405d4ae414436bb12882c08a5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732353"
---
# <a name="icorprofilercallback9dynamicmethodunloaded-method"></a><span data-ttu-id="a47dd-102">ICorProfilerCallback9::D método ynamicMethodUnloaded</span><span class="sxs-lookup"><span data-stu-id="a47dd-102">ICorProfilerCallback9::DynamicMethodUnloaded Method</span></span>

<span data-ttu-id="a47dd-103">[Se admite en el .NET Framework 4.7.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="a47dd-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  
  
<span data-ttu-id="a47dd-104">Notifica al generador de perfiles cada vez que un método dinámico se recolecta como elemento no utilizado y, posteriormente, se descarga.</span><span class="sxs-lookup"><span data-stu-id="a47dd-104">Notifies the profiler whenever a dynamic method is garbage collected and subsequently unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a47dd-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a47dd-105">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodUnloaded(  
     [in]  FunctionID  functionId
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a47dd-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a47dd-106">Parameters</span></span>  

<span data-ttu-id="a47dd-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="a47dd-107">[in] `functionId`</span></span>  
<span data-ttu-id="a47dd-108">El identificador de la función en memoria que se ha recolectado y descargado.</span><span class="sxs-lookup"><span data-stu-id="a47dd-108">The identifier of the in-memory function that has been garbage collected and unloaded.</span></span>

## <a name="requirements"></a><span data-ttu-id="a47dd-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a47dd-109">Requirements</span></span>  

 <span data-ttu-id="a47dd-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a47dd-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a47dd-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a47dd-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a47dd-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a47dd-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a47dd-113">**.NET Framework versiones:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a47dd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a47dd-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a47dd-114">See also</span></span>

- [<span data-ttu-id="a47dd-115">ICorProfilerCallback8. DynamicMethodJITCompilationStarted, método</span><span class="sxs-lookup"><span data-stu-id="a47dd-115">ICorProfilerCallback8.DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="a47dd-116">ICorProfilerCallback8. DynamicMethodJITCompilationFinished, método</span><span class="sxs-lookup"><span data-stu-id="a47dd-116">ICorProfilerCallback8.DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="a47dd-117">Interfaz ICorProfilerCallback9</span><span class="sxs-lookup"><span data-stu-id="a47dd-117">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
- [<span data-ttu-id="a47dd-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span><span class="sxs-lookup"><span data-stu-id="a47dd-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span></span>](cor-prf-high-monitor-enumeration.md)
