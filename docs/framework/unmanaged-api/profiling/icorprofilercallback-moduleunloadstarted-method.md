---
title: ICorProfilerCallback::ModuleUnloadStarted (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleUnloadStarted
helpviewer_keywords:
- ModuleUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ModuleUnloadStarted method [.NET Framework profiling]
ms.assetid: 2debcaab-6005-4245-afdb-4268bb7e74bd
topic_type:
- apiref
ms.openlocfilehash: 12d5f7e073337af6034b8f313a2e0161620a65ea
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720963"
---
# <a name="icorprofilercallbackmoduleunloadstarted-method"></a><span data-ttu-id="03d92-102">ICorProfilerCallback::ModuleUnloadStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="03d92-102">ICorProfilerCallback::ModuleUnloadStarted Method</span></span>

<span data-ttu-id="03d92-103">Notifica al generador de perfiles que se está descargando un módulo.</span><span class="sxs-lookup"><span data-stu-id="03d92-103">Notifies the profiler that a module is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03d92-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="03d92-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleUnloadStarted(  
    [in] ModuleID moduleId);
```  
  
## <a name="parameters"></a><span data-ttu-id="03d92-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="03d92-105">Parameters</span></span>  

 `moduleId`  
 <span data-ttu-id="03d92-106">de IDENTIFICADOR del módulo que se está descargando.</span><span class="sxs-lookup"><span data-stu-id="03d92-106">[in] The ID of the module that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="03d92-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="03d92-107">Remarks</span></span>  

 <span data-ttu-id="03d92-108">El valor de `moduleId` no es válido para una solicitud de información después de que se `ModuleUnloadStarted` devuelva el método; esta es la última oportunidad del generador de perfiles para obtener información acerca de este módulo.</span><span class="sxs-lookup"><span data-stu-id="03d92-108">The value of `moduleId` is not valid for an information request after the `ModuleUnloadStarted` method returns — this is the profiler's last chance to get information about this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03d92-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="03d92-109">Requirements</span></span>  

 <span data-ttu-id="03d92-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03d92-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03d92-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="03d92-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="03d92-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="03d92-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="03d92-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03d92-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03d92-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="03d92-114">See also</span></span>

- [<span data-ttu-id="03d92-115">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="03d92-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="03d92-116">Método ModuleUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="03d92-116">ModuleUnloadFinished Method</span></span>](icorprofilercallback-moduleunloadfinished-method.md)
