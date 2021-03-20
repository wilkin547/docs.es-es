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
ms.openlocfilehash: ce3cf406b8d2f91613bce878db8a4f9e0838c052
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2021
ms.locfileid: "104760436"
---
# <a name="icorprofilercallbackfunctionunloadstarted-method"></a><span data-ttu-id="3bcfe-103">ICorProfilerCallback::FunctionUnloadStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="3bcfe-103">ICorProfilerCallback::FunctionUnloadStarted Method</span></span>

<span data-ttu-id="3bcfe-104">Notifica al generador de perfiles que el tiempo de ejecución ha empezado a descargar una función.</span><span class="sxs-lookup"><span data-stu-id="3bcfe-104">Notifies the profiler that the runtime has started to unload a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3bcfe-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3bcfe-105">Syntax</span></span>  
  
```cpp  
HRESULT FunctionUnloadStarted(  
    [in] FunctionID functionId);
```  
  
## <a name="parameters"></a><span data-ttu-id="3bcfe-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3bcfe-106">Parameters</span></span>

<span data-ttu-id="3bcfe-107">`functionId` de IDENTIFICADOR de la función que se está descargando.</span><span class="sxs-lookup"><span data-stu-id="3bcfe-107">`functionId` [in] The ID of the function that is being unloaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="3bcfe-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3bcfe-108">Remarks</span></span>  

 <span data-ttu-id="3bcfe-109">El valor del `functionId` parámetro ya no es válido después de que este método vuelva al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="3bcfe-109">The value of the `functionId` parameter is no longer valid after this method returns to the caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3bcfe-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3bcfe-110">Requirements</span></span>  

 <span data-ttu-id="3bcfe-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3bcfe-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3bcfe-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3bcfe-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3bcfe-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3bcfe-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3bcfe-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3bcfe-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bcfe-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3bcfe-115">See also</span></span>

- [<span data-ttu-id="3bcfe-116">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3bcfe-116">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
