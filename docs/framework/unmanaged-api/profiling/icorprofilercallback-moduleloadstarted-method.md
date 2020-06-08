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
ms.openlocfilehash: a04f72fff9a88c8689821131b08b35500c23b3d9
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503359"
---
# <a name="icorprofilercallbackmoduleloadstarted-method"></a><span data-ttu-id="bb966-102">ICorProfilerCallback::ModuleLoadStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="bb966-102">ICorProfilerCallback::ModuleLoadStarted Method</span></span>
<span data-ttu-id="bb966-103">Notifica al generador de perfiles que se está cargando un módulo.</span><span class="sxs-lookup"><span data-stu-id="bb966-103">Notifies the profiler that a module is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb966-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bb966-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleLoadStarted(  
    [in] ModuleID moduleId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bb966-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bb966-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="bb966-106">de IDENTIFICADOR del módulo que se está cargando.</span><span class="sxs-lookup"><span data-stu-id="bb966-106">[in] The ID of the module that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bb966-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bb966-107">Remarks</span></span>  
 <span data-ttu-id="bb966-108">El valor de `moduleId` no es válido para una solicitud de información hasta que se llama al método [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="bb966-108">The value of `moduleId` is not valid for an information request until the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb966-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bb966-109">Requirements</span></span>  
 <span data-ttu-id="bb966-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb966-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb966-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bb966-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bb966-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bb966-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bb966-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb966-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb966-114">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="bb966-114">See also</span></span>

- [<span data-ttu-id="bb966-115">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bb966-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
