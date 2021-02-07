---
description: 'Más información sobre: ICorProfilerCallback:: Functionunloadstarted ((método)'
title: ICorProfilerCallback::FunctionUnloadStarted (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.FunctionUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::FunctionUnloadStarted
helpviewer_keywords:
- FunctionUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::FunctionUnloadStarted method [.NET Framework profiling]
ms.assetid: d6a5fa8b-09c6-47a5-b60e-6cf2e355df30
topic_type:
- apiref
ms.openlocfilehash: 3dd5d46a224c0c51dfee251cf5d0c6ae9320b630
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99705968"
---
# <a name="icorprofilercallbackfunctionunloadstarted-method"></a><span data-ttu-id="a47c6-103">ICorProfilerCallback::FunctionUnloadStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="a47c6-103">ICorProfilerCallback::FunctionUnloadStarted Method</span></span>

<span data-ttu-id="a47c6-104">Notifica al generador de perfiles que el tiempo de ejecución ha empezado a descargar una función.</span><span class="sxs-lookup"><span data-stu-id="a47c6-104">Notifies the profiler that the runtime has started to unload a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a47c6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a47c6-105">Syntax</span></span>  
  
```cpp  
HRESULT FunctionUnloadStarted(  
    [in] FunctionID functionId);
```  
  
## <a name="parameters"></a><span data-ttu-id="a47c6-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a47c6-106">Parameters</span></span>

- `functionId`

  <span data-ttu-id="a47c6-107">\[in] identificador de la función que se está descargando.</span><span class="sxs-lookup"><span data-stu-id="a47c6-107">\[in] The ID of the function that is being unloaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="a47c6-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a47c6-108">Remarks</span></span>  

 <span data-ttu-id="a47c6-109">El valor del `functionId` parámetro ya no es válido después de que este método vuelva al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a47c6-109">The value of the `functionId` parameter is no longer valid after this method returns to the caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a47c6-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a47c6-110">Requirements</span></span>  

 <span data-ttu-id="a47c6-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a47c6-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a47c6-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a47c6-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a47c6-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a47c6-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a47c6-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a47c6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a47c6-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="a47c6-115">See also</span></span>

- [<span data-ttu-id="a47c6-116">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a47c6-116">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
