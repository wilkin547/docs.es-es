---
title: ICorProfilerCallback::ClassLoadStarted (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassLoadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassLoadStarted
helpviewer_keywords:
- ICorProfilerCallback::ClassLoadStarted method [.NET Framework profiling]
- ClassLoadStarted method [.NET Framework profiling]
ms.assetid: 9f728de8-45c2-45a5-ac4a-45660bd36ecf
topic_type:
- apiref
ms.openlocfilehash: fbdc9345c8364f33ac69da452dd91155fd5eede9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700280"
---
# <a name="icorprofilercallbackclassloadstarted-method"></a><span data-ttu-id="90038-102">ICorProfilerCallback::ClassLoadStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="90038-102">ICorProfilerCallback::ClassLoadStarted Method</span></span>

<span data-ttu-id="90038-103">Notifica al generador de perfiles que se está cargando una clase.</span><span class="sxs-lookup"><span data-stu-id="90038-103">Notifies the profiler that a class is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90038-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="90038-104">Syntax</span></span>  
  
```cpp  
HRESULT ClassLoadStarted(  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="90038-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="90038-105">Parameters</span></span>

- `classId`

  <span data-ttu-id="90038-106">\[in] identifica la clase que se está cargando.</span><span class="sxs-lookup"><span data-stu-id="90038-106">\[in] Identifies the class that is being loaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="90038-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="90038-107">Remarks</span></span>  

 <span data-ttu-id="90038-108">El valor de `classId` no es válido para una solicitud de información hasta que se llama al método [ICorProfilerCallback:: classloadfinished (](icorprofilercallback-classloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="90038-108">The value of `classId` is not valid for an information request until the [ICorProfilerCallback::ClassLoadFinished](icorprofilercallback-classloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90038-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="90038-109">Requirements</span></span>  

 <span data-ttu-id="90038-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="90038-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90038-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="90038-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="90038-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="90038-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="90038-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90038-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90038-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="90038-114">See also</span></span>

- [<span data-ttu-id="90038-115">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="90038-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
