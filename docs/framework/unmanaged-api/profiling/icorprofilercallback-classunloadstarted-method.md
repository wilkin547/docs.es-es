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
ms.openlocfilehash: 752ebc4fcb284fbeb91a1efcda476249632adc5c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790182"
---
# <a name="icorprofilercallbackclassunloadstarted-method"></a><span data-ttu-id="af7ca-102">ICorProfilerCallback::ClassUnloadStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="af7ca-102">ICorProfilerCallback::ClassUnloadStarted Method</span></span>
<span data-ttu-id="af7ca-103">Notifica al generador de perfiles que se está descargando una clase.</span><span class="sxs-lookup"><span data-stu-id="af7ca-103">Notifies the profiler that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af7ca-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="af7ca-104">Syntax</span></span>  
  
```cpp  
HRESULT ClassUnloadStarted(  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="af7ca-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="af7ca-105">Parameters</span></span>

- `classId`

  <span data-ttu-id="af7ca-106">\[en] identifica la clase que se está descargando.</span><span class="sxs-lookup"><span data-stu-id="af7ca-106">\[in] Identifies the class that is being unloaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="af7ca-107">Notas</span><span class="sxs-lookup"><span data-stu-id="af7ca-107">Remarks</span></span>  
 <span data-ttu-id="af7ca-108">El valor de `classId` no es válido para una solicitud de información después de que se devuelva el método `ClassUnloadStarted`; esta es la última oportunidad del generador de perfiles para obtener información sobre esta clase.</span><span class="sxs-lookup"><span data-stu-id="af7ca-108">The value of `classId` is not valid for an information request after the `ClassUnloadStarted` method returns — this is the profiler's last chance to obtain information about this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af7ca-109">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="af7ca-109">Requirements</span></span>  
 <span data-ttu-id="af7ca-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="af7ca-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af7ca-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="af7ca-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="af7ca-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="af7ca-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="af7ca-113">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af7ca-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af7ca-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="af7ca-114">See also</span></span>

- [<span data-ttu-id="af7ca-115">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="af7ca-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="af7ca-116">ClassUnloadFinished (método)</span><span class="sxs-lookup"><span data-stu-id="af7ca-116">ClassUnloadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadfinished-method.md)
