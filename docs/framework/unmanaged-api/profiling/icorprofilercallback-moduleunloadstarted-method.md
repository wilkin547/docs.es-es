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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2ebeaaa88f3c7320f38d33a9c027d5aa76bf9673
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57495876"
---
# <a name="icorprofilercallbackmoduleunloadstarted-method"></a><span data-ttu-id="8d357-102">ICorProfilerCallback::ModuleUnloadStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="8d357-102">ICorProfilerCallback::ModuleUnloadStarted Method</span></span>
<span data-ttu-id="8d357-103">Notifica al generador de perfiles que se está descargando un módulo.</span><span class="sxs-lookup"><span data-stu-id="8d357-103">Notifies the profiler that a module is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d357-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8d357-104">Syntax</span></span>  
  
```  
HRESULT ModuleUnloadStarted(  
    [in] ModuleID moduleId);   
```  
  
## <a name="parameters"></a><span data-ttu-id="8d357-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8d357-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="8d357-106">[in] El identificador del módulo que se está descargando.</span><span class="sxs-lookup"><span data-stu-id="8d357-106">[in] The ID of the module that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8d357-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8d357-107">Remarks</span></span>  
 <span data-ttu-id="8d357-108">El valor de `moduleId` no es válido para una solicitud de información después de la `ModuleUnloadStarted` devuelve del método, se trata de la última oportunidad para obtener información acerca de este módulo del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="8d357-108">The value of `moduleId` is not valid for an information request after the `ModuleUnloadStarted` method returns — this is the profiler's last chance to get information about this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d357-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8d357-109">Requirements</span></span>  
 <span data-ttu-id="8d357-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d357-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d357-111">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8d357-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8d357-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8d357-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8d357-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d357-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d357-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="8d357-114">See also</span></span>
- [<span data-ttu-id="8d357-115">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8d357-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="8d357-116">ModuleUnloadFinished (método)</span><span class="sxs-lookup"><span data-stu-id="8d357-116">ModuleUnloadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadfinished-method.md)
