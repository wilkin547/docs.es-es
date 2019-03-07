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
ms.openlocfilehash: d19814b0c663310e977ef148ad37eb74129fd4d2
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466510"
---
# <a name="icorprofilercallbackclassloadstarted-method"></a><span data-ttu-id="24573-102">ICorProfilerCallback::ClassLoadStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="24573-102">ICorProfilerCallback::ClassLoadStarted Method</span></span>
<span data-ttu-id="24573-103">Notifica al generador de perfiles que se está cargando una clase.</span><span class="sxs-lookup"><span data-stu-id="24573-103">Notifies the profiler that a class is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24573-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="24573-104">Syntax</span></span>  
  
```  
HRESULT ClassLoadStarted(  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="24573-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="24573-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="24573-106">[in] Identifica la clase que se va a cargar.</span><span class="sxs-lookup"><span data-stu-id="24573-106">[in] Identifies the class that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="24573-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="24573-107">Remarks</span></span>  
 <span data-ttu-id="24573-108">El valor de `classId` no es válido para una solicitud de información hasta la [ClassLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md) se llama al método.</span><span class="sxs-lookup"><span data-stu-id="24573-108">The value of `classId` is not valid for an information request until the [ICorProfilerCallback::ClassLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24573-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="24573-109">Requirements</span></span>  
 <span data-ttu-id="24573-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24573-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24573-111">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="24573-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="24573-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="24573-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="24573-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24573-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24573-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="24573-114">See also</span></span>
- [<span data-ttu-id="24573-115">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="24573-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
