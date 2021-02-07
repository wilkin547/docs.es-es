---
description: 'Más información sobre: ICorProfilerCallback:: ModuleUnloadStarted ((método)'
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
ms.openlocfilehash: 3d10654e23481fe6f8956129a0aef7ed4206bba9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99745234"
---
# <a name="icorprofilercallbackmoduleunloadstarted-method"></a><span data-ttu-id="41623-103">ICorProfilerCallback::ModuleUnloadStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="41623-103">ICorProfilerCallback::ModuleUnloadStarted Method</span></span>

<span data-ttu-id="41623-104">Notifica al generador de perfiles que se está descargando un módulo.</span><span class="sxs-lookup"><span data-stu-id="41623-104">Notifies the profiler that a module is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41623-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="41623-105">Syntax</span></span>  
  
```cpp  
HRESULT ModuleUnloadStarted(  
    [in] ModuleID moduleId);
```  
  
## <a name="parameters"></a><span data-ttu-id="41623-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="41623-106">Parameters</span></span>  

 `moduleId`  
 <span data-ttu-id="41623-107">de IDENTIFICADOR del módulo que se está descargando.</span><span class="sxs-lookup"><span data-stu-id="41623-107">[in] The ID of the module that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="41623-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="41623-108">Remarks</span></span>  

 <span data-ttu-id="41623-109">El valor de `moduleId` no es válido para una solicitud de información después de que se `ModuleUnloadStarted` devuelva el método; esta es la última oportunidad del generador de perfiles para obtener información acerca de este módulo.</span><span class="sxs-lookup"><span data-stu-id="41623-109">The value of `moduleId` is not valid for an information request after the `ModuleUnloadStarted` method returns — this is the profiler's last chance to get information about this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41623-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="41623-110">Requirements</span></span>  

 <span data-ttu-id="41623-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41623-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41623-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="41623-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="41623-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="41623-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="41623-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41623-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41623-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="41623-115">See also</span></span>

- [<span data-ttu-id="41623-116">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="41623-116">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="41623-117">Método ModuleUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="41623-117">ModuleUnloadFinished Method</span></span>](icorprofilercallback-moduleunloadfinished-method.md)
