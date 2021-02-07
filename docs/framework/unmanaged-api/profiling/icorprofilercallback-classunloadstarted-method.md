---
description: 'Más información sobre: ICorProfilerCallback:: ClassUnloadStarted ((método)'
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
ms.openlocfilehash: 3dae88d9cbe9ed2a2e234d02420a65c6a9ca003d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99706378"
---
# <a name="icorprofilercallbackclassunloadstarted-method"></a><span data-ttu-id="64ccc-103">ICorProfilerCallback::ClassUnloadStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="64ccc-103">ICorProfilerCallback::ClassUnloadStarted Method</span></span>

<span data-ttu-id="64ccc-104">Notifica al generador de perfiles que se está descargando una clase.</span><span class="sxs-lookup"><span data-stu-id="64ccc-104">Notifies the profiler that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64ccc-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="64ccc-105">Syntax</span></span>  
  
```cpp  
HRESULT ClassUnloadStarted(  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="64ccc-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="64ccc-106">Parameters</span></span>

- `classId`

  <span data-ttu-id="64ccc-107">\[en] identifica la clase que se está descargando.</span><span class="sxs-lookup"><span data-stu-id="64ccc-107">\[in] Identifies the class that is being unloaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="64ccc-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="64ccc-108">Remarks</span></span>  

 <span data-ttu-id="64ccc-109">El valor de `classId` no es válido para una solicitud de información después de que se `ClassUnloadStarted` devuelva el método; esta es la última oportunidad del generador de perfiles para obtener información sobre esta clase.</span><span class="sxs-lookup"><span data-stu-id="64ccc-109">The value of `classId` is not valid for an information request after the `ClassUnloadStarted` method returns — this is the profiler's last chance to obtain information about this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64ccc-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="64ccc-110">Requirements</span></span>  

 <span data-ttu-id="64ccc-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64ccc-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64ccc-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="64ccc-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="64ccc-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="64ccc-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="64ccc-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64ccc-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64ccc-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="64ccc-115">See also</span></span>

- [<span data-ttu-id="64ccc-116">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="64ccc-116">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="64ccc-117">Método ClassUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="64ccc-117">ClassUnloadFinished Method</span></span>](icorprofilercallback-classunloadfinished-method.md)
