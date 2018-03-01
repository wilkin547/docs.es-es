---
title: "ICorProfilerCallback2::HandleDestroyed (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerCallback2.HandleDestroyed
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::HandleDestroyed
helpviewer_keywords:
- ICorProfilerCallback2::HandleDestroyed method [.NET Framework profiling]
- HandleDestroyed method [.NET Framework profiling]
ms.assetid: ab4f4bbd-40c7-4667-bfde-60cd73803110
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6a05c4559faf8e91dac3cc5a11c3331ee9d6c8e8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback2handledestroyed-method"></a><span data-ttu-id="82f33-102">ICorProfilerCallback2::HandleDestroyed (Método)</span><span class="sxs-lookup"><span data-stu-id="82f33-102">ICorProfilerCallback2::HandleDestroyed Method</span></span>
<span data-ttu-id="82f33-103">Notifica al generador de perfiles de código que se ha destruido un identificador de la colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="82f33-103">Notifies the code profiler that a garbage collection handle has been destroyed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82f33-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="82f33-104">Syntax</span></span>  
  
```  
HRESULT HandleDestroyed(  
    [in] GCHandleID handleId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="82f33-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="82f33-105">Parameters</span></span>  
 `handleId`  
 <span data-ttu-id="82f33-106">[in] El identificador del punto de control para la colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="82f33-106">[in] The ID of the handle for the garbage collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82f33-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="82f33-107">Requirements</span></span>  
 <span data-ttu-id="82f33-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82f33-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82f33-109">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="82f33-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="82f33-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="82f33-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="82f33-111">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82f33-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82f33-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="82f33-112">See Also</span></span>  
 [<span data-ttu-id="82f33-113">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="82f33-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="82f33-114">ICorProfilerCallback2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="82f33-114">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
