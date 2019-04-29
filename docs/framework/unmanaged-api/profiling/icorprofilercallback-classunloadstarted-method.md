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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f0707351d28ef75083b7bfb6ded38bc2a8460131
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61597588"
---
# <a name="icorprofilercallbackclassunloadstarted-method"></a><span data-ttu-id="60b71-102">ICorProfilerCallback::ClassUnloadStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="60b71-102">ICorProfilerCallback::ClassUnloadStarted Method</span></span>
<span data-ttu-id="60b71-103">Notifica al generador de perfiles que se está descargando una clase.</span><span class="sxs-lookup"><span data-stu-id="60b71-103">Notifies the profiler that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60b71-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="60b71-104">Syntax</span></span>  
  
```  
HRESULT ClassUnloadStarted(  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="60b71-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="60b71-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="60b71-106">[in] Identifica la clase que se está descargando.</span><span class="sxs-lookup"><span data-stu-id="60b71-106">[in] Identifies the class that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="60b71-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="60b71-107">Remarks</span></span>  
 <span data-ttu-id="60b71-108">El valor de `classId` no es válido para una solicitud de información después de la `ClassUnloadStarted` devuelve del método, se trata de la última oportunidad para obtener información acerca de esta clase del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="60b71-108">The value of `classId` is not valid for an information request after the `ClassUnloadStarted` method returns — this is the profiler's last chance to obtain information about this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60b71-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="60b71-109">Requirements</span></span>  
 <span data-ttu-id="60b71-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="60b71-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60b71-111">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="60b71-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="60b71-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="60b71-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="60b71-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60b71-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60b71-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="60b71-114">See also</span></span>

- [<span data-ttu-id="60b71-115">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="60b71-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="60b71-116">ClassUnloadFinished (método)</span><span class="sxs-lookup"><span data-stu-id="60b71-116">ClassUnloadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadfinished-method.md)
