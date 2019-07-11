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
ms.openlocfilehash: 5b847cbbdf1bfccd91ca212dadd1fcd82cc12c82
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67768199"
---
# <a name="icorprofilercallbackmoduleloadstarted-method"></a><span data-ttu-id="86dc4-102">ICorProfilerCallback::ModuleLoadStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="86dc4-102">ICorProfilerCallback::ModuleLoadStarted Method</span></span>
<span data-ttu-id="86dc4-103">Notifica al generador de perfiles que se está cargando un módulo.</span><span class="sxs-lookup"><span data-stu-id="86dc4-103">Notifies the profiler that a module is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86dc4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="86dc4-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleLoadStarted(  
    [in] ModuleID moduleId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="86dc4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="86dc4-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="86dc4-106">[in] El identificador del módulo que se va a cargar.</span><span class="sxs-lookup"><span data-stu-id="86dc4-106">[in] The ID of the module that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="86dc4-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="86dc4-107">Remarks</span></span>  
 <span data-ttu-id="86dc4-108">El valor de `moduleId` no es válido para una solicitud de información hasta la [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) se llama al método.</span><span class="sxs-lookup"><span data-stu-id="86dc4-108">The value of `moduleId` is not valid for an information request until the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86dc4-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="86dc4-109">Requirements</span></span>  
 <span data-ttu-id="86dc4-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86dc4-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86dc4-111">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="86dc4-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="86dc4-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="86dc4-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="86dc4-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86dc4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86dc4-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="86dc4-114">See also</span></span>

- [<span data-ttu-id="86dc4-115">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="86dc4-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
