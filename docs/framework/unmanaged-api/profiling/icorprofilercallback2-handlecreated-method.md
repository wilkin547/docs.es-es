---
title: ICorProfilerCallback2::HandleCreated (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.HandleCreated
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::HandleCreated
helpviewer_keywords:
- HandleCreated method [.NET Framework profiling]
- ICorProfilerCallback2::HandleCreated method [.NET Framework profiling]
ms.assetid: 6bbb7786-7c38-490f-9834-91aa2795c355
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e598c4f3a4f777cdb8a871cdc6ea56a080e3c9bc
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496916"
---
# <a name="icorprofilercallback2handlecreated-method"></a><span data-ttu-id="ed5b2-102">ICorProfilerCallback2::HandleCreated (Método)</span><span class="sxs-lookup"><span data-stu-id="ed5b2-102">ICorProfilerCallback2::HandleCreated Method</span></span>
<span data-ttu-id="ed5b2-103">Notifica al generador de perfiles de código que se ha creado un identificador de la colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="ed5b2-103">Notifies the code profiler that a garbage collection handle has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed5b2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ed5b2-104">Syntax</span></span>  
  
```  
HRESULT HandleCreated(  
    [in] GCHandleID handleId,  
    [in] ObjectID initialObjectId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ed5b2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ed5b2-105">Parameters</span></span>  
 `handleId`  
 <span data-ttu-id="ed5b2-106">[in] El identificador del controlador de la colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="ed5b2-106">[in] The ID of the handle for the garbage collection.</span></span>  
  
 `initialObjectId`  
 <span data-ttu-id="ed5b2-107">[in] El identificador del objeto para el que se creó el identificador de la colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="ed5b2-107">[in] The ID of the object for which the garbage collection handle was created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed5b2-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ed5b2-108">Requirements</span></span>  
 <span data-ttu-id="ed5b2-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed5b2-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed5b2-110">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ed5b2-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ed5b2-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ed5b2-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ed5b2-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed5b2-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed5b2-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="ed5b2-113">See also</span></span>
- [<span data-ttu-id="ed5b2-114">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ed5b2-114">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="ed5b2-115">ICorProfilerCallback2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ed5b2-115">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
