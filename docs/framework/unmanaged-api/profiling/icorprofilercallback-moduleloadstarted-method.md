---
title: ICorProfilerCallback::ModuleLoadStarted (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleLoadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleLoadStarted
helpviewer_keywords:
- ModuleLoadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ModuleLoadStarted method [.NET Framework profiling]
ms.assetid: 9cd2fe75-408a-400f-a6b1-9979624a2fe2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3503aa1eb86246365e31f52313893ad8713f5748
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59153691"
---
# <a name="icorprofilercallbackmoduleloadstarted-method"></a><span data-ttu-id="f4c92-102">ICorProfilerCallback::ModuleLoadStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="f4c92-102">ICorProfilerCallback::ModuleLoadStarted Method</span></span>
<span data-ttu-id="f4c92-103">Notifica al generador de perfiles que se está cargando un módulo.</span><span class="sxs-lookup"><span data-stu-id="f4c92-103">Notifies the profiler that a module is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4c92-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f4c92-104">Syntax</span></span>  
  
```  
HRESULT ModuleLoadStarted(  
    [in] ModuleID moduleId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f4c92-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f4c92-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="f4c92-106">[in] El identificador del módulo que se va a cargar.</span><span class="sxs-lookup"><span data-stu-id="f4c92-106">[in] The ID of the module that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f4c92-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f4c92-107">Remarks</span></span>  
 <span data-ttu-id="f4c92-108">El valor de `moduleId` no es válido para una solicitud de información hasta la [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) se llama al método.</span><span class="sxs-lookup"><span data-stu-id="f4c92-108">The value of `moduleId` is not valid for an information request until the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4c92-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f4c92-109">Requirements</span></span>  
 <span data-ttu-id="f4c92-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4c92-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4c92-111">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f4c92-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f4c92-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f4c92-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f4c92-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4c92-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4c92-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="f4c92-114">See also</span></span>

- [<span data-ttu-id="f4c92-115">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f4c92-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
