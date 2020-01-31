---
title: ICorProfilerCallback::ClassUnloadStarted (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassUnloadStarted
helpviewer_keywords:
- ClassUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ClassUnloadStarted method [.NET Framework profiling]
ms.assetid: bc93bead-f3a9-415c-b919-ddd3ca80facc
topic_type:
- apiref
ms.openlocfilehash: 75fb92be078c40f49ddcdc6662535b2a0be7a6ad
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866564"
---
# <a name="icorprofilercallbackclassunloadstarted-method"></a><span data-ttu-id="5c66c-102">ICorProfilerCallback::ClassUnloadStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="5c66c-102">ICorProfilerCallback::ClassUnloadStarted Method</span></span>
<span data-ttu-id="5c66c-103">Notifica al generador de perfiles que se está descargando una clase.</span><span class="sxs-lookup"><span data-stu-id="5c66c-103">Notifies the profiler that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c66c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5c66c-104">Syntax</span></span>  
  
```cpp  
HRESULT ClassUnloadStarted(  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c66c-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="5c66c-105">Parameters</span></span>

- `classId`

  <span data-ttu-id="5c66c-106">\[en] identifica la clase que se está descargando.</span><span class="sxs-lookup"><span data-stu-id="5c66c-106">\[in] Identifies the class that is being unloaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="5c66c-107">Notas</span><span class="sxs-lookup"><span data-stu-id="5c66c-107">Remarks</span></span>  
 <span data-ttu-id="5c66c-108">El valor de `classId` no es válido para una solicitud de información después de que se devuelva el método `ClassUnloadStarted`; esta es la última oportunidad del generador de perfiles para obtener información sobre esta clase.</span><span class="sxs-lookup"><span data-stu-id="5c66c-108">The value of `classId` is not valid for an information request after the `ClassUnloadStarted` method returns — this is the profiler's last chance to obtain information about this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c66c-109">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="5c66c-109">Requirements</span></span>  
 <span data-ttu-id="5c66c-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c66c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c66c-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5c66c-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5c66c-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5c66c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5c66c-113">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c66c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c66c-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="5c66c-114">See also</span></span>

- [<span data-ttu-id="5c66c-115">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5c66c-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="5c66c-116">ClassUnloadFinished (método)</span><span class="sxs-lookup"><span data-stu-id="5c66c-116">ClassUnloadFinished Method</span></span>](icorprofilercallback-classunloadfinished-method.md)
