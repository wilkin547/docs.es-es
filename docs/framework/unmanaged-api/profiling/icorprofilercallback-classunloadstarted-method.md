---
title: "ICorProfilerCallback::ClassUnloadStarted (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ClassUnloadStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ClassUnloadStarted
helpviewer_keywords:
- ClassUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ClassUnloadStarted method [.NET Framework profiling]
ms.assetid: bc93bead-f3a9-415c-b919-ddd3ca80facc
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 994fe840f728b244e5a6e6c83c03340961c30413
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackclassunloadstarted-method"></a><span data-ttu-id="76075-102">ICorProfilerCallback::ClassUnloadStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="76075-102">ICorProfilerCallback::ClassUnloadStarted Method</span></span>
<span data-ttu-id="76075-103">Notifica al generador de perfiles que se está descargando una clase.</span><span class="sxs-lookup"><span data-stu-id="76075-103">Notifies the profiler that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76075-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="76075-104">Syntax</span></span>  
  
```  
HRESULT ClassUnloadStarted(  
    [in] ClassID classId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="76075-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="76075-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="76075-106">[in] Identifica la clase que se está descargando.</span><span class="sxs-lookup"><span data-stu-id="76075-106">[in] Identifies the class that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="76075-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="76075-107">Remarks</span></span>  
 <span data-ttu-id="76075-108">El valor de `classId` no es válido para una solicitud de información después de la `ClassUnloadStarted` devuelve del método: se trata de última oportunidad del generador de perfiles para obtener información acerca de esta clase.</span><span class="sxs-lookup"><span data-stu-id="76075-108">The value of `classId` is not valid for an information request after the `ClassUnloadStarted` method returns — this is the profiler's last chance to obtain information about this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76075-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="76075-109">Requirements</span></span>  
 <span data-ttu-id="76075-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="76075-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76075-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="76075-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="76075-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="76075-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="76075-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76075-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76075-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="76075-114">See Also</span></span>  
 [<span data-ttu-id="76075-115">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="76075-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="76075-116">ClassUnloadFinished (método)</span><span class="sxs-lookup"><span data-stu-id="76075-116">ClassUnloadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadfinished-method.md)
