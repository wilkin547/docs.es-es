---
title: "ICorProfilerCallback2::HandleCreated (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback2.HandleCreated
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback2::HandleCreated
helpviewer_keywords:
- HandleCreated method [.NET Framework profiling]
- ICorProfilerCallback2::HandleCreated method [.NET Framework profiling]
ms.assetid: 6bbb7786-7c38-490f-9834-91aa2795c355
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d866261f16e344f6842ba59e83424219ec3d8dfb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallback2handlecreated-method"></a><span data-ttu-id="3b484-102">ICorProfilerCallback2::HandleCreated (Método)</span><span class="sxs-lookup"><span data-stu-id="3b484-102">ICorProfilerCallback2::HandleCreated Method</span></span>
<span data-ttu-id="3b484-103">Notifica al generador de perfiles de código que se ha creado un identificador de la colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="3b484-103">Notifies the code profiler that a garbage collection handle has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b484-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3b484-104">Syntax</span></span>  
  
```  
HRESULT HandleCreated(  
    [in] GCHandleID handleId,  
    [in] ObjectID initialObjectId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3b484-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3b484-105">Parameters</span></span>  
 `handleId`  
 <span data-ttu-id="3b484-106">[in] El identificador del punto de control para la colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="3b484-106">[in] The ID of the handle for the garbage collection.</span></span>  
  
 `initialObjectId`  
 <span data-ttu-id="3b484-107">[in] El identificador del objeto para el que se creó el identificador de la colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="3b484-107">[in] The ID of the object for which the garbage collection handle was created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b484-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3b484-108">Requirements</span></span>  
 <span data-ttu-id="3b484-109">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b484-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b484-110">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3b484-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3b484-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3b484-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3b484-112">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b484-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b484-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b484-113">See Also</span></span>  
 [<span data-ttu-id="3b484-114">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3b484-114">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="3b484-115">ICorProfilerCallback2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3b484-115">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
