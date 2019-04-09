---
title: ICorProfilerCallback::ClassLoadStarted (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassLoadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassLoadStarted
helpviewer_keywords:
- ICorProfilerCallback::ClassLoadStarted method [.NET Framework profiling]
- ClassLoadStarted method [.NET Framework profiling]
ms.assetid: 9f728de8-45c2-45a5-ac4a-45660bd36ecf
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: db7a033944272756a739dec39d4df11fde1d48b3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59178612"
---
# <a name="icorprofilercallbackclassloadstarted-method"></a><span data-ttu-id="3cbc2-102">ICorProfilerCallback::ClassLoadStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="3cbc2-102">ICorProfilerCallback::ClassLoadStarted Method</span></span>
<span data-ttu-id="3cbc2-103">Notifica al generador de perfiles que se está cargando una clase.</span><span class="sxs-lookup"><span data-stu-id="3cbc2-103">Notifies the profiler that a class is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cbc2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3cbc2-104">Syntax</span></span>  
  
```  
HRESULT ClassLoadStarted(  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3cbc2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3cbc2-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="3cbc2-106">[in] Identifica la clase que se va a cargar.</span><span class="sxs-lookup"><span data-stu-id="3cbc2-106">[in] Identifies the class that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3cbc2-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3cbc2-107">Remarks</span></span>  
 <span data-ttu-id="3cbc2-108">El valor de `classId` no es válido para una solicitud de información hasta la [ClassLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md) se llama al método.</span><span class="sxs-lookup"><span data-stu-id="3cbc2-108">The value of `classId` is not valid for an information request until the [ICorProfilerCallback::ClassLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3cbc2-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3cbc2-109">Requirements</span></span>  
 <span data-ttu-id="3cbc2-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3cbc2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3cbc2-111">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3cbc2-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3cbc2-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3cbc2-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="3cbc2-113">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="3cbc2-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3cbc2-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="3cbc2-114">See also</span></span>

- [<span data-ttu-id="3cbc2-115">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3cbc2-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
