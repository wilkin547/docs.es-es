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
ms.openlocfilehash: 1c154eee85811796321aea2647db1c8996997576
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700254"
---
# <a name="icorprofilercallbackclassunloadstarted-method"></a><span data-ttu-id="c22af-102">ICorProfilerCallback::ClassUnloadStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="c22af-102">ICorProfilerCallback::ClassUnloadStarted Method</span></span>

<span data-ttu-id="c22af-103">Notifica al generador de perfiles que se está descargando una clase.</span><span class="sxs-lookup"><span data-stu-id="c22af-103">Notifies the profiler that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c22af-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c22af-104">Syntax</span></span>  
  
```cpp  
HRESULT ClassUnloadStarted(  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c22af-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c22af-105">Parameters</span></span>

- `classId`

  <span data-ttu-id="c22af-106">\[en] identifica la clase que se está descargando.</span><span class="sxs-lookup"><span data-stu-id="c22af-106">\[in] Identifies the class that is being unloaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="c22af-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c22af-107">Remarks</span></span>  

 <span data-ttu-id="c22af-108">El valor de `classId` no es válido para una solicitud de información después de que se `ClassUnloadStarted` devuelva el método; esta es la última oportunidad del generador de perfiles para obtener información sobre esta clase.</span><span class="sxs-lookup"><span data-stu-id="c22af-108">The value of `classId` is not valid for an information request after the `ClassUnloadStarted` method returns — this is the profiler's last chance to obtain information about this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c22af-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c22af-109">Requirements</span></span>  

 <span data-ttu-id="c22af-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c22af-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c22af-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c22af-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c22af-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c22af-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c22af-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c22af-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c22af-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c22af-114">See also</span></span>

- [<span data-ttu-id="c22af-115">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c22af-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="c22af-116">Método ClassUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="c22af-116">ClassUnloadFinished Method</span></span>](icorprofilercallback-classunloadfinished-method.md)
