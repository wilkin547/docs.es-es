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
ms.openlocfilehash: 243660d3159e3c8c1d052c08e9c7499e7065d301
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753333"
---
# <a name="icorprofilercallback9dynamicmethodunloaded-method"></a><span data-ttu-id="83fa0-103">ICorProfilerCallback9::D método ynamicMethodUnloaded</span><span class="sxs-lookup"><span data-stu-id="83fa0-103">ICorProfilerCallback9::DynamicMethodUnloaded Method</span></span>

<span data-ttu-id="83fa0-104">[Se admite en el .NET Framework 4.7.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="83fa0-104">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  
  
<span data-ttu-id="83fa0-105">Notifica al generador de perfiles cada vez que un método dinámico se recolecta como elemento no utilizado y, posteriormente, se descarga.</span><span class="sxs-lookup"><span data-stu-id="83fa0-105">Notifies the profiler whenever a dynamic method is garbage collected and subsequently unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83fa0-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="83fa0-106">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodUnloaded(  
     [in]  FunctionID  functionId
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83fa0-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="83fa0-107">Parameters</span></span>  

<span data-ttu-id="83fa0-108">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="83fa0-108">[in] `functionId`</span></span>  
<span data-ttu-id="83fa0-109">El identificador de la función en memoria que se ha recolectado y descargado.</span><span class="sxs-lookup"><span data-stu-id="83fa0-109">The identifier of the in-memory function that has been garbage collected and unloaded.</span></span>

## <a name="requirements"></a><span data-ttu-id="83fa0-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="83fa0-110">Requirements</span></span>  

 <span data-ttu-id="83fa0-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83fa0-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83fa0-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="83fa0-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="83fa0-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="83fa0-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="83fa0-114">**.NET Framework versiones:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="83fa0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83fa0-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="83fa0-115">See also</span></span>

- [<span data-ttu-id="83fa0-116">ICorProfilerCallback8. DynamicMethodJITCompilationStarted, método</span><span class="sxs-lookup"><span data-stu-id="83fa0-116">ICorProfilerCallback8.DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="83fa0-117">ICorProfilerCallback8. DynamicMethodJITCompilationFinished, método</span><span class="sxs-lookup"><span data-stu-id="83fa0-117">ICorProfilerCallback8.DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="83fa0-118">Interfaz ICorProfilerCallback9</span><span class="sxs-lookup"><span data-stu-id="83fa0-118">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
- [<span data-ttu-id="83fa0-119">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span><span class="sxs-lookup"><span data-stu-id="83fa0-119">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span></span>](cor-prf-high-monitor-enumeration.md)
