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
ms.openlocfilehash: 7e43f58f619aaa63fa2294dd3e989026dcdfc604
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866135"
---
# <a name="icorprofilercallbackmoduleunloadstarted-method"></a><span data-ttu-id="45a29-102">ICorProfilerCallback::ModuleUnloadStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="45a29-102">ICorProfilerCallback::ModuleUnloadStarted Method</span></span>
<span data-ttu-id="45a29-103">Notifica al generador de perfiles que se está descargando un módulo.</span><span class="sxs-lookup"><span data-stu-id="45a29-103">Notifies the profiler that a module is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45a29-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="45a29-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleUnloadStarted(  
    [in] ModuleID moduleId);   
```  
  
## <a name="parameters"></a><span data-ttu-id="45a29-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="45a29-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="45a29-106">de IDENTIFICADOR del módulo que se está descargando.</span><span class="sxs-lookup"><span data-stu-id="45a29-106">[in] The ID of the module that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="45a29-107">Notas</span><span class="sxs-lookup"><span data-stu-id="45a29-107">Remarks</span></span>  
 <span data-ttu-id="45a29-108">El valor de `moduleId` no es válido para una solicitud de información después de que se devuelva el método `ModuleUnloadStarted`; esta es la última oportunidad del generador de perfiles para obtener información acerca de este módulo.</span><span class="sxs-lookup"><span data-stu-id="45a29-108">The value of `moduleId` is not valid for an information request after the `ModuleUnloadStarted` method returns — this is the profiler's last chance to get information about this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45a29-109">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="45a29-109">Requirements</span></span>  
 <span data-ttu-id="45a29-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45a29-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45a29-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="45a29-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="45a29-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="45a29-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="45a29-113">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45a29-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45a29-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="45a29-114">See also</span></span>

- [<span data-ttu-id="45a29-115">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="45a29-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="45a29-116">ModuleUnloadFinished (método)</span><span class="sxs-lookup"><span data-stu-id="45a29-116">ModuleUnloadFinished Method</span></span>](icorprofilercallback-moduleunloadfinished-method.md)
