---
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
ms.openlocfilehash: bab8d446347646081cee635035e954da58c3550c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733885"
---
# <a name="icorprofilercallbackfunctionunloadstarted-method"></a><span data-ttu-id="2d8d0-102">ICorProfilerCallback::FunctionUnloadStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="2d8d0-102">ICorProfilerCallback::FunctionUnloadStarted Method</span></span>

<span data-ttu-id="2d8d0-103">Notifica al generador de perfiles que el tiempo de ejecución ha empezado a descargar una función.</span><span class="sxs-lookup"><span data-stu-id="2d8d0-103">Notifies the profiler that the runtime has started to unload a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d8d0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2d8d0-104">Syntax</span></span>  
  
```cpp  
HRESULT FunctionUnloadStarted(  
    [in] FunctionID functionId);
```  
  
## <a name="parameters"></a><span data-ttu-id="2d8d0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2d8d0-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="2d8d0-106">\[in] identificador de la función que se está descargando.</span><span class="sxs-lookup"><span data-stu-id="2d8d0-106">\[in] The ID of the function that is being unloaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="2d8d0-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2d8d0-107">Remarks</span></span>  

 <span data-ttu-id="2d8d0-108">El valor del `functionId` parámetro ya no es válido después de que este método vuelva al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="2d8d0-108">The value of the `functionId` parameter is no longer valid after this method returns to the caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d8d0-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2d8d0-109">Requirements</span></span>  

 <span data-ttu-id="2d8d0-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d8d0-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d8d0-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2d8d0-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2d8d0-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2d8d0-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2d8d0-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d8d0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d8d0-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2d8d0-114">See also</span></span>

- [<span data-ttu-id="2d8d0-115">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2d8d0-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
