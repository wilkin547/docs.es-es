---
description: 'Más información acerca de: ICorProfilerCallback9::D ynamicMethodUnloaded (método)'
title: ICorProfilerCallback9::D método ynamicMethodUnloaded
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback9.DynamicMethodUnloaded
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: bc7f95b5101658c93eeb9fcef51e9c0f1bd2f2bd
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2021
ms.locfileid: "104760202"
---
# <a name="icorprofilercallback9dynamicmethodunloaded-method"></a><span data-ttu-id="038e7-103">ICorProfilerCallback9::D método ynamicMethodUnloaded</span><span class="sxs-lookup"><span data-stu-id="038e7-103">ICorProfilerCallback9::DynamicMethodUnloaded Method</span></span>

<span data-ttu-id="038e7-104">[Se admite en el .NET Framework 4.7.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="038e7-104">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  
  
<span data-ttu-id="038e7-105">Notifica al generador de perfiles cada vez que un método dinámico se recolecta como elemento no utilizado y, posteriormente, se descarga.</span><span class="sxs-lookup"><span data-stu-id="038e7-105">Notifies the profiler whenever a dynamic method is garbage collected and subsequently unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="038e7-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="038e7-106">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodUnloaded(  
     [in]  FunctionID  functionId
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="038e7-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="038e7-107">Parameters</span></span>  

<span data-ttu-id="038e7-108">`functionId` de El identificador de la función en memoria que se ha recolectado y descargado.</span><span class="sxs-lookup"><span data-stu-id="038e7-108">`functionId` [in] The identifier of the in-memory function that has been garbage collected and unloaded.</span></span>

## <a name="requirements"></a><span data-ttu-id="038e7-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="038e7-109">Requirements</span></span>  

 <span data-ttu-id="038e7-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="038e7-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="038e7-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="038e7-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="038e7-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="038e7-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="038e7-113">**.NET Framework versiones:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="038e7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="038e7-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="038e7-114">See also</span></span>

- [<span data-ttu-id="038e7-115">ICorProfilerCallback8. DynamicMethodJITCompilationStarted, método</span><span class="sxs-lookup"><span data-stu-id="038e7-115">ICorProfilerCallback8.DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="038e7-116">ICorProfilerCallback8. DynamicMethodJITCompilationFinished, método</span><span class="sxs-lookup"><span data-stu-id="038e7-116">ICorProfilerCallback8.DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="038e7-117">Interfaz ICorProfilerCallback9</span><span class="sxs-lookup"><span data-stu-id="038e7-117">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
- [<span data-ttu-id="038e7-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span><span class="sxs-lookup"><span data-stu-id="038e7-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span></span>](cor-prf-high-monitor-enumeration.md)
