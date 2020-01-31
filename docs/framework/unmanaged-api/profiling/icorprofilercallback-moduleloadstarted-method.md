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
ms.openlocfilehash: 88da5a968bf224dc5b6f45ee5d1d2e75386086f6
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866161"
---
# <a name="icorprofilercallbackmoduleloadstarted-method"></a><span data-ttu-id="30ae6-102">ICorProfilerCallback::ModuleLoadStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="30ae6-102">ICorProfilerCallback::ModuleLoadStarted Method</span></span>
<span data-ttu-id="30ae6-103">Notifica al generador de perfiles que se está cargando un módulo.</span><span class="sxs-lookup"><span data-stu-id="30ae6-103">Notifies the profiler that a module is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30ae6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="30ae6-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleLoadStarted(  
    [in] ModuleID moduleId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="30ae6-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="30ae6-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="30ae6-106">de IDENTIFICADOR del módulo que se está cargando.</span><span class="sxs-lookup"><span data-stu-id="30ae6-106">[in] The ID of the module that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="30ae6-107">Notas</span><span class="sxs-lookup"><span data-stu-id="30ae6-107">Remarks</span></span>  
 <span data-ttu-id="30ae6-108">El valor de `moduleId` no es válido para una solicitud de información hasta que se llama al método [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="30ae6-108">The value of `moduleId` is not valid for an information request until the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30ae6-109">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="30ae6-109">Requirements</span></span>  
 <span data-ttu-id="30ae6-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30ae6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30ae6-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="30ae6-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="30ae6-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="30ae6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="30ae6-113">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30ae6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30ae6-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="30ae6-114">See also</span></span>

- [<span data-ttu-id="30ae6-115">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="30ae6-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
